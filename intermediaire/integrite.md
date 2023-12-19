---
title: Qu'est-ce que l'intégrité des données
description: Un article dédié portant sur l'intégrité et les signatures électroniques
published: true
date: 2023-12-19T09:00:16.699Z
tags: intégrité, pgp, gpg, integrite, signatures
editor: markdown
dateCreated: 2023-10-28T09:53:37.530Z
---

# Intégrité
**Qu'est ce que l'intégrité ?**

> Par définition :
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

### **Passer à la pratique...**
- **Rendez vous dans le tutoriel [dédié](/tutoriels/verifier-integrite) à la vérification de l'intégrité et des signatures de fichiers !**
{.grid-list}

# Signature électronique

- Nous entrons dans un sujet assez complexe : l'aspect Signature électronique, notamment au travers PGP/GPG pour l'illustrer.

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

### **Passer à la pratique...**
- **Rendez vous dans le tutoriel [dédié](/tutoriels/gnupg) à GPG afin d'appliquer la théorie !** 
{.grid-list}

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo, marmotte et Theudric*