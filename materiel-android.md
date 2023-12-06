---
title: Trouver un matériel adapté à Android
description: Où trouver du matériel Android - vous trouverez ici des solutions...
published: true
date: 2023-12-06T09:23:19.348Z
tags: android, materiel
editor: markdown
dateCreated: 2023-02-14T11:18:41.344Z
---

Il est bien souvent difficile pour la majorité d'entre nous d'installer une nouvelle ROM sur nos téléphones, tant par le côté technique que potentiellement dangereux, surtout si nous ne sommes pas des bidouilleurs :)

Voilà pourquoi certaines entreprises sélectionnent du matériel (qu'ils vont juger vertueux), et proposent des téléphones clé en main, c'est-à-dire avec la couche logicielle déjà pré-installée.

> Nous ne citons ici que les entreprises qui, pour nous, proposent du matériel décent et n'usent pas forcément de marketing à outrance ou d'arguments fallacieux.
{.is-info}


# 200-300 Euros

- [Ekimia](https://ekimia.fr/produit/oneplus-5t-eos/) : Téléphones reconditionnés  sous /e/OS-Android 13 T :
     - **[One Plus 5T (2017)](https://ekimia.fr/produit/oneplus-5t-eos/)** 179 €
     ![op5t.ekimia.resized.png](/op5t.ekimia.resized.png)
- [Iodé](https://iode.tech/) : Téléphones reconditionnés sous IodeOS :
     - **[Samsung S9 (2018)](https://iode.tech/shop/samsung-galaxy-s9-bundle-en/)** : 253€  
     - **[Google Pixel 3](https://iode.tech/shop/pixel-3-bundle-en/)** : 293€ 
     ![pixel-3-iode-1000x1000-1-removebg-preview.resized.png](/pixel-3-iode-1000x1000-1-removebg-preview.resized.png)
     
- [Murena](murena.com)
			- **[Murena one](https://iode.tech/shop/samsung-galaxy-s9-bundle-en/)** : 299 € 



# Aux alentours des 400 Euros

- [Simple Phone](https://simplephone.tech/product/simple-phone/) : nouveau venu sur le terrain du matériel, le **Simple Phone** est accessible et vient avec leur OS open source Simple OS. Vous pouvez néanmoins installer une autre ROM par la suite si vous le désirez.
*Il s'agit d'un téléphone proposé par les développeurs des applications open source très connues "Simple".*

- [Iode](https://iode.tech/) : Dans cette gamme de prix :
     - **Samsung Galaxy S10 ou S10+ (évitez le S10e)**
     - **Samsung Galaxy Note 9, voire 10**

- [Murena](https://murena.com/fr/produits/smartphones/) : Murena est la société derrière l'OS /e/OS, et propose une boutique avec des téléphones clés en main, aux tarifs plus ou moins cohérents et honnêtes. Dans cette gamme de prix :
     - **Samsung Galaxy S9 et S9+**
     - **Murena One**
     - **Murena Fairphone 3+**

- [Shift Phone](https://shop.shiftphones.com/) : les téléphones shift sont des téléphones intéressants et aux tarifs honnêtes. Dans cette gamme de prix :
     - **Shift5me**

- [Volla Phone](https://volla.online/en/) : Avec des téléphones de bonne facture. Les 2 modèles aux mêmes tarifs :
	 - **Volla Phone 2**
	 - **Volla Phone X** 

# Aux alentours des 600 Euros

- [Shift Phone](https://shop.shiftphones.com/) : Dans cette gamme de prix :
     - **Shift6mq**

- [Monocles](https://store.monocles.eu/) : Monocles vend des téléphones avec une ROM à base de GrapheneOS pré-installée. Cependant, leurs tarifs sont assez élevés, et débutent à 600 Euros.

- _Pixels Phones_ : nous ne pouvons bien entendu pas passer outre les Google Pixel qui sont des machines spécifiquement développées pour Android et qui possédent un modèle de sécurité élevé que les autres téléphones n'ont pas. Si votre profil exige une sécurité à haut niveau, ces téléphones sont malgré tout très utiles :
	 - **Google Pixel 6**
	 - **Google Pixel 7**
   - **Google Pixel 8 / 8 Pro**
*Note : On évitera les modèles en fin de vie ou presque, i.e. jusqu'au Google Pixel 4 !*


# Pourquoi des Google Pixels ?

Un téléphone Pixel de Google ? étonnant !

Mais pas tant que cela, il y a des raisons techniques derrière : en effet, Google a beaucoup travaillé sur le durcissement (voir [Hardening](/glossaire#hardening) dans le glossaire) de ses appareils que tous les autres ne possèdent pas (encore ?).

## Le bootloader

Sur ces modèles Pixel, il n'y a aucun besoin de changer le "recovery" pour accéder au chargeur d'amorcage (bootloader). Tous les autres fabricants verrouillent le bootloader en mettant leur propre recovery ; d'où l'obligation d'installer un outil tiers comme TWRP (Team Win Recovery Project) pour changer le système sur les marques tiers, et ne pas nécessairement pouvoir re-verrouiller le bootloader.
*Exception faite pour les téléphones sous Android One, comme cela avait été le cas pour le Xiaomi MiA2.*

Si demain les Pixel ne permettent plus de déverrouiller directement le chargeur d'amorçage, ces types de projets auront moins de raison d'utiliser ces téléphones.

## La puce Titan

La sécurité liée à la puce Titan M, qui a son intérêt en terme de chiffrement fait en local, qui explique le choix de la gamme des Pixel, pour y porter des systèmes "libres".

Techniquement, cette puce constitue en fait un mini-HSM (Hardware Security Module) physique et non logiciel, résistant au tampering (violation physique), capable donc de stocker tous les items cryptographiques de manière très sécurisée. Concrètement, il est extrêmement difficile d'extraire des données de cette puce ou la compromettre ; si la puce détecte le moindre comportement anormal, elle efface toutes ses données !

## Kernel associé

Les kernels des Pixels embarquent déjà des patchs de sécurité afin de durcir la couche logicielle basse (intégration CFI, ShadowCallStack, etc.). GrapheneOS renforce encore plus ce durcissement pour information.

## Mécanisme anti-forensic

Le mécanisme anti-forensic est un autre aspect important : plus il y a de tentatives erronées d'intrusion sur le téléphone, plus le téléphone sera verrouillé longtemps. Ce qui contribue à renforcer le modèle de sécurité de l'appareil.

## Durcissement Wi-Fi

Il est admis aujourd'hui qu'un téléphone connecté à un réseau Wi-Fi peut être tracé de différentes manières, mais principalement via les adresses MAC qui sont des identifiants uniques des puces liées à une machine. À chaque connexion, l'adresse MAC est exposée. Il est donc possible d'identifier l'équipement.

Certains constructeurs ont déjà essayé de résoudre ce problème, via la randomisation d'adresse MAC. Cela dit, la majorité ne l'implémente pas du tout, et parfois la solution de randomisation est faible ou mal implémentée, ce qui souvent mène tout de même à l'exposition de la réelle adresse MAC.

Les Pixels implémentent convenablement la randomisation de l'adresse MAC, ainsi que d'autres fonctions de randomisation.

# Les fausses bonnes idées


- Nous déconseillons le Fairphone 4 tantque [certains problèmes ](https://gitlab.e.foundation/groups/e/-/issues/?sort=created_date&state=opened&label_name%5B%5D=FP4&label_name%5B%5D=type%3A%3ABug&not%5Blabel_name%5D%5B%5D=Testing&first_page_size=20&page_after=eyJjcmVhdGVkX2F0IjoiMjAyMi0xMi0wMiAwODo1NTo1MS4xNDc5NjkwMDAgKzAwMDAiLCJpZCI6IjIyMjUxIn0)  ne sont pas corrigés



# Les téléphones sous GNU/Linux

- [Librem](https://puri.sm/products/) : Surtout le Librem 5. sous PureOS, un Linux dérivé de Debian. Le téléphone est conçu de façon à maximiser la sécurité en utilisant autant que possible des logiciels libres. Le matériel propose trois boutons switch pour empêcher le fonctionnement de la caméra, du microphone, du Wi-Fi et du Bluetooth.
*Cependant, les utilisateurs attendent toujours leur téléphone, depuis 1 an ! Si vous êtes patients, pourquoi pas, sinon fournisseur à éviter pour le moment.*

- [Pinephone](https://www.pine64.org/pinephone/) : à l'origine une excellente idée, téléphone avec batterie amovible, sous Linux Ubuntu... Le but est d'offrir un smartphone à prix modéré, facilement réparable et relativement garant de la vie privée. Il est pour cela basé sur le système d'exploitation GNU/Linux, ses composants peuvent être facilement maintenus, et des interrupteurs matériels permettent d'isoler le téléphone des différents réseaux et capteurs.
*Les distributions GNU/Linux suivantes sont supportées : Mobian, Plasma Mobile (en), Ubuntu Touch, PostmarketOS, Sailfish OS, ou n'importe quel système d'exploitation Linux.*

Également :
- [Ubuntu Touch](https://ubuntu-touch.io/fr/) _n'est pas un téléphone_, mais est une version Linux d'Ubuntu destinée aux smartphones et aux tablettes. Son développement supervisé par Canonical a été arrêté le 5 avril 2017. La communauté a repris le projet sous le nom d'UBports, actuellement actif ([UBports](https://fr.wikipedia.org/wiki/UBports)).
*Les téléphones compatibles sont disponibles ici : [Ubuntu Touch Devices](https://devices.ubuntu-touch.io)*


# Autres Magasins tiers

- [Jolla Devices](https://buy.jolla-devices.com/) Smartphones reconditionnés sous Sony Sailfish OS.
- [Private Phone Shop](https://privatephoneshop.com/) Smartphones avec soit LineageOS, soit GrapheneOS, soit CalyxOS.
- [Nitrokey](https://www.nitrokey.com/fr) Smartphones et tablettes sous GrapheneOS.

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo,Viiper*