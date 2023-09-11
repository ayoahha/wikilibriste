---
title: Configurer son BIOS
description: Indispensable si vous souhaitez vous libérer et installer autre chose que Windows...
published: true
date: 2023-06-19T21:56:35.147Z
tags: usb, bios, secure boot
editor: markdown
dateCreated: 2023-03-09T09:43:00.410Z
---

Afin d'installer d'autres systèmes que Windows, il est nécessaire sur vos machines de configurer correctement votre [BIOS](/glossaire#firmware).

> L'objectif est d'autoriser le démarrage sur une clef USB afin d'accéder à l'installateur tiers et de désactiver le "[Secure Boot](/tutoriels/distro-protect-hardening#secure-boot)" qui bloque la machine dans le cas d'un boot sur un système différent de Windows.
{.is-info}

---

L'accès à ce programme se fait simplement, en utilisant une touche du clavier aux tous premiers instants de démarrage de la machine. Généralement, il s'agira d'une de ces touches :
- <kbd>SUPPR</kbd> (dans la majorité des cas)
- <kbd>F1</kbd>
- <kbd>F2</kbd>
- <kbd>F10</kbd>
- <kbd>F12</kbd>

Essayez-les les unes après les autres, il est souvent impossible d'y arriver la première fois donc persévérez ;) !

Celle-ci dépend de la marque de votre machine et/ou de la carte mère, et il n'est pas trivial de la trouver.
> Voici donc une [liste des touches claviers](https://www.disk-image.com/faq-bootmenu.htm) pour accéder à certains BIOS, touche que vous retrouverez dans la colonne "BIOS Key" pour celle correspondant à votre machine.
{.is-info}

---

Voici ensuite la procédure à suivre :
- Démarrez votre machine.
- Accédez au BIOS en appuyant sur la touche idoine (tout de suite après avoir démarré).
- Pour naviguer dans le BIOS, utilisez les touches fléchées du clavier (flèche de gauche et droite pour les menus et flèches haut et bas pour les éléments d'un menu).
- Allez sur un menu comportant une mention "Boot" ou s'en rapprochant.
- Désactivez le Secure Boot en le passant à l'état "Disabled". Attention, il se peut que cette option ne soit pas visible dans ce menu. Dans ce cas, allez sur un menu comportant une mention "Security" ou s'en rapprochant, et cherchez une option avec "Secure Boot" pour le passer à l'état "Disabled".
- Dans le menu "Startup" ou "Boot", passez ensuite votre périphérique USB, souvent nommé "USB HDD ..." (en lien avec votre clé - sa marque ou son modèle), en priorité de boot N°1 ou tout en haut de la liste.


Voici quelques images de BIOS pour vous aider à appréhender cet outil :

![](/images/secure-boot-lenovo.png){.align-center}
![](/images/secure-boot-aptio.png){.align-center}
![](/images/secure-boot-dell.jpg){.align-center}
![](/images/secure-boot-acer.jpg){.align-center}

- Sur les machines ACER récentes, il est par exemple obligatoire d'ajouter un mot de passe administrateur (onglet Security) avant d'avoir accès à l'option Secure Boot. Egalement, un appui simultané sur <kbd>CTRL</kbd>+<kbd>S</kbd> permet d'activer des options cachées...
- Les autres BIOS comportent également quelques spécificités selon le distributeur...

> Du fait de la grande diversité de BIOS, marques et modèles de carte mère, il est très difficile de vous guider sur cette étape. Demandez de l'aide si vous ne vous en sortez pas.
{.is-info}

---

> Une fois terminé, avant de redémarrer le PC, n'oubliez pas de sauvegarder la configuration du BIOS (Dans le menu "Exit" ou "Save & Exit").
{.is-warning}


**Voilà votre BIOS est configuré pour l'installation...**

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo, marmotte*