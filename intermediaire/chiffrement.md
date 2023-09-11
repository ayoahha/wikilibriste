---
title: Le Chiffrement
description: Article traitant le chiffrement dans son ensemble et les outils recommandés...
published: true
date: 2023-07-14T14:39:48.764Z
tags: chiffrement, confidentialité, aes, rsa, intermédiaire, intermediaire
editor: markdown
dateCreated: 2022-11-24T22:12:38.038Z
---

# Le chiffrement
Ce terme, que vous avez sans aucun doute déjà entendu, peut tout à fait vous parler, comme totalement vous être incompréhensible !

Le chiffrement, ça a tout l'air d'être pour les geeks en manque d'adrénaline :-) Eh bien, détrompez-vous... Même s'il est vrai qu'aujourd'hui il est très compliqué de comprendre aisément le sujet, nous allons tenter d'apporter un peu de clareté.

Pour commencer, voici la définition officielle du chiffrement :

> "*Opération qui consiste à transformer un message à transmettre, dit « message clair », en un autre message, inintelligible pour un tiers, dit « message chiffré », en vue d'assurer le secret de sa transmission.*" [^¹]

[^¹]: [Chiffrement](https://www.larousse.fr/dictionnaires/francais/chiffrement/15322), Larousse

L'idée même du chiffrement est extrêmement ancienne et consiste donc à rendre un message illisible pour ceux qui ne détiennent pas le _secret_. Nous en reparlons plus loin...

Les historiens datent son apparition dès l'antiquité, rien que cela ! Nous pouvons par exemple penser aux grecs avec leurs Scytales, ou aux romains qui se sont amusés avec le "code de César", en passant par le 16è siècle où les français furent prolifiques en cryptologie (Blaise de Vigenère, Rossignol des Roches...). Jusqu'au plus récent équipement Enigma (Machine de Lorenz) utilisé par les allemands, lors de la seconde guerre mondiale.

**Tous ces procédés ont en commun la _cryptographie_ c'est-à-dire l'art de protéger un message.**

Bien qu'ancienne, certains pans de la cryptographie moderne sont très récents : la cryptographie *asymétrique*, par exemple, a fait son apparition au XXè siècle. Le site techno-science.net propose des détails vulgarisés [^²] intéressants sur la cryptographie moderne, que nous n'allons pas paraphraser dans cet article car ce n'en est pas le but. Également, nous ne rentrerons pas dans les considérations techniques liées à la _cryptographie_, sous peine de vous voir partir en courant ! *Sauf si vous le demandez :-)*

[^²]: [Cryptographie](https://www.techno-science.net/definition/6143.html)

Intéressons-nous plutôt à la présence du chiffrement dans nos usages quotidiens. Sans le remarquer, nous utilisons tous les jours du chiffrement. Par exemple, vous utilisez sûrement votre navigateur pour accéder à votre banque : ici, le chiffrement est assuré par l'utilisation de *certificats* dans votre navigateur. Niveau technique : on parle alors de requêtes HTTP avec une couche de protection TLS.

Il existe plusieurs façons d'appliquer un chiffrement :

1. Si vous souhaitez transmettre un document personnel et confidentiel, il est possible de chiffrer ce document avant de le transmettre sur un quelconque réseau public comme internet ;
1. Si vous vous déplacez régulièrement (personnellement ou pour votre travail) et afin d'éviter des conséquences dramatiques de vol d'équipements contenant des informations que vous jugez sensibles (ordinateur, disque dur...), il est très recommandé de songer à appliquer un chiffrement à vos dossiers contenant ces informations ;
1. Si vous êtes journaliste, activiste, etc, vous devriez sans aucun doute appliquer un chiffrement complet de votre/vos partition(s).

> De manière générale, et afin de renforcer la sécurité des informations échangées lors de conversations personnelles, et par extension, améliorer notre vie privée, l'utilisation du chiffrement est un avantage à ne pas négliger.
{.is-success}

## Utilisons le bon vocable

Afin de bien débuter, un petit point *vocabulaire* s'impose afin de faciliter l'entrée dans les concepts et leurs usages.

### Cryptographie

Déjà évoqué en introduction, la cryptographie est la discipline dont le but est de protéger la transmission de messages.

### Chiffrer et Crypter

Loin de moi l'idée de donner un cours de grammaire, mais l'importance des mots et de leur sens a toute sa place; surtout lorsque le sujet évoqué est complexe. 
Contrairement à ce qui est régulièrement évoqué lorsque certains tentent de vulgariser, dans la langue française, *Chiffrer* et *Crypter* n'ont pas le même sens :
-   L'action de chiffrement relève de la modification d'un message afin de le rendre illisible.
-   Crypter un message reviendrait à le chiffrer, mais sans connaissance de la clé de chiffrement.

> **Il est donc important de comprendre que la notion de "crypter" n'est pas utilisée en français, lorsque nous faisons de la cryptologie. En tout cas pas autant qu'en anglais; et il s'agit en français, soit d'un abus de langage, soit d'une anglicisation du terme "chiffrer" lorsque l'on parle de "~~crypter~~" ou de "~~cryptage~~" (respectivement chiffrer et chiffrement, qui sont donc les termes corrects dans notre situation).**
{.is-warning}

### Algorithme

Un algorithme est une suite d'opérations permettant la résolution de problèmes. 
Dans le cas du chiffrement (ou du déchiffrement), qui nous intéresse particulièrement ici, il s'agit de toutes les transformations du message à effectuer afin de le rendre illisible (chiffrement), ou afin de le rendre de nouveau lisible (déchiffrement).

### Clé de sécurité

Une clé de sécurité, souvent appelée par défaut de vulgarisation *clé de chiffrement*, est un paramètre donné en entrée d'un algorithme afin que celui-ci fournisse le résultat attendu en sortie. Il s'agit du fameux *secret* !

### E2EE

De l'anglais "End to End Encryption", pour chiffrement de bout-en-bout. Le chiffrement bout en bout décrit en fait la manière dont les données sont chiffrées entre émetteur et destinataire : dans ce cas, les données sont chiffrées avant qu'elles ne quittent l'appareil de l'émetteur et celles-ci ne peuvent être déchiffrées uniquement que sur l'appareil du destinataire, de sorte qu'aucun intermédiaire, y compris les fournisseurs de services, ne peut accéder à leur contenu.

On oppose ce procédé au chiffrement client-serveur, dont le ou les serveurs vont jouer les intermédiaires et déchiffrer la donnée, pour la chiffrer de nouveau puis la transmettre au destinataire. L'intermédiaire a donc un potentiel accès aux données en transit sur ses serveurs.

De façon schématique et très simplifiée, voici comment nous pourrions décrire ces 2 procédés.
Mettons un émetteur Alice et un destinataire Bob :

**Chiffrement client-serveur** :

1. L'émetteur Alice (qui joue le rôle de client) chiffre les données à l'aide d'une clé de chiffrement.
2. L'émetteur Alice envoie les données au serveur.
3. Le serveur déchiffre à l'aide de la clé de déchiffrement et stocke les données.
4. Le serveur chiffre de nouveau les données à l'aide d'une nouvelle clé de chiffrement.
5. Les données chiffrées sont transmises du serveur au destinataire Bob.
6. Le destinataire Bob déchiffre les données à l'aide de la clé de déchiffrement correspondante.

**Chiffrement de bout-en-bout** :

1. L'émetteur Alice chiffre les données à l'aide d'une clé de chiffrement.
2. Les données chiffrées sont transmises directement de l'émetteur Alice au destinataire Bob (il peut tout à fait passer par des serveurs, mais ceux-ci n'auront pas les clés pour déchiffrer !).
3. Le destinataire Bob reçoit les données et les déchiffre à l'aide de la clé correspondante.

> Attention : E2EE n'est pas un standard de chiffrement.
{.is-warning}

## Généralités

![Principe général du chiffrement](/images/fonction_chiffrement.png =500x){.align-center}

Techniquement, chiffrer une information consiste à transposer un message, clair et compréhensible, en message, incompréhensible et indéchiffrable du moins si l’on ne possède pas le moyen de le déchiffrer. Ce moyen est appelé « secret » et plus encore correspond à une « clé (de sécurité) ». Cette clé est utilisée afin d’appliquer une opération (dite cryptographique) sur la donnée ou sur la communication afin d’en protéger le contenu, opération que nous nommons « **chiffrement** » (et l’inverse pour le déchiffrement bien sûr).

Différents mécanismes de chiffrement existent, rapidement :
-   Chiffrement basé sur la cryptographie **symétrique**, avec partage d’un même secret (clé), c’est-à-dire que la même clé est utilisée pour chiffrer et déchiffrer.
-   Chiffrement basé sur la cryptographie **asymétrique**, avec l’utilisation d’une paire de clés : dans ce cas, une clé sert au chiffrement et la seconde au déchiffrement et plus généralement une clé pour une opération et une seconde pour l'opération inverse (car il est possible d'appliquer une autre forme de protection, la signature numérique).

*Il est aussi tout à fait possible d’avoir un mécanisme hybride (cf. *TLS* ou *PGP*).*

## Robustesse / Force

Alors, non, nous n'allons pas vous faire un cours de cryptographie (en tout cas, pas comme l'article sur PGP :) !), ni même discuter de choix cryptographiques, sinon vous risquez de décrocher, et nous souhaitons garder notre audience attentive ! 

L'objectif de cette partie est de vous présenter les *_algorithmes_* qui **aujourd'hui** sont recommandés du fait de leur robustesse reconnue contre les attaques.

> Précisons qu'il s'agit là de l'état de l'art à 2022. Comme toute technologie, et encore plus en cryptographie, ceci est amené à évoluer (surtout avec l'apparition d'équipements quantiques). Il est donc important de prendre cet aspect en considération.
{.is-warning}

Lorsque nous devons appliquer un chiffrement, il nous est toujours demandé de choisir l'algorithme qui sera appliqué afin de pouvoir générer les clés de sécurité, pour ensuite dérouler toutes les procédures (de chiffrement) sur la/les donnée(s). 
Le choix dans les algorithmes est important, car il va conditionner la rapidité d'exécution, la complexité et la robustesse du résultat de sortie. Et il est souvent difficile pour le néophyte de choisir le bon algorithme, quand bien même l'outil donnerait des explications sur ce-dit algorithme. Par ailleurs, certains algorithmes sont plutôt adaptés pour une partie spécifique d'un chiffrement, et d'autres pour d'autres aspects...

Voici donc, suivant les **_usages spécifiques_**, les choix que nous recommandons :

-   **Chiffrement Fichier / Répertoire / Disque :**
    -   Préférons :
        -   _Avec accélération matérielle_ : AES (Rijndael) 256 bits minimum, avec CBC ou GCM, avec HMAC-SHA-2 ou HMAC-SHA-3 pour les digests signatures (ce que Veracrypt, Bitlocker et LUKS utilisent par défaut) ; Préférons SHA-3 tout de même.
        <span class="red-text"><strong>Une note concernant HMAC-SHAx</strong> : si nous souhaitons utiliser un token physique (type Yubikey, Nitrokey...), il est possible que ces tokens ne supportent que *HMAC-SHA1*. Par conséquent, nous devrons accepter l'utilisation de cet algorithme le temps que le token soit compatible avec les successeurs.</span>
        -   _Sans accélération matérielle_ : idem ci-dessus ou si disponible :
            -   ChaCha20 ou XChaCha20 (ChaCha20 disponible sur certains outils mais malheureusement pas sur Veracrypt),
            -   Serpent,
            -   TwoFish.
    -   On évite tout le reste.

-   **Sécurité navigateur internet (via HTTPS) :**
    -   Préférons TLS 1.3 (idéalement TLS 1.3 avec support ECH/eSNI <span class="red-text">\*</span>) ou au moins TLS 1.2 (très répandu).
    -   On évite tout le reste, c'est-à-dire TLS inférieur ou =1.1, ou SSL inférieur ou =3

-   **Signature messages ou fichiers avec PGP/GPG :**
    -   Préférons ECDSA (ed25519), ECDH (ec25519),
    -   RSA 4096 bits,
    -   On évite RSA 2048 bits.

-   **Clés SSH :**
    -   ED25519 (à préférer) ou RSA 4096 bits (à noter que certains outils permettent de générer des clés RSA 8192 bits. Vous pouvez en générer, mais attention à la compatibilité avec les logiciels qui utiliseront les clés : toutes les applications ne peuvent pas encore gérer des clés de cette longueur).
    -   On évite RSA 2048 bits voire 3072 bits.

<span class="red-text"> ECH, et eSNI avant lui, sont 2 procédés imaginés afin de protéger les échanges durant une phase particulière du TLS : le "handshake" - ou l'initialisation d'une communication, dans laquelle certaines métadonnées sont échangées entre client et serveur (comme clé de sécurité, SNI, ALPN...). En particulier, lors du tout premier message appelé "Client Hello", le plus critique :</span>
  - <span class="red-text">_eSNI_ pour _encrypted Server Name Indication_ a d'abord été implémenté, et permet de protéger une partie de ce premier message, le **'SNI**' qui donne une indication de quel client est en train de parler à quel serveur (donnée critique).</span>
  - <span class="red-text">_ECH_ pour _Encrypted Client Hello_ a par la suite été créé, et consiste à protéger l'entièreté du premier message (pour faire court !).</span>

## Chiffrer ses données

Suivant son modèle de menaces et parce que nous souhaitons éviter que des informations sensibles ou personnelles stockées (photos, photocopie de carte d'identité, etc.) puissent être divulguées, il est possible d'appliquer un chiffrement sur des fichiers, des répertoires et même sur des partitions/disques entiers.

Le chiffrement du disque est par exemple particulièrement recommandé pour les personnes ayant un modèle de sécurité moyen à élevé (comme les journalistes d'investigation, ou les avocats, les activistes, etc.). Cela dit, ceci s'accompagne d'inconvénients à gérer au quotidien. 

Voici un état des lieux :
- Avantages :
	- Protection _renforcée_ de son disque. Ce qui implique qu'un vol d'ordinateur ou de disque ralentisse considérablement voire bloque l'attaquant qui souhaite atteindre vos données.
  {.grid-list}
- Inconvénients :
	- Un nouveau mot de passe _fort_ à créer et à retenir, et à entrer à chaque démarrage de la machine. Ce qui pousse certains à baisser leur vigilance car trop fastidieux, voire à créer des mots de passe faibles qui augmente le risque de casse du mot de passe.
	- **Procédures récurrentes de [sauvegardes de ses données](/debutant/sauvegarde) à mettre en place**. En effet, en cas de panne, il est extrêmement compliqué de récupérer ses données sur des partitions chiffrées. Il est donc essentiel d'avoir une politique de sauvegarde de ses données afin de palier ce problème.
  {.grid-list}

> Généralement, il est recommandé spécifiquement aux personnes qui se déplacent beaucoup avec un ordinateur portable sensible de chiffrer a minima son disque (ou ses disques), en prenant bien compte des inconvénients à l'usage.
{.is-info}

**Voyons maintenant dans les détails...**

### Chiffrer ses fichiers et répertoires
La première façon de protéger ses informations de façon isolée consiste à appliquer un chiffrement sur des fichiers, voire des répertoires.

-   Les outils bureautiques actuels (LibreOffice par ex.) permettent pratiquement tous de protéger ses documents avec un mot de passe.
-   Quelques logiciels d'archive permettent également d'ajouter un mot de passe à un répertoire.
-   GnuPG permet de chiffrer de la même manière, mais avec son procédé asymétrique.

La CNIL propose un article sur le chiffrement de ces données, avec quelques tutoriels : [comment chiffrer ses documents et ses répertoires](https://www.cnil.fr/fr/comment-chiffrer-ses-documents-et-ses-repertoires)

Nous recommandons principalement les outils suivants, basés sur des solutions de chiffrement de fichiers :

- [7-zip *qui vous permettra de créer des archives protégées par mot de passe (attention de bien choisir des mots de passe FORTS. Nous vous renvoyons à l'article sur l'hygiène informatique.*](https://7-zip.org)
- [AESCrypt *également multiplateforme, cet outil offre une interface graphique assez simple. Nous vous invitons à prendre connaissance de sa documentation ^\*^*](https://www.aescrypt.com)
- [eCryptFs *Il s'agit d'un outil pour créer un répertoire chiffré, via chiffrement symétrique (mot de passe). Un très bon tutoriel détaillé est disponible sur le site de LinuxTricks.fr ^\**^*](https://www.ecryptfs.org/home)
- [GnuPG *que nous avons traité dans l'article du même nom.*](/intermediaire/chiffrement#pgp-gpg)
{.links-list}


^*^ [AESCrypt Documentation](https://www.aescrypt.com/documentation)
^**^ [EcryptFS Tutoriel](https://www.linuxtricks.fr/wiki/ecryptfs-chiffrer-son-dossier-personnel)


:arrow_right: **GnuPG avec Chiffrement à clé publique :**
*Mettons que vous avez un fichier mon-fichier.txt à chiffrer dans votre répertoire personnel ~/ et que l'ID de la clé 0xA6F76D3B09BC268A*:

Entrons :
```
gpg --output ~/mon-fichier.txt.gpg --encrypt --recipient 0xA6F76D3B09BC268A ~/mon-fichier.txt
```
Puis il faut faire :
```
ls
```
La sortie de commande vous donne :

```brainfuck
[...]
-rw-------  1 toi  toi     32 nov.  17 18:40  mon-fichier.txt
-rw-------  1 toi  toi    629 nov.  17 18:36  mon-fichier.txt.gpg
[...]
```

Pour déchiffrer, voici la commande :

```
gpg --output ~/mon-fichier.txt --decrypt ~/mon-fichier.txt.gpg
```

:arrow_right: **GnuPG avec Chiffrement symétrique :**

Entrons :
```
gpg --output ~/mon-fichier.txt.gpg --symmetric ~/mon-fichier.txt
```
Puis tapons :
```
ls
```
La sortie de commande vous donne :

```brainfuck
[...]
-rw-------  1 toi  toi     32 nov.  17 18:40  mon-fichier.txt
-rw-------  1 toi  toi    117 nov.  17 18:46  mon-fichier.txt.gpg
[...]
```

Pour déchiffrer, voici la commande :

```
gpg --output ~/mon-fichier.txt --decrypt ~/mon-fichier.txt.gpg
```

Il est possible de faire appel à un logiciel spécifique afin de chiffrer des données sur certains de vos Clouds propriétaires (Google Drive, OneDrive, Dropbox, iCloud drive, etc.) :

-   [Cyptomator](https://cryptomator.org/) vous permettra de créer des conteneurs (des répertoires, appelés judicieusement *coffres-forts* (ou *"vaults"* en anglais) chiffrés, que nous pourrons ensuite transférer sur ces clouds. Le chiffrement se fait via une clé symétrique et un mot de passe. Outil très simple d'emploi, à installer chez vous, et à utiliser comme n'importe quel outil :
    -   Créons un Coffre-fort/Vault,
    -   Choisissons vers quel service de stockage en ligne ("cloud") nous souhaitons le transférer,
    -   Entrons notre mot de passe fort,
    -   Sauvegardons en lieu sûr notre clé de récupération (très important si nous oublions un mot de passe ou si nous bougeons le répertoire),
    -   Terminons la création.

[La documentation de Cryptomator](https://docs.cryptomator.org/en/latest/desktop/getting-started/) est très explicite.

---
Enfin, 2 outils commencent à monter dans la communauté :
- [Kryptor *Outil qui se veut plus accessible que GPG. **N'hésitez pas à regarder notre tutoriel spécifique**.*](https://www.kryptor.co.uk/)
- [Age *Outil de chiffrement uniquement. **N'hésitez pas à regarder notre tutoriel spécifique.***](https://github.com/FiloSottile/age)
{.links-list}


> **Attention : nous n'avons que très peu de recul sur ces outils, même s'ils utilisent les derniers algorithmes, robustes. Veillons à les utiliser en toute connaissance de cause.**
{.is-warning}

### Chiffrer ses partitions

Si nous estimons que chiffrer votre ou vos partition(s) est nécessaire, voire votre disque, nous recommandons 2 outils que vous connaissez probablement :

-   [LUKS](https://gitlab.com/cryptsetup/cryptsetup) pour Linux Unified Key Setup, ou *cryptsetup* son implémentation, est l'outil de base des distributions GNU/Linux. 
  Certaines distributions proposent même, dès l'installation, de chiffrer vos partitions (via LUKS donc), comme Pop!OS à partir de la version 22.04[^³]. 
  D'autres distributions peuvent le proposer à l'installation moyennant un partitionnement manuel. Enfin, pour d'autres, aucune proposition de chiffrement de partition. Il faudra donc passer par la ligne de commandes... Oui je sais que vous adorez ça !

[^³]: [Pop!OS 22.04](https://support.system76.com/articles/install-pop) et chiffrement partition.

> **Les commandes qui suivent vont supprimer TOUTES nos données sur la partition que nous allons chiffrer. Nous perdrons TOUTES nos informations ! Il est donc crucial que nous fassions une sauvegarde intégrale sur une source externe, comme un second disque dur ou un NAS, avant d'exécuter les commandes.**
{.is-danger}


Afin de sauvegarder notre partition sur un disque dur externe, voici la commande que nous pouvons utiliser :

*Nous sauvegardons ici la partition /dev/sda3, veillons à bien connaître la partition que nous souhaitons sauvegarder, elle peut être différente...*

```bash
dd if=/dev/sda3 of=/media/user/MONDISQUEEXTERNE status=progress
```

Passons maintenant à la protection de cette partition :

```bash
sudo apt install cryptsetup
cryptsetup --help
```
La sortie de `cryptsetup` vous donne :
```brainfuck
    Clé compilée par défaut et paramètres de phrase secrète :
        Taille max. fichier de clé : 8192 ko, longueur max. interactive de phrase secrète 512 (caractères)
    PBKDF par défaut pour LUKS1 : pbkdf2, temps d'itération : 2000 (ms)
    PBKDF par défaut pour LUKS2 : argon2id
        Temps d'itération: 2000, Mémoire requise: 1048576 ko, Threads parallèles: 4

    Paramètres de chiffrement compilés par défaut :
        loop-AES: aes, Clé 256 bits
        plain: aes-cbc-essiv:sha256, Clé: 256 bits, Hachage mot de passe: ripemd160
        LUKS: aes-xts-plain64, Clé: 256 bits, Hachage en-tête LUKS: sha256, RNG: /dev/urandom
        LUKS: La taille de clé par défaut en mode XTS (deux clés internes) sera doublée.
```

Bien, ici, si l'on essaie de traduire :

1.  Clé compilée fait référence aux mots de passe de vos partitions chiffrées, stockés de façon sécurisée avec algorithme pbkdf2 pour LUKS1 et argon2id pour LUKS2. En référence aux algorithmes recommandés dans la partie dédiée, LUKS2 semble à privilégier !
2.  Chiffrement de la partition. L'algorithme utilisé est l'AES-256, ce qui correspond très bien aux recommandations d'algorithmes.

Ce petit aperçu nous donne une piste quant à l'utilisation de LUKS1 ou LUKS2, bien sûr vous l'aurez compris, nous utiliserons LUKS2. Ce qui tombe bien, a priori, puisque LUKS2 est utilisé par défaut... 

Passons maintenant de la théorie à la pratique : vous trouverez un tutoriel très [bien détaillé ici](https://www.val-r.fr/geek/os/linux/creer-et-utiliser-une-partition-chiffree-avec-luks-sous-linux/). Veillons à respecter scrupuleusement les indications !

-   [VeraCrypt](https://www.veracrypt.fr/en/Home.html) : outil très connu, surtout chez nos amis de Windows. Cet outil vous permettra non seulement de créer des partitions chiffrées, mais également de chiffrer des partitions déjà existantes. **Attention cependant, VeraCrypt ne permet pas de chiffrer sa partition système sur GNU/Linux, au contraire de LUKS**. Vous trouverez pléthore de tutoriels sur internet (y compris des Vidéos), dont voici une petite liste :
    -   L'excellent site de Malekal qui chiffre sa partition `HOME` sur [Ubuntu 22.04](https://www.malekal.com/veracrypt-chiffrer-un-disque-ubuntu-22-04-lts/)
    -   Le site de Tails OS nous donne accès à un [tutoriel intéressant](https://tails.boum.org/doc/encryption_and_privacy/veracrypt/index.fr.html)
    -   L'incontournable site [Openclassrooms](https://openclassrooms.com/fr/courses/1757741-securisez-vos-donnees-avec-la-cryptographie/6031867-protegez-vos-fichiers-avec-le-chiffrement-de-disque-dur) (ex Site du Zéro pour les anciens ;-) !)

> Pour synthétiser, vous l'aurez sûrement compris : afin de chiffrer nos partitions ou notre disque complet sur GNU/Linux, préférons LUKS, sur d'autres systèmes d'exploitation, VeraCrypt sera la solution.
{.is-info}


### Chiffrer ses échanges
Lorsque nous allons chiffrer un fichier avec un mot de passe, il va nous falloir nous demander comment allons-nous transmettre ce *mot de passe* à notre interlocuteur afin qu'il puisse déchiffrer le fichier ? 

Plutôt compliqué, le risque étant que ce mot de passe puisse être intercepté, et en toute honnêteté, ceci peut se produire aujourd'hui plutôt facilement si aucune mesure de sécurité n'est appliquée (nous ne vous faisons pas un dessin, vous avez sûrement vu ou entendu parler de ce genre de choses, vu que vous lisez cet article !).

Alors oui, aujourd'hui tout le monde envoie ses mots de passe par courriel ou messagerie, y compris et surtout par messagerie non chiffrée (ouch!). Et ça n'a que peu d'incidence, et c'est surtout par simplicité d'usage et par... fainéantise ! 
-  Mais pensons au risque que nous prenons avec ce genre d'habitudes : il se peut qu'un jour le message soit intercepté, personne n'est et ne sera jamais à l'abri de ce risque. 
-  Si nous chiffrons votre message, c'est que vous le percevez comme confidentiel (il peut s'agir d'une photocopie d'un passeport, ou d'une carte vitale par exemple). Bien souvent, ces données interceptées sans qu'on le sache se retrouvent sur les darknets, vendues au plus offrant afin d'usurper les identités ! C'est plutôt critique...
{.grid-list}

Il est donc recommandé, autant que faire se peut, d'abandonner ces techniques d'envoi "en clair", et d'adopter des pratiques plus respectueuses de _**notre**_ vie privée... Et aussi de _**la vie privée de nos interlocuteurs**_, qui peuvent être notre famille en premier lieu !

Ainsi, le chiffrement n'est pas spécifiquement utilisé pour des données stockées, mais peut également être utilisé pour des **données en transit sur internet**. Généralement, il s'agira de créer un tunnel sécurisé : ici, plutôt que d'appliquer le chiffrement à la donnée, il s'agira d'appliquer la couche de confidentialité au canal lui-même. Ainsi, chaque information en transit à l'intérieur de ce canal 'sécurisé' sera protégé, même si aucun chiffrement n'aura été appliqué au préalable à la donnée.

> Bien sûr, un canal sécurisé n'appliquera pas qu'une protection liée à la confidentialité (chiffrement), mais aussi une protection liée à l'intégrité, et une façon d'authentifier les échanges.
>
> Cela dit, cet article ne traite que du chiffrement, voilà pourquoi nous ne parlons ici que de cet aspect (sauf exception explicitement mentionnée).
{.is-info}

Il y a plusieurs avantages à l'utilisation d'un canal chiffré : dans un premier temps, nous réduisons les opérations à effectuer sur les données, ce qui, de plus, réduit le risque de corruption involontaire (moins d'opération d'écriture). Ensuite, dans certaines circonstances, cela simplifie également pour l'utilisateur les actions à effectuer.

Nous vous l'accordons, c'est un peu complexe à appréhender comme cela, mais retenons ceci :

-   Soit l'on chiffre les données elles-mêmes, objet de la partie précédente ;
-   Soit l'on chiffre un canal, c'est l'objet de la partie à suivre...

Voyons voir...

#### Navigation Web

Pour les plus techniques d'entre nous, nous aurons sûrement entendu parler, il y a quelques années, des décisions autour du renforcement de la sécurité concernant la navigation sur internet, au travers notamment du HTTP-S[^⁴].

[^⁴]: [S pour Secure](https://c-marketing.eu/passer-site-https/) dans HTTPS.

Aujourd'hui, la majorité des sites déploient une sécurisation des échanges entre leurs serveurs et nous-mêmes. Mais ce ne fut pas le cas il y a encore 6 ans ! C'est donc encore tout à fait récent...

Techniquement, il s'agit de l'utilisation du TLS (SSL pour les anciens !) : mécanisme qui ouvre un canal sécurisé entre votre navigateur internet et le serveur du site visité, à l'aide de certificats numériques (délivrés par des autorités tierces, à l'issue du processus de certification). De sorte que nos échanges soient chiffrés, hormis quelques métadonnées qui restent en clair (adresse IP, etc.).

C'est déjà un bon début, surtout lorsque nous consultons notre banque ou nos compagnies d'assurance.

Il est donc fortement recommandé de **forcer le HTTPS** dans votre navigateur internet ou d'installer une extension comme *HTTPS Everywhere / HTTPS Partout* (nous vous renvoyons à l'article sur les [navigateurs](/debutant/navigateurs)) : si un site s'avère être resté en HTTP (bouh pas bien !!), nous serons alors averti et ce sera à nous de prendre la décision de le consulter ou non. En se basant sur la confiance que nous faisons à ce site, et connaissant donc le risque potentiel de communiquer avec ce site totalement en clair !

Voici un exemple de l'avertissement en question :
![https_avert.png](/images/https_avert.png){.align-center}
![https_avert_solved.png](/images/https_avert_solved.png){.align-center}

Exemples pour forcer le HTTPS sur notre navigateur web (exemples respectivement pour Firefox et Chromium) :
![https_force_ff.png](/images/https_force_ff.png =700x){.align-center}
![https_force_chrom.png](/images/https_force_chrom.png =700x){.align-center}

#### Courriels

Ah le très fameux et très ancien courriel, très souvent appelé e-mail par anglicisme, pour 'electronic mail' (courrier électronique). Si vous avez lu l'article sur l'hygiène numérique, vous avez sans doute compris que nous ne portons pas forcément dans notre coeur le courriel.

En effet, bien qu'ancien, rien n'est fait aujourd'hui pour renforcer la sécurité autour de ce type de messages, ou si peu... En effet, il s'avère que l'avènement des messageries a porté un coup dur aux courriels. Néanmoins, ceux-ci sont tout de même encore beaucoup utilisés (surtout en entreprise, mais ce n'est pas notre sujet ici !), et malheureusement encore trop souvent non (assez) sécurisé. Ce qui porte la confidentialité des échanges à néant.

Il y a quelques années, l'histoire autour d'Edward Snowden a quelque peu changé les choses ; PGP a été mis en lumière et il s'avère qu'aujourd'hui, ce mécanisme est de plus en plus utilisé pour protéger les communications par courriels. Beaucoup d'outils (en ligne ou hors ligne) implémentent une façon d'utiliser des clés PGP simplement.

Un [article](/debutant/communications#courriel) spécifique est dédié aux communications via courriel ainsi qu'à sa sécurisation.

#### Messageries

Un article dédié est déjà publié, et nous présente les solutions les plus respectueuses de notre vie privée et les plus sécurisées aujourd'hui. Je vous y renvoie donc : [les messageries](/debutant/communications#messagerie).

### Gestionnaire de mots de passe

Avec tous les mots de passe que nous avons vu passer, il est évident que nous ne pourrons retenir la totalité de nos mots de passe. Certains outils très pratiques ont été créés pour cela.

Nous avons rédigé un article dédié à ce sujet : les [gestionnaires](/debutant/gestionnaire-mots-passe) de mots de passe.

Le point chiffrement sera rapide ici : il s'agit de créer une base de données qui sera chiffrée grâce à du chiffrement symétrique via des algorithmes très robustes (AES mais aussi d'autres, cf. partie [algorithme](/debutant/gestionnaire-mots-passe#algorithme)), protégés donc par mot de passe. Bien évidemment ici, un mot de passe très fort sera choisi afin de résister à différentes attaques (brute force, etc.).

Ici, le point important est de ne pas se fier à des outils qui proposent des services *en ligne* mais bien de générer nous-même notre base de données de mots de passe, la stocker chez nous à 2 ou 3 endroits au maximum et ne jamais la transférer par internet ! Malheureusement, peu d'outils respectent ces exigences, comme mentionné dans l'article sur les gestionnaires de mots de passe.

# L'intégrité
**Alors qu'est ce que l'intégrité ?**

Par définition :

> **L'intégrité d'une donnée, au sens large, désigne l'état fiable et crédible de cette donnée**.

Ou encore selon la norme [ISO/CEI 27000:2016](https://www.iso.org/fr/standard/66435.html)

> **L’intégrité est la propriété d’exactitude et de complétude**.

Dans le monde numérique, une **donnée** possède un *cycle de vie*. Pendant ce cycle de vie, il est possible que cette donnée soit altérée, résultant en une perte d'intégrité, de façon involontaire comme, par exemple, la corruption due aux nombreuses copies/recopies ou à un bogue, ou de façon volontaire comme l'altération via un changement de code (malware...).

Afin d'assurer donc la _fiabilité_ et la _crédibilité_ et par conséquent, la confiance que nous pouvons accorder à cette donnée, assurer son intégrité fait partie des processus les plus importants en informatique.

## Généralités

![Hachage](/images/2_hachage.png "Crédits : CNIL" =600x){.align-center}

Le procédé utilisé ici consiste à générer une valeur spécifique à partir de la donnée (qui peut être soit un message, un fichier ou un répertoire) appelée **"somme de contrôle"** (ou checksum) et souvent nommée en français **"empreinte"** (terme que nous utiliserons dans cet article car il correspond en tous points à ce qui est généré) calculée suivant un algorithme spécifique dit "fonction de hachage". Il n'est pas rare, cela dit, de voir également utilisés les termes de "somme de hachage" ou simplement "hash" ou enfin **"digest"**.

Il existe 2 principaux objectifs à cette valeur obtenue :
-   valeur obtenue via une fonction à code cyclique pour un contrôle de **"redondance cyclique"** (CRC). Ce principe est utilisé pour la vérification d'erreurs sur des communications réseau ou du transfert de données en stockage (ex. : CRC32).
-   valeur obtenue via une fonction à sens unique (one-way function pour les bilingues !). Nous obtenons ici une empreinte **"unique"** de la donnée, calculable et vérifiable par tout le monde (ex. : SHA2).

> **Cet article ne traite que du second procédé au travers d'une simple *empreinte* ou d'une signature numérique.**
{.is-info}


## Qu'est-ce que l'intégrité n'est pas ?

Les gens confondent parfois intégrité des données et sécurité des données. Or, l'intégrité n'est pas la sécurité...

_Explications_ : l'objectif de la **sécurité** des données est de *protéger* celles-ci contre des potentielles attaques extérieures en *cachant son contenu*, quand l'intégrité des données a pour objectif de garder les données intactes durant tout leur cycle de vie.

Ici, nous remarquons qu'il y a une différence sémantique entre les 2 termes. Pour ce qui est de la sécurité, par la **confidentialité** donc, nous vous renvoyons au premier chapitre de cet article.

De même, l'intégrité n'est pas l'**authenticité** : en effet, l'authenticité a pour objectif de prouver la provenance d'une donnée afin de pouvoir *identifier* l'auteur.

### Pourquoi vérifier absolument l'intégrité d'un fichier téléchargé ?

Les fichiers qui proviennent d'internet peuvent, par définition, faire l'objet de toute sorte de *corruption* :
-  :arrow_right: il se peut qu'un fichier sur un serveur de téléchargement (un "dépôt") ait été modifié afin d'y intégrer un malware [^⁶] .
-  :arrow_right: il se peut également que le fichier, à son arrivée sur notre machine, soit altéré, soit involontairement, soit volontairement (cf. attaque de l'homme du milieu ou MITM en anglais).
{.grid-list}

[^⁶]: [Le logiciel Ccleaner](https://www.latribune.fr/technos-medias/informatique/le-logiciel-ccleaner-infecte-par-un-malware-2-3-millions-d-utilisateurs-touches-750834.html) infecté par un malware 2,3 millions d'utilisateurs touchés

Imaginons dans le cas d'un fichier vidéo, un malware peut passer inaperçu pour l'utilisateur.

Imaginons également, lorsque nous récupérons une image d'un système d'exploitation (.ISO, .IMG...) volontairement corrompue ; cela peut être problématique voire fatal pour le système et potentiellement corrompre l'appareil que nous allons (ré)installer et surtout vos données !

> C'est pour cette raison qu'il est conseillé de toujours vérifier l'empreinte d'un fichier en provenance d'internet afin de vérifier son état, que ce soit en téléchargement sur un site ou via une messagerie quelconque.
{.is-warning}

La plupart du temps, sur le site du fournisseur du fichier, celui-ci nous donne plusieurs fichiers annexes contenant l'empreinte et l'algorithme utilisé. Cette information nous permettra donc de vérifier l'intégrité en comparant l'empreinte que nous calculerons sur notre machine (pas de panique, nous n'allons pas faire de maths, juste des commandes !) avec l'empreinte originale calculée par le fournisseur.

**Si celle-ci diffère, le fichier est altéré et ne peut pas être considéré comme fiable** !

## Algorithmes

En cryptographie, il est important de bien sélectionner son algorithme afin d'assurer la robustesse de la protection.

Voici les fonctions de hachage recommandées **à ce jour** (2022), dans l'ordre du plus recommandé au moins recommandé :
-   Préférons SHA-3 (SHA-256 ou SHA-512 version 3) ou éventuellement BLAKE2 si disponible.
-   On peut tout à fait encore utiliser SHA-2 (comme les très répandus SHA-256 ou SHA-512 version 2) qui sont encore robustes.
-   On évitera tout ce qui est SHA-1, MD5 (malheureusement encore très (trop) répandu !!), MD6 (rarement utilisé, tant mieux !)

*Il est donc ici à noter que dès lors que nous verrons un fichier téléchargé avec une empreinte calculée grâce à MD5 ou à SHA1 uniquement, nous devrons nous méfier, même si l'empreinte que nous trouvons est la même !*

> En cryptographie, les choses évoluent vite : certains algorithmes peuvent, entre temps, avoir été cassés. Il est donc utile de se tenir informé ; pour l'instant, la liste ci-dessus est applicable, mais rien ne dit qu'elle le sera dans 5 ans ou dans 10 ans, surtout avec l'ère post-quantique !
{.is-warning}

### **Passons maintenant à la pratique...**
- **Rendez vous dans le tutoriel [dédié](/tutoriels/verifier-integrite) à la vérification de l'intégrité et des signatures de fichiers !**
{.grid-list}

# PGP - GPG

**PGP** [^⁷] , pour Pretty Good Privacy, est un **protocole de protection** initialement créé pour protéger les échanges par courriels. Créé dans les années 90 aux États-Unis, par un activiste politique assez connu à l'époque, Phil Zimmermann [^¹1], l’objectif était de fournir au plus grand nombre et surtout aux activistes, journalistes et partis politiques, un mécanisme de chiffrement et de signature, open-source - et donc accessible à tous - et de niveau militaire. D’ailleurs, pour la petite histoire, le gouvernement US de l’époque ne voyait pas d’un très bon oeil l’arrivée de PGP, et a commencé à enquêter puis a décidé de reprendre sous son aile le principe. PGP était ainsi réputé pour être assez robuste.

[^¹1]: [Phil Zimmermann](https://fr.wikipedia.org/wiki/Philip_Zimmermann)

> Note intéressante : Phil Zimmermann a depuis rejoint les équipes du moteur de recherche Startpage [^¹2] (cf. article sur les [Moteurs de recherche](/debutant/moteurs-recherche))!

[^¹2]: [Startpage](https://www.startpage.com/)

## Généralités

D'abord mécanisme ouvert à tous puis devenu propriétaire à la demande des autorités, **PGP** est aujourd'hui devenu au fil du temps la propriété de Symantec Inc. (d'ailleurs racheté récemment par Broadcom Inc., entreprise de puces électroniques). Heureusement, il a fait l'objet en parallèle d'un travail de standardisation *open source* afin de ne dépendre d'aucune licence, ni autre brevet privé. C'est ainsi qu'est né dans le même temps un standard ouvert, appelé **OpenPGP**, utilisé de nos jours sur nos machines.

**GPG** quant à lui correspond à un logiciel qui est une implémentation sur les systèmes GNU/Linux/Unix, logiciel nommé GnuPG ou GPG pour GNU Privacy Guard [^⁸] [^⁹]. Ce logiciel est ensuite devenu multi-plateformes.

> **Attention donc à ne pas confondre PGP et GPG ; PGP étant le protocole de sécurisation et OpenPGP le standard ouvert, et GPG faisant référence à l'outil GnuPG implémentant OpenPGP !**
{.is-info}

[^⁷]: [PGP](https://fr.wikipedia.org/wiki/Pretty_Good_Privacy)
[^⁸]: [GnuPG](https://fr.wikipedia.org/wiki/GNU_Privacy_Guard)
[^⁹]: [Manuel de GnuPG](https://gnupg.org/gph/fr/manual.html)

À ce jour, PGP (et par extension OpenPGP) est décrié par certains notamment pour sa complexité d'utilisation, même si beaucoup travaillent à sa simplification et qu'il est possible aujourd'hui de trouver des outils capables de simplifier les choses.

---

*Pour la petite histoire, Signal est apparu afin d'apporter une plus grande simplicité dans le chiffrement vs PGP ; ils ont donc créé cette messagerie afin de concurrencer PGP/OpenPGP via leur propre protocole.*

---

PGP/GPG est donc devenu un des mécanismes de protection des communications via courriels depuis quelques dizaines d'années, car son utilisation n’a cessé d’être étudiée et améliorée. En effet, il est aujourd’hui possible de générer soi-même ses paires de clés et de les utiliser dans ses échanges. L’utilisation est « pratiquement » transparente même si la configuration en amont est *plutôt délicate*. Dans la pratique, quasiment tous les mandataires de courriels sérieux (s’ils ne le proposent pas, changez de mandataires !) proposent, soit la génération de clés de sécurité, soit l’import de ces clés : il conviendra donc, dans le second cas, d’utiliser un logiciel PGP basé par exemple sur le standard [openPGP](https://www.openpgp.org/), afin de générer des clés sur votre machine et les importer dans le gestionnaire de courriels choisi. Sur Linux, par exemple, il existe une implémentation nommée **GnuPG ou GPG**.

## Les principes clés

PGP s'appuie, entre autre, sur le mécanisme de la **cryptographie asymétrique**. Oui, cette fois-ci, nous n'allons pas y couper, seulement rassurez-vous, nous allons étudier cela dans le calme...

### Cryptographie Asymétrique

Le principe de la cryptographie asymétrique consiste en l'utilisation de _deux (2) clés de sécurité_ (et non une seule) dont l'une est une dérivée de la première. Couramment nommé "bi-clé" ou "paire de clés" :
-   La première clé est appelée "**clé privée**" (ou souvent appelée "clé secrète" !)
-   La seconde clé est appelée "**clé publique**"

L'idée générale derrière ce procédé est de simplifier l'échange du secret partagé. En cryptographie symétrique, les 2 parties doivent s'échanger la même clé pour pouvoir communiquer des informations, ce qui implique potentiellement que cette clé unique puisse être interceptée. Les choses vont être différentes côté asymétrique : comme son nom l'indique, la clé publique pourra être communiquée sur le réseau aux destinataires, et la clé privée devra rester bien entendu privée, cachée (à tous prix !). En effet, en théorie, il n'est pas possible de retrouver la clé privée en possédant la clé publique. L'avantage ici est qu'une opération (chiffrement par exemple) sera effectuée par une clé, l'opération inverse par l'autre clé, ceci évitant donc de compromettre entièrement la chaîne de sécurité.

*Alors vous allez me dire : super, alors pourquoi on utilise encore la cryptographie symétrique ?*

Tout simplement, car celle-ci est bien, bien, bien plus rapide que son pendant asymétrique et génère des fichiers de sortie bien, bien moins encombrants. Vous ne souhaiteriez pas attendre de longues secondes, voire minutes, afin d'accéder à un message ou en envoyer un. Voilà pourquoi dans la plupart des cas, nous utiliserons de concert la cryptographie symétrique et asymétrique afin d'éviter les ralentissements dans les communications.

À suivre, 2 exemples qui illustrent très bien ces concepts.

-   L'un des premiers emplois de PGP est d'assurer l'intégrité et l'authenticité d'une information. Pour ce faire, nous utilisons les signatures numériques. Celles-ci ont l'avantage de pouvoir fournir une confiance élevée dans :
¤ la fiabilité de l'information, 
¤ l'authenticité de son expéditeur. 
Nous vous renvoyons au second chapitre de l'article pour reprendre ces concepts. 

Voici donc le principe dans les grandes lignes :

_Exemple 1 :_ *Mettons un expéditeur - Alice - souhaitant transmettre un courriel à un destinataire - Bob.*

1.  Alice, l'émettrice, a préalablement généré sa paire de clés (publique et privée). Alice aura également au préalable permis à Bob de rapatrier la clé publique d'Alice, par le moyen qui leur convient.
2.  Alice écrit son message et applique une fonction de hachage sur celui-ci, mettons SHA-256, pour obtenir l'**empreinte**.
3.  Alice vient ensuite chiffrer cette empreinte avec sa **clé privée**, pour obtenir une **signature numérique**.
4.  Alice transmet le message, dans lequel cette signature est ajoutée au message.
5.  Bob - le destinataire - calcule l'empreinte du message, reçue avec le même algorithme SHA-256 qu'Alice, et obtient une empreinte.
6.  Bob utilise la clé publique d'Alice pour déchiffrer la signature numérique et obtenir l'empreinte qu'Alice a obtenu en (1).
7.  Bob peut ainsi :
    -   vérifier l'auteur de la donnée grâce aux métadonnées de la clé et à la signature : cela s'appelle l'identification, et concourt à l'authenticité de la donnée et de l'expéditeur,
    -   comparer les 2 empreintes (intégrité) : si l'empreinte a changé, la donnée est corrompue, il y a donc perte d'intégrité. Dans le cas contraire, la donnée est intègre et fiable.

![Principes de la signature numérique](/images/signature_pgp.png "Crédits : CNIL" ){.align-center}

-------------------
-   Le cas d'utilisation précédent permet d'authentifier et d'assurer l'intégrité de l'information, c'est une excellente chose, néanmoins le message n'est pas confidentiel. PGP permet donc aussi d'assurer la confidentialité d'une information. Pour ce faire, PGP utilisera la cryptographie symétrique de concert avec la cryptographie asymétrique, d'une manière différente que pour les signatures.

_Exemple 2 :_ *Reprenons nos 2 protagonistes, Alice qui cette fois-ci souhaite envoyer un courriel à notre ami Bob, et contenant cette fois-ci une photocopie de sa carte d’identité (qu'elle souhaite garder confidentielle et on la comprend !).*

1.  Bob, le destinataire, aura préalablement généré une paire de clés (clé publique et clé privée) et aura transmis la clé publique à Alice l'émettrice.
2.  Alice a écrit son message et ajouté sa photocopie en pièce jointe, et entre temps a généré une clé symétrique (appelée aussi *clé de session*).
3.  Alice chiffre le message intégral grâce à la clé symétrique du point (2).
4.  Alice va également chiffrer cette clé symétrique par la **clé publique** de Bob, reçue préalablement.
5.  Le message est envoyé à Bob avec la clé symétrique (pour rappel chiffrée elle-même par la clé publique de Bob).
6.  Le message est reçu par Bob. Il déchiffre sans problème la clé symétrique grâce à sa **clé privée**.
7.  Bob peut donc à ce moment déchiffrer le message en lui même grâce à la clé symétrique maintenant connue.

![Principes du chiffrement PGP](/images/chiffrement_pgp.png =600x){.align-center}

Le principe n'est évidemment pas trivial mais l'important est de plutôt comprendre les aspects de la paire de clés asymétriques :
-   on signe avec une clé privée et on vérifie la signature avec une clé publique.
-   on chiffre avec une clé publique et on déchiffre avec une clé privée.

> **TRÈS IMPORTANT : Une clé privée ne se transmet JAMAIS, en tout cas jamais sur un réseau !**
{.is-danger}

> **Bon dans la réalité, rassurez-vous, ces 2 exemples ne sont pas séparées et tout ceci sera bien plus transparent !**
{.is-success}


### Une histoire de confiance

Bien souvent lorsqu'il s'agit de sécurité de l'information, un principe incontournable s'applique : **la confiance**.

La confiance tout d'abord dans l'utilisation des moyens de protection que nous mettons en place, c'est-à-dire ici en premier lieu les *clés de sécurité*. Cette confiance doit être atteinte en respectant toutes les exigences nécessaires spécifiées au travers des standards et des normes. Dans notre cas, pour PGP, afin d'arriver à construire cette confiance dans l'outil, la génération de bi-clés devra respecter :
-   Une génération d'une bi-clé **maître** ou **racine** (grossièrement appelée clé maître), qui servira exclusivement à signer d'autres clés
-   une génération de sous-clés par fonction de protection souhaitée (Signature, Chiffrement, Authentification)
-   Si besoin, une sous-clé de compatibilité, qui pourra servir si des utilisateurs n'ont pas les dernières versions des outils

Cette *règle de l'art* apporte un avantage certain et non négligeable : les sous-clés sont liées à la clé maître (clé maître gardée bien au chaud), mais elles pourront être *révoquées* indépendamment sans impact sur les autres sous-clés. Si une de ces clés venait à être perdue voire compromise, il serait facile d'en générer une nouvelle via la clé maître et révoquer l'ancienne. Alors que si la clé maître avait été perdue ou compromise, il aurait fallu recommencer toute la génération et la chaîne de confiance tissée au fur et à mesure (les signatures des autres clés, voir partie Toile de confiance). Sans compter que l'attaquant aurait pu générer ses propres sous-clés à partir de cette clé maître et ainsi signer et chiffrer des messages en se faisant passer pour vous.

Un article très intéressant sur linuxfr [^¹0] discute de cet aspect avec plus de détails.

[^¹0]: [Gestion des clés](https://linuxfr.org/users/gouttegd/journaux/de-la-gestion-des-clefs-openpgp) 

Puis, ensuite, vient la confiance que l'on place dans un tiers, auprès duquel nous avons obtenu une information (une image ISO par exemple). À ce titre, si nous souhaitons en vérifier la fiabilité et l'origine, nous allons devoir établir une confiance avec ce tiers. Vous l'aurez compris, PGP va nous permettre de créer cette confiance. Ce, en abondant les bi-clés des-dits tiers, et en signant ces clés, dans ce que l'on nomme **le magasin de clés**. Sans ces bi-clés, une signature numérique ou un fichier ASCII d'empreinte pourrait très bien avoir été généré par une personne quelconque, sans que nous puissions en tracer l'origine. Grâce à ces bi-clés, qui auront été certifiées par des signatures ou du chiffrement, nous pourrons dire au logiciel PGP utilisé que nous avons confiance dans ce tiers, et que, par extension, tout ce qui aura été certifié par ces clés pourra être fiable.

Souvent, lors d'une vérification, nous obtenons le message suivant (extrait d'une commande GnuPG) :

```brainfuck
gpg: Attention : cette clef n'est pas certifiée avec une signature de confiance.
gpg: Rien n'indique que la signature appartient à son propriétaire.
```

Ici, ce message n'indique ni plus ni moins que nous avons oublié d'ajouter une clé de confiance dans notre magasin de clés et/ou de la signer, et que donc le logiciel même s'il valide l'empreinte ne peut valider complètement la chaîne de confiance jusqu'à l'auteur de la signature et s'assurer que la bonne clé privée a été utilisée.

OK je sens que nous vous avons perdu. Faites une pause, on arrive à la partie la plus amusante !

Bon en vrai, là si vous avez tout retenu, vous êtes un crack ;-).

### **Passons maintenant à la pratique...**
- **Rendez vous dans le tutoriel [dédié](/tutoriels/gnupg) à GPG afin d'appliquer la théorie !** 
{.grid-list}

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo, Nemtech*
<br>