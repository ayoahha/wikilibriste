---
title: Debloater son téléphone Android
description: Ce tutoriel vous montre comment vous pouvez supprimer les logiciels superflus de votre ordiphone préféré
published: true
date: 2025-05-08T17:27:22.664Z
tags: debloat, uad
editor: markdown
dateCreated: 2023-02-12T13:37:27.461Z
---

Ce tutoriel vous présentera un outil capable de supprimer les paquets logiciels pré-installés sur votre téléphone Android que nous nommons généralement des "bloatswares", c'est-à-dire des logiciels inutiles parfois même dangeureux pour notre vie privée (cf. [glossaire](/glossaire)).

Cet outil est le suivant :
- [Universal Android Debloater](https://github.com/0x192/universal-android-debloater)

Attention, celui-ci ne fonctionne a priori que sur les marques suivantes :
- Asus
- LG
- Google
- Fairphone
- Huawei
- Motorola
- Nokia
- OnePlus
- Oppo
- Realme
- Samsung
- Sony
- Tecno
- Unihertz
- Vivo/iQOO
- Xiaomi
- ZTE
De même, il se peut que l'outil ne fonctionne tout simplement pas avec votre modèle !


> Disclaimer : nous ne pouvons être tenus pour responsables d'un quelconque mal-fonctionnement du téléphone. Il vous appartient de vous documenter suffisamment et de respecter les conseils mentionnés ici.
> 
> Il est essentiel de plus de sauvegarder toutes les données personnelles car, dans le cas d'un dysfonctionnement, il pourra être utile de faire une réinitialisation des données ("reset and wipe data", donc pertes des données personnelles, photos, documents, etc...) voire une réinstallation complète du système.
> 
> Veuillez également lire attentivement notre page [Avertissements](/avertissement) et n'hésitez pas à vous faire conseiller auprès de la communauté. 
{.is-danger}

# Les pré-requis

Il est bien entendu **obligatoire** à ce stade de faire une sauvegarde de toutes vos données. Nous avons rédigé un [tutoriel](/tutoriels-android/twrp) pour vous montrer comment procéder.

Puis, suivez la procédure suivante :
- Sur votre téléphone :
1. Activez l'option pour les développeurs sur votre modèle : il suffit généralement de se rendre dans les Paramètres, "A Propos du Téléphone" et trouver des informations sur le logiciel, puis tapez 5 à 10 fois sur le "Numéro de Version", cela activera un menu caché nommé très souvent "Options de développement".

2. Activez le "Débogage USB" dans ces options (ou "USB debugging" si votre téléphone parle anglais :) !)

- Sur votre ordinateur :
3. Installez ADB :

### Tabs {.tabset}
#### Debian/Ubuntu
Ou autres distributions basées sur Ubuntu ou Debian :
```
sudo apt install android-sdk-platform-tools
```

#### Arch Linux
Ou autres distributions basées sur Arch :
```
sudo pacman -S android-tools
```

#### RedHat/Fedora
Ou autres distributions basées sur Redhat :
```
sudo dnf install android-tools
```

#### OpenSUSE
```
sudo zypper install android-tools
```

###
4. Pour télécharger la dernière version de l'outil, rendez vous [ici](https://github.com/0x192/universal-android-debloater/releases). Cliquez sur "Assets" et une liste de fichiers vous sera proposée.
Choisissez l'outil en fonction de votre système d'exploitation : ici, nous choisirons la [version 'uad_gui-linux.tar.gz'](https://github.com/0x192/universal-android-debloater/releases/download/0.5.1/uad_gui-linux.tar.gz)

> **Des versions "...-opengl" sont également disponibles**.
> Ne les téléchargez que si la version normale ne fonctionne pas chez vous...
> 
> Il est possible que vous deviez lancer de nouveau ce logiciel à chaque mise à jour du système car certaines applications système peuvent avoir été réinstallées.
{.is-info}

# Utilisation de l'outil

> Dans la suite du tutoriel, nous nous occupons d'un téléphone Samsung Galaxy S8, nom de code SM-G950F que vous verrez apparaître dans l'outil. Ce nom de code sera différent chez vous s'il ne s'agit pas d'un Galaxy S8 !
{.is-info}

Nous supposerons que le fichier a été téléchargé dans votre 'HOME' (`~/`) et dans le répertoire 'Téléchargements'.

1. Veuillez tout d'abord connecter votre téléphone à l'ordinateur et accepter sur le téléphone les demandes d'autorisation qui apparaissent (avec une potentielle autorisation d'un certificat), puis au choix :

## Tabs {.tabset}
### Via interface graphique

Pour ceux qui préfèrent passer par l'interface graphique, procédez comme suit :

![](/images/uad-0-1.png =900x){.align-center}
![](/images/uad-0-2.png =900x){.align-center}

> Les impressions-écran ci-dessus sont issues d'une distribution sur base GNOME. Cela peut être différent chez vous selon la distro et le DE choisis.
{.is-warning}

### Via ligne de commandes

Ouvrez un terminal et procédez comme suit :

```bash
cd ~/Téléchargements/
tar xzvf uad_gui-linux.tar.gz
sudo ./uad_gui-linux
```

##

L'application se lance et vous verrez apparaître cette fenêtre :

![](/images/uad-1.png =700x){.align-center}

---
Une (très longue) liste est susceptible d'être créée, mais l'outil va nous aider quelque peu.

Nous avons mis en avant 2 principaux paramètres qu'il est important de mettre en lumière :

![](/images/uad-1-1.png =700x){.align-center}

- Le *premier paramètre* à noter est le paramètre "user0" : chaque paquet que vous sélectionnerez sera désinstallé du profil en question, à savoir "user0". Si vous avez créé plusieurs profils distincts, l'outil vous proposera également ces profils au choix (ex. "user1", "user2", etc.). Vous devrez, dans ce cas, choisir pour chaque profil les paquets à désinstaller.

> Mais l'avantage de ce paramètre est que la désinstallation se fera uniquement sur le profil sélectionné et non de l'appareil lui-même ; si jamais cette désinstallation se passe mal, le paquet pourra toujours être restauré, ce qui est bien pratique en cas de dysfonctionnements.

- Le *second paramètre* important est le paramètre "Recommended" : une liste de choix vous est donnée par l'application concernant les paquets que vous pouvez désinstaller. Suivant ce choix, la liste peut être plus ou moins fournie, et si vous sélectionnez par exemple "Expert", les paquets système apparaissent.

![](/images/uad-1-2.png =700x){.align-center}

> **Attention : nous ne recommandons aucun autre paramètre que "Recommended"**.
> Ce paramètre propose (au maximum) les paquets pour éviter au téléphone d'entrer dans une boucle de boot infinie. Les paramètres additionnels ("advanced", "expert") doivent être sélectionnés uniquement si vous maîtrisez ce que vous faites et les conséquences potentielles.
{.is-warning}

2. Vous pouvez sélectionner la totalité des paquets pour désinstallation ("Select All" en bas à gauche). Néanmoins, si vous êtes précautionneux, pour chaque paquet que vous jugerez non essentiel, cochez simplement la case. 

> Nous vous recommandons de faire bien attention à ce que vous allez supprimer néanmoins.
{.is-warning}

Pour chaque paquet, il est possible d'avoir une explication. 

Voici quelques exemples :
**Pour ce paquet "com.cnn.mobile.android.phone.edgepanel" :**

![](/images/uad-2.png =700x){.align-center}

L'application nous donne un aperçu des fonctionnalités de ce paquet. Ici, nous n'avons vraiment pas besoin que CNN vienne nous donner des informations, nous allons cocher pour pouvoir supprimer ce paquet plus tard.

**Pour les 4 paquets "com.facebook.*"  :**

![](/images/uad-3.png =700x){.align-center}

Dans ce second exemple, nous pouvons voir que ce téléphone contient une version de Facebook pré-installée. Vu que je ne souhaite pas Facebook, nous allons pouvoir la supprimer intégralement du téléphone (non seulement le paquet principal mais aussi tous les paquets annexes).

**Pour ce paquet "com.hiya.star"  :**

![](/images/uad-4.png =700x){.align-center}

Visiblement, à la lecture de leur politique de vie privée, le développeur vous alerte sur ce paquet, qui risque fort de mettre à mal votre vie privée. Il s'agit néanmoins d'un fournisseur de service de détection d'appel de type spam ou suspicieux, qui pourrait donc servir à certains. Il vous appartient de choisir de faire confiance ou non à ce fournisseur de service.

**Pour ces paquets "com.microsoft.*"  :**

![](/images/uad-5.png =700x){.align-center}

Il ne nous semble pas nécessaire d'expliquer en quoi nous supprimons ces paquets, vous l'aurez certainement compris :) !

3. Une fois votre sélection faite, cliquez sur "Uninstall Selection" en bas à droite de l'application. Attendez jusqu'à ce que le nombre de paquets à supprimer soit de 0. La liste sera mise à jour et nettoyée des paquets supprimés.

4. Redémarrez votre téléphone.

5. Enfin, testez **toutes** les fonctionnalités pour vérifier son bon fonctionnement.

> Si d'aventure le téléphone ne fonctionnait pas de manière optimale, il est tout à fait possible de relancer l'outil et réinstaller les paquets qui pourraient poser problèmes.
{.is-info}

---
> **Vous avez enfin terminé le *debloat* de votre téléphone !**
{.is-success}

# Conclusion

La liste est extrêmement longue sur notre téléphone Samsung (il pourrait en être de même pour vos téléphones Samsung, mais aussi Huawei, Oppo, etc.) , et nous devons passer en revue _**chaque paquet**_ pour vérifier si nous laissons ou supprimons. 

> Il est à noter que si vous n'êtes pas absolument sûr du paquet et de sa suppression, le mieux est de le laisser, au risque de rendre votre téléphone instable voire inutilisable !
{.is-danger}

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo*
<br>