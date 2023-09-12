---
title: Désinstaller Cellbroadcast Receiver package via ADB
description: Article qui vous indique comment désinstaller Cellbroadcast receiver via android debug bridge et ADB shell
published: true
date: 2023-09-10T09:58:38.802Z
tags: android, adb, cellbroadcast, debloat
editor: markdown
dateCreated: 2022-11-28T09:58:21.788Z
---

Dans ce tutoriel rapide, nous allons apprendre à désinstaller Cellbroadcast Receiver via Android Debug Bridge et ADB shell.

Étape 1
=======
- Aller dans les Paramètres > À propos du téléphone.
- Faire glisser tout en bas puis taper (pas avec un marteau) 7 fois sur le numéro de build pour faire apparaître les options de développement. 
- Aller ensuite dedans puis activer le déboguage usb.

Étape 2 
=======
- Brancher votre téléphone à votre ordinateur.
- Ouvrir un terminal et entrer `adb shell`.
- Sur le smartphone, vous sera demandée confirmation : accepter (ou refuser et laisser tomber, on a toujours le choix dans la vie !)

Étape 3
=======
Entrer les commandes suivantes dans un terminal :
```bash
adb shell
```
Puis vous obtenez un prompt `oriole:/ $ ` ; entrer les commandes comme suit :
```brainfuck
		pm list packages cellbroadcast     
    pm uninstall --user 0 com.android.cellbroadcastreceiver.module
    pm uninstall --user 0 com.android.cellbroadcastreceiver
    pm uninstall --user 0 com.android.cellbroadcastservice
```

> Félicitations ! Vous avez lu le "fuckin' " manuel :D
{.is-success}

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Howerdel*