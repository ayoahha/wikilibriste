---
title: Installer VirtualBox et des VM
description: Installation de VM sous Virtualbox
published: true
date: 2023-07-17T14:31:26.950Z
tags: 
editor: markdown
dateCreated: 2023-03-13T23:07:03.586Z
---

![virtualbox.png](/images/virtualbox.png =200x){.align-center}

[**Oracle VM VirtualBox**](https://www.virtualbox.org/), plus communément appelé **VirtualBox** est un logiciel open-source permettant d'installer virtuellement un ou plusieurs autres sous-systèmes d'exploitation comme s'ils étaient installés sur le disque physique de l'ordinateur. Nous parlerons donc ici de VM ou "Virtual Machine" (machine virtuelle).

> *Pour plus de détails et explications sur le concept de la virtualisation, nous vous renvoyons vers l'article dédié à la [Virtualisation](/intermediaire/virtualisation).*
{.is-info}

 # Introduction
 
**VirtualBox** se compose en trois parties :
 - Le package de base **VirtualBox** qui est libre sous licence GNU GPL v2 ;
 - Les Additions Invité (**Guest Additions**) également sous licence GNU GPL v2 ;
 - Le pack d'extensions (**Oracle VM VirtualBox Extension Pack**) qui n'est qu'un module sous licence propriétaire [**P.U.E.L**](https://www.virtualbox.org/wiki/VirtualBox_PUEL) permettant de profiter de fonctionnalités, telle que la prise en charge de l'USB2/3. Cette fonctionnalité est passée sous licence libre à partir des versions **7.x** et est donc installée nativement. L'installation de ce pack présente désormais moins d'intérêt, c'est la raison pour laquelle nous n'en parlerons pas dans ce tutoriel.

# Présentation  

> Dans le présent article, nous parlerons de **"système hôte"** et **"système invité"** ; le système hôte correspond au système principal, tandis que le système invité est le système d'exploitation installé dans VirtualBox, virtualisé donc. 
{.is-info}

- Notre système hôte sera une **Debian 11**, nom de code **Bullseye**.
- Nous installerons en premier lieu **VirtualBox 7.0** sur cette Debian 11.
- Nous installerons ensuite une **ISO** de **Debian** avec l'environnement de bureau **(DE)** [**Gnome**](/debutant/linux-distributions#gnome) en tant que système **invité** :
	- [x] en mode automatique (une fois les renseignements demandés, l'installation se déroule sans être obligé de rester devant l'ordinateur),
  - [x] en mode manuel (pour vous montrer une seconde méthode).

# Pré-requis  

- Vous l'aurez compris, avoir un ordinateur ;-) [(Liste des OS hôtes supportés)](https://www.virtualbox.org/manual/ch01.html#hostossupport) ;
- Avoir téléchargé préalablement l'ISO du système d'exploitation que vous voulez installer dans votre VM, voir l'article sur [les distributions Linux](/debutant/linux-distributions)  pour vous aider à faire votre choix ;
- S'assurer que votre processeur supporte la virtualisation, ce qui est le cas sur les ordinateurs depuis environ 2010 mais cette fonction est peut être désactivée dans votre **BIOS**. Il est donc intéressant de rentrer dans votre BIOS, grâce à l'article [Configurer son BIOS](/tutoriels/bios-boot). Vérifiez ensuite que les paramètres de virtualisation sont activés, pour cela : 
> Recherchez dans le **BIOS** les termes "**VT-x**" pour **Intel** ; "**AMD-V**" ou "**SVM**" pour **AMD**. Si ces termes sont présents mais que leurs valeurs sont "**disabled**", activez-les en les passant à "**enabled"**.
>
> Une fois terminé, avant de quitter, n'oubliez pas de sauvegarder la configuration du BIOS (Dans le menu "Exit" ou "Save & Exit").
{.is-info}

- Enfin, il est recommandé de mettre à jour votre système hôte afin d'avoir les dernières versions du kernel et autres paquets système installés. Pour cela, lancez cette commande :
```bash
sudo apt update && sudo apt upgrade
```   

# Installation de VirtualBox

## Configuration des dépôts

> La dernière version de VirtualBox n'est pas dans les dépôts officiels de Debian, nous allons donc utiliser quelques lignes de commandes pour ajouter les liens vers les dépôts Oracle de VirtualBox avant son installation. Vous aurez ainsi la dernière version installée.
{.is-warning}

Pas de panique, rien de bien compliqué ;-), allons-y !

- Ajoutez la clé de signature du dépôt d'Oracle (dépôt officiel) :
```bash
wget -O- https://www.virtualbox.org/download/oracle_vbox_2016.asc | sudo gpg --dearmor --yes --output /usr/share/keyrings/oracle-virtualbox-2016.gpg
```

- Pour un système hôte sous Debian, ajoutez un fichier pour que votre gestionnaire de paquet puisse aller lire le dépôt d'Oracle :
```bash
echo "deb [signed-by=/usr/share/keyrings/oracle-virtualbox-2016.gpg] http://download.virtualbox.org/virtualbox/debian $(lsb_release -sc) contrib" | sudo tee /etc/apt/sources.list.d/virtualbox.list
```

> Si votre **système hôte est de type Ubuntu ou dérivé** (Mint, ...), lancez plutôt cette commande : 
> `source /etc/os-release && echo "deb [arch=amd64 signed-by=/usr/share/keyrings/oracle-virtualbox-2016.gpg] http://download.virtualbox.org/virtualbox/debian $UBUNTU_CODENAME contrib" | sudo tee /etc/apt/sources.list.d/virtualbox.list`
{.is-info}

- Pour prendre en compte la nouvelle adresse du dépôt ajoutée, rafraîchissez la liste des paquets de votre système :
```bash
sudo apt update
```

> Petit rappel, sur certaines distributions Linux, dans un terminal, lorsque vous tapez votre mot de passe, rien ne se passe à l'écran mais chaque appui de touche est pris en compte.
{.is-warning}

## Installons VirtualBox 7.0

- Lancez cette commande pour installer VirtualBox et tous les paquets nécessaires :
```bash
sudo apt install virtualbox-7.0
```

> VirtualBox 7 est, au moment de la rédaction de cet article, la dernière version qui apporte des fonctionnalités natives et open-source par rapport à la version précédente où il fallait installer un **pack d'extensions** qui n'était pas open source. 
> Il s'agit de la prise en compte de l'**USB 2 et l'USB 3**, de l'utilisation de webcam, de la possibilité de chiffrer totalement une machine virtuelle (uniquement en mode console pour l'instant).

> **Félicitations, vous venez d'installer la dernière version de VirtualBox !**
{.is-success}

# Ajoutons une VM

Voici l'interface épurée de VirtualBox lors de l'ouverture de celui-ci :

![capture_d’écran_2023-03-14_21-46-11.png](/images/capture_d’écran_2023-03-14_21-46-11.png){.align-center}

# Tabs {.tabset}
## Ajout VM en mode automatisé

### Création de la VM

- Pour créer une nouvelle machine virtuelle, cliquez sur le bouton "Nouvelle" et remplissez les champs comme suit :

1. Nom : Donnez un nom à votre machine virtuelle, par exemple "Debian".

2. Folder : Laissez par défaut, c'est là que seront placés les fichiers de la nouvelle VM sur le disque dur de votre machine hôte.

3. ISO Image : Ouvrez cette liste déroulante et cliquez sur "Autre" afin de sélectionner l'image ISO que vous avez précédemment téléchargée dans le chapitre Pré-requis.

> L'édition, le type et la version seront automatiquement détectés : pas besoin d'y toucher.
{.is-info}

4. Laissez la case "Skip Unattended Installation" _décochée_ pour que VirtualBox installe lui-même votre distribution (sans que vous n'ayez à passer par l'installateur).

> Il utilisera d'ailleurs les paramètres par défaut et installera l'environnement de bureau par défaut de la distro (ici pour Debian, ce sera GNOME).
{.is-info}

> Attention, cette procédure automatisée peut ne pas fonctionner pour une grande partie des distributions Linux !
> **Si ça ne fonctionne pas, utilisez alternativement l'Ajout VM en mode manuel (onglet de la seconde méthode) !**
{.is-warning}

![](/images/virtualbox-guest-unattened-01.png){.align-center}

### Paramètres utilisateur 

5. Entrez un nom d'utilisateur, et votre mot de passe dans le cadre "Username and Password".

> Le compte par défaut est `vboxuser` et son mot de passe `changeme`.
> Il est fortement recommandé de les changer et :
> -- de le stocker dans un gestionnaire de mots de passe,
> -- de choisir un mot de passe fort,
> -- de choisir un mot de passe différent de vos autres comptes !
> **:arrow_right: Consultez l'article lié aux [mots de passe](/debutant/gestionnaire-mots-passe) pour plus d'informations.**
{.is-warning}

6. Dans le cadre "Additional options", entrez un nom d'hôte (en minuscule et sans espace ; ce nom sert à identifier la machine sur le réseau) et de domaine si besoin.

7. _Cochez_ ensuite la case "**Guest Additions**" (nous y reviendrons).

![](/images/virtualbox-guest-unattened-02.png){.align-center}

### Paramètres mémoire et processeur

La fenêtre suivante vous permet d'allouer la quantité de mémoire vive (RAM) à votre machine virtuelle.
Selon la distribution choisie, il sera nécessaire d'allouer plus ou moins de mémoire. Par exemple :
- une VM Debian avec un DE léger comme [**LXQt**](https://lxqt-project.org/) se contentera de 1 Go de RAM
- alors qu'une Debian avec un DE [**Gnome**](https://www.gnome.org/) nécessitera plutôt 2 à 3 Go.

Gardez à l'esprit, cependant, que plus vous allouez de mémoire à votre VM, moins votre système hôte en disposera.

**Pour notre exemple, pour plus de confort, nous accorderons à notre système invité 2 Go de RAM.**

Ensuite, indiquez le nombre de processeurs que vous voulez lui allouer, comme pour la RAM, tout dépend de votre configuration matérielle. Deux processeurs est un bon compromis.

> Quelle que soit votre configuration, ne dépassez **jamais** le barregraphe **<span style="color:green;">vert</span>** sous peine de plantage et lenteur de votre système.
> {.is-danger}

![](/images/virtualbox-guest-unattened-03.png){.align-center}

### Paramètres du disque virtuel

L'écran suivant vous demande de choisir la quantité d'espace disque que vous voulez allouer à votre VM :
- Pour une VM Windows, un minimum de 50 Go est requis.
- Pour une VM Debian, 20 Go peuvent suffire mais dans notre exemple nous indiquerons 30 Go.

![](/images/virtualbox-guest-unattened-04.png){.align-center}

### Installation VM

- Cliquez sur "Finish" pour démarrer l'installation de la VM

> Tout est automatique ; souvenez-vous, nous avons laissé la case d'installation manuelle décochée.
{.is-info}

![](/images/virtualbox-guest-unattened-05.png){.align-center}

- Comptez environ 30 minutes pour que l'installation se termine :

![](/images/virtualbox-guest-unattened-06.png){.align-center}

> A la fin de l'installation, le système invité redémarre.
> Vous devrez entrer votre compte et mot de passe (attention, le clavier est peut-être en anglais !).
> Vous arrivez ensuite sur le bureau de votre VM. 
{.is-success}

> Si vous avez besoin de changer le clavier, c'est dans le menu Paramètres GNOME / Pays et langue / Source de saisie / Bouton + / Ajouter le Français (variante) puis retirer Anglais (US) :)
{.is-info}


- Lorsque vous mettez la fenêtre en plein écran, un message d'avertissement vous indique que la VM va "capturer" le pointeur de la souris, c'est-à-dire qu'il n'est plus possible d'avoir accès à la machine hôte :

> Les raccourcis clavier indiqués dans le message vous permettent d'y avoir accès de nouveau, donc veillez à bien retenir ces touches ;) :
> <kbd>CTRL droite</kbd> permet de récupérer l'accès souris sur la machine hôte
> <kbd>CTRL DEBUT</kbd> permet d'afficher le menu qu'elle que soit le mode d'affichage
> <kbd>CTRL F</kbd> permet de passer en plein écran ou d'en sortir
{.is-info}

![capture_d’écran_2023-03-18_21-19-16.png](/images/capture_d’écran_2023-03-18_21-19-16.png){.align-center}

**L'installation est terminée, passons aux configurations...**

## Ajout VM en mode manuel (seconde méthode)

L'installation que nous avons vue précédemment en mode automatisé est idéale si les paramètres et la configuration par défaut vous conviennent.

En revanche, si vous souhaitez configurer cette VM via l'installateur classique (choix des composants, des DE, etc.), il est préférable de choisir le mode manuel : pas d'inquiétude, nous sommes là pour vous expliquer la démarche étape par étape.

**C'est parti !**

1. Comme précédemment, cliquez sur **Nouvelle**.   

2. Indiquez le nom de la machine virtuelle.

3. Laissez le dossier par défaut.

4. Indiquez dans quel dossier se trouve l'image ISO que vous voulez installer.

5. Le type de système d'exploitation doit être reconnu automatiquement : dans le cas contraire, indiquez-le.

6. Cochez la case **Skip Unattended Installation**.

![capture_d’écran_2023-03-18_22-45-31.png](/images/capture_d’écran_2023-03-18_22-45-31.png){.align-center}

7. Ouvrez **Hardware**.

8. Comme pour l'installation précédente, indiquez la quantité de mémoire et le nombre de processeurs que vous voulez allouer à votre VM.

![capture_d’écran_2023-03-18_23-05-08.png](/images/capture_d’écran_2023-03-18_23-05-08.png){.align-center}

9. Indiquez la quantité d'espace disque souhaitée pour votre VM.

> Si vous ne cochez pas la case **Pre allocate full size**, votre VM va commencer avec une taille d'environ 2 Go et augmenter selon les besoins de votre VM jusqu'à la valeur que vous avez définie, à savoir pour notre exemple 20 Go.
> Si vous cochez cette case, les 20 Go de notre exemple seront tout de suite "déduits" de votre disque dur physique.
{.is-info}

10. Cliquez sur **Finish** pour terminer la préparation de votre machine virtuelle.

![capture_d’écran_2023-03-18_23-06-36.png](/images/capture_d’écran_2023-03-18_23-06-36.png){.align-center}

11. Sélectionnez votre VM, cliquez sur **Démarrer**.

![capture_d’écran_2023-03-18_23-07-06.png](/images/capture_d’écran_2023-03-18_23-07-06.png){.align-center}

12. Votre machine démarre et l'installation de votre système débute, normalement comme si vous étiez sur une machine classique.

> Pour installer Debian, vous pouvez suivre le tutoriel [Installation de Debian](/tutoriels/debian).
{.is-info}

![capture_d’écran_2023-03-18_23-09-34.png](/images/capture_d’écran_2023-03-18_23-09-34.png){.align-center}  

**Une fois votre installation terminée, passez aux configurations...**

# Configuration

## Guest additions (Additions Invité)

Les **VirtualBox Guest Additions** sont des pilotes de périphériques adaptés à VirtualBox et à un environnement virtualisé. Ils sont nécessaires pour améliorer les performances globales de la VM, le réseau, le comportement, optimiser l'affichage, etc. 

Voici les paramètres qui nous intéressent plus particulièrement :
- L'affichage plein écran de sa **VM** et la possibilité de régler la résolution d'écran ;
- Le presse-papier partagé (copier-coller) dans les deux sens : ou hôte vers invité ou invité vers hôte ;
- Les dossiers partagés entre les deux systèmes.

### Installation des **Additions Invité**

> Si vous avez suivi le chapitre "Ajout VM en mode automatisé" alors les Guest additions (Additions Invité) sont déjà installés : vous pouvez donc passer au chapitre suivant "Dossiers partagés".
{.is-info}

On peut voir sur l'image suivante que si nous cliquons sur "**Mode plein écran**", la fenêtre ne prend pas tout l'écran :
![capture_d’écran_2023-03-19_23-35-27.png](/images/capture_d’écran_2023-03-19_23-35-27.png){.align-center}

Ceci est dû au driver graphique manquant, et peut être résolu grâce aux Additions Invité.

- Commencez par mettre à jour l'**OS** de votre machine invitée :

```bash
sudo apt update
sudo apt upgrade
```

S'il y a eu une mise à niveau du noyau (**kernel**), redémarrez votre **VM**.
- Il nous faut ajouter les paquets nécessaires à la modification du noyau :
 ```bash
sudo apt install dkms build-essential
```

> -- Si votre **VM est sous Ubuntu ou dérivé**, vous pouvez vous passer des étapes ci-dessous et simplement lancer cette commande dans votre VM : `sudo apt update &&  sudo apt install virtualbox-guest-x11`
> -- Si votre **VM est sous Debian**, vous pourrez aussi lancer les 2 commandes ci-dessus mais il faudra auparavant [ajouter un dépôt comme décrit dans le wiki de Debian](https://wiki.debian.org/VirtualBox#Debian_10_.22Buster.22_and_Debian_11_.22Bullseye.22-1).
{.is-info}

> :arrow_down: **Les instructions ci-dessous fonctionneront dans tous les cas et toutes les distros.**
{.is-success}

- Insérez l'image CD des Additions Invité en cliquant sur ***Périphériques*** :arrow_right: **Insérer l'image CD des Additions Invité**.

> **Ne lancez pas l'exécution automatique**.
{.is-warning}  
  
![capture_d’écran_2023-03-19_23-37-12.png](/images/capture_d’écran_2023-03-19_23-37-12.png){.align-center} 

- Pour installer les Additions Invité, lancez un terminal :
```bash
sudo sh /media/cdrom0/VBoxLinuxAdditions.run
```

> `/media/cdrom0` étant généralement le chemin vers votre CD-ROM virtuel.

- ou, plus simple, rendez vous dans votre explorateur de fichiers, cliquez sur votre lecteur CD-ROM (virtuel) qui contient les **Additions Invité...**  pour ouvrir son contenu :

![capture_d’écran_2023-03-20_00-39-10.png](/images/capture_d’écran_2023-03-20_00-39-10.png){.align-center}

- Faîtes un clic-droit et sélectionnez "**Ouvrir un terminal ici**" :

![capture_d’écran_2023-03-22_22-31-16.png](/images/capture_d’écran_2023-03-22_22-31-16.png){.align-center}  

- Exécutez la commande suivante qui lancera l'installation des **Additions Invité** :
```bash
sudo sh VBoxLinuxAdditions.run
```

- Redémarrez votre **VM** pour terminer l'installation :
```bash
sudo reboot
```

- Miracle ! Votre **VM** prend désormais tout votre écran et/ou vous pouvez régler la résolution selon votre goût et possibilité de votre machine/écran :

![plein_écran.png](/images/plein_écran.png){.align-center}

## Dossiers partagés

Pour profiter pleinement de votre **VM** et interagir avec votre machine hôte, nous allons voir comment partager un ou des dossiers et activer le copier-coller entre les 2 systèmes.

> Petit rappel : pour profiter de ces fonctionnalités, il faut préalablement avoir installé les **Additions Invité** comme nous l'avons vu précédemment.
{.is-warning}  

Pour notre exemple, nous avons créé un dossier sur le bureau de la machine hôte nommé "***Dossier partagé Virtualbox***" avec à l'intérieur une capture d'écran de la page d'accueil de notre excellent site ;-)  

- Sélectionnez votre machine virtuelle, cliquez sur ***Configuration*** puis sur l'onglet ***Dossiers Partagés*** :  

![dossier_partagé.png](/images/dossier_partagé.png){.align-center}  

- Cliquez sur le signe **+** à droite pour ajouter un dossier :  

![machine_hôte.png](/images/machine_hôte.png){.align-center}  

- Une fenêtre de configuration s'ouvre :  

![capture_d’écran_2023-04-05_22-05-25.png](/images/capture_d’écran_2023-04-05_22-05-25.png)
- **1** Indiquez le chemin où se trouve votre dossier partagé sur la machine hôte.
Pour connaître celui-ci simplement, ouvrez votre dossier et copiez l'adresse qui se trouve dans la barre d'adresse de votre explorateur de fichiers. Dans notre exemple :  

![chemin_dossier.png](/images/chemin_dossier.png){.align-center}

- **2** Donnez un nom à votre dossier.
- **3** Si vous savez ce que vous faîtes, indiquez un point de montage, sinon laissez libre, **VirtualBox** s'en chargera pour vous.
	- **Lecture seule** : si vous cochez cette case, vous ne pourrez pas y transférer ou supprimer des fichiers. Cela n'a pas grand intérêt pour notre cas !
	- **Montage automatique** : si vous cochez cette case, le dossier sera lancé (monté) au démarrage de votre **VM**.
	- **Configuration permanente** : si vous ne cochez pas cette case, vous devrez, à chaque démarrage de votre **VM**, refaire la configuration de vos dossiers partagés. Il sera donc indispensable de la cocher.
- Cliquez ensuite sur **OK**.

### Accéder aux dossiers partagés dans VirtualBox sur une distribution Linux 

Sous **Linux**, afin de pouvoir échanger entre les deux machines hôte et invité, il faut ajouter l'utilisateur courant dans le dossier `vboxusers`.

- Pour ce faire, tapez cette commande dans votre **VM** afin d'ajouter votre utilisateur et indiquer au système que cet utilisateur a les droits :
```bash
sudo usermod -G vboxusers -a $USER
```

- Redémarrez votre **VM** pour que cette configuration soit prise en compte.

 Après redémarrage, votre dossier apparaîtra dans votre gestionnaire de fichiers :  
 
 ![config_dossier.png](/images/config_dossier.png){.align-center} 
 
 Son contenu :  
 
 ![dossier.png](/images/dossier.png){.align-center}  
 
 Voyons maintenant le contenu du fichier sur le système hôte :   
 
 ![capture_d’écran_2023-03-23_23-20-25.png](/images/capture_d’écran_2023-03-23_23-20-25.png){.align-center}  
 
> Vous pouvez désormais passer d'un système à l'autre.
{.is-success}


### Activer le copier-coller et le glisser-déposer

- Cliquez sur ***Configuration*** puis ***Général*** et enfin sur ***Avancé*** :  

![capture_d’écran_2023-03-23_21-59-28.png](/images/capture_d’écran_2023-03-23_21-59-28.png){.align-center}  

- Cliquez sur les flèches à droite de ***Disabled*** pour changer les valeurs du ***Presse-papier partagé*** et du ***Glisser-Déposer*** à ***Bidirectionnel*** :  

![capture_d’écran_2023-03-23_21-59-59.png](/images/capture_d’écran_2023-03-23_21-59-59.png){.align-center}  

# Conclusion

> Félicitations, vous êtes désormais capable d'installer **VirtualBox** sur **Linux** pour y installer ensuite des machines virtuelles.
{.is-success}

---

> Il est à noter que bien que ces fonctions de partage de répertoire et de presse-papier soient très pratiques, cela réduit, de fait, la *sécurité* des deux systèmes puisque le **cloisonnement** inhérent aux machines virtuelles n'est plus assuré en totalité.
>
> Encore une fois, il s'agit de faire des compromis entre praticité et sécurité !
> Nos recommandations sont donc de limiter au maximum l'activation de ces fonctionnalités (**si vous n'en avez pas besoin au quotidien, ne les activez pas**), surtout sur des machines virtuelles critiques (type Whonix VM).
{.is-warning}

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Theudric*