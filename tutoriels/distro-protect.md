---
title: Protéger sa distribution
description: Les premières étapes de la protection de notre distribution Linux...
published: true
date: 2024-04-07T17:37:53.656Z
tags: virus, malware, pare-feu, firewall, antivirus, antimalware, rkhunter, chkrootkit, clamav, clamtk, gufw, ufw
editor: markdown
dateCreated: 2023-01-15T12:16:32.765Z
---

Ce tutoriel a pour but de fournir un guide basique dans une première étape de la protection d'un système GNU/Linux. Avant toute chose prendre le temps d'abord de bien lire l'article sur les façons d'[améliorer son hygiène numérique](/hygiene-numerique), notamment la partie sur les antivirus / malwares afin de bien appréhender le sujet au préalable.

# Sauvegarde

Des sauvegardes régulières sont indispensables pour protéger vos données.

> Un article dédié vous montrera comment mettre en place des [sauvegardes automatisées](/debutant/sauvegarde) en utilisant les outils `Déjà-Dup` et `Timeshift`.
{.is-success}


# Pare-feu

Cette partie concerne le _filtrage réseau_ que vous pouvez activer sur votre machine : le mécanisme utilisé dans ce cas-là est appelé un *pare-feu* ("firewall" en anglais), mécanisme qui analyse les flux (requêtes) entrants et sortants d'une machine.

> Un pare-feu sur une distribution GNU/Linux ou BSD orienté _bureau_ est, cela dit, facultatif (c'est moins vrai sur des machines de type serveur), de par la nature même du système Linux et du type de requêtes.
>
> Egalement, les pare-feux Windows et Linux sont deux mécanismes bien différents.
{.is-info}

Si toutefois, vous préférez en activer un, voici la démarche : nous prendrons comme pare-feu le très connu **UFW** (Uncomplicated FireWall) et son interface graphique **GUFW**.

## Installation

S'il n'est pas déjà installé (_il l'est sur Linux Mint par exemple_) :
- Rendez-vous dans votre logithèque pour rechercher si l'application _GUFW_ est disponible. Si oui, installez-la !

![gufw-1](/images/gufw-1.png){.align-center}

- Si votre logithèque ne vous propose pas GUFW, nous allons devoir passer par la ligne de commandes comme suit :

#### Tabs {.tabset}
##### Debian/Ubuntu
Ou autres distributions basées sur Ubuntu ou Debian :
```
apt install gufw
```

##### Arch Linux
Ou autres distributions basées sur Arch :
```
pacman -S gufw
```

##### RedHat/Fedora
Sur les distributions basées sur Redhat, un firewall `firewalld` est déjà installé et activé par défaut. Nous suggérons de laisser ce pare-feu par défaut et de vous documenter sur son fonctionnement sur leur [documentation](https://docs.fedoraproject.org/en-US/quick-docs/firewalld/) ou bien leur [wiki](https://fedoraproject.org/wiki/Firewalld).

##### OpenSuse
Sur les distributions OpenSuse, un firewall `firewalld` est déjà installé et activé par défaut. Nous suggérons de laisser ce pare-feu par défaut et de vous documenter sur son fonctionnement sur leur [documentation](https://docs.fedoraproject.org/en-US/quick-docs/firewalld/) ou bien leur [wiki](https://fedoraproject.org/wiki/Firewalld).


## Activation

Ouvrez l'application GUFW. Nous allons l'activer tout simplement comme suit :

![gufw-2](/images/gufw-2.png){.align-center}

> Cliquez sur le slider en face de "Activer". Patientez quelques secondes, vous obtenez alors ceci :
{.is-info}

![gufw-3](/images/gufw-3.png){.align-center}

**Voilà votre pare-feu est en place.**

## Utilisation

Evidemment, si vous installez un service avec lequel vous aurez besoin de discuter sur cette machine (par exemple [syncthing](/tutoriels/syncthing)), il faudra probablement ouvrir quelques ports sur ce pare-feu. 

- Voici un exemple avec GUFW :

![gufw-4](/images/gufw-4.png){.align-center}
![gufw-5](/images/gufw-5.png){.align-center}
![gufw-6](/images/gufw-6.png){.align-center}
![gufw-7](/images/gufw-7.png){.align-center}
![gufw-8](/images/gufw-8.png){.align-center}

> Nous avons ici l'exemple de l'ouverture des ports 80 et 443 sur votre machine. 
> 
> Vous devrez adapter le *_numéro de port_* à vos besoins...
{.is-info}

# Anti-Malwares

Dans cette partie, vous apprendrez à installer et utiliser 2 types d'outils :
- Un anti-malware, ClamAV et son interface graphique ClamTk
- Deux anti-rootkits RkHunter et Chkrootkit qui se complètent

Puis nous expliquerons la marche à suivre si vous obtenez des résultats positifs.

> Retenez bien que ces outils sont généralement utilisés dans le cadre d'une analyse post-infection, c'est-à-dire si nous avons détecté une activité suspicieuse. Les résultats donnés par ces outils peuvent dérouter au premier abord, mais ceux-ci sont (très) souvent des "faux-positifs".
>
> Cela dit, il n'est pas interdit non plus d'utiliser ces outils de temps en temps, mais **ils ne doivent pas vous faire oublier que rien ne remplace une bonne hygiène numérique** et que **les résultats doivent être pris avec recul** !
{.is-warning}

## ClamAV - ClamTk

[Clam Anti-Virus](https://www.clamav.net/) n'est ni plus ni moins qu'un anti-malware multi-plateformes et surtout open-source. À l'origine développé pour Unix, et petit à petit  adapté pour tous les systèmes (y compris BSD, Solaris...). 

[ClamTk](https://gitlab.com/dave_m/clamtk/) est une interface utilisateur ("frontend" en anglais) se basant sur ClamAV pour Linux et BSD. Il permet donc d'interagir avec ClamAV non plus en ligne de commandes mais avec une interface graphique.

> Une fonctionnalité existe pour Linux afin de lancer un "*démon*" et avoir une protection temps réel comme sur les autres anti-virus du marché : `clamav-daemon`. Deux contre-indications, cela dit, pour cette fonctionnalité :
> ~~ si votre modèle implique anonymat et sécurité renforcée, vous ne devriez pas opter pour cette fonctionnalité, je vous renvoie à l'article sur l'hygiène numérique.
> ~~ en utilisant cette fonction, vous occupez de la mémoire. Si votre mémoire n'est pas très élevée (par ex. vous avez 8GB de RAM), cela peut inutilement occuper de la place et ralentir la machine. En contrepartie, effectuer un scan sera potentiellement plus rapide sur la machine si déjà en mémoire.
> **Dans la suite, nous ne proposerons donc pas l'installation du démon.**
{.is-info}

### Installation GUI

Pour ceux qui souhaitent éviter les lignes de commandes, vous retrouverez normalement l'application **ClamTk** sur la logithèque de votre distribution.

![clamtk-0.png](/images/clamtk-0.png){.align-center}

> Installer cette application installera également ClamAV.
{.is-info}

### Installation CLI

Pour ce faire, ouvrez un terminal (sur certaines distributions, l'appui sur <kbd>SUPER</kbd> + <kbd>T</kbd> le permet), sinon positionnez-vous sur le bureau, clic droit, et "ouvrir dans terminal" :

#### Tabs {.tabset}
##### Debian/Ubuntu
Ou autres distributions basées sur Ubuntu ou Debian :
```
apt install clamav clamtk
```

##### Arch Linux
Ou autres distributions basées sur Arch :
```
pacman -S clamav clamtk
```

##### RedHat/Fedora
Ou autres distributions basées sur Redhat :
```
dnf install clamav clamtk
```

##### OpenSuse
Ou autres distributions basées sur OpenSuse :
```
zypper install clamav clamtk
```


### Utilisation

Avant tout scan, prenez soin de mettre à jour l'application et la base de données des signatures :

```
sudo updatedb
sudo systemctl stop clamav-freshclam
sudo freshclam
sudo systemctl start clamav-freshclam
```

Puis nous pouvons lancer le scan :
1. Soit en utilisant ClamTk avec l'interface graphique, comme suit :

![clamtk-1.png](/images/clamtk-1.png){.align-center}
![clamtk-2.png](/images/clamtk-2.png){.align-center}
![clamtk-3.png](/images/clamtk-3.png){.align-center}
![clamtk-4.png](/images/clamtk-4.png){.align-center}
![clamtk-5.png](/images/clamtk-5.png){.align-center}
![clamtk-6.png](/images/clamtk-6.png){.align-center}
![clamtk-7.png](/images/clamtk-7.png){.align-center}

2. Soit en utilisant la ligne de commandes, comme suit :
- Scan complet, sur toute la machine via :
	`sudo clamscan -i -r /` 
	(i pour "infected" - n'affiche que les fichiers infectés, et r pour récursif)
- Scan sur un dossier spécifique, mettons pour l'exemple le dossier "Téléchargements", via :
	`sudo clamscan -i -r /home/user/Téléchargements/`

Voilà vous devriez avoir un résultat. S'il est positif (c'est-à-dire si vous avez des fichiers infectés, rendez-vous en bas du tutoriel).

## ChkRootkit

[Chkrootkit](http://www.chkrootkit.org/) est un logiciel de scan de logiciels espions sur votre machine Linux, nommés **rootkits**.

### Pré-requis

#### Tabs {.tabset}
##### Debian/Ubuntu
Ou autres distributions basées sur Ubuntu ou Debian :
```bash
sudo apt install curl
```

##### Arch Linux
Ou autres distributions basées sur Arch :
```bash
sudo pacman -S curl
```

##### RedHat/Fedora
Ou autres distributions basées sur Redhat :
```bash
sudo dnf install curl
```

##### OpenSuse
Ou autres distributions basées sur OpenSuse :
```bash
sudo zypper install curl
```

### Installation

> Malheureusement, la majorité des distributions ne possèdent pas la dernière version, la plus à jour, de l'outil. C'est pourquoi il va être important d'utiliser la ligne de commandes.
>
> **Nous allons nous baser sur la dernière version à l'heure où nous écrivons cet article, à savoir la version 0.57**.
> Dans la suite vous verrez apparaître un répertoire `chkrootkit-0.57`, qui contient donc cette même version 0.57. BIen entendu _**vous devrez donc remplacer ces chiffres par votre version**._
{.is-warning}

Nous allons nous placer dans le répertoire `Téléchargements` (ou `Downloads` sur certaines distributions) et installer l'outil :

```bash
cd ~/Téléchargements
curl --remote-name ftp://chkrootkit.org/pub/seg/pac/chkrootkit.tar.gz
```

```brainfuck
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 41948  100 41948    0     0  10429      0  0:00:04  0:00:04 --:--:-- 10429
```

```bash
curl --remote-name ftp://chkrootkit.org/pub/seg/pac/chkrootkit.md5
```

```brainfuck
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100    52  100    52    0     0     14      0  0:00:03  0:00:03 --:--:--    14
```

Après avoir téléchargé les 2 fichiers, nous vérifions l'intégrité :

```bash
cat chkrootkit.md5 
```

```brainfuck
80320d609bc732ac074262f4c2937447  chkrootkit.tar.gz
```

```bash
md5sum chkrootkit.tar.gz 
```

```brainfuck
80320d609bc732ac074262f4c2937447  chkrootkit.tar.gz
```

- Vérifiez bien ici que les sommes de contrôles sont les mêmes !

Ensuite :

```bash
tar xvzf chkrootkit.tar.gz
```

```brainfuck
chkrootkit-0.57/ACKNOWLEDGMENTS
chkrootkit-0.57/check_wtmpx.c
chkrootkit-0.57/chkdirs.c
chkrootkit-0.57/chklastlog.c
chkrootkit-0.57/chkproc.c
chkrootkit-0.57/chkrootkit
chkrootkit-0.57/chkrootkit.lsm
chkrootkit-0.57/chkutmp.c
chkrootkit-0.57/chkwtmp.c
chkrootkit-0.57/COPYRIGHT
chkrootkit-0.57/ifpromisc.c
chkrootkit-0.57/Makefile
chkrootkit-0.57/README
chkrootkit-0.57/README.chklastlog
chkrootkit-0.57/README.chkwtmp
chkrootkit-0.57/strings.c
```

```bash
cd chkrootkit-0.57
make sense
```

```brainfuck
cc -DHAVE_LASTLOG_H -o chklastlog chklastlog.c
cc -DHAVE_LASTLOG_H -o chkwtmp chkwtmp.c
cc -DHAVE_LASTLOG_H   -D_FILE_OFFSET_BITS=64 -o ifpromisc ifpromisc.c
cc  -o chkproc chkproc.c
cc  -o chkdirs chkdirs.c
cc  -o check_wtmpx check_wtmpx.c
cc -static  -o strings-static strings.c
cc  -o chkutmp chkutmp.c
```

### Utilisation

Afin de lancer un scan de la machine, lancez simplement la commande suivante dans le répertoire où les fichiers ont été décompressés (`~/Téléchargements/chkrootkit-0.57`):

```bash
sudo ./chkrootkit
```
```brainfuck
ROOTDIR is `/'
Checking `amd'... not found
Checking `basename'... not infected
Checking `biff'... not found
[...]
Checking `z2'... user user deleted or never logged from lastlog!
Checking `chkutmp'...  The tty of the following user process(es) were not found
 in /var/run/utmp !
! RUID          PID TTY    CMD
! user         1865 pts/0  bash
! user         2616 pts/0  sudo ./chkrootkit
chkutmp: nothing deleted
Checking `OSX_RSPLUG'... not tested
```

Une centaine de lignes apparaissent avec un statut. Visualisez ces lignes, et repérez les statuts à "INFECTED" ; 
- Si ce statut apparaît vous allez devoir investiguer car une potentielle menace est détectée.
**Dans ce cas, rendez-vous à la section "Réagir face à une infection".**

## RkHunter

[RkHunter](https://rkhunter.sourceforge.net/) est un second logiciel de scan de rootkits sur votre machine Linux.

### Installation GUI

Certaines distributions (notamment Arch) proposent l'application **RkHunter** dans leur logithèque, vous pouvez donc passer par celle-ci afin d'installer l'outil (il est cependant probable que ce ne soit pas la toute dernière version, dans ce cas, peut-être voudriez-vous privilégier la ligne de commandes).

![rkhunter.png](/images/rkhunter.png "Logithèque Manjaro"){.align-center}

### Installation CLI

Si votre logithèque ne vous propose pas ce logiciel, il sera donc nécessaire de passer en lignes de commandes :

#### Tabs {.tabset}
##### Debian/Ubuntu
Ou autres distributions basées sur Ubuntu ou Debian :
```
sudo apt install rkhunter perl
```

##### Arch Linux
Ou autres distributions basées sur Arch :
```
sudo pacman -S rkhunter perl
```

##### RedHat/Fedora
Ou autres distributions basées sur Redhat :
```
sudo dnf install rkhunter perl
```

##### OpenSuse
Ou autres distributions basées sur OpenSuse :
```
sudo zypper install rkhunter perl
```


### Utilisation

> **Le premier scan doit obligatoirement se faire manuellement, sur une installation clean (juste après l'installation de la distribution par exemple)**. 
{.is-warning}

Lancez les commandes suivantes :

```
sudo -i
rkhunter --propupd
nano /etc/rkhunter.conf
```

Un éditeur de texte se lance. Il va nous falloir modifier quelques lignes dans ce fichier (naviguer avec les touches <kbd>HAUT</kbd>, <kbd>BAS</kbd>) :
- `MIRRORS_MODE=1` **à modifier en** `MIRRORS_MODE=0`
- `UPDATE_MIRRORS=0` **à modifier en** `UPDATE_MIRRORS=1`
- `WEB_CMD="/bin/false"` **à modifier en** `WEB_CMD=""`
- `DISABLE_TESTS=suspscan hidden_ports hidden_procs deleted_files packet_cap_apps apps` **à modifier en** `DISABLE_TESTS=suspscan deleted_files packet_cap_apps`

Afin de quitter et enregistrer : <kbd>CTRL</kbd> + <kbd>X</kbd>, puis la touche <kbd>O</kbd> (O pour Oui) pour confirmer l'enregistrement (ou Y si vous êtes anglais :)), puis <kbd>ENTREE</kbd> pour valider.

Nous pouvons ensuite mettre à jour puis lancer le scan :

```bash
rkhunter --update
rkhunter -c -sk
```

L'analyse prend entre _**quelques minutes et plusieurs dizaines de minutes**_, selon votre machine, donc cela peut être assez long.

#### Premier SCAN

Généralement, le premier scan est une étape obligatoire afin de configurer convenablement l'outil, et qu'il n'évite de vous remonter des avertissements inutiles. Vous trouverez ici une piste afin de comprendre et contourner ces avertissements.

> Sur une distribution vierge, tous les résultats positifs doivent être vus comme des "faux-positifs" (nous revenons sur cette notion plus loin), et à ce titre traités comme ce qui suit...
{.is-info}

_**Deux exemples**_ : 
1. Sur notre machine, après notre 1er scan, Rkhunter remonte un avertissement concernant un fichier suspect `lwp-request`. Allons jeter un oeil dans le fichier journal qu'il a créé, généralement présent ici `/var/log/rkhunter.log` (attention, ce fichier doit s'ouvrir avec des droits administrateur). Ce rapport nous présente l'avertissement avec plus de détails. Voici les lignes en question :

```brainfuck
[...]
[15:48:50]   /usr/bin/lwp-request                            [ Warning ]
[15:48:50] Warning: The command '/usr/bin/lwp-request' has been replaced by a script: /usr/bin/lwp-request: Perl script text executable
[...]
```

Après un rapide tour sur internet afin de savoir ce que `lwp-request` avait à nous raconter, il s'avère que ce fichier doit être placé sur liste blanche dans l'outil, afin qu'il ne lève pas ce faux-positif à chaque fois. Pour ce faire nous allons modifier de nouveau le fichier de configuration `/etc/rkhunter.conf`, en décommentant la ligne ci-dessous, qui est en fait déjà présente dans ce fichier (!!) :

```bash
AVANT :
#SCRIPTWHITELIST=/usr/bin/lwp-request

APRES :
SCRIPTWHITELIST=/usr/bin/lwp-request
```

*Note : pour décommenter une ligne, il suffit de supprimer le '#' en début de ligne.*

**Voilà, au prochain scan vous ne déclencherez plus d'avertissement sur ce fichier.**

2. Notre second exemple concerne cette fois-ci un répertoire, `/etc/.java`. Tentons de refaire la même chose ; dans le rapport voici les lignes en avertissement :

```brainfuck
[...]
[15:52:37]   Checking for hidden files and directories       [ Warning ]
[15:52:37] Warning: Hidden directory found: /etc/.java
[...]
```

Un rapide tour sur internet (en copiant le message d'avertissement) pour s'apercevoir qu'ici encore, l'outil déclenche un faux positif sur ce répertoire ! Nous allons donc modifier de nouveau le fichier de configuration, et comme par magie, la ligne est déjà présente, mais elle est inactive (car commentée). Décommentez cette ligne :

```bash
ALLOWHIDDENDIR=/etc/.java
```

Puis pour prendre en compte cette modification, vous devrez mettre à jour la base (`propupd`). Puis tentons un second scan pour vérifier :
```bash
sudo -i
rkhunter --propupd
rkhunter -c -sk
```

Très bien, notre outil ne déclenche plus de faux-positifs.

> Il est recommandé d'effectuer un scan à chaque mise à jour importante de votre système, comme suite à une mise à jour du kernel.
{.is-info}

# Comment réagir ?

## Face à un avertissement

Malgré l'optimisation des outils, il n'est pas impossible que ceux-ci vous présentent des alertes (avertissements) qui n'ont aucun impact sur le fonctionnement de votre machine et qui ne sont pas liées à une quelconque infection : on appelle cela des "*faux-positifs*", en gros des avertissements qui n'en sont pas tout à fait ; Il peut par exemple très bien s'agir d'un fichier que vous auriez modifié volontairement ou que votre gestionnaire de paquets aurait modifié (configuration), ou d'un exécutable tout à fait inoffensif, etc.

Il est donc important de bien séparer ces "faux positifs" des menaces qui peuvent être plus réelles.

Pour ce faire, suivant votre profil, voici nos conseils :
- _Profil débutant_ : ne cherchez pas à creuser, contactez directement un groupe d'entraide (comme le nôtre) ou des groupements ou réseaux afin de vous aider et vous guider.
- _Profil intermédiaire à initié_ : vous pouvez chercher des pistes sur internet (forums, groupes, réseaux), certaines personnes ont peut-être rencontré la même anomalie, et avec un peu de chance vous trouverez quelqu'un qui a donné une remédiation à effectuer.

**Si l'infection vous semble avérée, rendez-vous dans la prochaine section !**

## Face à une infection

Dans le cas d'une infection a priori avérée, il sera nécessaire de faire une nouvelle réinstallation complète du système. Voici la procédure que vous devrez suivre :
1. Restez calme, méthodique...
2. Débranchez votre machine immédiatement de tout réseau (Ethernet ou Wifi, Bluetooth également)
3. Effectuez des sauvegardes de vos fichiers utiles si nécessaire sur un disque dur ou une clé USB annexe. Evidemment veillez à ne pas copier d'exécutables ou fichiers binaires sur ce disque ou tout autre fichier que vous ne pouvez pas scanner et vérifier !
4. À partir d'une autre machine, créez une clé USB bootable avec une distribution.
5. Réinstallez complètement votre système d'exploitation.
6. Installez tous les outils présentés dans cet article avant toute chose afin d'établir les premiers scans.
7. Ré-intégrez les fichiers que vous souhaitez et qui ont été sauvegardés sur le disque ou la clé USB annexe.
8. Refaites de nouveau les scans. Vous devriez normalement ne plus avoir d'alerte.

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo, DyanZan, marmotte*