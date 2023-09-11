---
title: Android Bootloader Unlock
description: Ce tutoriel vous parle des "bootloader" liés à Android et fait un état de lieux...
published: true
date: 2023-09-11T07:34:34.146Z
tags: android, smartphone, ordiphone, booloader, intermédiaire, intermediaire
editor: markdown
dateCreated: 2022-11-25T17:54:20.672Z
---

En informatique, l'emploi d'un terme anglophone est souvent incontournable. Nous essayons d'y recourir le moins possible. 

Veuillez vous référer au [glossaire](/glossaire#bootloader) pour en savoir plus.

> Veuillez lire attentivement la page [Avertissements](/avertissement) avant toute manipulation !
{.is-danger}

Le bootloader ou "chargeur d'amorçage"
========================

- C'est le premier logiciel executé quand vous allumez votre téléphone.
- Il va notamment pouvoir bloquer le lancement d'un autre logiciel que celui du fabricant.

Libération du bootloader
========================

Pourquoi certains cherchent-ils à déverrouiller ce fameux chargeur d’amorçage ?

Lorsque l'on veut remplacer une partie du système Android sur un smartphone, le déverrouillage du chargeur d’amorçage est une étape obligatoire ! C'est le cas par exemple si vous souhaitez :

-   Remplacer le recovery (TWRP, OrangeFox, LineageOS recovery...) ;
-   Remplacer le système (ROM) de votre téléphone Android (ROM Stock) OEM du constructeur par une ROM personnalisée (on parle alors de "custom ROM").

L'utilisateur qui veut reprendre le contrôle de son appareil va alors être confronté aux difficultés de débloquer le chargeur d'amorçage ("unlock bootloader") Android :D

En effet, certains constructeurs de téléphone rendent l'opération impossible

> Il faut donc choisir la marque de son téléphone en fonction de cette possibilité afin de le faire durer au maximum et éviter qu'il devienne un déchat numérique par obsolescence logicielle.
{.is-warning}



Marques et leur politique de déverrouillage
===========================================

Le tableau ci-dessous est non exhaustif (basé sur l'expérience de l'équipe) et peut avoir évolué depuis.
- Veillez à bien prendre ce tableau comme tel et informez-vous en amont sur les sites listés ci-dessous.

De plus, pour un même modèle suivant la région (USA, ASIE...) ou si revendu par un fournisseur d'accès au réseau mobile (Verizon, AT&T...), le téléphone peut être non déverrouillable ! 
- Veillez à bien vérifier ces aspects avant un achat.

> Bonne libération !
{.is-info}

## Les marques ou le déblocage est "facile" 

| Marque | Outil de flash | Complexité déverrouillage (OEM unlock) | Perte de la garantie | Modèles supportés |
|----------|----------|----------|----------|----------|
| BQ | fastboot | **Facile**<br> via le menu outils de dev : OEM unlock puis commande fastboot | oui | Tous |
| Essential | fastboot | **Facile**<br> OEM unlock + commande fastboot | non | PH-1 seulement |
| Fairphone | fastboot | **Facile**<br> OEM unlock + commande fastboot | non | Tous |
| Gigaset | fastboot | **Facile**<br> OEM unlock + commande fastboot | oui | GS290 seulement |
| Google      | fastboot | **Facile**<br> OEM unlock + commande fastboot | non | Tous les Google Pixel et Nexus<br>  |
| OnePlus | fastboot | **Facile**<br> OEM unlock + commande fastboot | non | Tous |
| Samsung | ODIN ou Heimdall | **Modéré** besoins d'utliser certaines touches <br>de l'appareil pour acceder au mode "download"| oui | Tous les Galaxy Sx et série Ax <br> Attention de plus en plus complexe sur > S10  |
| Teracube | fastboot | **Facile**<br> OEM unlock + commande fastboot | non | - |




## Les marques où le déblocage est "difficile" 



| Marque | Outil de flash | Complexité déverrouillage (OEM unlock) | Perte de la garantie | Modèles supportés |
|----------|----------|----------|----------|----------|
| HTC | fastboot | **Modéré**<br>  code via fastboot et site web fabriquant  | oui | HTC 10, One, One A9, U Ultra / U11 pour les versions carrier-unlocked |
| Motorola | fastboot | **Modéré**<br>  code via fastboot et site web fabriquant  | oui | - |
| Sony | fastboot | **Modéré**<br>  code via fastboot et site web fabriquant  | oui | - |
| Xiaomi | fastboot<br>Avec Mi Unlock Tool (propriétaire) | **Modéré**<br>Via application Xiaomi, interface graphique puis code OEM | oui | Tous peuvent être déverrouillés |


## Les marques à éviter absolument (déblocage impossible)



| Marque | Outil de flash | Complexité déverrouillage (OEM unlock) | Perte de la garantie | Modèles supportés |
|----------|----------|----------|----------|----------|
| ASUS | fastboot | **Impossible**<br> Depuis Mai 2023 Asus ne permet plus le déblocage via son application | oui| Une dizaine |
| Crosscall | fastboot | **Impossible** | oui | La série 5 sera déblocable (info a venir) - les anciennes, non. |
| Honor | fastboot | **Très difficile/impossible**<br>Méthodes non officielles car le fabricant ne donne plus les codes OEM unlock depuis 2017/2018 ! | oui | Honor 8 |
| Huawei | fastboot | **Très difficile/impossible**<br>Méthodes non officielles car le fabricant ne donne plus les codes OEM unlock depuis 2017/2018 ! | oui | Mate 9/9Pro, P10/P10Plus |
| LG | - | **Impossible**<br> | oui | Depuis Dec 2021, LG ne permet plus de déblocage |


## Les marques à completer 


| Marque | Outil de flash | Complexité déverrouillage (OEM unlock) | Perte de la garantie | Modèles supportés |
|----------|----------|----------|----------|----------|
| LeEco | - | - | - | - |
| Lenovo | - | - | - | - |
| Nextbit | - | - | - | - |
| Nokia | - | - | - | - |
| Nubia | - | - | - | - |
| OPPO | - | - | - | - |
| Razer | - | - | - | - |
| Nextbit | - | - | - | - |
| Realme | - | - | - | - |
| SHIFT | - | - | - | - |
| Wiko | - | - | - | - |
| Wileyfox | - | - | - | - |
| Wingtech | - | - | - | - |
| Yandex | - | - | - | - |
| YU | - | - | - | - |
| ZTE | - | - | - | - |
| ZUK | - | - | - | - |
{.dense}

Déverrouiller le bootloader
===========================

Alors comment le déverrouiller ce "bootloader" ?

Tout dépend des marques et même des modèles de smartphone. 
Sachez que la plupart du temps, si le modèle exact de votre téléphone **<span style="text-decoration: underline;">n'est pas listé</span>** sur les sites de ROM personnalisées suivants, alors il est très probable que cela soit impossible :

- [LineageOS *Cherchez votre téléphone dans la liste et cliquez dessus : vous serez renvoyé vers la page dudit modèle. Vérifiez tout en bas de cette page dans la section "Supported models" que le **modèle exact** est listé sur la page, si ce n'est pas le cas alors votre téléphone n'est pas supporté officiellement par LineageOS. S'il est supporté, allez lire la page sous Guides / Installation pour en savoir plus sur la procédure "unlock bootloader"*](https://wiki.lineageos.org/devices)
- [/e/OS Devices *Suivez ce lien eOS et faites défiler la page, cherchez votre téléphone dans la liste et cliquez dessus, selon le même principe que pour LOS*](https://doc.e.foundation/devices)
- [CalyxOS *Seuls les Google Pixel et certains OnePlus sont supportés (Attention cependant pour les OnePlus, l'impossibilité de reverrouiller le bootloader a poussé l'équipe Calyx à reconsidérer le support de ces téléphones, OnePlus ne rendant pas la tâche aisée)*](https://calyxos.org/install/)
- [GrapheneOS *Seuls les Google Pixel sont supportés du fait de leur modèle de sécurité spécifique*](https://grapheneos.org/faq#supported-devices)
- [IodéOS *Vérifiez si votre appareil est supporté*](https://iode.tech/installation/#1611168530685-c5ff66ab-4568)
- [DivestOS *Vérifiez si votre appareil est supporté*](https://divestos.org/index.php?page=devices&base=LineageOS)
- [DotOS *Vérifiez si votre appareil est supporté*](https://www.droidontime.com/devices)
- [Replicant *Certains modèles de Samsung*](https://replicant.us/supported-devices.php)
- [Forum XDA *En dernier recours, vous pouvez aller voir sur le site de référence en la matière. Mais attention ici, certaines ROMs ne sont plus maintenues et cela fluctue en fonction des développeurs...*](https://forum.xda-developers.com/all-forums-by-manufacturer)
{.links-list}
---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): marmotte, Ayo*