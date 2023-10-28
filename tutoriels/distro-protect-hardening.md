---
title: Optimiser sa distribution
description: Une seconde partie pour montrer comment sécuriser et optimiser encore plus nos distributions...
published: true
date: 2023-10-28T08:16:38.137Z
tags: linux, debutant, intermédiaire, débutant, intermediaire, initié, initie, durcissement, hardening, optimiser
editor: markdown
dateCreated: 2023-01-26T18:26:23.152Z
---

Dans cet article, nous allons pousser la configuration de votre distribution à un niveau plus élevé : nous allons optimiser le noyau et appliquer également ce que l'on nomme un [durcissement](/glossaire#hardening).

> **Certaines de ces optimisations peuvent cependant empêcher votre système de démarrer ou d'utiliser certaines fonctions utiles pour vous (virtualisation par exemple)... Procédez avec précaution et par étapes successives !**
{.is-warning}

# Introduction

Linux ne doit pas être considéré comme un système d'exploitation pour station de travail, sécurisé, _de base_. Afin d'obtenir un meilleur niveau de sécurité, il est cependant tout à fait possible d'améliorer ce niveau en appliquant certaines fonctionnalités ou règles au système et ainsi réduire la surface d'attaque.

Cet article a pour base *majoritairement* l'article issu du site [privsec](https://privsec.dev/posts/linux/desktop-linux-hardening/) qui fournit des détails très intéressants liés à la sécurité et à la vie privée. Nous avons cependant ajouté certaines optimisations et modifié certaines parties afin de limiter au strict nécessaire les modifications à apporter.

# À l'installation

## Partition chiffrée

Une partie des distributions proposent **nativement**, dans leur installateur, la possibilité de chiffrer votre ou vos partitions système et home, pour ceux qui ont un modèle de menaces qui requiert une protection élevée de leurs données.

Nous suggérons de le faire dès l'installation, comme mentionné dans notre article sur le [chiffrement](/intermediaire/chiffrement).


## ZRAM

Le noyau Linux peut être agrémenté de ce que l'on appelle des modules (ou LKM pour Loadable Kernel Module). [ZRAM](https://www.kernel.org/doc/html/next/admin-guide/blockdev/zram.html) (ex-projet "compcache") est un module du noyau GNU/Linux qui permet de créer un espace de mémoire virtuelle à l'intérieur de la RAM de votre machine ; mais ce module n'est, sur la majorité des distributions, pas activé par défaut. Le SWAP se fait donc sur une partie du disque dur (ou une partition dédiée si vous en avez créée une !).

Plutôt que d'utiliser une partie du disque dur, ZRAM va utiliser la RAM pour le SWAP. Ceci a plusieurs avantages majeurs :
- Limiter les écritures/lectures sur disques, surtout sur SSD,
- Augmenter la rapidité des tâches effectuées (et donc les performances, surtout si vous avez un disque dur mécanique), car la RAM par défaut est beaucoup plus véloce qu'un disque dur,
- Utiliser ZRAM vous permet également de réduire le risque de fuites mémoires.

Vous retrouverez plus d'informations sur l'intérêt d'utiliser ZRAM [ici](https://askubuntu.com/questions/298018/does-installing-zram-have-any-advantages-on-a-system-without-swap).


Voici comment activer cette fonction sur la majorité des distributions :

### Tabs {.tabset}
#### Debian/Ubuntu
Ou autres distributions basées sur Ubuntu ou Debian :
- Lancez cette commande pour installer `zram` :
```bash
sudo apt install zram-tools
```

- Nous allons ensuite configurer l'algorithme de compression `zstd` ainsi que la quantité de RAM à utiliser à 60% (au lieu de 50%) de celle disponible sur le système :
```bash
echo -e "ALGO=zstd\nPERCENT=60" | sudo tee -a /etc/default/zramswap
```

> `tee` va modifier les valeurs de ALGO et PERCENT dans le fichier de configuration `/etc/default/zramswap`. Vous pouvez alternativement le faire vous-même en éditant ce fichier manuellement avec `nano`.
{.is-info}

- Lancez cette commande pour prendre en compte la nouvelle configuration :
```bash
sudo service zramswap reload
```

#### Arch Linux
Ou autres distributions basées sur Arch :
- Lancez cette commande pour installer `zram` :
```bash
sudo pacman -S zram-generator
```

- Nous allons ensuite configurer l'algorithme de compression `zstd` ainsi que la quantité de RAM à utiliser à 100% (au lieu de 50%) de celle disponible sur le système :
```bash
echo -e "[zram0]\nzram-size=ram\ncompression-algorithm=zstd" | sudo tee /etc/systemd/zram-generator.conf
```

> `tee` va créer le fichier `zram-generator.conf` et ajouter le texte issu de la commande `echo` dans ce fichier de configuration. Vous pouvez alternativement le faire vous-même en créant ce fichier manuellement avec `nano` et en copiant manuellement le contenu 
> *Attention aux retours chariots : `\n` , qui sont en fait à remplacer par un simple retour à la ligne*.
{.is-info}

- Redémarrer votre machine.

#### RedHat/Fedora
Sur les distributions basées sur Redhat, ZRAM est utilisé [par défaut](https://fedoraproject.org/wiki/Changes/SwapOnZRAM)

#### OpenSuse
```bash
sudo zypper install systemd-zram-service
sudo reboot
sudo systemctl enable --now zramswap.service
```

###
Voilà c'est tout.
Afin de vérifier que le SWAP utilise ZRAM, procédons comme suit :
- `cat /proc/swaps`
Nous pouvons voir ici des `/dev/zramX` (un par coeur de processeur).

Pour voir l'utilisation des blocs zram :
- `zramctl`
ou
- `free -h`

# Petits ajustements

## Optimisations journalisation

La journalisation (en anglais : logging, produisants des fichers de "_logs_") sur toutes les distributions est rarement optimisée et peut parfois atteindre un volume de données importants, impliquant un ralentissement du système voire pire...

A ce titre, il peut être utile d'optimiser cette journalisation :
- en limitant la taille des journaux,
- en appliquant une rotation des fichiers dès qu'ils sont "pleins".

Voici les commandes à appliquer, en premier lieu, pour nettoyer les journaux actuels :

```bash
sudo systemd-resolve --flush-caches
sudo journalctl --rotate
```

Puis  nous optimisons la configuration :
```bash
sudo journalctl --vacuum-time=1s
sudo journalctl --vacuum-size=40M
sudo sed -i 's/#SystemMaxUse=/SystemMaxUse=100M/' /etc/systemd/journald.conf
sudo sed -i 's/#SystemMaxFiles=100/SystemMaxFiles=7/g' /etc/systemd/journald.conf
```

Enfin, nous réappliquons une rotation pour activer ces optimisations :
```bash
sudo journalctl --rotate
```

## Optimisations tmp

Le répertoire `/tmp` (des fichiers temporaires) est très sollicité, par le système mais aussi par les applications qui l'utilisent très souvent, parfois même pour écrire puis supprimer des petits fichiers rapidement. Cela implique des écritures disque incessantes, ce qui à terme peut fatiguer les disques surtout les SSD.

Afin d'améliorer cet aspect, nous pouvons rediriger ce répertoire en mémoire vive, ce qui limitera grandement l'écriture sur disque, et parfois même améliorera les performances :

```bash
echo -e "\ntmpfs /tmp	tmpfs defaults,noatime,nodiratime,noexec,nodev,mode=1777,nosuid,size=4G         0 0" | sudo tee -a /etc/fstab
echo -e "\ntmpfs /var/tmp  tmpfs defaults,noatime,nodiratime,noexec,nodev,mode=1777,nosuid,size=4G         0 0" | sudo tee -a /etc/fstab
```

> Ici veillez à ne pas avoir de partition séparée pour `/tmp`.
{.is-danger}

## MAC randomisation

Une grande partie des distributions utilisent le gestionnaire de réseau "NetworkManager". Il est possible de renforcer ses propriétés en appliquant une configuration sur la randomisation des adresses MAC des équipements réseau (Wifi et Ethernet-câble).

> Attention, cette optimisation semble ne pas correctement fonctionner sur les distributions à base de Fedora. Si vous ne retrouvez pas votre connexion, revenez en arrière sur cette partie.
{.is-warning}

Pour ce faire voici :

```bash
sudo nano /etc/NetworkManager/conf.d/00-macrandomize.conf
```

Copions ces lignes dans le fichier ainsi ouvert :

```brainfuck
[device]
wifi.scan-rand-mac-address=yes

[connection]
wifi.cloned-mac-address=random
ethernet.cloned-mac-address=random
```

Fermer le fichier. Puis :

```bash
sudo nano /etc/NetworkManager/conf.d/01-transient-hostname.conf
```

Et ajoutons ces lignes :

```brainfuck
[main]
hostname-mode=none
```

Redémarrons le service NetworkManager :

```bash
sudo systemctl restart NetworkManager
```

Et adaptons le nom d'hôte de notre machine sur `localhost` :

```bash
sudo hostnamectl set-hostname "localhost"
```

> Il est à noter que 
> ~~ La randomisation de l'adresse MAC de votre carte WiFi peut ne pas fonctionner, cela dépend du microcode de la puce en question.
> ~~ Plus important encore : il est intéressant de comprendre ces aspects si votre modèle de menaces est élevé ; le 1er bloc de 3 octets de l'adresse MAC renvoi à un identifiant international du fabricant, nommé OUI (pour "Organizational Unique Identifier") qu'il n'est pas judicieux de spoofer car il devient plus facile de détecter la randomisation en interrogeant une base de données de ces OUI. Par corrélation, il devient alors facile de deviner l'usurpation (voire même dans certains cas l'utilisation d'un VPN !). Il est donc plus judicieux de ne spoofer/randomiser que le 2éme bloc ou derniers 3 octets de l'adresse qui renvoient au numéro NIC (pour "Network Interface Controller") de votre propre carte réseau qui dispose d'une grande largesse dans l'attribution des numéros et qui peut servir à l'identification et au pistage. En simulant seulement la fin de l'adresse MAC, sa détection par corrélation devient alors plus difficile. 
> **Cette opération peut se faire depuis Linux via un outil comme [Macchanger](https://github.com/alobbs/macchanger)**. 
>
> Enfin il est à noter qu'il est impossible de se soustraire **complètement** au fingerprinting tant les possibilités d'identification sont protéiformes et nombreuses. L'idée est de réduire le risque.
{.is-info}

## Identification

Plusieurs points peuvent être renforcés ici :
- Eviter de créer un nom d'utilisateur explicite. Nous préférons par exemple utiliser un pseudonyme ou voire un mot générique comme `user`.
- Eviter également un nom d'hôte trop explicite. Ici encore préférer quelque chose de générique, comme `ordi`
- À l'installation d'une distribution, l'OS crée un identifiant unique pour la machine. Nous devrions vérifier qu'il s'agit d'une suite de chiffres et de lettres quelconque comme `b08dff433e7567a1921a7150ab01` Généralement vous trouverez cet ID ici : `/etc/machine-id` (systemd) ou `/var/lib/dbus/machine-id` (wayland et autres)

## Télémétrie

Une majorité des distributions effectuent un retour vers leurs serveurs sur le nombre d'installation de leur système et leurs logiciels. Il est possible de couper cette "télémétrie" si notre [modèle de menace](/hygiene-numerique#d%C3%A9finir-son-mod%C3%A8le-de-menaces) l'exige, ou en tout cas si nous souhaitons réduire notre empreinte réseau.

Voici une liste pour certaines distributions et logiciels, _non exhaustive_ :
- Fedora : bien que cette fonction soit désactivée par défaut, vous pouvez vous en assurer en ajoutant `countme=false` au fichier `/etc/dnf/dnf.conf`. Sur les systèmes utilisant rpm-ostree (Fedora Silverblue par ex.), vous pouvez suivre ces indications afin de [masquer la variable countme](https://coreos.github.io/rpm-ostree/countme/).
- OpenSuse : nous pouvons désactiver la remontée d'information via l'ID en supprimant simplement le fichier `/var/lib/zypp/AnonymousUniqueId`.
- Zorin OS : nous pouvons ici encore désactiver cette télémétrie en lançant cette commande `sudo apt purge --auto-remove zorin-os-census` puis en labellisant ce logiciel comme "non-installable" avec `sudo apt-mark hold zorin-os-census` pour éviter toute réinstallation accidentelle.
- Ubuntu : nous pouvons supprimer la remontée d'information en lançant cette commande `sudo apt purge --auto-remove ubuntu-report`.
- Snap : de base, nous ne conseillons pas l'utilisation de snap. Si malheureusement vous avez installé une distribution qui utilise SNAP, voici comment supprimer ce logiciel (exemple sur Ubuntu) :

```bash
sudo snap remove --purge firefox && snap remove --purge gtk-common-themes && snap remove --purge snapd-desktop-integration && snap remove --purge gnome-3-38-2004 && snap remove --purge snap-store && snap remove --purge bare && snap remove --purge core20 && snap remove --purge core18 && snap remove --purge snapd && apt -y purge --auto-remove snapd
```

Puis, afin d'éviter une réinstallation accidentelle, lancez la commande : `sudo apt-mark hold snapd`.

## Flatpak

L'utilisation de Flatpak est un bon moyen d'obtenir des logiciels. Flatpak conditionne, par défaut, ces logiciels en appliquant une isolation en bac à sable (sandboxing), un peu à la manière de ChromeOS ou d'Android, mais bien moins évolué et plus faible sur le filtrage.

Nous pouvons renforcer ce filtrage, si notre modèle de menace exige une compartimentation élevée afin d'assurer une sécurité sérieuse. L'installation de l'outil `Flatseal` nous permettra de finement régler cet aspect.

L'idée générale que nous pouvons appliquer pour commencer est de **désactiver tout accès** des applications aux fichiers système (`filesystem`). Puis de lancer ces applications et de vérifier leur fonctionnement et ajuster leurs accès. 

Pour vous aider à ajuster au mieux, [privsec](https://github.com/tommytran732/Flatpak-Overrides) et un développeur nommé [rusty-snake](https://github.com/rusty-snake/kyst/tree/main/flatpak) ont fourni des exemples d'ajustements pour certaines applications.

> Attention également à ne pas activer les mises à jour automatiques et de vérifier, après toute mise à jour, les accès ; en effet, il se peut que cette fonction réactive des paramètres par défaut.
{.is-warning}

## Contrôle d'accès

Afin de surveiller l'accès aux différentes parties du système, les distributions Linux implémentent un outil de renforcement des contrôles d'accès : SELinux ou AppArmor.

SELinux est l'outil installé par défaut sur les Android et les distributions RedHat et Fedora et AppArmor celui sur les distributions Debian/Ubuntu et une partie des OpenSuse. Voilà pourquoi Fedora est généralement perçue comme plus avancée au niveau sécurité dans les distributions (et a fortiori RedHat bien sûr), nous conseillons de laisser le mode SELinux à "Enforcing".

Pour ce qui est des autres distributions, nous conseillons fortement de garder l'outil par défaut car il est livré avec des règles renforcées.

> Pour ce qui est de Arch, il faudra en passer par l'utilisation de AppArmor et sa configuration nominale recommandée trouvable [ici](https://wiki.archlinux.org/title/AppArmor)
{.is-info}

Bien entendu, il est tout à fait possible de renforcer ou créer vos propres règles de confinement sur ces 2 outils, en suivant les recommandations de certains experts, que nous listons ici :
- [bubblewrap](https://github.com/containers/bubblewrap)
- [seccomp](https://docs.kernel.org/userspace-api/seccomp_filter.html)
- [Kicksecure’s apparmor-profile-everything](https://github.com/Kicksecure/apparmor-profile-everything)
- [Krathalan’s AppArmor profiles](https://github.com/krathalan/apparmor-profiles)
- [noatsecure’s SELinux templates](https://github.com/noatsecure/hardhat-selinux-templates)
- [Seirdy’s bubblewrap scripts](https://sr.ht/~seirdy/bwrap-scripts)

> Attention, cette tâche est fastidieuse et réservée à ceux qui voudront se documenter et passer un peu de temps à configurer leur système.
{.is-warning}

## Pare-Feu

Les distributions RedHat/Fedora et OpenSuse viennent avec un logiciel pare-feu nommé `Firewalld`. Les distributions à base Debian/Ubuntu utilisent quant à elles plus fréquemment `ufw`. La différence réside dans le fait que UFW ne peut appliquer de règle sur une connexion particulière, mais reste plus simple à l'usage.

Deux autres outils peuvent être également étudiés et utilisés afin de renforcer le filtrage :
- [OpenSnitch](https://github.com/evilsocket/opensnitch)
- [PortMaster](https://github.com/safing/portmaster)

> Gardez bien en tête que tous ces outils, bien qu'utiles au quotidien peuvent être _détournés_ : en effet, ces outils ne bloqueront pas une personne qui a des privilèges élevés sur la machine, et qui, par conséquent, pourra changer les règles de filtrage à sa guise.
{.is-warning}


# Durcissement

## Firmware

Il est important de recevoir des mises à jour des microcodes de vos CPUs pour, par exemple, réduire le risque de vulnérabilité (type [Meltdown et Spectre](https://www.ssi.gouv.fr/actualite/alerte-multiples-vulnerabilites-dans-des-processeurs-comprendre-meltdown-et-spectre-et-leur-impact/)). 

Pour ce faire, il est impératif d'activer les paquets *"non-free"* de vos distributions et de vérifier ou installer ces paquets :
- `intel-microcode` pour les CPUs Intel (`intel-ucode` sur base Arch),
- `amd-microcode` pour les CPUs AMD (`amd-ucode` sur base Arch).

En ce qui concerne la mise à jour des différents firmwares de nos machines, de simples commandes sont à effectuer régulièrement :
```bash
sudo fwupdmgr refresh && fwupdmgr update
```

Si `fwupd` n'est pas installé par défaut, nous devrons procéder à son installation.

## Noyau (kernel)

On entre ici sur un sujet assez complexe, le durcissement du noyau Linux (linux-kernel).

Certaines distributions Arch permettent de choisir le noyau spécial "durci" `linux-hardened` qui inclut par défaut les patchs de sécurité et une configuration plus stricte du noyau (qui peut malheureusement casser certains logiciels). Hormis ce type de noyau (Redhat par exemple se base sur `linux-hardened`, Whonix dont la base utilise les durcissements de `kicksecure`), la majorité des noyaux n'est pas durcie par défaut.

> Attention : cette partie s'adresse à des profils intermédiaires à initiés. Le risque de bloquer certains usages du quotidien est élevé lorsque nous appliquons des règles durcissement élevé. Au risque de nous répéter, la sécurité vient pratiquement toujours avec des compromis sur la facilité d'usage !
{.is-warning}

### System Control

Afin de durcir le noyau notamment au niveau des contrôles de privilège, du swap et des contrôles réseau, deux choix s'offrent à vous :
1. Sur les distributions Debian, vous pouvez appliquer les règles `kicksecure` en suivant ce [tutoriel](https://www.kicksecure.com/wiki/Debian).
2. Sur les autres distributions, copiez simplement ces 2 fichiers de configuration dans le dossier `/etc/sysctl.d` :
-   [`/etc/sysctl.d/30_security-misc.conf`](https://github.com/Kicksecure/security-misc/blob/master/etc/sysctl.d/30_security-misc.conf)
-   [`/etc/sysctl.d/30_silent-kernel-printk.conf`](https://github.com/Kicksecure/security-misc/blob/master/etc/sysctl.d/30_silent-kernel-printk.conf)

Note : vous pouvez télécharger ces fichiers depuis le dépôt github et les copier avec des droits administrateur dans le répertoire, ou simplement créer 2 fichiers vides dans `/etc/sysctl.d` du même nom et copier les contenus dans ces fichiers.

### Boot

Le boot est une étape importante et critique du lancement d'une machine. Il peut donc être utile de renforcer la sécurité autour de cette étape.

Voici les 2 commandes à lancer afin de durcir la séquence de boot :


#### Tabs {.tabset}
##### Debian/Ubuntu
Ou autres distributions basées sur Ubuntu ou Debian :

```bash
sudo sed -i'.bkp' -E 's|(GRUB_CMDLINE_LINUX_DEFAULT="quiet splash)|\1 slab_nomerge init_on_alloc=1 init_on_free=1 page_alloc.shuffle=1 pti=on vsyscall=none debugfs=off oops=panic mce=0 loglevel=0 spectre_v2=on spec_store_bypass_disable=on tsx=off tsx_async_abort=full,nosmt mds=full,nosmt l1tf=full,force nosmt=force kvm.nx_huge_pages=force randomize_kstack_offset=on|' /etc/default/grub
```
Puis
```bash
sudo update-grub
```

##### Arch Linux
Ou autres distributions basées sur Arch :

```bash
sudo sed -i'.bkp' -E 's|(GRUB_CMDLINE_LINUX_DEFAULT="quiet )|\1 slab_nomerge init_on_alloc=1 init_on_free=1 page_alloc.shuffle=1 pti=on vsyscall=none debugfs=off oops=panic mce=0 loglevel=0 spectre_v2=on spec_store_bypass_disable=on tsx=off tsx_async_abort=full,nosmt mds=full,nosmt l1tf=full,force nosmt=force kvm.nx_huge_pages=force randomize_kstack_offset=on |' /etc/default/grub
```
Puis
```bash
sudo update-grub
```

##### RedHat/Fedora
Sur les distributions basées sur Redhat :

```bash
sudo sed -i'.bkp' -E 's|(GRUB_CMDLINE_LINUX="rhgb quiet)|\1 slab_nomerge init_on_alloc=1 init_on_free=1 page_alloc.shuffle=1 pti=on vsyscall=none debugfs=off oops=panic mce=0 loglevel=0 spectre_v2=on spec_store_bypass_disable=on tsx=off tsx_async_abort=full,nosmt mds=full,nosmt l1tf=full,force nosmt=force kvm.nx_huge_pages=force randomize_kstack_offset=on|' /etc/default/grub
```
- Pour BIOS legacy :
```bash
sudo grub2-mkconfig -o /etc/grub2.cfg
```
- Pour BIOS uEFI :
```bash
sudo grub2-mkconfig -o /etc/grub2-efi.cfg 
```

##### OpenSuse

```bash
sudo sed -i'.bkp' -E 's|(GRUB_CMDLINE_LINUX_DEFAULT="splash=silent mitigations=auto quiet security=apparmor)|\1 slab_nomerge init_on_alloc=1 init_on_free=1 page_alloc.shuffle=1 pti=on vsyscall=none debugfs=off oops=panic mce=0 loglevel=0 spectre_v2=on spec_store_bypass_disable=on tsx=off tsx_async_abort=full,nosmt mds=full,nosmt l1tf=full,force nosmt=force kvm.nx_huge_pages=force randomize_kstack_offset=on|' /etc/default/grub
```
- Pour BIOS legacy :
```bash
sudo grub2-mkconfig -o /etc/grub2.cfg
```
- Pour BIOS uEFI :
```bash
sudo grub2-mkconfig -o /etc/grub2-efi.cfg 
```


### Modules

Kicksecure fournit une configuration durcie pour les modules du noyau chargés par le système. Il nous est possible de copier simplement ce fichier de configuration dans notre dossier `/etc/modprobe.d` :
-   [`/etc/modprobe.d/30_security-misc.conf`](https://github.com/Kicksecure/security-misc/blob/master/etc/modprobe.d/30_security-misc.conf)

Attention cependant :
- Ce fichier désactive par défaut le _bluetooth_. Si vous souhaitez tout de même l'utiliser, il faudra commenter les lignes commençant par  `install bluetooth` et `install btusb` (nous commentons des lignes en ajoutant le caractère "#" en début de ligne)
- Les systèmes de fichiers Apple sont désactivés par défaut, car inutiles sur des machines non Apple. Si vous installez Linux sur une machine Apple, il est bien entendu **obligatoire** de vérifier le système de fichier utilisé par votre partition EFI et de commenter la ligne contenant ce type de partition (sinon, Linux ne bootera pas ;) ). Par exemple, si votre EFI utilise HFS+, vous devrez commenter la ligne `install hfsplus /bin/disabled-filesys-by-security-misc`.

### Accès /proc et /sys

Porter une attention particulière aux accès aux répertoires `/proc` et `/sys` peut être une solution afin de réduire la surface d'attaque. Ces répertoires contiennent beaucoup de données sur le noyau, la distribution et l'état de la machine ainsi que les processus en cours d'exécution. Il peut donc être intéressant de limiter leur accès, bien que cela soit assez complexe et long à mettre en place.

Une possibilité est de reprendre les configurations suivantes issues de Kicksecure, et utilisées de base sur Whonix :
 - [proc-hidepid](https://github.com/Kicksecure/security-misc/blob/master/lib/systemd/system/proc-hidepid.service)
 - [hide-hardware-info](https://github.com/Kicksecure/security-misc/blob/master/lib/systemd/system/hide-hardware-info.service)


## Montage automatique

Lorsque vous insérez un média externe (clé USB ou disque dur...), sur la plupart des distributions leur montage est automatique. Bien que pratique, ce fonctionnement ajoute un vecteur d'attaque qui peut être facilement évité ; en effet, n'importe quelle personne malveillante peut insérer une clé et exécuter des programmes malicieux si vous ne bloquez pas ces accès...

Sur **Gnome** entrez ces commandes :
```bash
echo '[org/gnome/desktop/media-handling] automount=false automount-open=false' | sudo tee /etc/dconf/db/local.d/automount-disable

echo 'org/gnome/desktop/media-handling/automount org/gnome/desktop/media-handling/automount-open' | sudo tee /etc/dconf/db/local.d/locks/automount-disable
```
Puis :
```bash
sudo dconf update
```

- Sur **Cinnamon** : remplacez `gnome` par `cinnamon` ci-dessus.

Il est également recommandé, pour ceux qui ont un modèle de sécurité élevé, de mettre en place une surveillance active des ports USB, notamment grâce à [USBGuard](https://github.com/USBGuard/usbguard).

# Secure Boot

Vous avez sûrement noté, lorsque vous avez installé votre distribution, que nous avons désactivé le "Secure Boot" dans les paramètres de votre BIOS. En effet, les firmwares sur la grande majorité des machines aujourd'hui sont préconfigurées pour faire confiance uniquement aux clés Microsoft, ce qui bloque donc de facto l'installation d'autres types de systèmes. De ce fait, nous avons quelque peu _augmenté votre surface d'attaque_ sur votre machine.

Il est important de bien comprendre à quoi sert et ce que ne permet pas le Secure Boot : cette fonction permet de valider **l'authenticité et l'intégrité** du système (en vérifiant des signatures) que vous lancez au démarrage de votre machine. Il ne permet en aucun cas de protéger la **confidentialité** du système (un vol de donnée est toujours possible) ; pour cela, vous aurez besoin de chiffrement !

Il est donc à noter que :
-  quand bien même le "Secure Boot" serait activé et le boot sur média USB accepté, *le Secure Boot ne servirait à rien* si un attaquant boote sur une clé USB ; l'accès au système entier lui serait de toute manière assuré.
> Nous résolvons généralement ce problème en chiffrant tout le système (toutes les partitions d'intérêt).

- le Secure Boot peut de toute manière être désactivé si rien n'est fait pour protéger le contenu et l'accès au BIOS.
> Afin de contourner ce problème, il suffit de protéger l'accès au BIOS par un mot de passe administrateur et de ne pas autoriser le boot sur un média USB ; ce qui n'est pas si trivial à l'usage, mais renforce tout de même la sécurité au démarrage du système. Nous pourrions potentiellement également chiffrer et ajouter un mot de passe au boot. 
{.is-success}


Il est, cela dit, possible sur certaines machines de mettre en place un Secure Boot avec des distributions GNU/Linux, en utilisant un outil particulier : `sbctl`.

> Attention ici, toutes les machines ne sont pas compatibles de cette manipulation. Le risque est de bricker le mécanisme UEFI ce qui bloquera la machine. Il faudra alors faire un reset de l'EEPROM et revenir à une configuration nominale !
> Veuillez lire notre page [Avertissement](/avertissement).
{.is-danger}

Voici la procédure, comme décrite sur le dépôt de l'outil :

```bash
sudo sbctl status
```
```brainfuck
Installed:	✘ Sbctl is not installed
Setup Mode:	✘ Enabled
Secure Boot:	✘ Disabled
```
```bash
sudo sbctl create-keys
```
```brainfuck
Created Owner UUID a9fbbdb7-a05f-48d5-b63a-08c5df45ee70
Creating secure boot keys...✔
Secure boot keys created!
```
```bash
sudo sbctl enroll-keys
```
```brainfuck
Enrolling keys to EFI variables...✔
Enrolled keys to the EFI variables!
```
```bash
sudo sbctl status
```
```brainfuck
Installed:	✔ Sbctl is installed
Owner GUID:	a9fbbdb7-a05f-48d5-b63a-08c5df45ee70
Setup Mode:	✔ Disabled
Secure Boot:	✘ Disabled
```

Après avoir redémarré :
```bash
sudo sbctl status
```
```brainfuck
Installed:	✔ Sbctl is installed
Owner GUID:	a9fbbdb7-a05f-48d5-b63a-08c5df45ee70
Setup Mode:	✔ Disabled
Secure Boot:	✔ Enabled
```

Il est possible que, sur certains matériels, cela ne fonctionne toujours pas. Il faudra alors tenter d'exporter la clé publique sur votre partition EFI et de l'importer manuellement via votre BIOS. Voici la commande pour copier la clé publique sur la partition EFI :

```bash
sudo openssl x509 -in /usr/share/secureboot/keys/db/db.pem -outform DER -out /boot/efi/EFI/fedora/DB.cer
```

_Notes importantes_ :
- `/usr/share/secureboot/keys/db/db.pem` est à adapter au chemin de la clé publique
- `/boot/efi/EFI/fedora/DB.cer` est également à adapter chez vous (ici l'exemple est donné pour une distribution Fedora)


# Conclusion

Pour terminer sur le tour d'horizon du durcissement de notre machine, nous pourrions enfin ajouter :
- L'utilisation du chiffrement intégral du disque (FDE pour Full Disk Encryption), je vous renvoie à notre [article](/intermediaire/chiffrement) dédié ;
- La désactivation de toute télémétrie (par ex. : désactiver les rapports système, pas d'envoi de rapports de bugs...) ;
- La désactivation des connexions sans fil non nécessaires (Bluetooth, WiFi) ;
- Couvrir votre webcam si vous en avez une ;
- Désinstaller tout service ou application dont vous n'avez aucune utilité, et fermer les ports réseau non utilisés.

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo, Lou*