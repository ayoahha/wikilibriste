---
title: Utilisation de Syncthing
description: 
published: true
date: 2023-04-02T14:40:14.266Z
tags: 
editor: markdown
dateCreated: 2023-01-18T14:58:43.695Z
---

Bienvenue sur ce tutoriel qui vous présentera comment utiliser **Syncthing**.

Notre exemple porte sur une base de données de mots de passe initiée par l'application [KeepassXC](./keepass.md#), sur ordinateur fixe et mobile.

# Installation

Installer l'application sur votre ordinateur ainsi que sur votre téléphone :
- [Sur ordinateur](https://syncthing.net/downloads/)
- [Sur téléphone](https://f-droid.org/packages/com.nutomic.syncthingandroid/)


# Configuration

## Ordinateur

Ouvrez l'interface web sur votre ordinateur et l'application sur votre téléphone...

> N'oubliez pas de mettre un mot de passe la première fois que vous ouvrez l'interface web sur votre ordinateur : l'application vous le proposera. Ce n'est pas obligatoire mais fortement recommandé.
{.is-info}

![syncthing-2.png](./images/syncthing-2.png){.align-center}
![syncthing-1.png](./images/syncthing-1.png){.align-center}

Ajoutez un répertoire à partager :

![syncthing-3.png](./images/syncthing-3.png){.align-center}

![syncthing-3.png](./images/syncthing-3-1.png){.align-center}

![syncthing-3.png](./images/syncthing-3-2.png){.align-center}

![syncthing-3.png](./images/syncthing-3-3.png){.align-center}

![syncthing-4.png](./images/syncthing-4.png){.align-center}

Veuillez notez que nous avons bien modifié l' "**ID du partage**". 

***Notez-le vous en aurez besoin plus tard...***

## Téléphone

Maintenant, occupons-nous du téléphone, initialisons Syncthing :

![syncthing-6.png](./images/syncthing-6.png){.align-center}

Sur votre ordinateur, sur l'interface Web, cliquez sur "Actions" / "Afficher mon ID", vous obtiendrez un QR Code comme suit :

![syncthing-5.png](./images/syncthing-5.png){.align-center}

Sur votre téléphone, faites comme suit, à l'étape 3, scannez le QR Code.

![syncthing-7.png](./images/syncthing-7-1.png){.align-center}

Sur l'interface Web :

![syncthing-5.png](./images/syncthing-5-1.png){.align-center}

![syncthing-5.png](./images/syncthing-5-2.png){.align-center}

![syncthing-5.png](./images/syncthing-5-3.png){.align-center}

Retournez sur votre téléphone :

![syncthing-7.png](./images/syncthing-7-2.png){.align-center}

![syncthing-7.png](./images/syncthing-7-3.png){.align-center}

> Bien, nous avons maintenant terminé la configuration.
{.is-success}

# Tests

Nous pouvons tester...

Ici pour l'exemple nous ajoutons une base nommée "MaBase.kdbx" sur notre ordinateur :

![syncthing-8.png](./images/syncthing-8.png){.align-center}

Quelques instants plus tard, voici ce que nous obtenons :
- Vous pouvez voir que la synchronisation a été faite : nous avons maintenant 1 fichier
- A droite vous pouvez voir le fichier qui est apparu sur le téléphone

![syncthing-9.png](./images/syncthing-9.png){.align-center}

# Lancement automatique

Afin de permettre un lancement automatique de Syncthing au démarrage de votre système, vous pouvez procéder de 2 façons :

1. Utiliser l'application graphique "Applications au démarrage" :
 - Lancez cette application
 - Ajouter une nouvelle application à démarrer
 - Donner un titre et choisissez "Start Syncthing" via le bouton parcourir : généralement cette application se trouve dans `/usr/share/applications/` et nommé "syncthing-start.desktop"

2. Si vous préférez la ligne de commande :
 - Localiser "Start Syncthing", via `locate syncthing-start.desktop` (si locate n'est pas installé, installez le)
 - Puis copier ce fichier dans le dossier .config, comme suit : `cp /usr/share/applications/syncthing-start.desktop ~/.config/autostart/`

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo*