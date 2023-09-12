---
title: Chiffrer un document PDF
description: Cet article vous présente une solution rapide afin de chiffrer un document PDF
published: true
date: 2023-04-02T14:41:34.229Z
tags: chiffrement, pdf
editor: markdown
dateCreated: 2023-01-05T13:30:28.735Z
---

Voici une façon de rapidement chiffrer un document PDF.

# Installation de l'outil

Nous allons simplement pouvoir le faire sur Linux, en utilisant l'outil `pdftk`. Entrez les commandes suivantes avec des droits administrateur :

## Tabs {.tabset}
### Debian/Ubuntu
Ou autres distributions basées sur Ubuntu ou Debian :
```
sudo apt install pdftk
```

### Arch Linux
Ou autres distributions basées sur Arch :
```
sudo pacman -S pdftk
```

### RedHat/Fedora
Ou autres distributions basées sur Redhat :
```
sudo dnf install pdftk
```

### OpenSuse
```
sudo zypper install pdftk
```


# Utilisation

Une simple commande nous permettra d'utiliser cet outil :
*Mettons que vous avez un PDF nommé "mon-pdf.pdf" et que vous souhaitez le protéger par mot de passe.**

```
pdftk mon-fichier.pdf output mon-fichier-chiffre.pdf user_pw 1234
```    

**Le mot de passe permettant de le déchiffrer étant 1234 comme vous pouvez le voir.**

> Ce mot de passe est à envoyer au destinataire via un moyen sécurisé bien entendu, et pas dans le même message que le fichier chiffré lui-même !
{.is-warning}

Fichier qui sera déchiffrable sur n'importe quel outil propriétaire ou non.

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo*