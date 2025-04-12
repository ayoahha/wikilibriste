---
title: Désinstaller Cellbroadcast Receiver package via ADB
description: Article qui vous indique comment désinstaller Cellbroadcast Receiver via Android Debug Bridge et ADB shell.
published: true
date: 2025-04-12T22:53:30.102Z
tags: android, adb, cellbroadcast, debloat
editor: markdown
dateCreated: 2022-11-28T09:58:21.788Z
---

Dans ce tutoriel rapide, nous allons apprendre à désinstaller Cellbroadcast Receiver via Android Debug Bridge et ADB shell.

Qu'est-ce que c'est ?
=======
L’application CellBroadcastReceiver est une application système par défaut qui gère les alertes d’urgence et non urgentes (telles que les alertes Orange, terroristes et présidentielles) et présente les informations aux utilisateurs finaux en fonction des réglementations de l’opérateur et régionales.
Cette application est installée à un niveau système et pas désinstallable par la méthode classique.
Elle peut initier une connexion à une antenne de façon autonome et non contrôlable.

Étape 1
=======
- Aller dans les Paramètres > À propos du téléphone.
- Faire glisser tout en bas puis taper (pas avec un marteau) 7 fois sur le numéro de build pour faire apparaître les options de développement. 
- Aller ensuite dedans puis activer le débogage usb.

Étape 2 
=======
- Brancher votre téléphone à votre ordinateur.
- Ouvrir un terminal et entrer `adb shell`.
- Sur le smartphone, vous sera demandée une confirmation : accepter (ou refuser et laisser tomber, on a toujours le choix dans la vie !)

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
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Howerdel, Justin*