---
title: Debian
description: Installation et configuration de Debian sur PC
published: true
date: 2024-02-04T20:21:05.983Z
tags: debutant, distribution, debian
editor: markdown
dateCreated: 2023-02-05T19:31:26.969Z
---

[Debian](https://www.debian.org/index.fr.html) est une distribution GNU/Linux dite "majeure" créée en 1993 par [Ian Murdock](https://fr.wikipedia.org/wiki/Ian_Murdock).

![debian-logo.png](/images/debian-banner.jpg){.align-center}

**Elle se distingue des autres distributions, notamment parce que :**
- C'est l'une des premières distributions Linux toujours en activité (avec Slackware), _une distribution "mère"_ ;  la popularité de Debian a pour conséquence que de nombreuses distributions en sont dérivées comme : Ubuntu, Mint Debian Edition, Emmabuntüs, MX Linux, Kali Linux, Tails, Raspbian,...
- Debian est reconnu pour sa stabilité (sur la branche Stable), notamment grâce à son long cycle de développement (2 ans au lieu de classiquement 6 mois à 1 an), ce qui permet de réaliser 6 mois de débogage après avoir bloqué l’évolution des logiciels, ainsi que par la rigueur exigée pour qu’un logiciel soit accepté.
- Debian a pour objectif d’être un système d’exploitation universel, et propose donc des images pour de nombreuses architectures processeurs 32 et 64 bits (Intel/AMD/ARM mais aussi PowerPC, MIPS)
- Debian utilise peu de ressources matérielles et est facilement modulable, ce qui en fait une distribution parfaite pour serveurs ou ordinateurs anciens
- La communauté est constituée de nombreux contributeurs et utilisateurs à travers le monde. Le projet est dirigé directement par les développeurs du projet sous forme de démocratie directe, ce qui permet de rester fidèle aux principes de Debian définis dès 1993 sous la forme d’une charte, et ainsi d’être indépendante de toute influence commerciale ou financière désirant dérouter le projet.

> Ce tutoriel ne concerne que l'installation de Debian sur un PC.
{.is-info}

> Si vous souhaitez installer Debian sur serveur, nous recommandons une installation de type minimal sans environnement de bureau comme décrit dans l'article [Serveur sous Debian Stable](/tutoriels-serveur/serveur-debian-stable).
{.is-warning}

# Quelle saveur de Debian adopter ?

Entre les branches, les environnements de bureau (DE), les types de processeurs et les pilotes libres ou pas... on s'y perd :D

**Faisons le tour pour déterminer ce qui vous convient le mieux.**

## Versions et cycle de vie

Chaque [version de Debian](https://fr.wikipedia.org/wiki/Historique_des_versions_de_Debian) a un nom de code qui est [choisi parmi les personnages du film d'animation Toy Story](https://wiki.debian.org/fr/ToyStory) :
- *Buster* (Debian 10) aujourd’hui « old-old-stable » est sortie en 2019.
- *Bullseye* (Debian 11) aujourd’hui « old-stable », est sortie en 2021.
- *_Bookworm_* (Debian 12) est l’actuelle version stable « current-stable » sortie en 2023
- *Trixie* :bug:, aujourd’hui en développement (branche Testing) sortira sous le nom de Debian 13.
- *Forky*, sera le nom de la version suivante.

:arrow_right: Bookworm est donc actuellement la version stable et Trixie le deviendra lorsque sa phase de test (testing) sera terminée.

> Le [support](https://wiki.debian.org/fr/LTS) de chaque version dure 5 ans.
> Environ tous les 2 ans, l'actuelle stable devient old-stable, testing devient stable et une nouvelle version testing est créée.
> Pour en savoir plus, lisez le [cycle de vie décrit sur site Cahier de l'administrateur Debian](https://debian-handbook.info/browse/fr-FR/stable/sect.release-lifecycle.html)
{.is-info}

## Quelle branche choisir ?

Il existe donc 4 à 5 [branches actives de Debian](https://www.debian.org/releases/index.fr.html) (c’est-à-dire bénéficiant de mises à jour), nous ne parlerons que des 3 dernières :
- old-old-stable
- old-stable
- **stable** (nous recommandons)
- **testing**
- **unstable** (sid)

### Branche "Stable"

La branche Stable est une version dite figée :
- La nouvelle version Stable est publiée après généralement 1,5 ans d’évolution (système et logiciels) puis 6 mois de déboguage (période dite de « freeze »), puis seuls les bugs et failles de sécurité sont corrigés et publiés dans les mises à jour, sans ajouter de nouvelles fonctionnalités. La version stable est la distribution officielle de Debian, **recommandée pour la majorité des utilisateurs** ;
- Debian sort lorsqu’elle est prête, et ce choix de stabilité est fait au détriment de la nouveauté des logiciels, qui à sa sortie, ont déjà au moins 6 mois.

> À privilégier si vous souhaitez des **logiciels stables** mais pas forcément dans leurs dernières versions. Les mises à jour seront moins fréquentes et moins volumineuses.
{.is-success}

Si vous avez besoin d’une version récente d'un logiciel, vous pourrez néanmoins activer des dépôts dits "[backports](https://backports.debian.org/Instructions/)" (paquets provenant de la branche "Testing" cf. ci-après, adaptés à la branche "Stable").

> Si les dépôts "backports" ne conviennent pas, une autre solution est l'utilisation des logiciels sous d'autres formats, comme les [Flatpak](#flatpak) ou les AppImage, pour avoir une version plus récente.
{.is-info}

### Branche "Testing"

La branche Testing est la future version Stable :
- Les paquets de la brance Unstable/sid arrivent automatiquement dans la branche Testing une fois validés : un algorithme vérifie qu’ils sont restés un nombre fixe de jours sans bugs détectés et après avoir validé certains critères de stabilité ;
- Seuls les logiciels suffisamment aboutis (entendu bugs critiques corrigés !) y sont ajoutés pour tester leur intégration dans le système ;

> Cette branche contient donc les **logiciels les plus récents**, pouvant toutefois comporter quelques bugs mineurs, avec des mises à jour pouvant parfois casser le système.
{.is-info}

### Branche "Unstable"

Le nom de code de cette version est et sera toujours Sid (le garçon qui s'amuse à casser les jouets de sa sœur dans Toy Story :boom:). C'est la version en développement constant :
- `Sid` est continuellement alimentée par les toutes dernières versions des logiciels en cours de développement (hors période de « freeze »)
- Des bugs apparaissant couramment mais les corrections sont rapidement apportées
- Les bugs sont souvent juste de petits désagréments rapidement corrigés qui ne dérangeront pas les utilisateurs débrouillards, mais qui pourront perturber les plus novices
- Les développeurs veillent en continu à une cohérence de Unstable, en proposant rapidement des mises à jour en cas de soucis
- Les correctifs de sécurité sont appliqués rapidement
- Des outils comme `apt-list bugs` permettent d'éviter des mises à jour problématiques

> **À réserver aux développeurs, contributeurs et testeurs.**
> D'ailleurs, Debian recommande vivement de s'abonner à la [liste de diffusion debian-devel-announce](https://lists.debian.org/debian-devel-announce/) pour recevoir les notifications de modifications majeures, par exemple, _les mises à niveau pouvant casser le système_ !
{.is-warning}

---
Pour conclure :

:arrow_right: **Dans le présent tutoriel, nous conseillons et utiliserons la version _Stable_.**

:warning: Nous ne recommandons pas forcément l'utilisation de Debian Testing. Mais un tutoriel dédié à l'[installation de Debian Testing](/tutoriels/debian-testing) est toutefois disponible si vous savez ce que vous faites.

:x: Enfin, nous vous déconseillons l'installation de `Sid` sur votre machine si vous n'êtes pas développeur ou testeur.


## Qu'est-ce que les "Non-free Firmware" ?

Les [dépôts Debian](https://wiki.debian.org/fr/DebianRepository) sont compartimentés par type de licence :
- main : les paquets libres
- contrib : les paquets libres... mais qui comportent des dépendances avec des paquets non-libres
- non-free : les paquets sous licence non libres (non-free)

> non-libre / non-free ici au sens de la [Debian Free Software Guidelines (DFSG)](https://www.debian.org/social_contract.fr.html)
{.is-info}

Donc les "non-free firmware" sont des pilotes _non libres_ que l'on retrouve dans les dépôts non-free.
Il existe d'ailleurs des images `.iso` de Debian avec les pilotes non libres inclus directement et [dans la prochaine version, ces firmwares seront automatiquement inclus](/tutoriels/debian-testing) https://lists.debian.org/debian-devel-announce/2022/10/msg00001.html).

- La raison : certains constructeurs de composants ne fournissent pas les spécifications de fonctionnement du matériel qu'ils fabriquent. Parfois, ils fournissent quand même des pilotes à la communauté GNU/Linux/Unix, mais ils ne sont pas libres. Suivant votre matériel, il vous faudra installer une image `.iso` les incluant pour réussir à installer Debian sur votre machine.

## Quelle est l'architecture de mon processeur ?

> CPU 64 ou 32 bits ?

La plupart des PC aujourd'hui sont dotés d'un processeur de type 64 bits (amd64).
Les ordinateurs ayant des processeurs produits avant 2007/2008, auront potentiellement un processeur 32 bits (i386).

> Même si les systèmes 32 bits sont moins gourmands en ressources, ces systèmes sont à éviter car beaucoup de logiciels hors dépôt Debian ne sont maintenant disponibles qu'en 64 bits.
{.is-warning}

Si vous n'êtes pas sûr des jeux d'instructions supportés par votre CPU, vous pouvez [vérifier par vous-même](https://itsfoss.com/32-bit-64-bit-ubuntu/).

## Quel environnement de bureau (DE) ?

Lors de l'installation, vous devrez choisir votre environnement de bureau.

Debian vous laissera le choix entre :
- GNOME (par défaut) : Consomme beaucoup de mémoire vive (RAM), basé sur GTK3
- KDE Plasma: Consomme un peu moins de RAM que GNOME
- Cinnamon: C'est le DE de Mint, fork de GNOME mais plus léger
- MATE: C'est le DE de Mint, fork de GNOME2, encore plus léger que Cinnamon
- GNOME Flashback: Comme MATE mais basé sur GTK3
- XFCE: Consomme très peu de RAM, basé sur GTK+
- LXQt: Consomme très peu de RAM, basé sur Qt
- *LXDE: Nous déconseillons son utilisation, il est en fin de vie, préférez dans ce cas LXQt !*

> Pour vous aider dans votre choix, consultez le [chapitre Environnement de Bureau dans l'article Distributions Linux](https://wikilibriste.fr/debutant/linux-distributions#les-environnements-de-bureau)
{.is-info}

# Préparation
Avant de procéder à l'installation, il nous faut télécharger Debian, préparer une clef USB pour l'installation et configurer le BIOS du PC.

## Source d'installation
> A partir de maintenant, nous partons du principe que :
> -- vous avez choisi l'environnement de bureau que vous allez installer ;
> -- vous connaissez l'architecture de votre processeur (généralement x86_64 / amd64).
{.is-warning}

## Tabs {.tabset}
### Pour les débutants (Installation Graphique simplifiée)

Téléchargez le fichier correspondant au processeur de votre PC et à votre bureau préféré :
- Live CD 64 bits (avec non-free firmware) :
https://cdimage.debian.org/cdimage/unofficial/non-free/cd-including-firmware/11.6.0-live+nonfree/amd64/iso-hybrid/
- ou Live CD 32 bits (avec non-free firmware) :
https://cdimage.debian.org/cdimage/unofficial/non-free/cd-including-firmware/11.6.0-live+nonfree/i386/iso-hybrid/
{.links-list}

> Téléchargez aussi, sur cette même page, le fichier `SHA256SUMS` correspondant afin vérifier l'intégrité du fichier téléchargé.
{.is-warning}

> Dans ce tutoriel, afin de vous éviter tout problème de compatibilité avec votre matériel, nous utiliserons la version **Stable _avec non-free firmwares_.**
> A partir de la prochaine version de Debian, les non-free firmwares seront inclus par défaut.
{.is-info}

### Pour les autres (Installation Graphique classique)

Téléchargez le fichier correspondant au processeur de votre PC :
- Branche Stable 64 bits avec non-free firmware : `firmware-11.6.0-amd64-netinst.iso` 
https://cdimage.debian.org/cdimage/unofficial/non-free/cd-including-firmware/current/amd64/iso-cd/
- Branche Stable 32 bits avec non-free firmware : `firmware-11.6.0-i386-netinst.iso`
https://cdimage.debian.org/cdimage/unofficial/non-free/cd-including-firmware/current/i386/iso-cd/
{.links-list}

> Téléchargez aussi, sur cette même page, le fichier `SHA256SUMS` correspondant afin vérifier l'intégrité du fichier téléchargé.
{.is-warning}

> Dans ce tutoriel, afin de vous éviter tout problème de compatibilité avec votre matériel, nous utiliserons la version **Stable _avec non-free firmwares_.**
> A partir de la prochaine version de Debian, les non-free firmwares seront inclus par défaut.
{.is-info}

## Création d'un média d'installation

Rendez vous sur l'article dédié pour [rendre une clé USB bootable](/tutoriels/usb-bootable) et ainsi créer le média d'installation de Debian.

## Préparation du BIOS

Suivez les instructions sur la page [Configurer le BIOS de votre PC](/tutoriels/bios-boot) pour autoriser le démarrage sur clef USB et désactiver le SecureBoot.

## Démarrage sur clef USB

- Branchez la clef USB que vous avez préparée précédemment sur un port USB de votre PC.
- Redémarrez le PC.
- L'écran suivant devrait apparaître :

![](/images/debian-stable-01.jpg){.align-center}

> Si cet écran n'apparaît pas, vérifiez votre clef USB et/ou la configuration du BIOS !
{.is-danger}

# Installation Debian Stable

Voici 2 méthodes d'installation de Debian Stable :
1. Installation Graphique simplifiée (via l'installeur [Calamares](https://en.wikipedia.org/wiki/Calamares_(software))) parfaite pour les débutants.
2. Installation Graphique classique avec un peu plus d'options mais moins conviviale.

> Temps d'installation entre 30 minutes et 1 heure en fonction de :
> -- Le DE que vous aurez choisi
> -- Votre connexion internet (ADSL, VDSL, Fibre...)
> -- La rapidité de votre disque dur
> -- Si vous chiffrez votre disque dur ou non
{.is-info}

# Tabs {.tabset}
## Installation simplifiée (débutants)

> Dans cette méthode, nous allons utiliser une image live de Debian, il vous faut donc au préalable avoir créé votre clef USB avec l'un des fichiers `.iso` avec l'environnement de bureau de votre choix en bas de la [page live images non-free for the Debian GNU/Linux amd64](https://cdimage.debian.org/cdimage/unofficial/non-free/cd-including-firmware/11.6.0-live+nonfree/amd64/iso-hybrid/) !
{.is-warning}

- Sélectionnez l'option par défaut "Debian GNU/Linux Live ..." et appuyez sur <kbd>ENTRÉE</kbd>.

![](/images/debian-stable-live-01.jpg){.align-center}

- Patientez quelques minutes jusqu'à ce que le bureau apparaisse.

> Si la résolution est trop petite, allez dans les préférences système puis matériel et affichage pour régler une résolution plus élevée.
{.is-info}

![](/images/debian-stable-live-02.jpg){.align-center}

- Cliquez sur "Install Debian" :

![](/images/debian-stable-live-03.jpg){.align-center}

- Choisissez votre langue, ici "Français" puis cliquez sur "Suivant" :

![](/images/debian-stable-live-04.jpg){.align-center}

- Choisissez votre région, ici "Paris" puis cliquez sur "Suivant" :

![](/images/debian-stable-live-05.jpg){.align-center}

- Choisissez votre clavier, ici "French" (Alt. Latin 9 only) puis cliquez sur "Suivant" :

> Si vous n'êtes pas sûr, vous pouvez tester votre clavier dans la zone de saisie en bas de l'écran.
{.is-info}

![](/images/debian-stable-live-06.jpg){.align-center}

- Sélectionnez "Effacer le disque" puis cliquez sur "Suivant" :

> Si vous installez un PC portable qui sera amené à être souvent déplacé ou que votre modèle de menaces est modéré ou élevé, nous vous conseillons de cocher la case "Chiffrer le système".
> [En apprendre plus sur le chiffrement](/intermediaire/chiffrement#le-chiffrement).
{.is-warning}

> **Dans tous les autres cas** (PC fixe ou portable sans déplacement), **_ne cocher pas_ la case "Chiffrer le système"**, le disque dur ne sera pas chiffré.
{.is-success}

![](/images/debian-stable-live-07.jpg){.align-center}

- Dans "Quel est votre nom", mettez ce que vous souhaitez voir afficher sur l'écran de connexion pour votre compte utilisateur.

> De façon générale, ne mettez pas d'informations personnelles ici. Vous pourrez de toute façon facilement changer ce libellé plus tard.
{.is-warning}

- Dans "Quel nom souhaitez-vous utiliser pour la connexion", entrez l'identifiant utilisateur en minuscule et sans espace.

> Choisissez un identifiant qui ne vous identifie pas explicitement sur le système, par exemple, utilisez plutôt un pseudo.
> Vous ne pourrez pas modifier l'identifiant plus tard, il est figé.
> Un répertoire portant son nom sera d'ailleurs créé sous le dossier `/home/`
{.is-warning}

- Dans "Quel est le nom de votre ordinateur", choisissez un nom pour votre PC
> Petit conseil, n'utilisez pas de nom _explicite_ qui pourrait, sur le réseau, désigner votre PC ou le système d'exploitation installé ou toute autre information qui pourrait compromettre la sécurité de votre machine, y compris votre identité ;)
> Ici par exemple le nom du PC correspond à un fleuve ("volga") mais cela pourrait très bien être un monument, une célébrité, une planète... soyez créatif !
{.is-success}

- Entrez votre mot de passe utilisateur, à l'identique dans chacune des cases

> Il est fortement recommandé :
> -- de le stocker dans un gestionnaire de mots de passe
> -- de choisir un mot de passe fort
> -- de choisir un mot de passe différent de vos autres comptes !
> **:arrow_right: Consultez l'article lié aux [mots de passe](/debutant/gestionnaire-mots-passe) pour plus d'informations.**
{.is-warning}

- _Ne cochez pas_ "Démarrer la session sans demander de mot de passe"

- Cliquez sur "Suivant" :

![](/images/debian-stable-live-08.jpg){.align-center}

- Un récapitulatif vous est présenté, lisez-le puis cliquez sur "Installer" pour lancer l'installation :

> **Assurez-vous d'avoir sauvegardé les informations importantes avant de valider !**
> Attention, une fois cet écran validé, _toutes les données seront effacées_ !
{.is-warning}

![](/images/debian-stable-live-09.jpg){.align-center}

- Installation en cours ...

![](/images/debian-stable-live-10.jpg){.align-center}

- Assurez-vous que la case "Redémarrer maintenant" soit cochée puis cliquez sur "Terminé" pour redémarrer l'ordinateur :

![](/images/debian-stable-live-11.jpg){.align-center}

> L'installation est terminée, **vous devez maintenant éjecter votre média d'installation**.
{.is-success}

- Appuyez sur la touche <kbd>ENTRÉE</kbd>, le PC va redémarrer :

![](/images/debian-stable-live-12.jpg){.align-center}

- Votre PC redémarre, si tout s'est bien passé vous verrez brièvement pendant quelques secondes l'écran de sélection du noyau (kernel).

> Debian va démarrer automatiquement au bout de quelques secondes.
> Si votre disque est chiffré, il vous faudra saisir le mot de passe de déchiffrement du disque.
{.is-info}

![](/images/debian-stable-live-13.jpg){.align-center}

> L'écran de connexion à votre bureau apparaît, vous avez réussi à installer Debian, bravo !
{.is-success}

> Maintenant que Debian est installée, n'oubliez pas de suivre les chapitres ci-dessous pour le configurer.
{.is-info}

![](/images/debian-stable-live-14.jpg){.align-center}

## Installation classique

> Dans cette méthode, nous allons utiliser une image netinstall de Debian, il vous faut donc au préalable avoir créé votre clef USB avec l'un des fichiers `.iso` avec l'environnement de bureau de votre choix en bas de la [page Branche Stable 64 bits avec non-free firmware](https://cdimage.debian.org/cdimage/unofficial/non-free/cd-including-firmware/current/amd64/iso-cd/) !
{.is-warning}

- Sélectionnez "Graphical Install" et appuyez sur <kbd>ENTRÉE</kbd>.

![](/images/debian-stable-01.jpg){.align-center}

- Choisissez votre langue, ici "Français" :

![](/images/debian-stable-02.jpg){.align-center}

- Choisissons maintenant les paramètres régionaux, "France" :

![](/images/debian-stable-03.jpg){.align-center}

- Sélectionnez votre type de clavier :

![](/images/debian-stable-04.jpg){.align-center}

- Debian va maintenant charger les composants pour l'installation :

![](/images/debian-stable-05.jpg){.align-center}

- Choisissez un nom pour votre PC (hostname) puis cliquez sur "Continuer" :
> Petit conseil, n'utilisez pas de nom _explicite_ qui pourrait, sur le réseau, désigner votre PC ou le système d'exploitation installé ou toute autre information qui pourrait compromettre la sécurité de votre machine, y compris votre identité ;)
> Ici par exemple le nom du PC correspond à un fleuve ("volga") mais cela pourrait très bien être un monument, une célébrité, une planète... soyez créatif !
{.is-success}

![](/images/debian-stable-06.jpg){.align-center}

- Laissez ce champ vide puis validez :

![](/images/debian-stable-07.jpg){.align-center}

- Laissez ces champs vide et cliquez sur "Continuer" :

> Ainsi le compte `root` sera désactivé et c'est votre compte utilisateur qui sera capable via `sudo` de lancer des tâches d'administration :
{.is-info}

![](/images/debian-stable-08.jpg){.align-center}

- Entrez le nom que vous souhaitez voir afficher sur l'écran de connexion pour votre compte utilisateur :

> Si vous ne souhaitez pas pouvoir être identifié, ne mettez pas d'informations personnelles ici.
{.is-warning}

> Vous pourrez facilement changer ce libellé plus tard.
{.is-info}

![](/images/debian-stable-09.jpg){.align-center}

- Entrez maintenant l'identifiant de cet utilisateur en minuscule et sans espace :

> Vous ne pourrez pas modifier l'identifiant plus tard, il est figé. Un répertoire portant son nom sera d'ailleurs créé sous le dossier `/home/`
> Choisissez un identifiant qui ne vous identifie pas explicitement sur le système, par exemple, utilisez plutôt un pseudo.
{.is-warning}

![](/images/debian-stable-10.jpg){.align-center}

- Les 2 écrans suivants vous demanderont de choisir un mot de passe pour votre compte utilisateur

> Il est fortement recommandé :
> -- de le stocker dans un gestionnaire de mots de passe
> -- de choisir un mot de passe fort
> -- de choisir un mot de passe différent de vos autres comptes !
> **:arrow_right: Consultez l'article lié aux [mots de passe](/debutant/gestionnaire-mots-passe) pour plus d'informations.**
{.is-warning}

![](/images/debian-stable-11.jpg){.align-center}

- L'outil de partitionnement démarre ...

> Le partitionnement est un sujet complexe et controversé.
> Le [Wiki de Arch Linux](https://wiki.archlinux.org/title/partitioning) explique très bien les différents cas d'usage.
{.is-warning}

![](/images/debian-stable-12.jpg){.align-center}

- Vous allez maintenant devoir partitionner le disque de votre machine.

> Dans notre exemple nous partirons sur un partitionnement de type "assisté" avec une partition `/home` dédiée. C'est l'installateur guidé de Debian qui réalisera tout pour vous et va créer automatiquement dans notre cas, 4 partitions :
> ~ **/boot** : Qui contient tous les fichiers nécessaires à l'amorçage (noyau Linux, ...)
> ~ **SWAP**: Le "fichier" d'échange
> ~ **/home** : Dans ce dossier, vous retrouverez les profils utilisateurs. D'ailleurs votre compte sera un sous répertoire de `/home/` et contiendra vos paramètres, votre Bureau, vos Documents, Photos, Vidéos, Téléchargements
> ~ **/** : Ce point de montage sera la racine du système de fichiers, et contiendra tout le reste. L'intérêt de le séparer, est que si `/home` venait à être saturé, cela n'impactera pas le système ;)
{.is-success}

> Si vous installer un PC portable qui sera amené à être souvent déplacé ou que votre modèle de menaces est modéré ou élévé, nous vous conseillons de choisir "Assisté - utiliser tout un disque avec LVM chiffré".
> [En apprendre plus sur le chiffrement](/intermediaire/chiffrement#le-chiffrement).
{.is-warning}

> **Dans tous les autres cas** (PC fixe ou portable sans déplacement), **choisissez "Assisté - utiliser un disque entier"**, le disque dur ne sera pas chiffré.
> **Notez que dans ce cas, certain des écrans liés à LVM ou au chiffrement ne seront dans ce cas pas présentés par la suite.**
{.is-success}

![](/images/debian-stable-13.jpg){.align-center}

- Sélectionnez le disque principal, généralement "**sda**" ou "**nvme0n1**":

![](/images/debian-stable-14.jpg){.align-center}

- Sélectionnez "Partition /home séparée" :

![](/images/debian-stable-15.jpg){.align-center}

- Sélectionnez "Oui" puis cliquez sur "Continuer" :

> **Assurez vous d'avoir sauvegardé les informations importantes avant de valider !**
> Attention, une fois cet écran validé, _toutes les données seront effacées_ !
{.is-warning}

![](/images/debian-stable-16.jpg){.align-center}

- Avant de chiffrer votre disque, Debian est maintenant en train d'écrire des données aléatoires sur tout le contenu du disque :

> Cette étape va durer un certain temps, comptez environ 10 mins par tranche de 25 Go, tout dépend de la rapidité de votre disque ainsi que sa taille !
> Cette opération ne sera faite qu'une seule fois, ainsi soyez patient, cela vaut le coup !
{.is-info}

![](/images/debian-stable-17.jpg){.align-center}


- Choisissez maintenant un mot de passe pour déchiffrer votre disque :

> Il est fortement recommandé :
> -- de le stocker dans un gestionnaire de mots de passe
> -- de choisir un mot de passe fort
> -- de choisir un mot de passe différent de celui de votre compte utilisateur
> **:arrow_right: Consultez l'article lié aux [mots de passe](/debutant/gestionnaire-mots-passe) pour plus d'informations.**
{.is-warning}

![](/images/debian-stable-18.jpg){.align-center}

- Laissez la valeur par défaut et validez :

> Vous pouvez aussi saisir `max` mais normalement par défaut l'installeur calcul l'espace maximum pour vous.
{.is-info}

![](/images/debian-stable-19.jpg){.align-center}

- Relisez le récapitulatif et sélectionnez "Terminer ..." pour valider le schéma de partitionnement. Cliquez ensuite sur "Continuer" :

![](/images/debian-stable-20.jpg){.align-center}

- Sélectionnez "Oui" pour valider les changements et cliquez sur "Continuer"  :

![](/images/debian-stable-21.jpg){.align-center}

- Debian va maintenant installer le système "de base", celui qui est disponible sur votre média d'installation :

![](/images/debian-stable-22.jpg){.align-center}

- Choisissez "Non" car nous n'avons pas d'autre média à charger puis cliquez sur "Continuer" :

![](/images/debian-stable-23.jpg){.align-center}

> Pour stocker et distribuer les paquets logiciels, les distributions GNU/Linux utilisent des dépôts dupliqués et répliqués sur les serveurs de contributeurs à travers le monde, que l'on appelle "miroir".
{.is-info}

- Sélectionnez avec "Oui" pour utiliser un miroir sur le réseau :

> Seulement si votre connexion Internet est trop lente et que vous utilisez le DVD (pas le netinstall) : vous pouvez sélectionner "Non" ; dans ce cas Debian ne sera pas mis à jour durant l'installation et vous devrez le faire plus tard. Évidemment vous ne verrez pas certains des écrans ci-dessous.
{.is-info}

![](/images/debian-stable-24.jpg){.align-center}

- Sélectionnez votre pays :

![](/images/debian-stable-25.jpg){.align-center}

- Vous pouvez sélectionner un miroir proche de chez vous ou opter pour celui par défaut :

![](/images/debian-stable-26.jpg){.align-center}

- Dans la plupart des cas on laisse ce champ vide (si toutefois vous avez un "proxy", renseignez les informations pour y accéder) :

![](/images/debian-stable-27.jpg){.align-center}

- La liste des paquets va maintenant être mise à jour...

![](/images/debian-stable-28.jpg){.align-center}

- Vous devez maintenant choisir de participer ou non aux [statistiques d'utilisation des paquets Debian](https://popcon.debian.org/). Choisissez "No" si vous ne souhaitez pas participer aux statistiques :

![](/images/debian-stable-29.jpg){.align-center}

- **Laissez coché "Utilitaires usuels du système"** puis choisissez _un_ environnement de bureau (DE) :

![](/images/debian-stable-30.jpg){.align-center}

- Installation en cours ...

![](/images/debian-stable-31.jpg){.align-center}

- Sélectionnez "Oui" pour installer GRUB :

![](/images/debian-stable-32.jpg){.align-center}

- Sélectionnez votre disque principal pour y placer GRUB :

![](/images/debian-stable-33.jpg){.align-center}

> L'installation est terminée, **vous devez maintenant éjecter votre média d'installation**.
{.is-success}

- Cliquez sur "Continuer" et le PC va redémarrer :

![](/images/debian-stable-34.jpg){.align-center}

- Votre PC redémarre, si tout s'est bien passé, vous verrez brièvement pendant quelques secondes l'écran de sélection du noyau (kernel).

![](/images/debian-stable-35.jpg){.align-center}

> Debian va démarrer automatiquement au bout de quelques secondes.
> Si votre disque est chiffré, il vous faudra saisir le mot de passe de déchiffrement du disque.
{.is-info}

![](/images/debian-stable-36.jpg){.align-center}

> L'écran de connexion à votre bureau apparaît, vous avez réussi à installer Debian, bravo !
{.is-success}

![](/images/debian-stable-37.jpg){.align-center}

> Maintenant que Debian est installé, n'oubliez pas de suivre les chapitres ci-dessous pour le configurer.
{.is-info}

# Logithèque

Pour installer des logiciels depuis la ligne de commande, on utilise l'outil `apt`.
Par exemple, la commande suivante va installer VLC :
```bash
sudo apt install vlc
```

Une autre manière d'installer des logiciels consiste à passer par la logithèque.
:arrow_right: Suivant votre environnement de bureau, vous retrouverez l'une des logithèques ci-dessous.

## Synaptic (LXDE / MATE)

Le [gestionnaire de paquet Synaptic](https://wiki.debian.org/fr/Synaptic) est probablement la plus ancienne logithèque encore existante à ce jour.
Cependant, elle est austère et peu intuitive mais cela pourra vous être utile si votre DE n'inclut pas d'autre logithèque par défaut !

> Vous le trouverez, en général, dans le menu démarrer sous la catégorie "Préférences".
{.is-info}

## KDE / LXQt

C'est la logithèque [Discover](https://apps.kde.org/discover/) qui est embarquée par défaut.
Elle est très évoluée et est capable de gérer les paquets traditionnels `.deb` mais aussi les flatpak !

> Vous la trouverez, en général, dans le menu démarrer sous la catégorie "Outils Système".
{.is-info}

## GNOME / Cinnamon

GNOME et Cinnamon embarquent par défaut la logithèque [GNOME Software](https://wiki.gnome.org/Apps/Software).
Elle est très évoluée et est capable de gérer les paquets traditionnels `.deb` mais aussi les flatpak !

> Vous la trouverez dans le menu principal sous le nom "GNOME Logiciels".
{.is-info}

Si GNOME Software n'est pas disponible, voici comment l'installer :
```bash
sudo apt install -y gnome-software
```

## Flatpak

Le problème avec les logiciels présents dans les dépôts Debian **Stable** (contrairement à Debian Testing), c'est qu'ils peuvent être plus anciens que les versions actuelles du fournisseur du logiciel.

Pour contourner ce problème, si vous souhaitez installer la dernière version de votre logiciel préféré, vous pouvez utiliser le système [Flatpak](https://fr.wikipedia.org/wiki/Flatpak) :)

Pour ce faire, lancez la commande suivante : vous pourrez ensuite, depuis GNOME Logiciels ou Discover, installer des flatpak :

- Pour GNOME Software :
```bash
sudo apt install -y flatpak gnome-software-plugin-flatpak
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

- Pour Discover :
```bash
sudo apt install flatpak plasma-discover-flatpak-backend
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

> L’inconvénient des flatpak est qu'ils utilisent plus d'espace disque, cela est dû au fait qu'ils embarquent les dépendances nécessaires au fonctionnement du logiciel, c'est ce qui fait aussi leur force, la portabilité !
{.is-warning}

# Logiciels recommandés

## Navigateur

Par défaut le navigateur installé est Firefox ESR.
C'est une édition spéciale de Firefox qui est plutôt destinée aux entreprises ou bien à ceux qui préfèrent la stabilité plutôt que de nouvelles fonctionnalités. En effet les mises à jour majeures sont beaucoup moins fréquentes.

Si cette édition ESR ne vous convient pas, vous pouvez la désinstaller et retirer les fichiers de configuration avec ces commandes :
```bash
sudo apt purge -y firefox-esr
sudo apt autoremove
```

> Les données personnelles de votre profil (favoris, cache, cookies, ...) ne seront pas supprimées, vous devrez le faire vous-même en supprimant le dossier `~/.mozilla/`
{.is-warning}

> Pour installer un autre navigateur, consultez la [liste des navigateurs recommandés pour PC](/debutant/navigateurs#pour-ordinateurs) et installez-le depuis votre logithèque.
{.is-info}

## Suite bureautique

Si LibreOffice n'est pas de facto installé, installez-le si vous avez besoin d'une suite bureautique (tableur, traitement de texte, ...) comme suit :
```bash
sudo apt install -y libreoffice libreoffice-l10n-fr libreoffice-help-fr
```

Si vous souhaitez obtenir des polices de caractères supplémentaires :
```bash
sudo apt install -y openclipart*-libreoffice hyphen-fr mythes-fr fonts-crosextra-carlito fonts-crosextra-caladea ttf-mscorefonts-installer
```

> Le paquet `ttf-mscorefonts-installer` (polices MS) n'est pas libre !
{.is-info}

## Lecture audio et vidéo

Si les outils fournis avec Debian et le DE par défaut ne vous conviennent pas, vous pouvez installer VLC depuis la logithèque ou avec cette commande :
```bash
sudo apt install -y vlc
```

En règle générale, VLC devrait être capable de lire la plupart des flux audio et vidéo, cependant si vous rencontrez des problèmes avec certains codecs, il vous faudra certainement installer `libavcodec-extra` :
```bash
sudo apt install libavcodec-extra
```

Enfin si vous avez un lecteur de DVD et que vous souhaitez les lire :
```bash
sudo apt install libdvdread4 libdvdcss2
```
Finalisez ensuite avec cette commande pour configurer la lecture DVD :
```bash
sudo dpkg-reconfigure libdvd-pkg
```

> Si toutefois il y a encore des fichiers qui ne sont toujours pas lisibles, regardez sur la [page MultimediaCodecs du wiki Debian](https://wiki.debian.org/fr/MultimediaCodecs).
{.is-info}

## Archivage et compression

Si vous n'arrivez pas à décompresser certaines archives, installez le logiciel `PeaZip` qui est excellent pour cela, vous le trouverez au format Flatpak dans votre logithèque.

## Écran de veille

> Il est conseillé de laisser l'écran de veille fourni avec votre DE
{.is-info}

Si toutefois vous souhaitez en installer d'autres, vous devrez le remplacer par XScreenSaver :
```bash
sudo apt remove *-screensaver
sudo apt install xscreensaver xscreensaver-gl xscreensaver-gl-extra xscreensaver-data xscreensaver-data-extra xscreensaver-screensaver-bsod xscreensaver-screensaver-dizzy xscreensaver-screensaver-webcollage
```

Découvrez notamment en vidéo, le célèbre écran de veille XScreensaver BSOD :
<iframe class="frame-style" title="XScreensaver BSOD" src="https://yewtu.be/embed/R_z4SDCCC0M?autoplay=0" allow="fullscreen; accelerometer; encrypted-media; gyroscope; picture-in-picture" sandbox="allow-same-origin allow-scripts allow-popups" frameborder="1"></iframe>

# Mises à jour

> L'une des principales mesure de sécurité est **d'installer régulièrement** les mises à jour de sécurité.
> Nous allons donc configurer Debian pour les installer automatiquement.
{.is-warning}

Depuis le menu "Préférences", lancez l'outil "Software & Updates" (commande `software-properties-gtk`).

- Dans l'onglet "Debian Software", cochez :
  - Officiellement ... (c'est le dépôt principal main)
  - Logiciel libre ... (dépôt contrib)
  - Vous pouvez décocher "Code source"
> Vous pouvez cocher "Logiciel non libre (dépôt non-free)" dans le cas où vous avez besoin de pilotes ou applications non-libres
> Entrez votre mot de passe si demandé
{.is-info}

![](/images/debian-config-02.jpg){.align-center}

- Dans l'onglet "Updates" :
  - **Cochez impérativement** "Mises à jour de sécurité" (dépôt security)
  - Cochez "Mises à jour recommandées" (dépôt updates)
  - Choisissez une fréquence, par exemple tous les 2 jours
  - **Choisissez  impérativement** "Download and install automatically

![](/images/debian-config-03.jpg){.align-center}

> Sur le site Debian, vous trouverez toutes les [informations sur les dépôts](https://wiki.debian.org/fr/SourcesList).
{.is-info}

> Seules les mises à jour de sécurité et les paquets de base de Debian seront mis à jour automatiquement.
{.is-warning}


- Vous devrez quand même, mettre à jour vos logiciels vous-même manuellement de temps en temps, pour cela, il vous faudra simplement lancer cette commande :
```bash
sudo apt update
sudo apt upgrade -y
```

> La mise à jour des logiciels n'impose pas le redémarrage sauf si le noyau est mis à jour.
> Cependant si pendant que vous faites votre mise à jour certaines applications sont lancées, celles-ci pourraient vous demander de les fermer.
{.is-info}

# Configuration

## Bureau

- Changez la résolution de l'écran pour celle qui correspond le mieux à celle de votre écran.

- choisir une image d'avatar pour votre compte utilisateur, un fond d'écran pour le bureau, un thème, les icônes, l'apparence des fenêtres, les curseurs souris si ceux par défaut ne vous plaisent pas.

- Vous pouvez aussi suivant les DE, installer des thèmes additionnels si vous n'aimez pas ceux installés par défaut.

- Enfin, toujours suivant les DE, vous aurez la possibilité d'activer le mode nuit pour protéger vos yeux de la lumière bleue de votre écran. L'application redshift permet de réduire cette rémanence : `sudo apt install -y redshift redshift-gtk`

## Sauvegardes

> Si vous avez choisi de chiffrer votre disque lors de l'installation, **mettez _impérativement_ en place au plus vite une solution de sauvegarde**.
> La récupération de données sur un disque chiffré endommagé s'avère très difficile, voire impossible dans certains cas.
{.is-danger}

Dans tous les cas, **ne négligez pas les sauvegardes**, consultez sur l'article [Sauvegarder mes données](/debutant/sauvegarde) pour les mettre en place.

## Firewall et Anti-Malwares

Rendez vous sur le tutoriel [Protéger sa distribution](/tutoriels/distro-protect) pour installer un firewall et un anti-malware.

## Nettoyage

2 applications qui permettent de nettoyer le système (anciens fichiers, cache, miniatures, ...) :
- [Stacer](https://oguzhaninan.github.io/Stacer-Web/) : `sudo apt install stacer`
- [Bleachbit](https://www.bleachbit.org/) : `sudo apt install bleachbit`

## Carte graphique

Si vous faites de l'édition vidéo ou jouez à des jeux vidéos récents, il vous faudra certainement installer les pilotes du fabricant de votre carte graphique.

### Pour Nvidia:

- Installez nvidia-detect :
```bash
sudo apt install nvidia-detect
```
- Lancez la détection :
```bash
sudo nvidia-detect
```
- Installez le driver recommandé par nvidia-detect, par exemple `nvidia-driver`
> à adapter suivant le retour de la commande précédente !
{.is-warning}

```bash
sudo apt install nvidia-driver
```

### AMD

```bash
sudo apt install firmware-linux firmware-linux-nonfree libdrm-amdgpu1 xserver-xorg-video-amdgpu
```
si vous jouez à des jeux vidéos ajoutez aussi:
```bash
sudo apt install mesa-vulkan-drivers libvulkan1 vulkan-tools vulkan-validationlayers
```

## Processeur et carte mère

Installez les firmwares correspondant à votre CPU, pour cela vous devrez connaitre la marque :

Si vous ne savez pas quel type de processeur dispose votre PC :
- installez [`CPU-X`](https://thetumultuousunicornofdarkness.github.io/CPU-X/) : 
```bash
sudo apt install cpu-x
```

- Démarrez `CPU-X` et repérez la marque du CPU :

![](/images/debian-config-04.jpg){.align-center}

### Intel

- Pour installer les micro-codes pour processeur Intel :
```bash
sudo apt install intel-microcode
```

### AMD

- Pour installer les micro-codes pour processeur AMD :

```bash
sudo apt install amd-microcode
```

## Mémoire

Nous allons aborder dans ce chapitre le sujet controversé de la gestion de la mémoire sur PC.

### Swappiness

On peut configurer le noyau Linux pour utiliser le SWAP sur disque moins souvent, cela se fait en configurant le "swappiness".
Plus sa valeur est faible, moins on utilisera le SWAP. Ce sera donc la mémoire vive (RAM), qui est beaucoup plus rapide, qui sera utilisée en priorité.

> La valeur par défaut est définie à 60 sur une échelle de 0 à 100.
{.is-info}

Nous vous conseillons de la réduire à 10 sur PC, voici comment procéder.

- Editez le fichier `sysctl.conf` :
```bash
sudo nano /etc/sysctl.conf
```

- Ajoutez cette ligne à la fin du fichier puis sauvez et quittez :
```brainfuck
vm.swappiness=10
```

> La modification sera prise en compte après le redémarrage du PC.
> Si vous ne voulez pas redémarrer, il vous faudra également exécuter cette commande : `sudo sysctl vm.swappiness=10`
{.is-info}

### zRAM

zRAM est un module du noyau Linux capable de compresser la mémoire vive et peut être intéressant dans bien des cas de figure.
Pour installer et configurer zRAM, consultez le chapitre [du tutoriel Optimiser sa distribution](/tutoriels/distro-protect-hardening#zram) 

## Disque dur et cache en écriture

L'activation du cache en écriture accélère les opérations d'écriture sur le disque. Par défaut Debian 
ne l'active pas.

> Notez que, **dans certains cas**, comme l'arrêt brutal de la machine, **l'activation du cache peut entraîner la perte ou la corruption de données** ! C'est à vous de décider et n'oubliez pas d'implémenter des sauvegardes régulières de votre PC.
{.is-warning}

- Voici comment l'activer sur les bureaux de type GNOME avec l'outil `Disques` :
1. Depuis le menu en bas à gauche, lancez l'outil `Disques` puis sélectionnez votre disque.
2. Cliquez sur le menu en haut à droite.
3. Sélectionnez "Paramètres du disque".
4. Activez les paramètres.
5. Passez le paramètre à "Activer le cache en écriture".
6. Cliquez sur "Valider".

![debian-config-01.jpg](/images/debian-config-01.jpg){.align-center}

- Pour l'activer en ligne de commande :
```bash
sudo hdparm -W 1 /dev/sda
```

## Batterie

> Pour PC portable seulement !
{.is-warning}

Les constructeurs fournissent rarement les spécifications de leur batterie et pour cette raison, la batterie dure souvent moins longtemps sous Linux.

**Rassurez-vous le programme [`TLP`](https://linrunner.de/tlp/installation/debian.html
) va arranger cela :)**

- Lancez cette commande pour l'installer :
```bash
sudo apt install -y tlp tlp-rdw
```

- Installons aussi son interface graphique :
```bash
flatpak install tlpui
```
- Pour la configuration nous vous renvoyons vers ce site : https://www.linuxfordevices.com/tutorials/linux/tlpui-to-increase-laptop-battery

> Il existe aussi des extensions pour GNOME qui permettent d'agir sur le processeur [CPU](https://github.com/deinstapel/cpupower) & [GPU](https://github.com/fffilo/prime-indicator).
{.is-info}


## Hibernation

**Si vous avez un PC portable** et que souhaitez mettre en place l'hibernation il vous faudra une partition SWAP (ou fichier swap) au moins égale à la taille de votre mémoire RAM.

Le wiki de Debian a une page dédiée pour [activer le mode hibernation](https://wiki.debian.org/Hibernation).

# Conclusion

> Bravo, vous avez réussi à installer et à configurer Debian sur votre PC !
{.is-success}

- Si vous avez envie d'aller plus loin :
  - rendez vous sur [Les Cahiers du débutant du site debian-facile](https://debian-facile.org/projets/lescahiersdudebutant/)
  - le [wiki Debian](https://wiki.debian.org/fr/FrontPage)
  - [le guide officiel d'installation de Debian Stable](https://www.debian.org/releases/stable/amd64/)

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): marmotte, Theudric, DyanZan, Ayo*