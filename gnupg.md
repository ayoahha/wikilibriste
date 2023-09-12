---
title: Utilisation de GPG dans son quotidien
description: 
published: true
date: 2023-04-15T11:09:09.278Z
tags: gpg
editor: markdown
dateCreated: 2023-04-14T17:44:38.124Z
---

Bien configurer son outil
=========================

Nous allons dans la suite de cet article utiliser le logiciel GnuPG en lignes de commandes (CLI) qui implémente le standard open source OpenPGP. L'avantage d'utiliser les commandes est que ça ne dépend d'aucune plateforme, bien que nous resterons sur une distribution GNU/Linux. Ce logiciel est par défaut généralement embarqué dans toutes les distributions GNU/Linux. Si ce n'est pas le cas exécutez cette commande dans un terminal avec des droits administrateur (sudo) :

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

###
Dans toute la suite de l'article nous utiliserons la commande `gpg2`. Si celle-ci n'est pas effective, utilisez dans votre cas `gpg`.

Nous allons donc au préalable configurer l'outil, afin qu'il remplisse parfaitement les exigences de sécurité du moment (force des algorithmes, longeur des clés, etc.). Vous trouverez le fichier de configuration `gpg.conf` dans votre répertoire 'HOME' (~/) dans un répertoire caché nommé *.gnupg*. Si le fichier n'existe pas, vous devrez le créer :

```
touch ~/.gnupg/gpg.conf

chmod 600 ~/.gnupg/gpg.conf
```

Vérifiez (ou ajoutez) les paramètres suivants :
```brainfuck
    # Limite les informations diffusées pour les clés
    no-emit-version
    no-comments
    export-options export-minimal

    # Permet d'afficher le format long de l'ID des clefs et leurs empreintes pour éviter toute collision
    keyid-format 0xlong
    with-fingerprint
    #fixed-list-mode #Devenu inutile depuis gnupg v2

    # Affiche la validité des clefs
    list-options show-uid-validity
    verify-options show-uid-validity

    # Limite les algorithmes utilisés
    personal-cipher-preferences AES256
    personal-digest-preferences SHA512
    default-preference-list SHA512 SHA384 SHA256 RIPEMD160 AES256 TWOFISH BLOWFISH ZLIB BZIP2 ZIP Uncompressed

    cipher-algo AES256
    digest-algo SHA512
    cert-digest-algo SHA512
    compress-algo ZLIB

    # Désactive les algorithmes faibles
    disable-cipher-algo 3DES
    weak-digest SHA1

    # S2K (String-to-Key) - RFC4880 - 3.7
    # Paramètres de la phrase de passe des clefs
    s2k-cipher-algo AES256
    s2k-digest-algo SHA512
    s2k-mode 3
    # Le paramètre s2k-count peut être réduit sur les machines peu puissantes
    # Ce paramètre doit être compris entre 1024 et 65011712
    s2k-count 65011712
```

> **Veiller à copier ces paramètres sur TOUTES les machines que vous utiliserez pour signer et chiffrer.**
{.is-warning}


Voilà, nous venons d'indiquer au logiciel les paramètres de sécurité à utiliser pour la suite. A savoir qu'ici, les bonnes pratiques pour des clés PGP est d'utiliser :
-   L'algorithme RSA, avec une longueur de clé de 4096 bits au minimum. Vous pouvez tenter une longueur de 8192 bits, mais attention, peu de logiciels savent utiliser cette longueur.
-   L'algorithme ECC, avec une longueur de clé de 384 bits au minimum. Uniquement disponible pour les fonctions de signature et d'authentification. 
Par ordre de préférence, voici les choix recommandés pour ECC :
    -   Curve 25519
    -   NIST P-521
    -   Brainpool P-512
    -   Brainpool P-384
    -   NIST P-384
**On évitera autant que faire se peut les tailles de 256 bits :**
    -   NIST P-256
    -   secp256k1
    -   Brainpool P-256

> Pour les détails en ce qui concerne les aspects algorithmes et robustesse, nous vous renvoyons vers l'article [dédié](./chiffrement.md#).
{.is-warning}


Créer sa clé maitre
===================

Comme vu précédemment, la clé maitre doit être la base de toute la confiance dans PGP (comme d'ailleurs dans les autres mécanismes de certificat, X 509 par exemple). A ce titre celle-ci doit être générée et gardée de façon sécurisée. Voici les pré-requis à respecter :
-   Phase de génération sur un ordinateur _non connecté_ au réseau internet (filaire ou Wifi), c'est à dire hors ligne
-   Si possible sur une machine secondaire avec une distribution toute fraiche, voire carrément sur une distro axée sécurité comme Tails OS
-   Si possible sur un disque dur chiffré

Nous allons utiliser la commande *complète* afin de bien maitriser la génération. Dans notre exemple, nous ne génèrerons que 2 sous-clés (une pour la signature et une pour le chiffrement), vous pouvez tout à fait en générer une 3è pour l'authentification, ce n'est pas ce que nous avons choisi :

```bash
gpg2 --full-gen-key --expert
```

Vous allez obtenir une sortie à cette commande, sous forme de questions. Nous mettons les questions les unes à la suite des autres afin d'éviter d'alourdir l'article, vérifiez donc bien étape par étape tout ce qui est écrit :
```brainfuck
    gpg (GnuPG) 2.2.19; Copyright (C) 2019 Free Software Foundation, Inc.
    This is free software: you are free to change and redistribute it.
    There is NO WARRANTY, to the extent permitted by law.

    Sélectionnez le type de clef désiré :
       (1) RSA et RSA (par défaut)
       (2) DSA et Elgamal
       (3) DSA (signature seule)
       (4) RSA (signature seule)
       (7) DSA (indiquez vous-même les capacités)
       (8) RSA (indiquez vous-même les capacités)
       (9) ECC et ECC
      (10) ECC (signature seule)
      (11) ECC (indiquez vous-même les capacités)
      (13) Clef existante
      (14) Existing key from card
    Quel est votre choix ? 8

    Actions possibles pour une clef RSA : Signer Certifier Chiffrer Authentifier 
    Actions actuellement permises : Signer Certifier Chiffrer 

       (S) Inverser la capacité de signature
       (C) Inverser la capacité de chiffrement
       (A) Inverser la capacité d'authentification
       (Q) Terminé

    Quel est votre choix ? s

    Actions possibles pour une clef RSA : Signer Certifier Chiffrer Authentifier 
    Actions actuellement permises : Certifier Chiffrer 

       (S) Inverser la capacité de signature
       (C) Inverser la capacité de chiffrement
       (A) Inverser la capacité d'authentification
       (Q) Terminé

    Quel est votre choix ? c

    Actions possibles pour une clef RSA : Signer Certifier Chiffrer Authentifier 
    Actions actuellement permises : Certifier 

       (S) Inverser la capacité de signature
       (C) Inverser la capacité de chiffrement
       (A) Inverser la capacité d'authentification
       (Q) Terminé

    Quel est votre choix ? q
    les clefs RSA peuvent faire une taille comprise entre 1024 et 4096 bits.
    Quelle taille de clef désirez-vous ? (3072) 4096
    La taille demandée est 4096 bits
    Veuillez indiquer le temps pendant lequel cette clef devrait être valable.
             0 = la clef n'expire pas
          <n>  = la clef expire dans n jours
          <n>w = la clef expire dans n semaines
          <n>m = la clef expire dans n mois
          <n>y = la clef expire dans n ans
    Pendant combien de temps la clef est-elle valable ? (0) 0
    La clef n'expire pas du tout
    Est-ce correct ? (o/N) o

    GnuPG doit construire une identité pour identifier la clef.

    Nom réel : Jean Dupont
    Adresse électronique : jean.dudu@pont.fr
    Commentaire : 
    Vous avez sélectionné cette identité :
        « Jean Dupont <jean.dudu@pont.fr> »

    Changer le (N)om, le (C)ommentaire, l'(A)dresse électronique
    ou (O)ui/(Q)uitter ? o
```

A cet instant, une invite de commande ou fenêtre vous demande de saisir une phrase de passe ou un mot de passe pour cette clé. Choisissez un mot de passe extrêmement fort et retenez le bien, vous en aurez besoin. Ensuite :
```brainfuck
    De nombreux octets aléatoires doivent être générés. Vous devriez faire
    autre chose (taper au clavier, déplacer la souris, utiliser les disques)
    pendant la génération de nombres premiers ; cela donne au générateur de
    nombres aléatoires une meilleure chance d'obtenir suffisamment d'entropie.
    gpg: clef 0xA6F76D3B09BC268A marquée de confiance ultime.
    gpg: revocation certificate stored as '/home/user/.gnupg/openpgp-revocs.d/5445E89C355F4FB4E6533D47A6F76D3B09BC268A.rev'
    les clefs publique et secrète ont été créées et signées.

    pub   rsa4096/0xA6F76D3B09BC268A 2022-11-14 [C]
          Empreinte de la clef = 5445 E89C 355F 4FB4 E653  3D47 A6F7 6D3B 09BC 268A
    uid                              Jean Dupont <jean.dudu@pont.fr>
```

> **Voilà, vous venez de créer votre première bi-clé PGP/GPG. Bravo !**
{.is-success}


Quelques remarques ici :
-   `clef 0xA6F76D3B09BC268A marquée de confiance ultime`. Notez bien l'ID de votre clé, en l'occurence ici 0xA6F76D3B09BC268A, nous en aurons besoin par la suite.
-   Notez en face de la clé dont la date de création 2022-11-14 qu'un " C " est présent : cela correspond à la fonction de la bi-clé. Ici il s'agit de la fonction de \[C\]ertification, sous-entendu certification de sous-clés ou d'autres clés.
-   Remarquez également que les métadonnées " Nom, Prénom et adresse courriel " sont bien incluses dans les clés. Ces données seront partagées avec les clés publiques, donc il est important de comprendre que générer des clés PGP n'a pas pour objectif l'anonymat, mais la sécurité et la fiabilité de l'information. Si nécessaire, il est possible d'utiliser du pseudonymat, mais dans ce cas, cela casse le principe et le côté *confiance* de PGP.

Créer ses sous-clés
===================

Passons maintenant à la génération des sous-clés. Souvenez-vous, nous avions spécifié que chaque sous-clé devait avoir une seule fonction de sécurité. Nous allons respecter cette exigence et allons créer 2 sous-clés :
-   Une première dédiée au chiffrement, fonction \[E\] (E pour Encryption)
-   Une seconde dédiée aux signatures, fonction \[S\] (S pour ... Bon je vais pas tout vous traduire !)

*Dans la suite, vous pourrez utiliser l'ID de la bi-clé maitre ou bien l'adresse courriel associée (dans notre cas : jean.dudu@pont.fr). GPG sait reconnaitre l'un ou l'autre. En ce qui nous concerne, nous utiliserons l'ID (0xA6F76D3B09BC268A).*

```bash
gpg2 --edit-key 0xA6F76D3B09BC268A
```
```brainfuck
		gpg (GnuPG) 2.2.19; Copyright (C) 2019 Free Software Foundation, Inc.
    This is free software: you are free to change and redistribute it.
    There is NO WARRANTY, to the extent permitted by law.

    La clef secrète est disponible.

    gpg: vérification de la base de confiance
    gpg: marginals needed: 3  completes needed: 1  trust model: pgp
    gpg: profondeur : 0  valables :   1  signées :   0
         confiance : 0 i., 0 n.d., 0 j., 0 m., 0 t., 1 u.
    sec  rsa4096/0xA6F76D3B09BC268A
         créé : 2022-11-14  expire : jamais       utilisation : C   
         confiance : ultime        validité : ultime
    [  ultime ] (1). Jean Dupont <jean.dudu@pont.fr>
```

Vous vous retrouvez ici avec un prompt de l'outil GPG. Nous allons donc taper une suite de commandes très simples afin de générer ces 2 sous-clés :
*A la suite de la commande `addkey`, GPG vous demande d'entrer le mot de passe de la clé maitre précédemment créée.*
```brainfuck
    gpg> addkey
    Sélectionnez le type de clef désiré :
       (3) DSA (signature seule)
       (4) RSA (signature seule)
       (5) Elgamal (chiffrement seul)
       (6) RSA (chiffrement seul)
      (14) Existing key from card
    Quel est votre choix ? 4
    les clefs RSA peuvent faire une taille comprise entre 1024 et 4096 bits.
    Quelle taille de clef désirez-vous ? (3072) 4096
    La taille demandée est 4096 bits
    Veuillez indiquer le temps pendant lequel cette clef devrait être valable.
             0 = la clef n'expire pas
          <n>  = la clef expire dans n jours
          <n>w = la clef expire dans n semaines
          <n>m = la clef expire dans n mois
          <n>y = la clef expire dans n ans
    Pendant combien de temps la clef est-elle valable ? (0) 0
    La clef n'expire pas du tout
    Est-ce correct ? (o/N) o
    Faut-il vraiment la créer ? (o/N) o
    De nombreux octets aléatoires doivent être générés. Vous devriez faire
    autre chose (taper au clavier, déplacer la souris, utiliser les disques)
    pendant la génération de nombres premiers ; cela donne au générateur de
    nombres aléatoires une meilleure chance d'obtenir suffisamment d'entropie.

    sec  rsa4096/0xA6F76D3B09BC268A
         créé : 2022-11-14  expire : jamais       utilisation : C   
         confiance : ultime        validité : ultime
    ssb  rsa4096/0x2C7E486743774AEA
         créé : 2022-11-14  expire : jamais       utilisation : S   
    [  ultime ] (1). Jean Dupont <jean.dudu@pont.fr>
```
```brainfuck
    gpg> addkey
    Sélectionnez le type de clef désiré :
       (3) DSA (signature seule)
       (4) RSA (signature seule)
       (5) Elgamal (chiffrement seul)
       (6) RSA (chiffrement seul)
      (14) Existing key from card
    Quel est votre choix ? 6
    les clefs RSA peuvent faire une taille comprise entre 1024 et 4096 bits.
    Quelle taille de clef désirez-vous ? (3072) 4096
    La taille demandée est 4096 bits
    Veuillez indiquer le temps pendant lequel cette clef devrait être valable.
             0 = la clef n'expire pas
          <n>  = la clef expire dans n jours
          <n>w = la clef expire dans n semaines
          <n>m = la clef expire dans n mois
          <n>y = la clef expire dans n ans
    Pendant combien de temps la clef est-elle valable ? (0) 0
    La clef n'expire pas du tout
    Est-ce correct ? (o/N) o
    Faut-il vraiment la créer ? (o/N) o
    De nombreux octets aléatoires doivent être générés. Vous devriez faire
    autre chose (taper au clavier, déplacer la souris, utiliser les disques)
    pendant la génération de nombres premiers ; cela donne au générateur de
    nombres aléatoires une meilleure chance d'obtenir suffisamment d'entropie.

    sec  rsa4096/0xA6F76D3B09BC268A
         créé : 2022-11-14  expire : jamais       utilisation : C   
         confiance : ultime        validité : ultime
    ssb  rsa4096/0x2C7E486743774AEA
         créé : 2022-11-14  expire : jamais       utilisation : S   
    ssb  rsa4096/0xD403F40075C53CA0
         créé : 2022-11-14  expire : jamais       utilisation : E   
    [  ultime ] (1). Jean Dupont <jean.dudu@pont.fr>
```

A noter qu'à la génération de chaque sous-clé il vous sera demandé via une invite de commande ou une fenêtre d'entrer un mot de passe. Choisissez-les robustes, mais surtout, retenez les ! A la fin, vous verrez donc un récapitulatif avec les 3 bi-clés générées :
-   La première (la clé maitre) dont la fonction est de certifier (\[C\])
-   Une seconde avec l'ID 0x2C7E486743774AEA dont la fonction est de signer des informations (\[S\])
-   Une troisième avec l'ID 0xD403F40075C53CA0 dont la fonction est de chiffrer des informations (\[E\])

A noter également que j'ai choisi de ne jamais faire expirer les clés (choix 0 = la clef n'expire pas). C'est un choix, à adapter à chaque situation ; en effet, on peut par exemple participer à un projet éphémère uniquement sur 1 an et n'avoir besoin que de signer des informations sur cette période et pas au délà, auquel cas nous ferons expirer nos clés au bout de 1 an (ce principe est sujet à débat dans la communauté). Cette façon de faire est à moduler selon les besoins de chacun et de chaques clés, nous recommandons donc le choix 0 pour la plupart des débutants, et d'autres choix pour ceux qui ont des usages plus avancés. Nous allons maintenant sauvegarder grâce à cette commande :
```brainfuck
gpg> save
```
A cet instant, sur cette machine, vous disposez donc de 3 bi-clés, enfin plus précisément d'une bi-clé maitre et de 2 sous-bi-clés dérivées de la bi-clé maitre :
La commande :
```bash
gpg2 -K
```
vous renvoit :
```brainfuck
		/home/user/.gnupg/pubring.kbx
    ----------------------------
    sec   rsa4096/0xA6F76D3B09BC268A 2022-11-14 [C]
          Empreinte de la clef = 5445 E89C 355F 4FB4 E653  3D47 A6F7 6D3B 09BC 268A
    uid                  [  ultime ] Jean Dupont <jean.dudu@pont.fr>
    ssb   rsa4096/0x2C7E486743774AEA 2022-11-14 [S]
    ssb   rsa4096/0xD403F40075C53CA0 2022-11-14 [E]
```
La commande :
```bash
gpg2 -k
```
vous renvoit :
```brainfuck
    /home/user/.gnupg/pubring.kbx
    ----------------------------
    pub   rsa4096/0xA6F76D3B09BC268A 2022-11-14 [C]
          Empreinte de la clef = 5445 E89C 355F 4FB4 E653  3D47 A6F7 6D3B 09BC 268A
    uid                  [  ultime ] Jean Dupont <jean.dudu@pont.fr>
    sub   rsa4096/0x2C7E486743774AEA 2022-11-14 [S]
    sub   rsa4096/0xD403F40075C53CA0 2022-11-14 [E]
```

*Notez ici que le magasin de clés se nomme `pubring.kbx` et qu'il est de base créé à la première utilisation de l'outil.*

> Bien, nous allons maintenant terminer ce processus en mettant en sécurité la clé maitre, en nettoyant la machine secondaire et en important nos sous-clés sur des machines.
{.is-info}


Bien gérer ses clés
===================

## Révocation

Tout d'abord, intéressons-nous au sujet de la révocation, sujet important dans la gestion des clés et des certificats numériques.

**Mais à quoi peut donc bien servir un certificat de révocation me direz-vous ? Vous êtes impatient de savoir j'en suis sûr...**

Voici les explications : durant le cycle de vie d'une bi-clé maitre, il est admis qu'il existe une probabilité que celle-ci puisse être perdue voire compromise, ou tout simplement que vous ayez oublié le mot de passe de la clé maitre (hum!). On évitera bien entendu ce cas de figure en respectant scrupuleusement la partie précédente, mais la probabilité n'est jamais nulle ! Pour palier ce problème, PGP utilise un moyen qui permet d'identifier un statut particulier d'une clé : une clé dite *révoquée* ne sera plus jugée fiable (c'est à dire que la confiance sera rompue) et il appartiendra aux personnes les utilisant de prendre toutes les précautions nécessaires afin de demander la nouvelle clé.

Pour faire connaitre ce statut, il faudra donc *publier* (sur un serveur de clés) ou transmettre à ses *amis PGP* le fameux **certificat de révocation** et/ou la clé révoquée, qui permettra à l'outil de vous mettre en garde sur la fiabilité de la clé. Rien de plus ! C'est simple, non ?

Pour information, voici à quoi ressemble un certificat de révocation (format ASCII) :
```
    -----BEGIN PGP PUBLIC KEY BLOCK-----
    Comment: This is a revocation certificate

    iQI2BCABCgAgFiEEVEXonDVfT7TmUz1HpvdtOwm8JooFAmNyWboCHQIACgkQpvdt
    Owm8JopsAA/+POQfYqLQ6ykT8djqyneI04qcEaVAlhXECy4xyCidraBWoaiz0oD/
    YPnQPBjJJNh4I+4iVgqyuVXzSSAkDDh7n+IP4xFnfg+02MCnkM2VzIJnxVf/8iCT
    OUjFzFJ+EMVCVgRCbg7aUfwinuGN7IFuRPgx4bnleQNUaZhrk5HmJ3e62R20K/4s
    OZNrahwYHFiasfXqM5CNSJ7m8j2qLYPDJafoqShvuJcGYvms0p/kBrpj5rzZfL0/
    qnLd+wiZGdXAdImEXCMAtCPIQz5sLxibav9ZqDYpAGYFDzjeC85UoAiO4nSHXdYe
    ql7spwhgubcvQFvUbsY8ttLJu1OKceJ/BdipTsbYRv7kQK7JFcBVIIXIEiTasIya
    Z6dzvOvgcBcsnVJvmmvwU93eOF51evOomMDFGjKqoWKjPWUQJzU02iiuJvLTxa52
    v8YAEpedntUAxByBT9LTSgE5glXENPMRxLzbns7AdZXppMOZMexTmYmk4pcZzQ/7
    w+Uc8D8kODW3Ed3YJFdsgD7+ex67pnr5chm+Pt0qB+TRqAtJAQ1Jo1XmJ3oVwMC3
    k+nGpELMcEHoyGXLw+wwhQ+nNdlyhvnMaSwtgkMgYCY9ouKQ4u6soNHsRa2W8zpM
    p85DYuiQX/PXD6VvvuyZD3RmNWk3uq72cPLpTDRcdg3GfMznBZtK1v4=
    =ypC2
    -----END PGP PUBLIC KEY BLOCK-----
```
Passons au côté pratique : nous l'avons évoqué plus haut, vous allez devoir générer votre certificat de révocation, comme ceci :
*ici nous reprenons l'ID de la clé maitre, générée plus haut, à savoir 0xA6F76D3B09BC268A*

La commande :
```
gpg2 --output ~/.gnupg/A6F76D3B09BC268A.rev --gen-revoke 0xA6F76D3B09BC268A
```
vous renvoit :
```brainfuck
    sec  rsa4096/0xA6F76D3B09BC268A 2022-11-14 Jean Dupont <jean.dudu@pont.fr>

    Faut-il créer un certificat de révocation pour cette clef ? (o/N) o
    choisissez la cause de la révocation :
      0 = Aucune cause indiquée
      1 = La clef a été compromise
      2 = La clef a été remplacée
      3 = La clef n'est plus utilisée
      Q = Annuler
    (Vous devriez sûrement sélectionner 1 ici)
    Quelle est votre décision ? 1
    Entrez une description facultative, en terminant par une ligne vide :
    > 
    Cause de révocation : La clef a été compromise
    (Aucune description donnée)
    Est-ce d'accord ? (o/N) o
    sortie forcée avec armure ASCII.
    Certificat de révocation créé.

    Veuillez le déplacer sur un support que vous pouvez cacher ; toute personne
    accédant à ce certificat peut l'utiliser pour rendre votre clef inutilisable.
    Imprimer ce certificat et le stocker ailleurs est une bonne idée, au cas où le
    support devienne illisible. Attention tout de même : le système d'impression
    utilisé pourrait stocker ces données et les rendre accessibles à d'autres.
```

Deux choses ici :
-   Après le choix de la cause de la révocation, vous pouvez laisser vide la description, en appuyant simplement sur "ENTREE".
-   Après la ligne "Est-ce d'accord ? (o/N)", entrez le mot de passe de votre clé maitre. Grâce à ces commandes, vous obtiendrez le certificat de révocation, qui sera disponible sous votre répertoire 'HOME' dans le répertoire gnupg correspondant (~/.gnupg/), et portant le nom `A6F76D3B09BC268A.rev`.

> **Allez, nous y sommes presque, plus que quelques actions...**
{.is-success}


## Stockage

Souvenez-vous, nous avions posé des pré-requis afin de respecter les exigences de sécurité. Nous allons ici partir du principe que vous avez scrupuleusement respecté les exigences de génération de clés spécifiées en début d'article, à savoir l'utilisation d'une machine hors ligne (voire secondaire), ou d'un live USB voire de Tails OS.

Afin de sécuriser la clé maitre (surtout la clé privée) et de rappatrier les clés pour une utilisation quotidienne, il va vous falloir vous munir de 3 (deux) clés USB neuves et vierges (1 à 2Go suffit largement, vous en trouverez dans le commerce à moindre prix).
**Pourquoi 3 ?**
-   Pour commencer : 2 clés USB contenant les informations de votre bi-clé maitre. Tout simplement pour faire redondance, au cas où une clé soit illisible (la probabilité d'avoir 2 clés illisibles est tout de même assez minime). Commencez par formater ces 2 clés en chiffrant la partition :
    -   Volume LUKS sur une partition ext4 pour GNU/Linux (utilisez l'utilitaire 'Disques')
    -   Utilisation d'un conteneur chiffré via Veracrypt pour les autres systèmes d'exploitation (Windows et MAC OS)
-   Puis une 3è clé USB est nécessaire pour transférer les sous-clés. Même si moins critique que la bi-clé maitre, on veillera tout de même à bien faire attention à sécuriser leur stockage (cela reste des items de sécurité).

Nous allons ensuite *exporter* du magasin de clés la bi-clé maitre :
-*Nous supposerons que votre clé USB est montée dans le répertoire `/media/user/CLESECRETE/`. Si le chemin diffère chez vous, veillez à bien modifier le répertoire après le chevron '&gt;' !*
-*Nous exportons 2 types de fichiers : .asc pour format ASCII (format lisible) et .gpg pour format binaire (format non lisible). Ceci afin d'avoir les 2 formats utilisés par tous les logiciels sur le marché.*
```bash
    # Stockage de la clé privée maitre
    gpg2 -a --export-secret-key 0xA6F76D3B09BC268A > /media/user/CLESECRETE/secret_key.asc
    gpg2 --export-secret-key 0xA6F76D3B09BC268A > /media/user/CLESECRETE/secret_key.gpg

    # Stockage de la clé publique maitre
    gpg2 -a --export 0xA6F76D3B09BC268A > /media/user/CLESECRETE/public_key.asc
    gpg2 --export 0xA6F76D3B09BC268A > /media/user/CLESECRETE/public_key.gpg

    # Stockage du certificat de révocation
    mv ~/.gnupg/*.rev /media/user/CLESECRETE/A6F76D3B09BC268A.rev
```

> **Répétez cette opération pour la deuxième clé USB puis stockez les en lien sûr.**
{.is-info}


Maintenant que nous avons mis bien au chaud notre clé maitre, nous allons maintenant exporter les sous-clés sur une 3è clé USB. Idem ici, il est souhaitable (mais pas obligatoire) de chiffrer la partition.
-*Nous supposerons que votre clé USB est montée dans le répertoire `/media/user/MACLEUSB/`. Si le chemin diffère chez vous, veillez à bien modifier le répertoire après le chevron '&gt;' !*
```bash
    # Export des sous-clés
    gpg2 -a --export-secret-subkeys 0xA6F76D3B09BC268A > /media/user/MACLEUSB/secret_subkeys.asc
    gpg2 --export-secret-subkeys 0xA6F76D3B09BC268A > /media/user/MACLEUSB/secret_subkeys.gpg
```

*A noter que la commande `--export-secret-subkeys` exporte bien toutes les clés et sous-clés, privées ET publiques donc, HORMIS la clé privée maitre, qui doit demeurer un secret absolu !*

## Nettoyage

Cette partie reste facultative si vous avez opté pour la génération de vos clés sur une live USB ou une distribution type Tails OS. En effet, les clés seront nettoyées automatiquement à l'extinction de la machine. Après cela ne coûte pas grand chose d'appliquer ce nettoyage !

En revanche elle est obligatoire si vous avez utilisé une machine que vous utilisez tous les jours, ce que nous ne recommandons pas... Afin de bien nettoyer les traces de la génération, vous pourrez utiliser des commandes spécifiques à GPG, que voici :
La commande :
```bash
gpg2 --delete-secret-keys 0xA6F76D3B09BC268A
```
Vous renvoit :
```brainfuck
    gpg (GnuPG) 2.2.19; Copyright (C) 2019 Free Software Foundation, Inc.
    This is free software: you are free to change and redistribute it.
    There is NO WARRANTY, to the extent permitted by law.


    sec  rsa4096/0xA6F76D3B09BC268A 2022-11-14 Jean Dupont <jean.dudu@pont.fr>

    Faut-il supprimer cette clef du porte-clefs ? (o/N) o
    C'est une clef secrète — faut-il vraiment la supprimer ? (o/N) o
```
La commande :
```bash
gpg2 --delete-key 0xA6F76D3B09BC268A
```
vous renvoit :
```brainfuck
    gpg (GnuPG) 2.2.19; Copyright (C) 2019 Free Software Foundation, Inc.
    This is free software: you are free to change and redistribute it.
    There is NO WARRANTY, to the extent permitted by law.


    pub  rsa4096/0xA6F76D3B09BC268A 2022-11-14 Jean Dupont <jean.dudu@pont.fr>

    Faut-il supprimer cette clef du porte-clefs ? (o/N) o
```

Nous vérifions qu'il n'y a plus de clé stockée via ces commandes :
```
gpg2 -K
gpg2 -k
```

## Import de clés

Une fois la génération terminée, il va nous falloir bien entendu importer les sous-clés sur la ou les machine(s) qui en auront l'utilité.

Pour ce faire, branchez la 3è clé USB contenant les sous-clés et exécutez ces commandes :
-*Nous supposerons que votre clé USB est montée dans le répertoire `/media/user/MACLEUSB/`. Si le chemin diffère chez vous, veillez à bien modifier le répertoire !*
```bash
gpg2 --import /media/user/MACLEUSB/secret_subkeys.gpg
```
```brainfuck
    gpg: clef A6F76D3B09BC268A : clef publique « Jean Dupont <jean.dudu@pont.fr> » importée
    gpg: To migrate 'secring.gpg', with each smartcard, run: gpg2 --card-status
    gpg: clef A6F76D3B09BC268A : clef secrète importée
    gpg: Quantité totale traitée : 1
    gpg:               importées : 1
    gpg:       clefs secrètes lues : 1
    gpg:   clefs secrètes importées : 1
```
Voilà, vous venez d'importer dans le magasin de clés vos sous-clés. Vous pouvez vérifier en exécutant ces commandes (-K pour clés privées) :
```bash
gpg2 -K
```
```brainfuck
    /home/user/.gnupg/pubring.kbx
    ----------------------------
    sec#  rsa4096/0xA6F76D3B09BC268A 2022-11-14 [C]
          Empreinte de la clef = 5445 E89C 355F 4FB4 E653  3D47 A6F7 6D3B 09BC 268A
    uid                  [  ultime ] Jean Dupont <jean.dudu@pont.fr>
    ssb   rsa4096/0x2C7E486743774AEA 2022-11-14 [S]
    ssb   rsa4096/0xD403F40075C53CA0 2022-11-14 [E]
```
Remarquez bien ici le "\#" accolé à la mention *sec* : ceci indique que la clé maitre n'est pas réellement présente, ce qui est tout à fait normal.

Idem avec la liste des clés publiques (-k pour clés publiques) :
```bash
gpg2 -k
```
```brainfuck
    /home/user/.gnupg/pubring.kbx
    ----------------------------
    pub   rsa4096/0xA6F76D3B09BC268A 2022-11-14 [C]
          Empreinte de la clef = 5445 E89C 355F 4FB4 E653  3D47 A6F7 6D3B 09BC 268A
    uid                  [  ultime ] Jean Dupont <jean.dudu@pont.fr>
    sub   rsa4096/0x2C7E486743774AEA 2022-11-14 [S]
    sub   rsa4096/0xD403F40075C53CA0 2022-11-14 [E]
```
> Voilà, vous avez terminé de construire votre chaine de confiance PGP. Pour finaliser le tout et donner la possibilité à vos contacts d'utiliser vos clés, il va maintenant être temps de les leur communiquer.
{.is-success}


## Distribution des clés

Comme il va être nécessaire pour ceux qui veulent vous contacter de connaitre votre clé publique, vous allez devoir trouver un moyen de la leur transférer. Deux choix s'offrent alors à vous :

-   En ligne, sur des serveurs de clés publiques
-   De manière manuelle, confidentielle

> **Nous ne conseillons vraiment pas de publier votre ou vos clés en ligne si vous avez peu de contacts qui utilisent PGP.**
{.is-warning}


### Serveur de clés

Si vous tombez dans la case personnage publique ou développeur et/ou avez un besoin de largement exposer vos clés, voici la façon la plus simple afin de publier votre clé publique. Pour commencer, voici les 3 principaux serveurs de clés PGP sur lesquels vous pourrez téléverser votre clé publique, choisissez-en un :
-   keys.gnupg.net
-   pgp.mit.edu
-   keyserver.ubuntu.com
{.grid-list}


Et publiez votre clé :
*Nous choisirons le serveur suivant : pgp.mit.edu, et reprenons l'ID de notre clé maitre 0xA6F76D3B09BC268A.*
```bash
gpg2 --keyserver pgp.mit.edu --send-keys 0xA6F76D3B09BC268A
```

Voilà, vos interlocuteurs vont maintenant pouvoir rapatrier cette clé publique et l'ajouter à leur chaine de confiance.

### Distribution manuelle

Donc hormis si vous êtes une personne publique sans forcément de besoins de sécurisation extrême des informations ou bien une personne fournissant des items signés (développeur, etc.), vous ne devriez pas avoir besoin de serveurs en ligne sur lesquels ajouter publiquement votre clé publique (et par extension vos métadonnées). Pour plusieurs raisons : il est évident que ces serveurs sont scrutés, non seulement par des personnes potentiellement malveillantes voire des entités de surveillance, car étant tout à fait publiques. Si votre modèle de menaces inclut l'anonymat, publier votre clé publique vous désanonymise si vous avez utilisé votre réelle identité et/ou si vous avez publié cette clé avec votre IP personnelles publique... Il va sans dire que nous ne recommandons pas spécialement ce mode de fonctionnement, hors cas particuliers et hormis si vous savez ce que vous faites.

Préférez donc un transfert manuel de votre clé publique, via une clé USB ou par courriel par exemple. Attention dans tous les cas de bien vérifier la validité des clés reçues par vos interlocuteurs, via une vérification visuelle de l' **empreinte** de la clé. Empreinte que vous pouvez transmettre sur un autre canal, par exemple sur une messagerie instantanée. Pour accéder à l'empreinte, voici la commande :
*Reprenons ici l'ID de la clé qui a été préalablement générée, 0xA6F76D3B09BC268A*
```bash
gpg2 --fingerprint 0xA6F76D3B09BC268A
```
```brainfuck
    pub   rsa4096/0xA6F76D3B09BC268A 2022-11-14 [C]
          Empreinte de la clef = 5445 E89C 355F 4FB4 E653  3D47 A6F7 6D3B 09BC 268A
    uid                  [  ultime ] Jean Dupont <jean.dudu@pont.fr>
    sub   rsa4096/0x2C7E486743774AEA 2022-11-14 [S]
          Empreinte de la clef = C5A2 7004 D904 34E0 BFDF  25DF D417 8662 358D 2E9A
    sub   rsa4096/0xD403F40075C53CA0 2022-11-14 [E]
          Empreinte de la clef = C5A2 6035 D903 33E0 BFDF  DEEF D417 866D 358D 2A9A
```

## Recommandations Diverses

### Sauvegardes

Il est également important de penser à sauvegarder, de façon récurrente, ses sous-clés voire tout son répertoire `~/.gnupg`, idéalement sur un stockage différent du disque actuel afin de palier une possible perte. L'avantage de sauvegarder son répertoire est de pouvoir restaurer toute la configuration, le magasin de clés, les signatures... Gardez ces sauvegardes au chaud, et de façon sécurisée si possible.

Afin de sauvegarder ce dossier, voici la commande que vous pouvez exécuter :
```bash
umask 077; tar -cf $HOME/gnupg-backup.tar -C $HOME .gnupg
```
Une commande `ls` devrait vous donner :
```brainfuck
    [...]
    -rw-------  1 toi  toi  20480 nov.  15 14:41 gnupg-backup.tar
    [...]
```

Note :
-   `$HOME` correspond en fait à votre répertoire 'HOME' (~/).
-   `umask 077` applique une restriction des permissions sur cette sauvegarde, comme vous pouvez le remarquer : -rw------- (lecture/écriture uniquement par vous même).

Pous pouvez maintenant sauvegarder ce fichier '.tar' sur une clé USB, ou tout autre support.

Afin de restaurer ce dossier, voici la commande :
*Nous partons du principe que vous avez déposé le .tar dans votre répertoire 'HOME'.*
```bash
tar xzf $HOME/gnupg-backup.tar
```

### Besoin de la clé maitre

Il y aura forcément diverses situations dans lesquelles vous aurez besoin de votre clé maitre, souvenez-vous, stockée sur 1 voire 2 clés USB, bien au chaud. Pour ce faire c'est très simple :
-*Mettons que notre clé USB soit montée ici : `/media/user/CLESECRETE`*
```bash
gpg2 --import /media/user/CLESECRETE/secret_key.gpg
```
```brainfuck
		gpg: key A6F76D3B09BC268A: "Jean Dupont <jean.dudu@pont.fr>" not changed
    gpg: key A6F76D3B09BC268A: secret key imported
    gpg: Total number processed: 1
    gpg:              unchanged: 1
    gpg:       secret keys read: 1
    gpg:  secret keys unchanged: 1
```

Veillez à bien de nouveau supprimer cette clé privée après avoir effectué vos opérations :
```bash
gpg2 --delete-secret-keys 0xA6F76D3B09BC268A
```

### Toile de confiance

Le véritable intérêt de PGP est lié à ce concept : la **toile de confiance** ou le fameux *Web of trust* en anglais. Souvenez vous que vous pouvez signer une clé rapatriée d'un de vos interlocuteurs (ou échangée de la main à la main), afin d'acter la confiance que vous portez à cette clé et à son titulaire : vous pourriez par exemple avoir échangé dans un bar lors d'une *Key Exchange Party* quelques clés avec des connaissances, que vous auriez vu physiquement. En apposant cet acte, vous reconnaissez alors le propriétaire de la clé comme légitime et établissez avec lui une *confiance*.

Puis vient ensuite le niveau de confiance, en une seconde étape, qui pourra être *ultime* comme *limité* voire *non fiable*.

Techniquement, on signe la *clé publique* de notre interlocuteur avec notre *clé privée maitre*, pour créer la chaine de confiance. Il s'agit d''une opération très importante, voilà pourquoi il faudra ressortir notre clé maitre de sa clé USB afin de signer cette autre clé ! En effet, lorsque l'on signe une clé, on ne signe pas seulement la clé publique ou une sous-clé quelconque, on signe la chaine entière (clé maitre et sous-clés) ainsi que l'identité qui y est rattachée. Opération tellement importante et critique que nous recommandons une nouvelle fois de procéder sur une machine hors ligne.

> Nous allons ici nous amuser un peu !
{.is-success}

Rapatrions une clé publique d'Edward Snowden (nous en avons choisi une chouette, tentez de comprendre pourquoi !) dans notre magasin de clés :
```bash
gpg2 --keyserver keyserver.ubuntu.com --recv-keys 347ff6babdee5137d2d06299da20a6cb20cabb31
```
```brainfuck
		gpg: clef DA20A6CB20CABB31 : clef publique « Edward Snowden Awaited Documents <edward.snowden@cryptome.org> » importée
    gpg: Quantité totale traitée : 1
    gpg:               importées : 1
```

```bash
gpg2 -k
```
```brainfuck
    /home/user/.gnupg/pubring.kbx
    ----------------------------
    pub   rsa4096/0xA6F76D3B09BC268A 2022-11-14 [C]
          Empreinte de la clef = 5445 E89C 355F 4FB4 E653  3D47 A6F7 6D3B 09BC 268A
    uid                  [  ultime ] Jean Dupont <jean.dudu@pont.fr>
    sub   rsa4096/0x2C7E486743774AEA 2022-11-14 [S]
    sub   rsa4096/0xD403F40075C53CA0 2022-11-14 [E]

    pub   rsa4096 2015-01-01 [SC]
          347FF6BABDEE5137D2D06299DA20A6CB20CABB31
    uid          [ inconnue] Edward Snowden Awaited Documents <edward.snowden@cryptome.org>
    uid          [ inconnue] Edward Snowden Release All Documents Now 15-0101 <edward-snowden-release-all-documents-now-15-0101@cryptome.org>
    uid          [ inconnue] Edward Snowden Awaited Documents <nytimes.snowden@cryptome.org>
    uid          [ inconnue] Edward Snowden Awaited Documents <laura.poitras@cryptome.org>
    uid          [ inconnue] Edward Snowden Awaited Documents <barton.gellman@cryptome.org>
    uid          [ inconnue] Edward Snowden Awaited Documents <glenn.greenwald@cryptome.org>
    sub   rsa4096 2015-01-01 [E]
```

Nous avons donc ajouté cette clé publique. Mettons que nous ayons rencontré Edward lors d'un apéro, et qu'il nous a certifié que cette clé était la bonne, nous allons donc pouvoir faire confiance à cette clé et la signer nous-même pour agrandir la chaine de confiance, puis publier notre clé sur le serveur afin d'acter cette signature.

**Pour ce faire, de retour chez nous, connectons notre clé USB chiffrée avec notre clé maitre à notre machine, hors ligne. Ensuite, réimportons la clé privée ; reportez-vous à la partie précédente "Besoin de la clé maitre".**

Une prémière commande nous permet de lister toutes les signatures déjà effectuées sur cette clé. Vous voyez ici que celle-ci a été signée par 7 personnes, jugées comme légitimes, dont d'ailleurs certaines peuvent vous sembler familière :
```bash
gpg2 --check-sigs 347FF6BABDEE5137D2D06299DA20A6CB20CABB31
```
```brainfuck
    pub   rsa4096 2015-01-01 [SC]
          347FF6BABDEE5137D2D06299DA20A6CB20CABB31
    uid          [ inconnue] Edward Snowden Awaited Documents <edward.snowden@cryptome.org>
    sig!     N   DA20A6CB20CABB31 2015-01-01  Edward Snowden Awaited Documents <edward.snowden@cryptome.org>
    uid          [ inconnue] Edward Snowden Release All Documents Now 15-0101 <edward-snowden-release-all-documents-now-15-0101@cryptome.org>
    sig!     N   DA20A6CB20CABB31 2015-01-01  Edward Snowden Awaited Documents <edward.snowden@cryptome.org>
    uid          [ inconnue] Edward Snowden Awaited Documents <nytimes.snowden@cryptome.org>
    sig!     N   DA20A6CB20CABB31 2015-01-01  Edward Snowden Awaited Documents <edward.snowden@cryptome.org>
    uid          [ inconnue] Edward Snowden Awaited Documents <laura.poitras@cryptome.org>
    sig!     N   DA20A6CB20CABB31 2015-01-01  Edward Snowden Awaited Documents <edward.snowden@cryptome.org>
    uid          [ inconnue] Edward Snowden Awaited Documents <barton.gellman@cryptome.org>
    sig!     N   DA20A6CB20CABB31 2015-01-01  Edward Snowden Awaited Documents <edward.snowden@cryptome.org>
    uid          [ inconnue] Edward Snowden Awaited Documents <glenn.greenwald@cryptome.org>
    sig!     N   DA20A6CB20CABB31 2015-01-01  Edward Snowden Awaited Documents <edward.snowden@cryptome.org>
    sub   rsa4096 2015-01-01 [E]
    sig!         DA20A6CB20CABB31 2015-01-01  Edward Snowden Awaited Documents <edward.snowden@cryptome.org>

    gpg: 7 good signatures
```

Puis à notre tour, nous allons la signer :
```bash
gpg2 --sign-key 347FF6BABDEE5137D2D06299DA20A6CB20CABB31
```
```brainfuck
    pub  rsa4096/DA20A6CB20CABB31
         créé : 2015-01-01  expire : jamais       utilisation : SC  
         confiance : inconnu       validité : inconnu
    sub  rsa4096/48DD0B84DF8B900B
         créé : 2015-01-01  expire : jamais       utilisation : E   
    [ inconnue] (1). Edward Snowden Awaited Documents <edward.snowden@cryptome.org>
    [ inconnue] (2)  Edward Snowden Release All Documents Now 15-0101 <edward-snowden-release-all-documents-now-15-0101@cryptome.org>
    [ inconnue] (3)  Edward Snowden Awaited Documents <nytimes.snowden@cryptome.org>
    [ inconnue] (4)  Edward Snowden Awaited Documents <laura.poitras@cryptome.org>
    [ inconnue] (5)  Edward Snowden Awaited Documents <barton.gellman@cryptome.org>
    [ inconnue] (6)  Edward Snowden Awaited Documents <glenn.greenwald@cryptome.org>

    Voulez-vous vraiment signer toutes les identités ? (o/N) o

    pub  rsa4096/DA20A6CB20CABB31
         créé : 2015-01-01  expire : jamais       utilisation : SC  
         confiance : inconnu       validité : inconnu
     Empreinte clef princip. : 347F F6BA BDEE 5137 D2D0  6299 DA20 A6CB 20CA BB31

         Edward Snowden Awaited Documents <edward.snowden@cryptome.org>
         Edward Snowden Release All Documents Now 15-0101 <edward-snowden-release-all-documents-now-15-0101@cryptome.org>
         Edward Snowden Awaited Documents <nytimes.snowden@cryptome.org>
         Edward Snowden Awaited Documents <laura.poitras@cryptome.org>
         Edward Snowden Awaited Documents <barton.gellman@cryptome.org>
         Edward Snowden Awaited Documents <glenn.greenwald@cryptome.org>

    Voulez-vous vraiment signer cette clef avec votre
    clef « Jean Dupont <jean.dudu@pont.fr> » (A6F76D3B09BC268A)

    Voulez-vous vraiment signer ? (o/N) o
```

Puis nous allons appliquer un niveau de confiance à cette clé. Ici nous allons décider de faire légèrement confiance à cette clé (choix 3) :
```bash
gpg2 --edit-key 347FF6BABDEE5137D2D06299DA20A6CB20CABB31
```
```brainfuck
    gpg (GnuPG) 2.2.27; Copyright (C) 2021 Free Software Foundation, Inc.
    This is free software: you are free to change and redistribute it.
    There is NO WARRANTY, to the extent permitted by law.


    pub  rsa4096/DA20A6CB20CABB31
         créé : 2015-01-01  expire : jamais       utilisation : SC  
         confiance : inconnu       validité : inconnu
    sub  rsa4096/48DD0B84DF8B900B
         créé : 2015-01-01  expire : jamais       utilisation : E   
    [ inconnue] (1). Edward Snowden Awaited Documents <edward.snowden@cryptome.org>
    [ inconnue] (2)  Edward Snowden Release All Documents Now 15-0101 <edward-snowden-release-all-documents-now-15-0101@cryptome.org>
    [ inconnue] (3)  Edward Snowden Awaited Documents <nytimes.snowden@cryptome.org>
    [ inconnue] (4)  Edward Snowden Awaited Documents <laura.poitras@cryptome.org>
    [ inconnue] (5)  Edward Snowden Awaited Documents <barton.gellman@cryptome.org>
    [ inconnue] (6)  Edward Snowden Awaited Documents <glenn.greenwald@cryptome.org>

    gpg> trust
    pub  rsa4096/DA20A6CB20CABB31
         créé : 2015-01-01  expire : jamais       utilisation : SC  
         confiance : inconnu       validité : inconnu
    sub  rsa4096/48DD0B84DF8B900B
         créé : 2015-01-01  expire : jamais       utilisation : E   
    [ inconnue] (1). Edward Snowden Awaited Documents <edward.snowden@cryptome.org>
    [ inconnue] (2)  Edward Snowden Release All Documents Now 15-0101 <edward-snowden-release-all-documents-now-15-0101@cryptome.org>
    [ inconnue] (3)  Edward Snowden Awaited Documents <nytimes.snowden@cryptome.org>
    [ inconnue] (4)  Edward Snowden Awaited Documents <laura.poitras@cryptome.org>
    [ inconnue] (5)  Edward Snowden Awaited Documents <barton.gellman@cryptome.org>
    [ inconnue] (6)  Edward Snowden Awaited Documents <glenn.greenwald@cryptome.org>

    Décidez maintenant de la confiance que vous portez en cet utilisateur pour
    vérifier les clefs des autres utilisateurs (en regardant les passeports, en
    vérifiant les empreintes depuis diverses sources, etc.)

      1 = je ne sais pas ou n'ai pas d'avis
      2 = je ne fais PAS confiance
      3 = je fais très légèrement confiance
      4 = je fais entièrement confiance
      5 = j'attribue une confiance ultime
      m = retour au menu principal

    Quelle est votre décision ? 3

    pub  rsa4096/DA20A6CB20CABB31
         créé : 2015-01-01  expire : jamais       utilisation : SC  
         confiance : marginale     validité : inconnu
    sub  rsa4096/48DD0B84DF8B900B
         créé : 2015-01-01  expire : jamais       utilisation : E   
    [ inconnue] (1). Edward Snowden Awaited Documents <edward.snowden@cryptome.org>
    [ inconnue] (2)  Edward Snowden Release All Documents Now 15-0101 <edward-snowden-release-all-documents-now-15-0101@cryptome.org>
    [ inconnue] (3)  Edward Snowden Awaited Documents <nytimes.snowden@cryptome.org>
    [ inconnue] (4)  Edward Snowden Awaited Documents <laura.poitras@cryptome.org>
    [ inconnue] (5)  Edward Snowden Awaited Documents <barton.gellman@cryptome.org>
    [ inconnue] (6)  Edward Snowden Awaited Documents <glenn.greenwald@cryptome.org>
    Veuillez remarquer que la validité affichée pour la clef n'est pas
    forcément correcte avant d'avoir relancé le programme.

    gpg> save
```

> *Bien sûr, nous aurions pu au maximum attribuer une confiance entière à cette clé car nous avons rencontré physiquement Edward. Cela dit, c'est un choix à faire !*
{.is-info}


En ce qui concerne justement les niveaux de confiance :
-   **ULTIME** : Une confiance *ultime* ne doit être appliquée qu'à vos propres clés ! Jamais à des clés d'autres personnes, mêmes issues de votre famille.
-   **ENTIEREMENT** ou **LEGEREMENT** : Une entière confiance ou une légère confiance se détermine par le niveau que vous êtes prêts à donner à la personne, suivant ses usages du numérique (par exemple : Mamie Janette sait forcément moins bien se servir d'internet que votre filleul Louis qui a une conscience de sa vie privée numérique et fait attention à ses usages)
-   **PAS CONFIANCE** : Choisir de ne PAS FAIRE CONFIANCE indiquera au logiciel que chaque tentative de signature ou de vérification de signature en lien avec cette clé doit être fait avec une attention particulière sachant que vous ne faites pas confiance à la clé !
-   **PAS D'AVIS** : Enfin le premier choix, je ne vous fais pas un dessin !

Veillez à bien de nouveau supprimer votre clé privée après avoir effectué vos opérations :
```bash
gpg2 --delete-secret-keys 0xA6F76D3B09BC268A
```

### Action urgente sur les clés

Nous avons déjà evoqué ce sujet (Voir partie Révocation) mais tentons d'aller un peu plus loin : il est tout à fait possible que vous rencontriez un jour le besoin de **révoquer** une de vos sous-clés, toutes les sous-clés voire votre bi-clé entièrement. Les raisons d'une révocation sont les suivantes :

-   Clé non utilisée depuis un petit moment (révocation optionnelle)
-   Clé expirée (révocation optionnelle)
-   Perte de clé
-   Vol de votre ordinateur où se trouvent vos sous-clés
-   Possible compromission d'une sous-clé ou de la clé

> **Comme cette action est critique, il est également ici nécessaire de ré-importer votre clé maitre, stockée sur clé USB ; reportez-vous à la partie précédente "Besoin de la clé maitre".**
{.is-danger}


#### Révoquer une sous-clé

Si vous deviez revoquer une sous-clé, il est nécessaire de procéder comme suit :
-*Mettons que vous souhaitiez révoquer la sous-clé de signature*
1- Edition de la clé
2- Sélection de la sous-clé en question : key 1 (clé d'indice 1) dans notre cas - Entre 0 et 2 ou 3
3- Application de la révocation : revkey
```
gpg2 --edit-key 0xA6F76D3B09BC268A
```
```brainfuck
    gpg (GnuPG) 2.2.19; Copyright (C) 2019 Free Software Foundation, Inc.
    This is free software: you are free to change and redistribute it.
    There is NO WARRANTY, to the extent permitted by law.

    La clef secrète est disponible.

    sec  rsa4096/0xA6F76D3B09BC268A
         créé : 2022-11-14  expire : jamais       utilisation : C
         confiance : ultime        validité : ultime
    ssb  rsa4096/0x2C7E486743774AEA
         créé : 2022-11-14  expire : jamais       utilisation : S   
    ssb  rsa4096/0xD403F40075C53CA0
         créé : 2022-11-14  expire : jamais       utilisation : E   
    [  ultime ] (1). Jean Dupont <jean.dudu@pont.fr>

    gpg> key 1

    sec  rsa4096/0xA6F76D3B09BC268A
         créé : 2022-11-14  expire : jamais       utilisation : C
         confiance : ultime        validité : ultime
    ssb* rsa4096/0x2C7E486743774AEA
         créé : 2022-11-14  expire : jamais       utilisation : S   
    ssb  rsa4096/0xD403F40075C53CA0
         créé : 2022-11-14  expire : jamais       utilisation : E   
    [  ultime ] (1). Jean Dupont <jean.dudu@pont.fr>

    gpg> revkey
    Voules-vous réellement révoquer cette sous clef ? (o/N) o
    Merci de sélectionner la raison de la révocation :
      0 = Aucune raison
      1 = La clef a été compromise
      2 = La clef est expirée
      3 = La clef n'est plus utilisée
      Q = Quitter
    Votre décision? 1
    Merci de donner une description optionnelle; terminez par une ligne vide :
    > Ma clé a été volée. :-(
    > 
    Raison de la révocation: La clef a été compromise
    Ma clé a été volée. :-(
    Est-ce correct? (o/N) o

    sec  rsa4096/0xA6F76D3B09BC268A
         créé : 2022-11-14  expire : jamais         utilisation : C
         confiance : ultime        validité : ultime
    La clef suivante a été révoquée le 2022-11-16 par RSA clef 2C7E486743774AEA Jean Dupont <jean.dudu@pont.fr>
    ssb  rsa4096/0x2C7E486743774AEA
         créé : 2022-11-14  révoquée : 2022-11-17   utilisation : S
    ssb  rsa4096/0xD403F40075C53CA0
         créé : 2022-11-14  expire : jamais         utilisation : E   
    [  ultime ] (1). Jean Dupont <jean.dudu@pont.fr>

    gpg> save
```

Vous venez de révoquer la sous-clé de Signature. N'oubliez pas de retransmettre votre clé à vos interlocuteurs et/ou de publier sur les serveurs de clés afin que tout le monde puisse être informé.

Enfin, veillez à bien de nouveau supprimer cette clé privée après avoir effectué vos opérations :
```bash
gpg2 --delete-secret-keys 0xA6F76D3B09BC268A
```

#### Révoquer intégralement une clé

Dans le cas d'une révocation intégrale, nous allons importer le certificat de révocation généré lors de la création de la bi-clé, et stockée sur clé USB avec la clé maitre :
*Mettons que notre clé USB soit montée ici : `/media/user/CLESECRETE`, et que notre certificat de révocation soit le fichier A6F76D3B09BC268A.rev*
```bash
gpg2 --import /media/user/CLESECRETE/A6F76D3B09BC268A.rev
```
```brainfuck
    gpg: clef A6F76D3B09BC268A : « Jean Dupont <jean.dudu@pont.fr> » certificat de révocation importé
    gpg: Quantité totale traitée : 1
    gpg:    nouvelles révocations de clef : 1
    gpg: marginals needed: 3  completes needed: 1  trust model: pgp
    gpg: profondeur : 0  valables :   2  signées :   0
         confiance : 0 i., 0 n.d., 0 j., 0 m., 0 t., 2 u.
    gpg: la prochaine vérification de la base de confiance aura lieu le 2024-11-16
```

Vous pouvez ensuite vérifier que la clé est bien révoquée :
```
gpg2 -K
```
```brainfuck
    /home/user/.gnupg/pubring.kbx
    ----------------------------
    sec   rsa4096 2022-11-14 [C] [révoquée : 2022-11-17]
          5445 E89C 355F 4FB4 E653  3D47 A6F7 6D3B 09BC 268A
    uid          [ révoquée] Jean Dupont <jean.dudu@pont.fr>
```
```
gpg2 -k
```
```brainfuck
    /home/user/.gnupg/pubring.kbx
    ----------------------------
    pub   rsa4096 2022-11-14 [C] [révoquée : 2022-11-17]
          5445 E89C 355F 4FB4 E653  3D47 A6F7 6D3B 09BC 268A
    uid          [ révoquée] Jean Dupont <jean.dudu@pont.fr>
```
Vous venez de révoquer la clé. 

> N'oubliez pas de retransmettre votre clé à vos interlocuteurs et/ou de publier sur les serveurs de clés afin que tout le monde puisse être informé.
{.is-success}


Enfin, veillez à bien de nouveau supprimer cette clé privée après avoir effectué vos opérations :
```
gpg2 --delete-secret-keys 0xA6F76D3B09BC268A
```

### Interface Graphique

Il est tout à fait possible d'utiliser une interface graphique pour effectuer toutes les actions précédentes. Cela dit, nous recommandons vivement la ligne de commandes car plus pratique et surtout plus verbeuse (si le moindre problème arrive, une interface graphique ne vous donne que très peu d'information !).

Néanmoins, vous pouvez par exemple utiliser :
-   Une extension au gestionnaire de fichier avec d'avoir des options de "Signature" et de "Chiffrement" au clic droit :

Par exemple, sur les distributions sous GNOME avec l'utilisation de Nautilus :
```
apt install seahorse-nautilus
```

-   Egalement, il existe un outil déjà intégré aux distributions, nommé GPA, pour la gestion de vos clefs.

S'il n'est pas installé, voici la commande :
```
apt install gpa
```

Pour conclure
=============

Voilà, vous avez enfin terminé, vous maitrisez maintenant tous les aspects de PGP :-) !

Vous n'avez donc aucune excuse pour ne pas l'utiliser...

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo, Nemtech*
<br>