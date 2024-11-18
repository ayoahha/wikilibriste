---
title: Android Bootloader Unlock
description: Ce tutoriel vous parle des "bootloader" liés à Android et fait un état de lieux...
published: true
date: 2024-11-18T11:49:37.268Z
tags: android, smartphone, ordiphone, booloader, intermédiaire, intermediaire
editor: markdown
dateCreated: 2022-11-25T17:54:20.672Z
---

En informatique, l'emploi d'un terme anglophone est souvent incontournable. Nous essayons d'y avoir recours le moins possible. 

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

> Il faut donc choisir la marque de son téléphone afin de le faire durer au maximum et éviter qu'il devienne un déchet numérique par obsolescence logicielle.
{.is-warning}

> Tous les produits Apple sont évidemment bloqués et donc à éviter absolument ! voir iosref.com/ios pour leur calendrier d'obsolescence



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
| BQ | fastboot | **Facile**<br> Commande fastboot | Oui | Tous |
| Essential | fastboot | **Facile**<br> Commande fastboot | Non | PH-1 seulement |
| Fairphone | fastboot | **Facile**<br> OEM unlock (site de [Fairphone](https://www.fairphone.com/en/bootloader-unlocking-code-for-fairphone)) + commande fastboot | Non | Tous |
| Gigaset | fastboot | **Facile**<br> Commande fastboot | Oui | GS290 seulement |
| Google      | fastboot | **Facile**<br> Commande fastboot | Non | Tous les Google Pixel et Nexus<br>  |
| Nothing | fastboot | **Facile**<br> Commande fastboot | Non | Tous |
| OnePlus | fastboot | **Facile**<br> Commande fastboot | Non | Tous |
| Razer | fastboot | Commande fastboot | Oui | Phone 1, Phone 2 |
| Samsung | ODIN ou Heimdall | **Modéré** Besoins d'utliser certaines touches <br>de l'appareil pour acceder au mode "download"| oui | Tous les Galaxy Sx et série Ax <br> Attention de plus en plus complexe sur > S10  |
| SHIFT | fastboot | **Facile**<br> Commande fastboot | Non | info [ici](https://forum.shiftphones.com/threads/bootloader-unlock-root-custom-recoveries-roms-mods.3207/)  |
| Yandex | fastboot | **Facile** <br> Commande fastboot | Oui | Un seul téléphone est sorti (2018) |
| YU | fastboot | **Facile** <br> Commande fastboot | Oui | Marque disparu depuis 2018 |
| Teracube | fastboot | **Facile**<br> Commande fastboot | Non | Tous |
| ZUK | fastboot | **Facile** <br> Commande fastboot | Oui | Z1 et Z2 uniquement, marque disparu depuis 2016 |






## Les marques où le déblocage est "difficile" 



| Marque | Outil de flash | Complexité déverrouillage (OEM unlock) | Perte de la garantie | Modèles supportés |
|----------|----------|----------|----------|----------|
| HTC  avant Juin 2018| fastboot | **Modéré**<br>  code via fastboot et site web fabriquant <br>pour les téléphones [d'avant juin 2018](https://www.htcdev.com/bootloader) | Oui | HTC 10, One, One A9, U Ultra / U11 pour les versions carrier-unlocked <br>[Un verrou S-ON/S-OFF](https://github.com/melontini/bootloader-unlock-wall-of-shame/blob/main/brands/htc/README.md) complique l'installation de ROM|
| Sony | fastboot | **Modéré**<br>  OEM unlock (site de [Sony](https://developer.sony.com/open-source/aosp-on-xperia-open-devices/get-started/unlock-bootloader)) + commande fastboot  | Oui | [Tous ou presque](https://github.com/melontini/bootloader-unlock-wall-of-shame/blob/main/brands/sony/README.md) |
| Motorola | fastboot | **Modéré**<br> OEM unlock (site de [Motorola](https://en-us.support.motorola.com/app/utils/welcome?p_next_page=standalone%2Fbootloader%2Funlock-your-device-b)) + commande fastboot  | Oui | Passé un age de téléphone [non communiqué](https://github.com/melontini/bootloader-unlock-wall-of-shame/blob/main/brands/motorola/README.md), Motorola ne permet plus le déblocage |
| Xiaomi <br> Redmi <br> POCO| fastboot<br>Avec Mi Unlock Tool (propriétaire) | **Modéré**<br>Via application Windows Xiaomi, interface graphique puis code OEM <br> Déverrouillage [impossible](https://github.com/melontini/bootloader-unlock-wall-of-shame/blob/main/brands/xiaomi/README.md) pour les versions China | Oui | Toutes les versions non destiné au marché Chinois peuvent être déverrouillés [(pour le moment)](https://x.com/chunvn8888) |


## Les marques à éviter absolument (déblocage très difficile voir impossible)



| Marque | Outil de flash | Complexité déverrouillage (OEM unlock) | Perte de la garantie | Modèles supportés |
|----------|----------|----------|----------|----------|
| Apple | - | **Impossible** | Oui | Il existe bien [un projet](https://projectsandcastle.org/status) pour installer Android sur Iphone mais beaucoup de pilotes <br>manques, en particulier si ce n'est pas un modèle 7, 7+, 7G |
| ASUS | fastboot | **Impossible**<br> Depuis Novembre 2023 Asus [ne permet plus](https://github.com/melontini/bootloader-unlock-wall-of-shame/blob/main/brands/asus/README.md) le <br>débloquage via son application et implémente un anti roolback | Oui| Une dizaine |
| Cat | - | **Impossible** | Oui | - |
| Crosscall | fastboot | **Impossible** | Oui | La série 5 sera débloquable (info a venir)<br> - les anciennes, non. |
| HMD Global | fastboot | **Impossible** | Oui | Politique de [verrouillage systématique](https://github.com/melontini/bootloader-unlock-wall-of-shame/blob/main/brands/nokia/README.md) du bootloader, cependant quelques méthodes <br>existent pour les téléphones de l'ère Nokia <br> La cadence très élevé de sortie des téléphones rend peu probable la sortie de nouvelle <br>méthode et ROM alternative |
| Honor | fastboot | **Très difficile/impossible**<br>Méthodes non officielles car le fabricant ne donne <br>plus les codes OEM unlock depuis 2017/2018 ! <br> Certains telephones peuvent débloqué avec [PotatoMV](https://github.com/mashed-potatoes/PotatoNV) <br> (gratuit) ou HCU Client (payant) | Oui | Téléphone avec Kirin 620 (Honor 5C) à 659 et Kirin 925 à 960 (Honor 9) pour PotatoMV <br>et plus de modèles compatibles avec HCU Client  |
| HTC  après Juin 2018| fastboot | **Impossible**| Oui | - |
| Huawei | fastboot | **Très difficile/impossible**<br>Méthodes non officielles car le fabricant ne donne <br>plus les codes OEM unlock depuis 2017/2018 !<br> Certains telephones peuvent débloqué avec [PotatoMV](https://github.com/mashed-potatoes/PotatoNV) <br> (gratuit) ou HCU Client (payant) | Oui | Téléphone avec Kirin 620 (Huawei P8 Lite) à 659 et Kirin 925 à 960 (Huawei P10, Mate 9) <br>pour PotatoMV et plus de modèles compatibles avec HCU Client |
| LG | - | **Impossible** | Oui | Depuis Dec 2021, LG ne permet plus de déblocage |
| Meizu | fastboot | **Difficile** <br> Quelques [méthodes](https://github.com/melontini/bootloader-unlock-wall-of-shame/blob/main/brands/meizu/README.md) gratuite ou payante au cas par cas | Oui | 16T, 16xs, Note 9 |
| Nokia | fastboot | **Difficile** <br> Un [site officieux](https://www.hikaricalyx.com/request-bootloader-unlock/) permet le déblocage des modèles d'avant <br>début 2019 et cette [autre méthode](https://fih-firmware.hikaricalyx.com/protoabl/) permet de débloquer d'autre téléphones <br>et presque tout les Windows Phones dispose d'une [méthode officieuse](http://allaboutwindowsphone.com/features/item/24245_Aguideforunlockingthebootloade.php)| Oui | - |
| Nubia (ZTE)| fastboot (Redmagic) <br> edl (Nubia) | **Facile** <br> Commande fastboot ou edl <br> Uniquement des anciens modèles| Oui | Anciens modèles, Nuvia appartient à ZTE donc<br> peu d'espoir pour les nouveaux modèles |
| OPPO | fastboot | **Impossible** <br>Fastboot est bloqué | Oui | - |
| Realme | fastboot | **Impossible** <br>Fastboot est bloqué  | Oui | - |
| Redmagic| fastboot | Voir Nubia| Oui | - |
| Sharp | - | **Difficile** <br> Quelques modèles peuvent être déverouillé via cette [méthode](https://hikaricalyx.com/request-bootloader-unlock) | Oui | Aquos S2/C10, Aquos S3/D10 et Aquos S3 Mini |
| Wiko | - | **Difficile** <br> Possible si la clef par défaut a été utilisé | Oui | Au cas par cas en suivant la [méthode générale](https://github.com/melontini/bootloader-unlock-wall-of-shame/tree/main?tab=readme-ov-file#universal-soc-based-methods) ([lien alternatif](https://www.hovatek.com/blog/how-to-unlock-the-bootloader-on-your-android-smartphone-or-device/)) <br>du fabricant de la puce car Wiko utilise en général la clef par défaut |
| ZTE | devinfo hexa edit | **Difficile** <br> Pour les téléphones jusqu'à Android 8 Oreo, cette [methode](https://xdaforums.com/t/bootloader-unlocking-on-older-qualcomm-zte-devices-devinfo-partition-modification.4100897/) est disponible | Oui | - |


## Les marques à completer 


| Marque | Outil de flash | Complexité déverrouillage (OEM unlock) | Perte de la garantie | Modèles supportés |
|----------|----------|----------|----------|----------|
| LeEco | - | - | - | - |
| Lenovo | - | - | - | - |
| Nextbit | - | - | - | - |
| Wileyfox | - | - | - | - |
| Wingtech | - | - | - | - |
{.dense}

Déverrouiller le bootloader
===========================

Alors comment le déverrouiller ce "bootloader" ?

Tout dépend des marques et même des modèles de smartphone. 
Sachez que la plupart du temps, si le modèle exact de votre téléphone **<span style="text-decoration: underline;">n'est pas listé</span>** sur les sites de ROM personnalisées suivants, alors il est très probable que cela soit impossible :

- [LineageOS *Cherchez votre téléphone dans la liste et cliquez dessus : vous serez renvoyé vers la page dudit modèle. Vérifiez tout en bas de cette page dans la section "Supported models" que le **modèle exact** est listé sur la page, si ce n'est pas le cas alors votre téléphone n'est pas supporté officiellement par LineageOS. S'il est supporté, allez lire la page sous Guides / Installation pour en savoir plus sur la procédure "unlock bootloader"*](https://wiki.lineageos.org/devices)
- [/e/OS Devices *Suivez ce lien eOS et faites défiler la page, cherchez votre téléphone dans la liste et cliquez dessus, selon le même principe que pour LOS*](https://doc.e.foundation/devices)
- [CalyxOS *Seuls les Google Pixel et certains mobiles de type Motorola, Fairphone et Shift sont supportés.*](https://calyxos.org/install/)
- [GrapheneOS *Seuls les Google Pixel sont supportés du fait de leur modèle de sécurité spécifique*](https://grapheneos.org/faq#supported-devices)
- [IodéOS *Vérifiez si votre appareil est supporté*](https://iode.tech/installation/#1611168530685-c5ff66ab-4568)
- [DivestOS *Vérifiez si votre appareil est supporté*](https://divestos.org/index.php?page=devices&base=LineageOS)
- [DotOS *Vérifiez si votre appareil est supporté*](https://www.droidontime.com/devices)
- [Replicant *Certains modèles de Samsung*](https://replicant.us/supported-devices.php)
- [Forum XDA *En dernier recours, vous pouvez aller voir sur le site de référence en la matière. Mais attention ici, certaines ROMs ne sont plus maintenues et cela fluctue en fonction des développeurs...*](https://forum.xda-developers.com/all-forums-by-manufacturer)
{.links-list}

Vous pouvez aussi pour les fabricants qui ont une méthode de déverouillage par clef mais qui ne propose pas / plus au public d'y accéder de [bruteforcer la clef](https://github.com/samuelcaldas/Bruteforce-Bootloader-Unlocker) en espérant qu'aucun système antibruteforce n'est été implémenté, donc en dernier recours après le forum XDA.

Merci au Github [Bootloader Unlock Wall of Shame](https://github.com/melontini/bootloader-unlock-wall-of-shame/tree/main) et aux différents sites de ROM (Lineage, /e/os...) pour les méthodes de déverrouillage du bootloader.

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): ayo, freechelmi, marmotte, Justin*
