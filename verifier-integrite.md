---
title: Comment vérifier l'intégrité ?
description: Ce tutoriel vous montre comment vérifier l'intégrité et la signature d'un fichier...
published: true
date: 2023-09-10T14:02:30.797Z
tags: 
editor: markdown
dateCreated: 2023-04-14T17:53:30.746Z
---

Nous allons tenter dans cette partie de passer à la pratique, en effectuant une vérification d'intégrité suivant deux méthodes.

# Méthode de l'empreinte

## Bibliothèques nécessaires

Sur la plupart des distributions GNU/Linux, les outils de calcul et vérification d'empreintes sont la plupart du temps installés par défaut (ex. : md5sum, sha256sum...). Si ce n'est pas le cas sur votre système, vous pouvez exécuter la commande suivante dans un terminal avec des droits administrateur et installer **Coreutils [^²]** qui contient une grande partie des utilitaires standards shell :

### Tabs {.tabset}
#### Debian/Ubuntu
Ou autres distributions basées sur Ubuntu ou Debian :
```bash
apt install coreutils
```

#### Arch Linux
Ou autres distributions basées sur Arch :
```bash
pacman -S coreutils
```

#### RedHat/Fedora
Ou autres distributions basées sur Redhat :
```bash
dnf install coreutils
```

#### OpenSuse
```bash
zypper install coreutils
```

[^²]: [Coreutils](https://www.gnu.org/software/coreutils/manual/html_node/Summarizing-files.html#Summarizing-files)

## Vérification d'intégrité

Afin de vérifier l'intégrité d'un fichier (il peut s'agir également d'un répertoire) ayant une empreinte, assurez-vous d'avoir le fichier ainsi que son empreinte. Cette empreinte se trouve sous la forme d'une suite de chiffres et de lettres d'une certaine longueur suivant l'algorithme utilisé (exemple pour du MD5 : 8747e564eb53cb2f1dcb9aae0779c2aa).

Prenons l'exemple avec un fichier image ISO, nommé "monfichier.iso", téléchargé et disponible sur votre système dans le dossier Téléchargements. Le fournisseur du fichier vous indique qu'il a calculé son empreinte avec la fonction MD5 et qu'il obtient une valeur de : 8747e564eb53cb2f1dcb9aae0779c2aa.

> Note : ceci n'est qu'un exemple car comme nous l'avons vu plus haut, MD5 n'est plus un algorithme recommandé. Si toutefois le fournisseur du fichier ne fournit qu'une empreinte MD5, vous pouvez toujours la vérifier, à vos risques et périls...
{.is-info}

Sur votre machine, `cd ~/Téléchargements/` puis exécutez la commande suivante dans un terminal :
```bash
md5sum monfichier.iso
```
```brainfuck
8747e564eb53cb2f1dcb9aae0779c2aa  monfichier.iso
```

Vous obtenez donc une suite de chiffres et de lettres. Bravo vous venez de calculer votre première empreinte ou hash !

Comparez maintenant ce résultat avec le résultat donné par le fournisseur du fichier (pour rappel 8747e564eb53cb2f1dcb9aae0779c2aa) :
-   **Si celui-ci est le même, le fichier est sain.** Il s'avère que dans notre cas, la valeur est la même donc le fichier est fiable.
-   **Dans le cas contraire, le fichier est altéré**. Dans ce cas, il convient de le télécharger à nouveau à partir du même site ou de ses miroirs et de tenter de nouveau la vérification de l'empreinte.

Il est également possible de procéder différemment : si le fournisseur a généré un fichier additionnel, par exemple **monfichier.iso.sum** (contenant la valeur de l'empreinte), vous pourrez le télécharger sur votre machine et exécuter les commandes suivantes :
```bash
md5sum -c monfichier.iso monfichier.iso.sum
```
```brainfuck
monfichier.iso: Réussi
```

Dans le cas contraire, si le fichier est altéré voici ce que vous obtiendrez :
```brainfuck
monfichier.iso: Échec
md5sum: Attention : 1 somme de contrôle ne correspond pas
```

### Cas SHA

Si le fournisseur du fichier vous propose une empreinte calculée avec les fonctions de hachage de la famille SHA2 ou SHA3 (SHA256, SHA384 par exemple), il s'agira de procéder de la même manière mais avec une commande différente :
```
shaXXXsum monfichier.iso
```
_Avec_ `XXX` = 224, 256, 384 ou 512.
Vous obtenez une suite de chiffres et de lettres : il s'agit de l'empreinte de votre fichier téléchargé, par exemple 43b796f15f57192dd813306938d199871d9d8b881c0124b43412d81585c0efd5 (empreinte calculée via sha256).

# Méthode de la signature numérique

Nous l'avons vu plus haut, une signature numérique peut être créée tout autant pour assurer l' *intégrité* d'une donnée que pour en assurer également l' *authenticité* ce qui renforce la confiance accordée. Une sorte de protection 2 en 1, cool non ?! Ce mécanisme fait appel à la **cryptographique asymétrique** en plus de l'utilisation d'une fonction de hachage qui nous permettra d'obtenir l'empreinte.

Nous allons nous concentrer dans cette partie sur un des mécanismes les plus utilisés par le grand public pour les signatures numériques : PGP et son standard open source OpenPGP. Toutes les commandes ci-après sont relatives au logiciel GNU/Linux qui implémente ce standard [^³]. Je vous renvoie à l'article concernant le mécanisme [PGP](./chiffrement.md##pgp-gpg) (et son implémentation GnuPG) afin de (re)lire et comprendre.

[^³]: [GnuPG](https://www.gnupg.org/_GnuPG)

## Bibliothèques nécessaires
Si GnuPG n'est pas déjà installé sur votre système, exécutez cette commande dans un terminal avec des droits administrateur :

### Tabs {.tabset}
#### Debian/Ubuntu
Ou autres distributions basées sur Ubuntu ou Debian :
```
apt install gnupg2
```

#### Arch Linux
Ou autres distributions basées sur Arch :
```
pacman -S gnupg2
```

#### RedHat/Fedora
Ou autres distributions basées sur Redhat :
```
dnf install gnupg2
```

#### OpenSuse
```
zypper install gnupg2
```


## Vérification de la signature

Dans la suite de l'article nous utiliserons la commande `gpg2`. Si celle-ci n'est pas effective, utilisez dans votre cas `gpg`.
  
**Nous allons appliquer notre cas pratique sur la vérification de la signature du fichier d'empreinte (SHA par exemple) d'une image ISO de Linux Mint 20.3, disponible sur le mirroir [https://mirror.crexio.com/linuxmint/isos/stable/20.3/ Mirroir1](https://mirror.crexio.com/linuxmint/isos/stable/20.3/_Mirroir1 "wikilink")**

Sur le même principe que le fichier contenant l'empreinte vu dans la partie précédente, certains fournisseurs permettent de télécharger un autre type de fichier contenant ou lié à une signature numérique. Généralement, vous verrez ici des fichiers annexes avec une extension `.asc` ou `.gpg` (bien que ces extensions soient majoritairement utilisées d'une mauvaise manière : **asc** signifierait un fichier ASCII tandis que **gpg** un fichier binaire. La réalité est parfois différente, donc ne vous fiez jamais à ces extensions). Si le fichier est de type ASCII, il sera lisible avec n'importe quel éditeur de texte.

Nous partirons du principe que vous avez déjà téléchargé le fichier `sha256sum.txt` qui contient l'empreinte de l'ISO.
Téléchargeons également le fichier lié à la signature numérique `sha256sum.txt.gpg`.
Vous pouvez ouvrir ce fichier avec n'importe quel éditeur de texte puisqu'il s'agit en fait d'un fichier ASCII et non binaire (je vous avais dit de ne pas vous fier aux extensions !).

Voici son contenu :
```
-----BEGIN PGP SIGNATURE-----
iQIzBAABCgAdFiEEJ96xVkTGs88719KRMA+Ea6JbrgkFAmHgoF4ACgkQMA+Ea6Jb
rglrYRAApoF9qyaixnA+PmX0pueJSJMRjDXAMmRzvKwUkkqt+CGI2NKiwoYgKDKW
pBVZz0fEycLi9vAVxbtyBKbxr/rqZY+wnKJr6o3FKXa8J/EcRyU/QPCEKz2Y20y4
QhkHwQ2VN+6N8tnxQ47jsHwvZg4GqQmY/CS9lQH4HuvrZJfJF/taMUYBy/tUxhxs
JSw2EfM3pUP+3iDTZul9uecTHFbo062dtmD8kj0B/DuKHVA2phOa7ud9lHQuMOHB
vsj5R3YkRN8OFRnTSzMZMCDsX/IW5BPtBK22pkuvMQn8mmrfkDQsP9G3j3LeAEoZ
jkLmk/dmDhW7CIGv4ZwAn/4huOrFufygUurVsj6T8MZyx5cJ7xgybTdWyeiH+30E
+zn15nJmNkRXz05BUppzjv1hqO51ce3advw2sMeW+TmcEkT/gwr10ucPLpiPsxPF
wetH+RGkFdUpyDME+XT6t9gvdaeN078hKZahI88tRR+AJEZ88Z1IAahy0GegtF0m
xfcfnSk3bulNjzKqiNYbjSGjN2BVweBz/1Fsa9BJ+vvREHPfsiqV2IFIdUn9Knfi
wiw4znKNXzZCHfK2qK4iqg55CdG7L2RFZ+4XiRRIo5pkGMS/wzkPIK9pyfI+uyjP
u9l+qfxt4M9kYs0ymXd7MuRKnsyv6sU1gwhmiG8IKaHFoL0BIb4==SVgr
-----END PGP SIGNATURE-----
```

Vous pouvez voir ici qu'il n'y a rien de très compliqué : une en-tête *BEGIN PGP SIGNATURE*, une suite de chiffres et lettres d'une certaine longueur et un bloc de fin *END PGP SIGNATURE*. Voilà, vous venez de découvrir le formalisme d'une signature numérique PGP !

Souvenez-vous, nous avons évoqué plus haut l'échange d'un secret partagé, en l'occurrence ici l'échange d'une *clé publique* de l'auteur de la signature numérique. Dans notre cas pratique, il va nous falloir rapatrier cette clé publique qui a été générée par le fournisseur de la donnée. Généralement, ces fournisseurs mettent à disposition leurs clés publiques sur des "serveurs de clés". Nous n'avons plus qu'à les télécharger puis à vérifier la signature.

La documentation Linux Mint nous indique que la clé publique de signature est disponible sur un serveur de clés accessible ici \[hkp://keyserver.ubuntu.com:80\]

*Note : si la commande wget n'est pas disponible sur votre distribution, installez-là !*

Passons sur un terminal, rendez-vous dans Téléchargements (`cd Téléchargements/`) :
Les fichiers présents sont :
```brainfuck
linuxmint-20.3-cinnamon-64bit.iso sha256sum.txt.gpg sha256sum.txt
```
La commande suivante :
```bash
gpg2 --keyserver hkp://keyserver.ubuntu.com:80 --recv-key "27DE B156 44C6 B3CF 3BD7  D291 300F 846B A25B AE09"
```
Donne :
```brainfuck
gpg: clef 300F846BA25BAE09 : clef publique « Linux Mint ISO Signing Key <root@linuxmint.com> » importée
gpg: Quantité totale traitée : 1
gpg:               importées : 1
```
Et celle-ci :
```bash
gpg2 --verify sha256sum.txt.gpg sha256sum.txt
```
Donne :
```brainfuck
gpg: Signature faite le jeu. 13 janv. 2022 22:57:50 CET
gpg:                avec la clef RSA 27DEB15644C6B3CF3BD7D291300F846BA25BAE09
gpg: Bonne signature de « Linux Mint ISO Signing Key <root@linuxmint.com> » [inconnu]
gpg: Attention : cette clef n'est pas certifiée avec une signature de confiance.
gpg:          Rien n'indique que la signature appartient à son propriétaire.
Empreinte de clef principale : 27DE B156 44C6 B3CF 3BD7  D291 300F 846B A25B AE09
```

Quelques explications :

-   Nous utilisons `gpg2 --keyserver` pour aller interroger le serveur de clés sur lequel la clé de signature est déposée. Cette clé porte l'identifiant (en fait, il s'agit ni plus ni moins que l'empreinte de la clé elle même !) 27DEB15644C6B3CF3BD7D291300F846BA25BAE09 et est donc téléchargée dans notre propre gestionnaire de clés GPG.
-   Puis nous utilisons `gpg2 --verify` entre le fichier contenant les empreintes SHA-256 et la signature de ce fichier.

Ici, nous voyons qu'il est indiqué **Bonne signature** ce qui prouve que le fichier sha256sum.txt a bien été signé par cette clé A25BAE09.
Dans le cas contraire, vous auriez reçu ce message :
```brainfuck
gpg: Signature faite le jeu. 13 janv. 2022 22:57:50 CET
gpg:                avec la clef RSA 27DEB15644C6B3CF3BD7D291300F846BA25BAE09
gpg: MAUVAISE signature de « Linux Mint ISO Signing Key <root@linuxmint.com> » [inconnu]
```

Vous pouvez lire également cette mention :
```brainfuck
gpg: Attention : cette clef n'est pas certifiée avec une signature de confiance.
gpg: Rien n'indique que la signature appartient à son propriétaire.
```

Cela n'indique pas que la signature est fausse mais indique que nous n'avons pas encore validé la clé rapatriée comme clé de **confiance**. Cela peut être fait en ajoutant cette clé dans notre trousseau et en la signant avec notre propre clé privée. Je vous renvoie vers l'article sur [PGP/GPG](./chiffrement.md.md##pgp-gpg) pour plus de détails sur cet aspect.

> Attention ici, il ne s'agit que d'une utilisation de GPG ; en effet, dans notre cas pratique, nous ne vérifions que le fichier .txt d'empreintes de l'image ISO et non l'image elle-même, car les développeurs de Linux Mint n'ont pas jugé intéressant d'ajouter une signature à l'image ISO ; les empreintes calculées suffiraient d'après leurs dires.
> **Il ne s'agit ici que d'appréhender la logique : l'utilisation des clés publiques dans la chaîne de vérification.**
{.is-info}

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo*
<br>