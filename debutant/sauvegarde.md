---
title: Sauvegarder ses données
description: Sauvegarder et restaurer vos données sous Linux est crucial... Suivez le guide !
published: true
date: 2023-11-03T16:27:25.812Z
tags: debutant, intermediaire, sauvegarde, backup, restaurer, restore
editor: markdown
dateCreated: 2023-03-15T23:44:19.951Z
---

La sauvegarde ("backup" en anglais) consiste à recopier des données depuis leur emplacement d'origine vers un support annexe tel qu'une bande magnétique, un disque dur *secondaire*, une clef USB ou un espace de stockage sur le cloud.

Le but est bien sûr de pouvoir restaurer ("restore" en anglais) ces données dans les cas suivants :
- revenir à une version précédente d'un ou plusieurs fichiers ;
- réinstaller un système après une corruption de données, qu'elle soit due à une panne (disque dur défaillant), une fausse manipulation (erreur) ou à un acte malveillant (attaque).

Une sauvegarde consiste tout autant à recopier des photos, documents, vidéos... de sa machine sur un support externe (de façon manuelle ou automatique), que de sauvegarder un système entier (répertoires et fichiers). Oui vous avez bien lu, il est tout à fait possible de sauvegarder votre système d'exploitation intégralement ;)

Quelques précisions à propos des **méthodes de sauvegarde** : lorsque l'on sauvegarde les données d'un appareil la première fois, tout est sauvegardé ! 
- C'est ce que l'on appelle une **sauvegarde complète** ("full backup").

Par la suite, pour économiser du temps et surtout de l'espace disque, il est inutile de tout sauvegarder de nouveau, nous ne sauvegarderons donc que ce qui à changé. Deux variantes existent ici :
- les sauvegardes **incrémentales** : nous ne sauvons ici que les données qui ont changé _depuis la dernière sauvegarde_.
- les sauvegardes **différentielles** : nous ne sauvons que les données qui ont changé _depuis la dernière sauvegarde **complète**_ !


> Quand on vient à discuter de sûreté et de sécurité des données, la sauvegarde est probablement l'un des sujets les plus importants !
> D'autant plus vrai si vos données sont stockées sur un disque chiffré et que celui-ci subit une panne (ce qui arrivera tôt ou tard). Vous n'aurez dans ce cas, probablement plus que cette solution pour récupérer vos précieuses informations !
{.is-info}

> Dernier point important, une _sauvegarde_ qui n'est _pas testée régulièrement_ est _considérée comme non fiable_, c'est pourquoi nous vous conseillons de faire des restaurations de temps en temps !
{.is-warning}

Ce tutoriel s'articule autour de 3 catégories de sauvegardes :
- suivant que le logiciel de sauvegarde est installé sur la machine à sauvegarder (votre PC) :
:arrow_right: C'est le thème du premier chapitre `Déjà-Dup`. C'est ici que nous sauvegardons des photos, documents personnels...
- suivant le périmètre, c'est-à-dire que l'on souhaite sauvegarder certains dossiers contenant des données de travail (premier et deuxième chapitre) ou bien que l'on souhaite sauvegarder un système complet :
:arrow_right: Ce second cas fera l'objet du deuxième chapitre qui se focalise sur la sauvegarde d'un système complet avec l'outil `Timeshift`
- suivant que le logiciel de sauvegarde est installé sur un serveur qui s'occupera de déclencher les sauvegardes à distance par l'intermédiaire d'un agent installé sur les PC à sauvegarder :
:arrow_right: Nous aborderons ce cas dans le dernier chapitre.

> Dans ce tutoriel, nous ne parlerons pas de :
> -- l'archivage qui consiste à stocker pendant plusieurs années des informations figées à un état donné (par exemple sur CD/DVD-ROM ou bandes magnétiques),
> -- ni du clone de disque dur qui consiste à dupliquer un disque entier sur un autre (par exemple avec les outils `dd`, `CloneZilla` ou `Rescuezilla`),
> -- ni du [dump d'une base de données](/glossaire#dump-base-de-donn%C3%A9es) qui consiste à sauvegarder une base dans un état intègre,
> -- ni de la réplication des données, même si c'est souvent la technique utilisée pour les sauvegardes.
{.is-danger}

> Cas à part :
> # Sauvegarder sous Android
> 
> Concernant les sauvegardes de smartphone sous Android, consultez la vidéo [Présentation et Sauvegarde / Restauration NANDroid avec TWRP](/tutoriels-android/twrp). 
> 
> Et sinon pour sauvegarder ses applications libres installées(**apk**)des smartphones android , il existe Droidify(paramètres> import export, mettre en favoris). 
> Mais pour sauver les **données** et **fichiers de configuration/paramètres** des applications libres, c'est différent (suivant si l'accès est root, adb root ou simple/sans root demandé)
> ## **Depuis le téléphone:**
>  -seedvault https://github.com/seedvault-app/seedvault (intégré quasi dans toutes les ROM dégooglisées, via Paramètres>Sauvegarde, il sauvegarde a minima les applications)
>  -NeoBackup(root)
>  -DataBackup(root)
>  -dans chaque application (ca peut être long suivant le nombre d'applications, exporter/importer les paramètres et/ou données)
>  -solutions non libres(swift backup, etc)
>  ## **Depuis le pc:**
>  -adb(apk)
>  -android_backup_project https://github.com/AndDiSa/android_backup_project
>  -open-android-backup https://github.com/mrrfv/open-android-backup
> Et pour les documents, photos, musiques et video, la carte SD peut suffire mais c'est manuel.



# Sauvegarder ses données personnelles

> **Nous recommandons a minima de mettre en place des sauvegardes de ce type.**
> *Pour sauvegarder un système complet, en complément, suivez le deuxième chapitre (Timeshift).*
{.is-success}

Il existe de nombreux de logiciels de sauvegarde des données personnelles. En voici quelques-uns sous licence libre :
- [Borg](https://borgbackup.readthedocs.io/en/stable/) : Sans interface graphique, il n'est donc utilisable qu'en ligne de commandes. Nous vous recommandons plutôt **Pika**. Cependant, il peut être utile sur un serveur. Voici un bon article sur Linuxtricks à propos de [Borg Backup](https://www.linuxtricks.fr/wiki/borg-backup-gerer-ses-backups-sous-linux).
	- [Pika](https://apps.gnome.org/fr/app/org.gnome.World.PikaBackup/) : Avec interface graphique, il utilise Borg pour réaliser les sauvegardes. Vous trouverez plus d'informations sur le site d'Adrien de la chaîne Linuxtricks pour l'[installer et configurer Pika](https://www.linuxtricks.fr/wiki/pika-backup-la-sauvegarde-graphique-avec-la-puissance-de-borg).
- [Rsync](https://fr.wikipedia.org/wiki/Rsync) : Sans interface graphique, il n'est donc utilisable qu'en ligne de commandes. Nous vous recommandons plutôt **LuckyBackup**. Cependant, il peut être utile sur un serveur. 
	- [LuckyBackup](https://fr.wikipedia.org/wiki/LuckyBackup) : Avec interface graphique, il utilise rsync pour réaliser les sauvegardes.
- [Duplicity](https://en.wikipedia.org/wiki/Duplicity_(software)) : Sans interface graphique, il n'est donc utilisable qu'en ligne de commandes. Nous vous recommandons plutôt **Déjà Dup** ! Cependant, il peut être utile sur un serveur.
	- [Déjà Dup](https://wiki.gnome.org/Apps/DejaDup/Details) : Avec interface graphique, il utilise Duplicity pour réaliser les sauvegardes. Elles peuvent être chiffrées et stockées localement ou bien sur une machine distante (réseau local ou cloud). Très simple d'utilisation, nous recommandons pour les débutants !

> **Pour la sauvegarde de données, Déjà Dup est la solution que nous recommandons et que nous allons détailler ci-après.** 
{.is-success}

## Déjà Dup

Comme expliqué en introduction, il s'agit d'un des logiciels les plus simples à utiliser. Pour autant, il est très puissant car il est capable de :
- réaliser des sauvegardes :
  - [x] chiffrées par l'intermédiaire de [GPG](/intermediaire/chiffrement#pgp-gpg) (OpenPGP),
  - [x] compressées,
  - [x] exactes puisqu'il conserve les dates, droits et autres propriétés des fichiers,
  - [x] automatiques que vous pourrez planifier,
  - [x] externalisées sur disque interne ou externe, partage réseau ou dans le "cloud",
  - [x] avec déduplication des données, c'est-à-dire qu'un doublon de fichier ne sera sauvegardé qu'une seule fois, ce qui économise de l'espace disque !
  - [x] complètes et incrémentales ;
- supprimer les anciennes sauvegardes ;
- évidemment restaurer vos fichiers à partir d'un de vos jeux de sauvegarde.

### Préparation

> **Une règle d'or : Ne jamais sauvegarder les données d'un disque sur ce même disque !**
> :arrow_right: C'est pourquoi, il faut utiliser un média (support) externe comme une clef USB, un disque externe en local ou sur le réseau ou bien dans le cloud.
{.is-warning}

Nous avons donc 4 possibilités :
1. Stocker les jeux de sauvegarde sur un disque externe (ou clef USB) branché sur le PC à sauvegarder :
:arrow_right: **Cette solution est contraignante et encombrante dans le cas d'un PC portable.**
2. Si le PC dispose de 2 disques physiques internes différents, on peut envisager de croiser les sauvegardes :
:arrow_right: Sachant que tout le monde n'a pas plusieurs disques internes sur une même machine, **nous ne rentrerons pas dans le détail de cette solution**.
3. Utiliser un espace de stockage cloud pour stocker les sauvegardes :
:arrow_right: **Il est possible de configurer un accès Webdav, pour Nextcloud par exemple, [voir ici comment procéder](https://isolution.pro/fr/q/au14272034/il-manque-l-option-nextcloud-dans-les-sauvegardes-deja-dup-dans-20-04-lts)**

4. Externaliser sur un disque externe branché sur une autre machine :
:arrow_right: **C'est cette solution que nous allons présenter**. :thumbsup:

> Dans notre exemple, nous utiliserons donc cette dernière possibilité en branchant un disque externe (ou clef USB) sur notre Box internet :)
{.is-info}

#### Déterminer le volume de ses données

> Il vous faut tout d'abord savoir ce que vous souhaitez sauvegarder.
> C'est indispensable pour déterminer la taille de votre disque externe !
{.is-info}

- Pour cela, ouvrez l'outil "Analyseur d'utilisation des disques" :

![](/images/dejadup-prep-01.jpg){.align-center}

> Ce qui nous intéresse, dans la majorité des cas sur un PC personnel, c'est de sauvegarder les données présentes dans notre dossier personnel (profil utilisateur) sous `/home`
{.is-info}

- Cliquez sur "/home/`votre-pseudo`" afin d'analyser son contenu :

![](/images/dejadup-prep-02.jpg){.align-center}

- Les sous-dossiers de votre profil utilisateur s'affichent triés par taille, par exemple :

![](/images/dejadup-prep-03.jpg){.align-center}

Dans notre exemple, nous décidons de sauvegarder tout notre dossier `/home` **mais d'exclure les dossiers suivants** :
- `~/.local/share/Trash` = 0,002 Go : **C'est la corbeille**, pas besoin de sauvegarder ce qui a été supprimé. De toute façon, si cela a été mis à la corbeille, vous le retrouverez dans un jeu de sauvegarde précédent.
- `~/.cache` = 0,240 Go : C'est le cache des logiciels, éphémère, inutile de garder cela.
- `~/Téléchargements` 5,3 Go : C'est un choix personnel, nous considérons que ce qui est téléchargé et non *rangé* peut être facilement retrouvé sur Internet !
- `~/Vidéos` 0,966 Go : Comme dans le cas précédent, ce sont des vidéos provenant d'Internet dans notre cas. Cependant attention, si vous faites du montage vidéo, il peut être quand même intéressant de ne pas l'exclure !
- `~/Musique` 5,2 Go : Même choix que pour les vidéos !
- `~/VirtualBoxVMs` 67,5 Go : Ce sont des machines virtuelles (VMs) VirtualBox, nous n'avons pas besoin de les sauvegarder.
- `~/.var/app` = 0,538 Go : Les logiciels installés via Flatpak
- `~/Apps` 0,632 Go : Il s'agit d'un dossier personnel (logiciels de type AppImage ici).

> **Ceci n'est qu'un exemple** : à vous d'adapter suivant votre situation personnelle !
{.is-warning}

- Prenez la taille totale affichée tout en haut, dans notre cas 131 Go.
- Retranchez ce que vous avez décidé d'exclure. Ce qui nous donne : 131 - ( 0,002 + 0,240 + 5,3 + 0,966 + 5,2 + 67,5 + 0,538 + 0,632 ) = **50,622 Go**

> Nous avons donc 50,6 Go à sauvegarder
> :arrow_right: un disque externe de 256 Go sera suffisant dans notre cas.
{.is-success}

#### Préparer son support de sauvegarde

> Vous pensiez ne pas avoir de serveur chez vous ? En fait, les Box sont des serveurs ;)
{.is-info}

Les box sont capables de faire office de routeur, switch, pare-feu mais aussi serveur DHCP, DNS, impression **et fichiers** !

Pour l'exemple, nous allons utiliser une LiveBox 3 (version Play). Celle-ci étant plutôt ancienne, vous verrez un cas d'usage intéressant car elle ne supporte que la version 1 du protocole CIFS (SMB).

> Concurrent de NFS, le protocole CIFS est un protocole de partage de fichiers sur le réseau créé par IBM. Microsoft l'a implémenté sous le nom de SMB.
*Connecter un disque réseau* sous Windows revient à utiliser SMB (et par extension CIFS).
{.is-info}

Pour être reconnu par la plupart des box, nous allons formater le disque externe avec le système de fichier FAT32.

- Branchez votre clef USB ou disque externe sur votre PC

> **Veuillez à sauvegarder tout d'abord l'intégralité des données** présentes sur votre clef USB ou disque externe car nous allons formater et donc effacer celles-ci !
{.is-warning}

- Lancez l'outil `Disques` de GNOME :

![](/images/dejadup-prep-11.jpg){.align-center}

- Sur la partie gauche, sélectionnez **votre disque externe** en le repérant grâce à sa taille ;
- Cliquez sur le menu en haut à droite (les 3 points) et sélectionnez "Formater le disque" :

> **Attention de bien choisir votre disque externe** et pas votre disque dur interne installé dans votre PC !
{.is-danger}

![](/images/dejadup-prep-12.jpg){.align-center}

- Sélectionnez "Ne pas écraser les données existantes..." et "Compatible avec tous les périphériques (MBR/DOS) ;
- Cliquez sur "Formater...", un message d'avertissement se lance pour vous permettre de vous assurer que vous ne faites pas une bêtise : vérifiez donc les informations, et si elles sont correctes, confirmez de nouveau par "Formater".

> **Attention d'être sûr de formater votre disque _externe_ !**
> La communauté Wikilibriste ne peut être tenue responsable en cas de perte de vos données, merci de toujours lire nos [avertissements](/avertissement) !
{.is-danger}

- Saisissez votre mot de passe, si nécessaire :

![](/images/dejadup-prep-13.jpg){.align-center}

- Pour créer une nouvelle partition, cliquez sur le bouton **+** :

![](/images/dejadup-prep-14.jpg){.align-center}

- Assignez le maximum de l'espace disque puis cliquez sur Suivant :

![](/images/dejadup-prep-15.jpg){.align-center}

- Entrez le nom de volume : `BACKUP` ;
- Si vous cochez "Effacer", cela risque de prendre pas mal de temps : à vous de décider si vous souhaitez utiliser cette option ;
- Sélectionnez "Compatible avec tous les systèmes et périphériques (FAT)" ;
- Cliquez sur "Créer" :

> Il est possible que votre mot de passe vous soit re-demandé.
{.is-info}

![](/images/dejadup-prep-16.jpg){.align-center}

- Une fois le formatage terminé, fermez l'outil Disques et lancez votre explorateur de fichiers. Dans l'explorateur, le disque devrait normalement s'afficher.
- Créez un dossier `backups` à sa racine (nous l'utiliserons plus tard) :

![](/images/dejadup-prep-17.jpg){.align-center}

- Éjectez le disque en cliquant sur le bouton "Éteindre ce disque" ou via un clic-droit puis "Démonter" suivant votre système :

![](/images/dejadup-prep-18.jpg){.align-center}

- Enfin débranchez-le de votre PC.

#### Montage permanent du support externe

Nous allons ici effectuer un montage permanent du support externe sur votre machine via le réseau.

- Branchez votre clef ou disque externe sur un des ports USB (si possible USB3) _de votre Box internet_ ;

- Retournez sur votre PC et lancez la commande suivante afin de découvrir les périphériques de stockage branchés sur votre Box :

```bash
smbclient -L //192.168.1.1
```

> Ici, `192.168.1.1` est l'adresse IP correspondant à votre Box.
{.is-info}

> Si ce message apparaît, alors c'est sûrement lié au fait que votre box ne gère que la version 1 de SMB !
> ```brainfuck
> protocol negotiation failed: NT_STATUS_CONNECTION_DISCONNECTED
> ```
> Dans ce cas, lancez plutôt cette commande :
> ```bash
> smbclient -L //192.168.1.1 --option='client min protocol=NT1'
> ```
{.is-warning}

- Le mot de passe vous sera demandé : comme il n'y en a pas la plupart du temps, appuyez juste sur la touche <kbd>ENTRÉE</kbd> :
```brainfuck
Password for [WORKGROUP\username]:
```

- Voici un exemple de sortie écran, nous découvrons notre disque externe `BACKUP` listé :
```brainfuck
	Sharename       Type      Comment
	---------       ----      -------
	BACKUP         Disk      Additional storage
	IPC$            IPC       IPC Service (Livebox)
Reconnecting with SMB1 for workgroup listing.

	Server               Comment
	---------            -------
	LIVEBOX              Livebox

	Workgroup            Master
	---------            -------
	WORKGROUP            LIVEBOX
```

Un second exemple de sortie écran, cette fois-ci sans SMB1 :
```brainfuck
	Sharename       Type      Comment
	---------       ----      -------
	BACKUP          Disk      AutoShare of fbxhdiskd partition 1001
	IPC$            IPC       IPC share
SMB1 disabled -- no workgroup available
```

- Nous allons créer, sur notre PC, un dossier pour monter le disque qui est maintenant branché sur la box :

```bash
sudo mkdir /media/box
```

- Afin de tester que le montage fonctionne, nous lançons cette commande :

```bash
sudo mount -t cifs //192.168.1.1/backup /media/box -o guest -o vers=1.0
```

> ~~ `mount` est la commande Linux qui s'occupe de connecter (monter) un disque qu'il soit local ou réseau ;
> ~~ `-t cifs` est un paramètre qui définit le type de montage, ici CIFS (Samba / SMB) ;
> ~~ `//192.168.1.1/backup` est le chemin réseau pour arriver sur le disque USB branché sur la box ;
> ~~ `/media/box` est le répertoire de votre PC où l'on va monter le disque réseau ;
> ~~ `-o guest` permet de se connecter sans mot de passe, c'est le cas sur la plupart des box.
> Si votre Box est récente, elle prend en charge SMB v2 ou v3 : vous pouvez vous passer de ce paramètre `-o vers=1.0` et le retirer.
{.is-info}

- Nous allons lister le contenu :

```bash
ll /media/box/
```

- Il devrait contenir le dossier que nous avions créé précédemment :
```brainfuck
total 3
drwxrwxrwx 7 root root    0 janv.  1  1601  ./
drwxr-xr-x 4 root root 4096 mars  26 15:27  ../
drwxr-xr-x 4 root root 4096 mars  26 15:35  backups
```

- Maintenant que notre test est terminé, nous allons démonter le disque :

```bash
sudo umount /media/box
```

- Afin de le monter en permanence, nous allons modifier le fichier `fstab` :
```bash
sudo nano /etc/fstab
```

> Le fichier fstab contient la configuration des disques montés au démarrage de notre machine.
> Soyez vigilant lorsque vous le modifiez et **ne retirez ou commentez aucune ligne** !
> {.is-danger}

- Tout en bas du fichier, ajoutez les lignes suivantes :
```brainfuck
# Montage Disque USB sur Box
//192.168.1.1/backup   /media/box  cifs    nofail,x-systemd.device-timeout=1ms,iocharset=utf8,guest,vers=1.0   0   0
```

> -- la première ligne commence par un `#`, il s'agit uniquement d'un commentaire pour vous y retrouver ;
> -- `nofail` et `x-systemd.device-timeout=1ms` permettront de ne pas bloquer le démarrage de votre PC si le partage réseau n'existe pas (clef ou disque USB débranché ou HS) ;
> -- `iocharset=utf8` permet d'utiliser des caractères accentués dans les noms de fichiers ;
> -- `guest` est utile lorsqu'aucun mot de passe n'est défini pour le partage (c'est le cas avec la plupart des box, même si vous pouvez vous même paramétrer cet aspect) ;
> -- Si votre Box prend en charge SMB v2 ou v3, vous pouvez vous passer de ce paramètre `vers=1.0`
{.is-info}

- Lancez simplement cette commande afin de monter le disque réseau ! 

```bash
sudo mount -a
```

- Dans votre explorateur de fichiers, vous allez voir un partage réseau "box". Ouvrez-le :)

> Vous devriez voir à sa racine, le dossier `backups` que nous avions crée : nous l'utiliserons plus tard pour y stocker nos sauvegardes. ;)
{.is-success}

![](/images/dejadup-prep-19.jpg){.align-center}

### Installer Déjà Dup

- Lancez cette commande pour installer Déjà Dup :
```bash
sudo apt install deja-dup
```

> Comme `deja-dup` s'appuie sur `duplicity` pour réaliser les sauvegardes, celui-ci sera également installé automatiquement. 
{.is-info}

### Configurer les sauvegardes

Il existe _deux approches_ pour la configuration de la sauvegarde de vos données personnelles stockées sous "/home/`votre-pseudo`" :

- [ ] **On ne sauvegarde que les sous-dossiers qui nous intéressent dans notre dossier personnel**, dans la plupart des cas, a minima : `~/Bureau`, `~/Documents` *et éventuellement : `~/Images`, `~/Musique`, `~/Téléchargements`, `~/Vidéos`,...*

> L'avantage, c'est que l'on réduit considérablement le volume des sauvegardes.
{.is-success}

> Les inconvénients, c'est que :
> -- d'une part, les paramètres et données des applications ne seront pas sauvegardés car ils sont stockés dans des dossiers cachés commençant par un **.**, par exemple `~/.configs`, `~/.local`, `~/.nom-appli`,  ...
> -- et d'autre part, si plus tard nous créons de nouveaux fichiers à la racine de notre dossier personnel ou des sous-dossiers, par exemple `~/Apps`, ils ne seront pas sauvegardés !
{.is-danger}

- [x] **On sauvegarde tout le contenu du dossier personnel, puis on configure des exclusions ensuite**, afin de ne pas sauvegarder certains dossiers inutiles ou non souhaités.

> L'avantage, c'est que l'on est sûr de tout sauvegarder et que nous n'aurons pas à penser à revoir ce paramétrage dans le futur !
{.is-success}

> Les inconvénients, c'est que :
> -- on utilisera plus d'espace disque sur le support externe ;
> -- il va vous falloir déterminer les sous-dossiers à exclure !
{.is-danger}

> Nous recommandons plutôt cette deuxième approche pour les débutants !
> :arrow_right: **_C'est ce que nous allons vous présenter tout de suite._**
{.is-info}


- Lancez Déjà Dup et cliquez en haut à droite sur l'icône menu <span class="mdi mdi-menu"></span>
- Cliquez sur "Préférences" :

![](/images/dejadup-config-01.jpg){.align-center}

- La première chose à faire est de configurer les dossiers à sauvegarder : cliquez sur "Folders " :

![](/images/dejadup-config-02.jpg){.align-center}

- *Par défaut, votre dossier personnel est déjà inclus.*
- Dans "Dossiers à ignorer", cliquez sur le bouton **+** pour **spécifier les dossiers à ne pas sauvegarder** :

![](/images/dejadup-config-03.jpg){.align-center}

- Par défaut, les dossiers cachés (ceux qui commencent par un **.**) ne sont pas affichés ; faites un clic-droit puis cochez "Afficher les fichiers cachés" :

![](/images/dejadup-config-04.jpg){.align-center}

- Sélectionnez le dossier `~/.cache/` et cliquez sur "Ajouter" :

![](/images/dejadup-config-05.jpg){.align-center}

- Répétez l'opération pour chacun des dossiers que vous souhaitez exclure des futures sauvegardes. Un fois terminé, cliquez sur le menu "General" :

> Vous devriez déjà avoir une idée des dossiers à exclure grâce au chapitre "Déterminer le volume de mes données" ;)
{.is-info}

![](/images/dejadup-config-06.jpg){.align-center}

- Dans le menu "General", sélectionnez tout d'abord la destination des sauvegardes en cliquant sur "Emplacement" :

![](/images/dejadup-config-07.jpg){.align-center}

- Dans "Emplacement de stockage", sélectionnez "Dossier local", puis cliquez sur "Choisir un dossier" :

![](/images/dejadup-config-08.jpg){.align-center}

- Cliquez sur "Autres emplacements" pour afficher plus de dossiers :

![](/images/dejadup-config-09.jpg){.align-center}

- Sélectionnez votre montage réseau "box" dans `/media/box` :

![](/images/dejadup-config-10.jpg){.align-center}

- Sélectionnez ensuite le dossier "backups" et cliquez sur "OK" :

![](/images/dejadup-config-11.jpg){.align-center}

- De retour dans le menu "General", selectionnez :
  - La durée de rétention dans "Conserver les sauvegardes", par exemple "Au moins six mois" ;
  - Activez "Sauvegarder automatiquement"  et choisissez la "Fréquence des sauvegardes automatiques", par exemple "Tous les jours".
<br>
- Fermez la fenêtre pour sauvegarder vos paramétrages :

![](/images/dejadup-config-12.jpg){.align-center}

### Première sauvegarde

- Cliquez sur "Créer ma première sauvegarde" :

![](/images/dejadup-backup-01.jpg){.align-center}

- Déja Dup reprend les paramètres par défaut, cliquez sur "Suivant" :

![](/images/dejadup-backup-02.jpg){.align-center}

- Ici encore, cliquez sur "Suivant" :

![](/images/dejadup-backup-03.jpg){.align-center}

- Cochez "Protéger votre sauvegarde par un mot de passe" ;
- Cochez "Se souvenir du mot de passe" ;
- Entrez votre mot de passe de chiffrement pour les fichiers de sauvegarde, à l'identique, dans chacune des cases puis cliquez sur "Suivant" :

> Il est fortement recommandé :
> -- de le stocker dans un gestionnaire de mots de passe,
> -- de choisir un mot de passe fort,
> -- de choisir un mot de passe différent de vos autres comptes !
> **:arrow_right: Consultez l'article lié aux [mots de passe](/debutant/gestionnaire-mots-passe) pour plus d'informations.**
{.is-warning}

![](/images/dejadup-backup-04.jpg){.align-center}

- Sauvegarde en cours ...

> Soyez patient c'est la première sauvegarde et elle peut durer plusieurs heures !
{.is-info}


![](/images/dejadup-backup-05.jpg){.align-center}

- Une fois la sauvegarde terminée, vous pouvez fermer l'application :

> Déja Dup s'occupera automatiquement des prochaines sauvegardes en tâche de fond :)
{.is-success}

![](/images/dejadup-backup-06.jpg){.align-center}

- Pour les plus curieux, vous pouvez naviguer via le réseau et contempler dans `/media/box/backups` les fichiers chiffrés GPG de vos sauvegardes :

![](/images/dejadup-backup-07.jpg){.align-center}

### Restaurer un ou plusieurs fichiers

- Lancez Déjà Dup et cliquez sur le menu "Restaurer" :

![](/images/dejadup-restore-01.jpg){.align-center}

- En bas à droite, sélectionnez la date à laquelle vous souhaitez restaurer vos données :

![](/images/dejadup-restore-02.jpg){.align-center}

- Naviguez dans les dossiers jusqu'au(x) fichier(s) à restaurer :

> Vous pouvez aussi utiliser l'icône "loupe" pour faire une recherche.
{.is-info}

![](/images/dejadup-restore-03.jpg){.align-center}

- Sélectionnez le fichier à restaurer puis cliquez sur "Restaurer" :

> Vous pouvez aussi en sélectionner plusieurs en maintenant la touche <kbd>CTRL</kbd> lors des clics.
{.is-info}

![](/images/dejadup-restore-04.jpg){.align-center}

- Vous avez alors deux cas de figure possibles :
1. Le (ou les) fichier(s) à restaurer a (ont) été détruit(s) _ou_ vous n'en avez plus besoin dans leur version actuelle :
:arrow_right: Choisissez alors "Restaurer les fichiers vers leurs emplacements d'origines" puis cliquez sur "Restaurer".

2. Vous n'êtes pas sûr de ce que vous faites _ou_ que le (les) fichier(s) existe(nt) encore et vous souhaitez juste restaurer une ancienne version :
:arrow_right: Choisissez plutôt "Restaurer vers un dossier spécifique" et choisissez le dossier de destination puis cliquez sur "Restaurer".

![](/images/dejadup-restore-05.jpg){.align-center}

- Restauration en cours ...

![](/images/dejadup-restore-06.jpg){.align-center}

- Restauration terminée, cliquez sur "Fermer".

![](/images/dejadup-restore-07.jpg){.align-center}

### Récupérer des données

Nous décrivons ici comment récupérer des données après un crash de votre système.

> Il peut arriver ce que l'on appelle un "désastre", c'est-à-dire que le système d'exploitation (Linux) ou que le disque dur interne de votre machine soit HS/en panne :collision:
{.is-info}

Heureusement, vous avez vos sauvegardes et elles sont externalisées, c'est-à-dire stockées en dehors de votre machine, n'est-ce pas ! :)

Si vous êtes dans cette situation, cela va vous prendre du temps mais au moins vous allez pouvoir :
- réparer votre ordinateur en remplaçant le disque et en réinstallant votre distro Linux favorite ;

> Si vous aviez mis en place des sauvegardes système avec `Timeshift`, c'est le moment de les utiliser !
{.is-success}

- restaurer vos données.

Pour restaurer vos données, dès que votre distro est réinstallée, procédez comme suit :

- installez Déjà Dup :
```bash
sudo apt install deja-dup
```

- **Débranchez de votre Box votre clef ou disque USB contenant vos sauvegardes et branchez-le _sur votre machine_** ;

- Ouvrez Déjà Dup puis cliquez "Restaurer à partir d'une sauvegarde précédente" :

![](/images/dejadup-recover-01.jpg){.align-center}

- Cliquez sur "Choisir un dossier" :

![](/images/dejadup-recover-02.jpg){.align-center}

- Naviguez jusqu’à votre disque où se trouvent vos sauvegardes puis cliquez sur "OK" :

![](/images/dejadup-recover-03.jpg){.align-center}

- Cliquez sur "Rechercher" :

![](/images/dejadup-recover-04.jpg){.align-center}

- Vos jeux de sauvegarde sont chiffrés, n'est ce pas ;) , cliquez sur "Saisir le mot de passe" :

![](/images/dejadup-recover-05.jpg){.align-center}

- Cochez "Se souvenir du mot de passe" puis entrez votre mot de passe de déchiffrement et cliquez sur "Continuer" :

![](/images/dejadup-recover-06.jpg){.align-center}

- Choisissez la date de sauvegarde en bas à droite (logiquement la plus récente) :

![](/images/dejadup-recover-07.jpg){.align-center}

- Sélectionnez ensuite les dossiers que vous souhaitez restaurer (en général tous) puis cliquez sur "Restaurer" :

![](/images/dejadup-recover-08.jpg){.align-center}

Deux stratégies possibles :
- Soit vous venez de réinstaller la même distribution Linux qu'avant le "crash" : dans ce cas, sélectionnez "Restaurer les fichiers vers leurs emplacements d'origines" ;
- Soit vous avez installé une autre distro _OU_ vous savez ce que vous faites :
  - Sélectionnez "Restaurer vers un dossier spécifique" :
  - Créez un dossier `/home/<votre-user>/restore` dans votre dossier personnel puis dans la liste déroulante, choisissez-le pour y restaurer les données. **Dans ce cas, il vous faudra ensuite déplacer vos données manuellement vers leur emplacement d'origine.**
</br>
- Enfin, cliquez sur "Restaurer" pour démarrer la récupération.

![](/images/dejadup-recover-09.jpg){.align-center}

- La restauration est en cours ...

![](/images/dejadup-recover-10.jpg){.align-center}

- C'est terminé, cliquez sur "Fermer" :

![](/images/dejadup-recover-11.jpg){.align-center}

> Vos données sont maintenant récupérées. :)
{.is-success}

> Il vous faudra, pour terminer, débrancher votre disque externe de votre machine et le re-connecter à la box.
> Puis ensuite, suivre de nouveau les chapitres "Montage permanent du support externe sur votre machine via le réseau" et "Configurer les sauvegardes" pour configurer de nouveau son accès via le réseau.
{.is-info}


# Sauvegarder un système complet

> Ce type d'outil n'est pas vraiment destiné à sauvegarder des données personnelles, même si cela est possible.
> **Le but étant plutôt de sauvegarder un système complet afin de pouvoir le restaurer en cas de fausse manipulation ou de sinistre.**
{.is-info}

La mise en place de ce genre de solution vous permettra, par exemple, de revenir à un état antérieur fonctionnel de votre OS.

> Pour la sauvegarde d'un système complet, `Timeshift` est la solution que nous recommandons et détaillerons dans la suite de ce chapitre. 
> Nous l'utiliserons en combinaison avec `Déjà Dup`, qui lui, s'occupera de sauvegarder les données personnelles. Timeshift sauvegardera tout le reste.
{.is-success}

## Timeshift

> Attention, pour être efficace, ce genre de solution nécessitera de tout sauvegarder, sauf les dossiers `/home` et `/root`.
> Suivant la fréquence des instantanés ("snapshots" en anglais), cela peut vite être très "gourmand" en terme de volume utilisé et saturer votre disque de destination !
{.is-warning}

### Installation

- Pour installer `timeshift`, c'est très simple :
```bash
sudo apt install timeshift
```
### Configuration

- Lancez Timeshift, votre mot de passe vous sera demandé pour surélever les droits.

> Cela est nécessaire pour pouvoir accéder à toute l'arborescence `/` du disque !
{.is-info}

- Cliquez sur le bouton "Paramètres" :

![](/images/timeshift-config-01.jpg){.align-center}

- Dans l'onglet Type, sélectionnez "RSYNC" :

![](/images/timeshift-config-02.jpg){.align-center}

- Dans l'onglet Emplacement, sélectionnez le disque où placer les sauvegardes snapshots :

> **Si vous avez un 2ème disque dur dans votre machine, c'est le moment de le mettre à contribution**. :)
> Sinon, sélectionnez une partition avec assez d'espace disque, par exemple votre `/home`
{.is-success}

![](/images/timeshift-config-03.jpg){.align-center}

- Dans l'onglet Planning, choisissez la fréquence des Snapshots :

> Attention, plus vous ajouterez des instantanés (snapshots), plus vous utiliserez d'espace disque !
> À vous de choisir le paramétrage idéal, suivant l'espace disque disponible.
{.is-warning}

![](/images/timeshift-config-04.jpg){.align-center}

- Dans l'onglet Utilisateurs, laissez par défaut :

> Les dossiers `/home` et `/root` seront exclus des snapshots.
{.is-info}

![](/images/timeshift-config-05.jpg){.align-center}

- Dans l'onglet Filtres, laissez par défaut :

![](/images/timeshift-config-06.jpg){.align-center}

- Dans l'onglet Divers, laissez par défaut.
- Cliquez sur "Valider" pour enregistrer :

![](/images/timeshift-config-07.jpg){.align-center}

### Sauvegarde

- Pour lancer votre première sauvegarde complète, cliquez sur "Créer" :

![](/images/timeshift-backup-01.jpg){.align-center}

- Estimation en cours ...

![](/images/timeshift-backup-02.jpg){.align-center}

- Sauvegarde en cours ...

> Soyez patient : cela peut prendre quelques minutes à plusieurs heures, suivant votre système et la puissance de votre machine !
{.is-warning}

![](/images/timeshift-backup-03.jpg){.align-center}

- Le premier snapshot est terminé, les suivants s'exécuteront bientôt, suivant votre planification puis seront affichés dans cette fenêtre principale :

![](/images/timeshift-backup-04.jpg){.align-center}

### Restauration

Pour restaurer, deux cas de figure :

1. Le système est encore utilisable : dans ce cas, c'est très simple. Lancez Timeshift, entrez votre mot de passe et sélectionnez l'instantané à restaurer, enfin cliquez sur "Restaurer" et validez :

> Redémarrez après la restauration.
{.is-info}

> -- **ne restaurez pas** `/home` à l'aide de Timeshift. **Utilisez ultérieurement votre sauvegarde `Déjà-Dup` !**
> -- puisque votre système démarre correctement, **ne restaurez pas non plus** `/boot` et `/boot/efi` !
{.is-warning}

![](/images/timeshift-restore-01.jpg){.align-center}

2. Le système ne démarre plus :collision: ; dans ce cas, il vous faudra :
- créer une clef USB bootable de votre distro,
- démarrer votre machine sur cette clef USB en utilisant la fonction Live USB,
- installer Timeshift sur le système tournant sur cette clef USB (en mode Live USB),
- restaurer votre système grâce à votre sauvegarde Timeshift, éteindre le PC, débrancher la clef et re-démarrer le PC.

> -- **ne restaurez pas** `/home` à l'aide de Timeshift. **Utilisez ultérieurement votre sauvegarde `Déjà-Dup` !**
> -- restaurez `/boot` et `/boot/efi` ainsi que la racine `/` (et d'autres éventuelles partitions, suivant votre configuration).
> ![](/images/timeshift-restore-02.jpg){.align-center}
{.is-warning}


# Sauvegarder des données sur serveur

> Ce genre d'outils ne s'adresse pas aux débutants mais plutôt aux utilisateurs confirmés.
{.is-warning}

Comme nous l'avons vu en introduction, la variante client/serveur consiste à installer un outil de sauvegarde sur une machine dédiée, par exemple un serveur. Additionnellement, un agent sera installé, la plupart du temps, sur les machines clientes à sauvegarder en passant par le réseau.

Cette approche est intéressante pour les raisons suivantes :
- Les sauvegardes sont centralisées ;
- On peut sauvegarder la totalité d'un système et le restaurer rapidement ;
- On économise de la place sur le volume total de machines à sauvegarder ;
- On peut sauvegarder plusieurs machines, quel que soit l'OS ;
- Ces outils proposent plus de fonctionnalités.

Nous n'entrerons pas dans le détail de leur mise en place, mais voici quelques solutions libres ou open-source :

- [Amanda](https://www.amanda.org/) : Similaire à Bacula et BareOS.
- [Bacula](https://www.bacula.org/) : Quasiment identique à BareOS.
- [BareOS](https://docs.bareos.org/IntroductionAndTutorial/WhatIsBareos.html) : BareOS (Backup Archiving Recovery Open Sourced) est un fork de Bacula. Il est capable de sauvegarder des appareils sous Linux, BSD, Solaris, MacOS et Windows !
- [BackupPC](https://backuppc.github.io/backuppc/) : Même si la dernière version date de 2020, c'est un excellent outil qui a pour principal intérêt d'être administrable via une interface web PHP. Aussi, il supporte la sauvegarde des machines sous Linux, BSD, MacOS et Windows !
- [Proxmox Backup Server](https://www.proxmox.com/en/proxmox-backup-server) : PBS est à recommander dans le cas où vous utilisez l'excellente solution de virtualisation PVE (ProxMox Virtualization Environment).
- [UrBackup](https://www.urbackup.org/) : sauvegardes complètes et incrémentielles de partitions entières et de répertoires. Il supporte la déduplication et les clients sous Linux, Windows et FreeBSD. L'interface d'administration est de type web.

# Conclusion

Vous êtes maintenant capable de mettre en place sur vos appareils une solution de sauvegarde qui convient à votre utilisation.

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): marmotte, DyanZan*