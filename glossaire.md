---
title: Glossaire
description: Pleins de définitions utiles
published: true
date: 2024-01-16T11:43:59.126Z
tags: glossaire, debutant, intermédiaire, débutant, intermediaire
editor: markdown
dateCreated: 2022-11-25T17:34:26.638Z
---

Pour vous aider à vous y retrouver, voici un glossaire des acronymes, abréviations et termes souvent employés sur ce wiki.

> En informatique, l'emploi d'anglicismes est souvent incontournable. Nous essayons d'y recourir le moins possible.
{.is-info}

# ADB

Android Debug Bridge : "Pont de débogage Android" en français.

L'utilisateur n'ayant pas les droits "root" sous Android (voir "Rooter" plus bas dans le glossaire), l'usage est d'utiliser un ordinateur depuis lequel réaliser les actes d'administration avancés à destination du smartphone.

Pour y parvenir, on crée "un _pont_" entre l'ordinateur et le smartphone _Android_, pour "_déboguer_" ce dernier (même si les usages que nous en attendons s'éloignent du débogage), via un programme appelé Android Debug Bridge ou ADB.

Outre le débogage, on peut réaliser toute opération d'administration à privilèges élevés sur le smartphone, telles que :
- contrôler certains paramètres de sécurité qui nécessitent une élévation de privilège
- désinstaller les "pourriciels" (les "bloatwares") imposés par le fabriquant, et qui ne peuvent pas être désinstallés depuis le smartphone, vu que positionnés parmi les "applications système" (sys-apps): ce qu'on appelle "débloater" (et que nous traduirions par "dépourrifier")
> Dans notre contexte, nous allons utiliser ces fonctionnalités pour supprimer les surcouches applicatives imposées, et par Google, et par les fabricants eux-mêmes.
{.is-success}
- injecter des programmes d'installation Android ("APK" : Android Package, cf. ci -après) sur le mobile, en dehors d'un magasin applicatif ou d'un téléchargement en ligne d' "APK"
> Méthode que nous ne recommandons pas aux débutants, sans contrôles adéquats du fichier téléchargé, pour des raisons liées à l'intégrité de celui-ci, et d'où découle la sécurité de l'appareil mobile !
{.is-warning}

# API

Une API ou « Application Programming Interface » (interface de programmation d’application) est une interface logicielle d'accès à un service tiers.
C'est en quelque sorte la "multiprise" qui sert à un appareil pour se connecter à différents serveurs informatiques eux-mêmes offrant différents services.

_Par exemple_ : Google fournit une API qui permet d'avoir accès à leurs vidéos Youtube, l'application NewPipe (sur Android) va utiliser cette API pour lister, visionner et télécharger les vidéos.

# APK

Android PacKage : littéralement "Paquet Android" (sous-entendu paquet logiciel).

L'extension `.apk` est le format pour les fichiers exécutables qui permettent d'installer une application Android. Ils se présentent sous la forme "nom_application.apk".

Voici d'autres exemples de formats de fichiers d'installation sur d'autres systèmes d'exploitation :
- `.deb` pour les distributions GNU/Linux basées sur Debian (Ubuntu, ...)
- `.msi` (ainsi que `.exe`) pour Microsoft Windows
- `.dmg` pour Apple MacOS

![apk-image.jpeg](/images/apk-image.jpeg =100x){.align-center}

> Le téléchargement direct de fichiers APK, en dehors d'un magasin d'applications, est réservé à minima aux profils intermédiaires.
> Si vous effectuez ce genre de manipulation sans réaliser de contrôle de [l'intégrité](/tutoriels/verifier-integrite) du fichier, le risque encouru est de télécharger un fichier dont la signature unique ne correspond pas à celle du programme officiel, porte ouverte à un éventuel logiciel malveillant.
>
> **Nous nous [déchargeons de toute responsabilité](/avertissement) si vous réalisez une telle opération, sans maîtriser ce que vous faites.**
{.is-warning}

# Blockchain

Une blockchain, littéralement chaîne de blocs, est une technologie comportant 3 caractéristiques principales :
1. Elle est construite par une liste de blocs de données, qui sont en fait des enregistrements;
2. Chaque bloc référence le précédent, et y inclut sa signature - ou une empreinte numérique (hash) -, de sorte à les protéger contre la falsification;
3. Afin d'accorder une **légitimité** à la chaîne, un _consensus_ doit avoir lieu entre les participants : un consensus est un ensemble de règles qui régissent la façon dont sont approuvés les blocs (on parle par ex. de consensus de PoW ou "Proof of Work" pour preuve de travail ou de PoS pour "Proof of Stake" pour preuve de participation).

Une blockchain doit en théorie atteindre ce consensus sans avoir recours à une tierce partie ; c'est un consensus établi grâce à un environnement _**distribué**_ et/ou _**décentralisé**_. C'est-à-dire en se basant sur un groupement de plusieurs machines et/ou ressources, dont on emprunte une partie de l'espace de stockage et de la puissance de calcul, afin d'inscrire les blocs et les signer. Et afin de renforcer son côté légitime.

![blockchain.jpg](/images/blockchain.jpg =700x){.align-center}

Wikipedia en fournit une [définition plus technique de la blockchain](https://fr.wikipedia.org/wiki/Blockchain). Nous préférons néanmoins notre définition que nous estimons plus abordable.


> C'est notamment la technologie utilisée par les cryptomonnaies, ou même encore certains services de messageries chiffrées, comme Session.
{.is-info}

# Bot

Egalement appelé "robot internet".
Il s'agit d'un programme capable d'exécuter certaines tâches automatiquement et suivant ce que son auteur a programmer. Il peut s'agir d'un programme utile tout autant qu'un programme malveillant.

Nous discutons de ce type de programme malveillant dans l'article [Améliorez votre hygiène numérique](/hygiene-numerique#malware-virus-trojan), à la section Malware-Virus-Trojan.

# BootLoader

Vient du terme "boot" en anglais, lui-même lié au mot "[bootstrap](https://en.wikipedia.org/wiki/Bootstrapping)". C'est la petite languette qui se trouve à l'arrière d'une chaussure permettant de la chausser facilement.

Étymologiquement, ce mot viendrait de l'expression "to pull oneself up by one's bootstraps", en référence aux "Aventures du Baron de Munchausen" qui se serait tiré tout seul d'une situation périlleuse sans l'aide de personne :-/ !

En informatique, ce chargeur d’amorçage (bootloader, bootstrap) est un bout de code qui est stocké sur un périphérique de stockage (ROM, EEPROM, Flash) qui va se charger lui-même, à partir de rien.

Il va ensuite enchaîner avec le processus de démarrage de l'appareil en faisant appel éventuellement à d'autres programmes pour, en définitive, charger et afficher le système d'exploitation (OS ou "Operating System") prévu par le constructeur.

Le "bootstrap" fait appel à plusieurs niveaux de bootloader :

-   _Premier niveau_ sur ordinateur personnel : on va parler de BIOS ou EFI/UEFI pour les systèmes propriétaires, de CoreBoot ou LibreBoot pour les systèmes libres.
-   _Deuxième niveau_ sur ordinateur personnel : NTLDR ou BOOTMGR pour Microsoft, iBoot ou BootX sur Apple, SysLinux ou GNU/GRUB sur les OS libres GNU/Linux et BSD (FreeBSD loader, ...).

Sur Android, le bootloader est installé par le fabricant et, tout comme sur ordinateur personnel, il va se charger d’enchaîner avec le chargement des différents bouts de code jusqu’au système d'exploitation Android OEM du fabricant.
Durant ce processus, le bootloader va notamment vérifier l'intégrité, la signature, la validité de tous les éléments chargés en mémoire, que ce soit sur ordinateur avec SecureBoot ou sur Android avec "Trusted Execution Environment".

Sur ce dernier, les partitions boot vont être analysées et, si elles sont valides, le kernel Linux (ou noyau Linux) sera chargé ainsi que le système d'exploitation (OS). Sinon, au mieux, un message d'avertissement est affiché et, au pire,... le téléphone est bloqué (on parlera alors de téléphone "brické").

# Briquer ou Bricker

Du terme anglais "bricked" (briqué, transformé en brique) : se dit d'un appareil dont l'intégrité du Firmware (micrologiciel, microprogramme, microcode, logiciel interne ou encore logiciel embarqué, cf. ci-après) n'est plus bonne, et par conséquent il devient inutilisable (ne démarre plus, redémarre en boucle ou affiche un [Screen Of Death](https://en.wikipedia.org/wiki/Screen_of_death) ("écran de la mort").

Il existe des "semi-brick" (réparables) et des "brick" intégraux ("full-brick" : irréparables, sauf dans certains cas par le fabricant).

# Chargeur d'amorçage

Voir [Bootloader](#bootloader) ci-haut.

# Checksum

La somme de contrôle (ou "checksum") est une valeur hexadécimale (suite de chiffres et de lettres entre 0-9 et A-F) qui est unique pour un fichier donné. C'est une méthode de contrôle. Il existe divers algorithmes qui permettent de calculer cette somme comme MD5, SHA1, SHA2, SHA3...

On utilise un outil basé sur ces algorithmes pour calculer cette somme et ainsi vérifier qu'un fichier est intègre, c'est-à-dire qu'il n'a pas été altéré durant son "transport".

> Nous renvoyons à cet [article](/tutoriels/verifier-integrite) pour apprendre à vérifier l'intégrité d'un fichier.
{.is-info}

# Daemon

Un Daemon (Deïmon) est un terme anglais qui désigne un service ou un groupe de services s'exécutant en arrière plan de l'OS afin de réaliser des actions sur le matériel, répondre à des requêtes réseau... sans contrôle direct par un utilisateur.

Nous pouvons citer par exemple, sous UNIX :
- Les services réseau ou de type serveur comme par exemple SSH ou HTTP ou LPD pour les imprimantes. Ils se terminent souvent par un "d", par ex. `httpd`, ou `lighttpd` ou `sshd`
- Les services de tâches récurrentes, comme par ex. `crond`


# DHCP

Le DHCP (Dynamic Host Configuration Protocol) est comme son nom l'indique un protocole de configuration dynamique des hôtes.

C'est donc un protocole réseau qui va s'occuper de configurer les paramètres des équipements connectés à un réseau.

C'est généralement la "box" de votre fournisseur Internet qui s'en charge sur votre réseau local. Ainsi lorsque vous branchez un PC avec un câble ethernet ou que vous connectez un smartphone à votre Wifi, ceux-ci obtiennent automatiquement une adresse IP et un nom de domaine (cf. DNS) vers qui envoyer les requêtes.

# Distribution (ou distro)

Il s'agit ici des différentes variantes d'un Système d'Exploitation (SE en français / OS en anglais). Pour citer un exemple parlant du quotidien : lorsque l'on parle d'Android, il s'agit du type de système d'exploitation... Android étant "le socle", ce dernier peut se présenter sous différentes variantes, telles que :
- One UI pour les smartphones Samsung,
- EMUI pour les smartphones Xiaomi et Huawei,
- Pixel Experience pour les smartphones de chez Google.

Tous font bien partie du système d'exploitation Android ; ils n'en sont que des variantes (on parle également de ROMs pour Android), qui incluent les applications de la marque du fabricant, ainsi qu'une personnalisation de la façon de naviguer dans l'OS qui est leur marque de fabrique.

Pour GNU/Linux, la démarche est la même : au même titre que pour Android, de par la nature ouverte de la méthode de développement du SE (grâce au code source ouvert), on peut en réaliser autant de variantes. Avec des interfaces et des logiciels pré-installées différents selon les besoins : pour la cyber-sécurité, pour les chercheurs en science, pour l'éducation, etc...
Les environnements de bureau et logiciels pré-installés sont ainsi **distribués** de manière différente : d'où le terme _distributions_, quand on parle des variantes d'Android ou de GNU/Linux.

Aussi, nous vous invitons à lire l'article sur les principales [distributions Linux](/debutant/linux-distributions).

> A distinguer des _versions_, qui représentent des itérations d'un système d'exploitation, et intègrent les mises à jour logicielles et de sécurité, avec un support assuré sur une certaine durée.
> 
> _Exemples_ : la version 20.04 d'Ubuntu, parue en l'année 2020 (20.) le mois d'avril (.04), et qui assure un support des mises à jour pendant 5 ans. Ou encore la version 22.04 d'Ubuntu, qui vous le devinerez est sortie en ... Avril 2022.
{.is-info}

# DNS

DNS (Domain Name System), est une sorte "d'annuaire des sites internet".

> Nous renvoyons à l'[article](/debutant/dns) dédié à ce sujet.
{.is-info}

# Dump (Base de données)

Un "dump" est une exportation des données stockées dans une Base De Données (BDD).

> On ne copie jamais les fichiers bruts d'une base de données, on fait plutôt un "dump".
> ~~ Soit à l'aide d'une exportation au format SQL,
> ~~ Soit avec les outils inclus avec le SGBD (Système de Gestion de Bases de Données).
{.is-warning}

- Pour MySQL, MariaDB, PostGreSQL, les dumps sont constitués d'une suite de commandes SQL permettant de recréer les tables, les permissions et données d'une base.
- Sur d'autres comme Oracle, SQLServer, le dump sera une copie binaire des données.

> Cette action permet de sauvegarder une base dans un état intègre (c.à.d. sans dégradation, sans corruption) et permettre de restaurer les données si un problème survient.
{.is-success}

# Durcissement

Voir [Hardening](#hardening) ci-après.

# Exploit

Dans le langage de la cyber-sécurité, un "exploit" est un bout de code ou une suite de commandes qui **_exploite_** une vulnérabilité ou un bug afin de s'introduire sur la machine cible et d'effectuer des actions de compromission attendues (chiffrement pour rançon, infection pour espionnage, infection pour déni de services, etc.).

# FAI

Fournisseurs d'Accès à Internet, comme par exemple :
- en France : Orange, Bouygues Telecom, SFR ou Free.
- en Allemagne : Deutsche Telekom, Vodafone, O2.
- aux USA : AT&T, Verizon.

# Firmware

Traduit en français par "microcode" ou "micrologiciel", il s'agit d'un logiciel embarqué dans du matériel. 

Concrètement, il peut servir d'intermédiaire entre les composants qui forment l'appareil utilisé - comme détaillé ci-bas - et le système d'exploitation. L'UEFI ou "BIOS" est le firmware lié au processeur, qui gère tous les paramètres de la machine : quel volume de stockage est lu en premier (disque dur ou clé USB, disquette pour les plus anciens :)), est lancé en premier, dans quel ordre les différents systèmes d'exploitation sont lancés au démarrage de la machine ?...

Plus techniquement, un firmware est une forme de logiciel s'occupant d’interagir au plus bas niveau avec les composants électroniques de la cible matérielle (l'appareil dans son ensemble, ainsi que les périphériques : écran, clavier, souris...) ; il s'agit donc d'un logiciel dit de bas niveau, capable d'être une couche d'abstraction pour des logiciels de plus haut niveau comme les systèmes d'exploitation.

Le firmware est ainsi généralement présent dans des composants numériques comme une carte réseau, un lecteur de CD-ROM mais aussi dans des appareils plus complexes comme une télévision, un routeur, une télécommande, une caméra ou bien entendu un ordiphone (smartphone).

# Flasher

Flasher un Firmware : consiste à injecter du code sur un support de stockage (par exemple une mémoire). Cela revient à reprogrammer complètement le programme d'un appareil pour modifier son fonctionnement, le remplacer, résoudre une défaillance (bug) ou combler une faille de sécurité.

# Fork

De l'anglais "fourche", pour signifier la déviation depuis un matériau originel ; l'utilisation de ce terme se fait sous 2 angles différents :

1. Le premier angle est la définition standard du mot "fork" : fork sur les systèmes UNIX est une fonction qui permet de dupliquer un processus (programme en cours d'exécution) afin par exemple d'assurer un traitement parallèle. Au delà de la pure notion de duplication, il existe également une notion de filiation : le processus père alloue à son clone - le processus fils - tous ses attributs.

2. Le second angle est principalement utilisé en développement : créer un fork signifie, grossièrement, dupliquer le code source d'un logiciel existant pour en créer un nouveau.

# FTP

FTP est l'acronyme de "File Transfert Protocol". Le FTP est un très ancien protocole, dédié au transfert de fichiers sur un réseau, et toujours utilisé pour beaucoup d'usages notamment :
- l'envoi de fichiers Web (html, php, css, .. ) pour mettre à jour son site internet chez son hébergeur en mutialisé
- communiquer avec sa box (exemple : freebox) lorsque celle-ci est utilisée en mode NAS.

Nous recommandons d'utiliser 
- Sur machine PC : le client FTP [Filezilla](https://filezilla-project.org/), sous licence libre et disponible sur toutes les plateformes. Un des meilleurs outils FTP.

> Les réglages par défaut de Filezilla sont les suivants :
> ~~ la détection automatique de l'encodage du fichier (ou charset en anglais)
> ~~ la détection automatique du type de transfert en ASCII ou binaire
> Ces réglages satisfont la majorité des besoins. Nous vous conseillons de ne pas les changer.
{.is-info}

- Sur Android : le client FTP [FTPClient](https://f-droid.org/packages/de.qwerty287.ftpclient/) est tout indiqué.

# Hack - hacker
De l'anglais "hack" : bidouiller, faire preuve d'astuce.

Loin des clichés des pirates informatiques, le terme "hackeur" remonte aux origines de l'informatique moderne, dans la bataille que le fondateur du logiciel libre - Richard Stallman - livre depuis plusieurs années contre les multinationales prédatrices, et privatrices de l'informatique. Multinationales qui ont privatisé un secteur précédemment ouvert via leurs licences (ou "copyright"), là où les programmes s'échangeaient précédemment sans aucune restriction concernant leur étude, ou leur amélioration.

Cet [article](/https://www.telerama.fr/techno/richard-stallman-hacker-vaillant,51770.php), qui présente R.M. Stallman comme un "hacker vaillant" illustre bien le sens initial du mot "hack" - bidouiller, faire preuve d'astuce pour résoudre une problématique - par la suite dévoyé... Pour illustrer ce terme, on peut citer les vidéos de "life hacks" ou bidouilles / astuces du quotidien !

Peut-être les multinationales comme Microsoft ou Apple ont-elles influencé le sens de ce terme informatique en un terme négatif - l'assimilant systématiquement à du piratage - pour discréditer un mouvement qu'ils estimaient menacer leur modèle économique ? Ou peut-être ce terme a-t-il été détourné par les médias, par mécompréhension de la philosophie sous-jacente ? Quoi qu'il en soit, un pirate informatique est un "hackeur" en ce qu'il "bidouille", et le matériel, et les accès sécurisés d'un matériel.

Cependant un "hacker" n'est pas nécessairement un pirate informatique... Installer un jeu vidéo sur un robot de cuisine en remplaçant son système initial, représente ainsi un hack qui permet de faire montre de toute son astuce et ses compétences informatiques. Ou même remplacer un système Android fourni avec le téléphone, par une version plus respectueuse de la vie privée...

# Hardening

Le Hardening, ou **Durcissement** en français, consiste à renforcer la protection du système ou de la cible à durcir, et ainsi réduire la surface d'attaque. En complément de la sécurité périmétrique (pare-feu, IDP/IPS...), le durcissement est un processus qui permet de garantir une protection en profondeur. Ce processus doit pouvoir réduire les menaces externes et internes, ainsi que diminuer le risque d'erreurs de configuration.

En règle générale, cela consiste, par exemple :

-   à appliquer les derniers correctifs et mises à jour,
-   à supprimer les services ou objets non utilisés (_Exemples_ : débloater Windows ou un smartphone Android, désactiver les services NFS si non utilisés, etc.),
-   à suivre les recommandations (ou "hardening guidelines") pour les services exposés (SSH, TLS etc.),
-   etc.

# Hardware

Est l'anglicisme pour désigner en français un "matériel".

# IP

IP (Internet Protocol) désigne en fait une ensemble de protocoles de communication conçus pour Internet par Vinton Gray Cerf et Bob Kahn dans les années 1970. Communément, dans le jargon, lorsque nous parlons d'IP on désigne plutôt une adresse IPv4 comme par exemple : `192.168.1.134`.

Plus d'informations à propos de la terminologie IP sur la page dédiée sur [Wikipedia](https://fr.wikipedia.org/wiki/Internet_Protocol).

# Kernel

C'est le noyau. Généralement il est intégré à un système d'exploitation. Parmi les plus connus :

-   Linux Kernel (GNU/Linux distro)
-   Free/Open BSD Kernel (BSD distro)
-   Windows NT Kernel (Microsoft)
-   XNU Darwin Kernel (Apple)

# LDAP

LDAP (pour Lightweight Directory Access Protocol) est un système d'annuaire, et un protocole réseau permettant de centraliser la gestion des utilisateurs et des clients (grosso modo les ordinateurs) sur un réseau. C'est un service principalement utilisé dans les entreprises et les infrastructures informatiques.

L'avantage d'un tel système est par exemple d'offrir un grand nombre de services Internet, mais l'utilisateur n'aura besoin que d'un identifiant/mot de passe pour se connecter à n'importe lequel de ces services. De même, lorsqu'un parc informatique est grand, il permettra de gérer toute ou partie des clients de manière centralisée.

![fonctionnement-ldap-avec_gnu-linux.jpeg](/images/fonctionnement-ldap-avec_gnu-linux.jpeg){.align-center}

# Logiciel gratuit

Un logiciel gratuit (appelé également gratuiciel ou freeware) est un logiciel dont le code est fermé (propriétaire), mais distribué gratuitement.

# Logiciel libre

Un logiciel libre est un logiciel qui respecte ces 4 libertés (numérotées 0 à 3) :

0. La liberté d'exécuter le programme, pour tous les usages ;

1. La liberté d'étudier le fonctionnement du programme et de l'adapter à ses besoins ;

2. La liberté de redistribuer des copies du programme (ce qui implique la possibilité aussi bien de donner que de vendre des copies) ;

3. La liberté d'améliorer le programme et de distribuer ces améliorations au public, pour en faire profiter toute la communauté.

_Plus d'informations_ : Les [4 libertés essentielles](https://www.gnu.org/philosophy/free-sw.fr.html#four-freedoms).

A la différence du logiciel "open-source" qui se veut technique et marketing, le logiciel libre vise l'éthique et la liberté. Il s'agit d'un mouvement philosophique, politique et social à la différence de l'open source qui en est désintéressé.

Exemple de logiciels libres : Mozilla Firefox, VLC, LibreOffice.

# Micrologiciel

Ou microcode ou logiciel embarqué.

Voir Firmware ci-avant.

# OEM

OEM, pour "Original Equipment Manufacturer" (fabriquant d'équipement d'origine), est un terme qui désigne un fabriquant de pièces détachées qui vend à des entreprises pour un produit final, plus complexe.

Par exemple, un ordinateur personnel (PC) de marque Asus ne sera pas forcément uniquement équipé de composants matériels et de logiciels de la marque Asus, mais également d'autres constructeurs tels que : Intel, Nvidia, AMD, Seagate, Microsoft (pour Windows par exemple) etc.

# Open source

Open Source : littéralement "à source ouverte".
*A ne pas confondre avec un logiciel gratuit.*

C'est à dire dont le code source, la "recette de fabrication" du logiciel est ouverte au public. Cumulée aux [4 libertés essentielles](#logiciel-libre), c'est une des caractéristiques des logiciels libres. Il s'inspire de l'idée marketing qu'un produit qui peut-être examiné par tout le monde sera nécessairement de meilleure qualité. Cependant un logiciel peut être open source sans être libre, dès lors qu'il ne respecte pas les 4 libertés essentielles ci-haut mentionnées : l'open source est avant tout un standard de développement, qui garantit que le "logiciel fait bien ce qu'on dit qu'il fait", sans mensonge ni omission possible, de par la publication du code source ("la recette de fabrication").

Pour plus de détails sur la distinction entre un logiciel simplement "open source" et un logiciel "libre (et open source)", suivre [ce lien](https://fr.wikipedia.org/wiki/Logiciel_libre). Et pour ceux qui veulent entrer plus dans le détail (intermédiaires ou débutants curieux), les listes de licences suivantes sont disponibles sur le site de leurs fondations :
- libres de droits (GPL) : https://www.gnu.org/licenses/license-list.fr.html
- open source : https://opensource.org/licenses/category

# OS (SE)

Pour "Operating System" ou Système d'exploitation en français.

Sorte de "super logiciel", qui permet à l'utilisateur final d' "exploiter" (entendre ici *utiliser*) l'éco-"système" de la machine qu'il a entre les mains. Le système d'exploitation fait ainsi l'intermédiaire de premier niveau (complété par le firmware pour les périphériques : écran, clavier, souris, imprimante) entre l'utilisateur final et les applications (bureautique, navigation internet...), ou même le matériel lui-même (exemple : je clique sur éteindre : je communique directement avec le matériel).

Par exemple, lorsque l'utilisateur utilise la souris, le système d'exploitation interagit avec le firmware de la souris, pour afficher les déplacements réalisés par l'utilisateur, depuis l'écran.

Il s'agit ainsi d'une collection de programmes dont les fonctions sont d'orchestrer l’interaction des divers composants d'un appareil (PC, Smartphone, ...) grâce aux firmwares et logiciels installés sur ce même appareil.

![os.png](/images/os.png =200x){.align-center}

Parmi les OS les plus connus :
-   Les centaines de distributions GNU/Linux (entendre variantes de : voir la définition de "Distributions" ci-haut) : Debian, Ubuntu, Fedora, Red Hat, openSUSE...
-   Les dizaines de distribution BSD : FreeBSD, OpenBSD ...
-   La série des Microsoft Windows (et bien avant eux DOS), incluant Windows Phone OS
-   Apple avec ses OS macOS et iOS
-   Android (LineageOS, GrapheneOS, /e/OS...)

> Pour en savoir plus au sujet des distributions GNU/Linux, nous vous invitons à lire l'article sur les principales [distributions Linux](/debutant/linux-distributions).
{.is-info}

# OTP

De l'anglais "**O**ne **T**ime **P**assword" : Mot de passe à usage unique.
Produit à partir d'un objet physique ou virtuel, ce "One Time Password" donne des droits pour accomplir certaines opérations.

Généré depuis une application mobile - objet virtuel - :
![exemple_otp.jpeg](/images/exemple_otp.jpeg =300x){.align-center}

Ou depuis un boîtier prévu à cet effet - objet physique - comme ce boîtier proposé par une banque :
![boîtier_-otp-modif_sans_marque_bk.jpg](/images/boîtier_-otp-modif_sans_marque_bk.jpg =300x){.align-center}

Il s'agit d'un "jeton" utilisé dans le cadre d'une authentification à double facteur, ou multi-facteurs. Cette technologie a évolué vers **TOTP : Time-based One Time Password** (cf. ci-après).

> Nous vous renvoyons d'ailleurs vers les différents articles sur l'hygiène numérique [ici](/hygiene-numerique#acc%C3%A8s-aux-informations-ou-authentification) et [ici](/hygiene-numerique#authentification), pour bien comprendre et obtenir de plus amples détails.
{.is-info}

# Partition

Un périphérique de stockage (disque dur, mémoire flash...) peut être compartimenté en plusieurs zones de stockage secondaires, de sorte que chaque zone puisse être administrée séparément. Ces zones sont donc appelées des "*Partitions*".

Exemple de partitions allouées pour chaque système d'exploitation ; partitions Windows avec le logo "fenêtre" <span class="mdi mdi-microsoft-windows-classic"></span> (01, 05 et 07) ; partitions GNU/Linux symbolisées par le manchot <span class="mdi mdi-penguin"></span> (03, 04 et 06) :

- **La partition 02 est une partition étendue et n'a pas de système de fichiers désigné. Elle permet juste de créer des partitions logiques sur une table de type MBR.**

![partions_os.webp](/images/partions_os.webp =600x){.align-center}

> Notez qu'avant de créer des partitions manuellement, il vous faudra créer une table des partitions sur le disque.
> ~~ Les UEFI (BIOS récents) utilisent une table de type GPT (à privilégier).
> ~~ Les BIOS utilisent une table de type MBR/DOS (sur les appareils anciens).
> Pour en savoir plus, consultez l'[article Wikipedia sur GPT](https://fr.wikipedia.org/wiki/GUID_Partition_Table).
{.is-info}

> Sur chaque partition, on choisit un système de fichiers (ext4, btrfs, zfs, swap, ...) et éventuellement un point de montage (/home, /var, ...) : cf. la définition d'un [système de fichier](#syst%C3%A8me-de-fichiers-fs) ci-après.
{.is-info}

# Ports réseau

Les ports réseau sont au réseau routier ce que sont les _sorties autoroutes_.

Des sorties d'autoroute numérotées (cf. tableau ci-après) suivant les "protocoles réseau" qu'elles utilisent, et qui servent à échanger des requêtes internet. Ces mêmes requêtes internet représentent ainsi le trafic, en entrée et en sortie, de l'appareil relié à internet.

**Les applications/services, selon les cas, écoutent ou émettent des informations sur ces ports**.

Exemples de ports réseau, d'après leur numérotation : 
![ports-réseau.jpeg](/images/ports-réseau.jpeg =600x){.align-center}


Parmi les ports les plus communs, on trouve les ports :
- 22 : SSH
- 80 : HTTP
- 443 : HTTPS

> Pour plus de détails sur les ports réseau, consulter l'excellent [article de Malekal](https://www.malekal.com/liste-des-ports-ports-reseaux-de-connexion-et-ce-que-cest/).
{.is-info}

# Propriétaire

Un système d'exploitation, programme, application "propriétaire" se dit d'un outil soumis à licence _commerciale_ pour son utilisation, et dont **le propriétaire est l'éditeur logiciel** et non l'utilisateur final, **par opposition aux logiciels libres**.

_Exemples_ : Windows, MacOS, Google Chrome, Safari, OneDrive, Gmail...

# Proxy

Sûrement un mécanisme dont vous n'avez que très peu entendu parler. Et pourtant, cette technologie est celle qui est la plus plébiscitée pour les réseaux (entreprises, universités, personnels...).

*Qu'est-ce qu'un proxy ?*

Un proxy est un élément d'un réseau qui va jouer le rôle d' **intermédiaire**. Schématiquement il s'agit d'un élément par lequel nous allons faire transiter toutes nos données, entrantes et sortantes, impossible d'y échapper donc (s'il est bien configuré !) :

![Principes d'un Proxy](/images/proxy.png =500x){.align-center}

Techniquement, il ne s'agit ni plus ni moins que d'un serveur avec des règles de filtrage particulières sur plusieurs niveaux. Ses fonctionnalités et objectifs sont divers :
-  L'anonymat (à un certain niveau) : il est tout à fait possible de faire appel à un proxy public afin de router le trafic via ce mandataire proxy. Ici donc, notre adresse IP est différente et il nous est possible donc de cacher la nôtre aux sites que l'on visite ! Attention cependant : ici le même problème que pour les VPN apparaît ; vous devez faire une absolue confiance en ce mandataire qui va réellement collecter votre adresse IP. Ce n'est donc **pas** un mécanisme recommandé pour atteindre l'anonymat.
-  Le contournement de la géo restriction : si vous faites appel à un mandataire proxy dans un autre pays, vous allez obtenir une adresse IP dans ce pays, ce qui peut donc vous donner accès à des sites ou contenus exclusivement liés à ce pays. Ici encore attention à la sécurisation des données en transit, un proxy ne chiffrant pas les échanges (hormis exceptions !).
-  La sécurité/le filtrage : imaginons que nous gérons une université, nous souhaitons donner accès à internet à nos étudiants (très utile pour eux !) mais nous souhaitons éviter qu'ils naviguent sur certains sites (porno par exemple)... Nous pourrons donc implémenter un proxy, avec des règles de filtrage sur des domaines liés à des sites pornographiques. Bon nous pourrions ici très bien nous contenter d'un pare-feu, mais un proxy viendra filtrer à plus haut niveau, et ainsi parfaitement utile. Vous l'aurez compris, un proxy est généralement utilisé dans une architecture réseau afin d'apporter une couche de sécurité, en parallèle d'autres mécanismes (pare-feu, IDS, VPNs...).

**Un proxy peut être une alternative dans une certaine mesure aux VPN grands publics, le chiffrement en moins dans la plupart des cas !**

# Recovery

C'est une "partition" de récupération (recovey en anglais) contenue sur les appareils Android et nommée recovery. Elle contient le mode de récupération Android.

Lorsque l'on veut remplacer le système Android, on doit alors le déverrouiller puis le "flasher" pour remplacer le recovery avec un Recovery personnalisé (Custom Recovery). Certaines custom ROM permettent de re-verrouiller ensuite l'appareil par souci de sécurité.

> Nous renvoyons vers l'article dédié à [Android et ses ROM alternatives](/debutant/android-roms) pour en savoir plus.
{.is-info}


# Réseau (Informatique)

Par définition, un réseau désigne un ensemble de points reliés les uns avec les autres par le biais de liaisons afin d’établir des communications.

Pour bien comprendre comment nous nous interconnectons, il est indispensable de comprendre qu’internet est un réseau, et si l’on veut être plus précis encore : un « réseau de réseaux ». Un réseau donc, que l’on définit comme public, c’est-à-dire ouvert à tous.

Par analogie : le réseau routier où les points sont les maisons (avec leurs adresses postales), les liaisons sont les routes (départementales, nationales, autoroutes...). C’est exactement ce qu’il se passe avec internet : les points sont les boîtiers internet des fournisseurs d’accès (avec leur adresse « IP » - Internet Protocol), les liaisons sont les câbles reliant les points entre eux (câbles communaux, câbles sous marins...).

Nous voyons apparaître ci-haut une notion fondamentale d’un réseau informatique : l’adresse IP. Plus précisément cette adresse IP est dite « publique », tout comme internet l’est, car visible par tous. Par analogie encore et afin de bien appréhender cette notion : l’adresse IP publique est à l’environnement numérique, ce que l’adresse postale est à l’environnement réel. Cette adresse est un identifiant « numérique » pour votre vie digitale, tout comme votre adresse postale est un identifiant physique pour votre vie réelle. C’est par ce biais que vous pouvez communiquer avec n’importe qui sur la planète via internet. Mais c’est aussi par ce biais que vous êtes identifiable sur internet !

Cette adresse vous est fournie (obligatoirement) par un FAI ou Fournisseur d’Accès à Internet (Orange, Bouygues... pour la France, AT&T, Verizon... pour les USA etc.) - qui vous procure un boîtier spécifique (boîtier internet) et vous assigne automatiquement une adresse sur le réseau internet, afin d’y avoir accès. Vous ne pouvez donc pas vous-même vous attribuer une adresse IP publique.

![Schématisation du réseau de réseaux internet](/images/internet.gif){.align-center}

*Petite particularité : vous avez sûrement un téléphone portable, avec une connexion 3G, 4G... Ici le boîtier internet sera en fait le module réseau du téléphone, associé à la carte SIM que vous livrera l’opérateur téléphonique (qui en somme est un FAI). A cette carte SIM sera associée une adresse IP publique, afin d’accéder au réseau internet. Attention donc à ne pas confondre votre boîtier internet à la maison (avec son Wifi probablement), et votre téléphone portable avec sa connexion 3G/4G/5G !*

*D’ailleurs petite note technique : afin que le réseau 3G/4G/5G puisse vous offrir un accès au réseau internet, les antennes relais 3G/4G/5G sont elles-mêmes reliées aux câbles communaux.*
  
> Attention à ne pas confondre réseau internet, par essence public, et réseau privé qui correspond au réseau que vous créez "chez vous". Et qui est différent du réseau internet. Par exemple en activant le Wifi sur votre Box, celle-ci crée un réseau privé sur lequel vos équipements peuvent se connecter via le Wifi...
{.is-info}


Par convention : une adresse IP se trouve par exemple, dans sa version actuelle la plus répandue, sous la forme suivante :

- 85.134.243.10

Pour les plus techniques d’entre vous : il s’agit bien sûr d’une représentation pour le protocole IP version 4, en attendant le basculement complet vers IP version 6, dont les adresses se présentent par exemple ainsi : 2001:db8:0:85a3:0:0:ac1f:8001.

> Une petite astuce afin de connaître son adresse IP publique : vous pouvez visiter ce site : [DNS Leak test](https://www.dnsleaktest.com).

# Réseau (Infrastructure)

Cette définition est en fait plusieurs définitions : nous présentons ici les différentes topologies réseau que nous mentionnons dans les articles et que vous avez sûrement dû entendre au moins une fois, ainsi que les architectures potentielles associées à ces topologies. Pour schématiser, voici ce dont nous parlons :

![topologie.jpg](/images/topologie.jpg =500x){.align-center}

## Topologies

### Centralisée
*Centraliser ; synonymes : concentrer, grouper.*

Le mode de réseau le plus répandu aujourd'hui. Il s'agit d'un réseau basé sur un serveur ou plusieurs serveurs mais dont l'infrastructure est opérée par une seule entité politique ou commerciale ou personne physique.

> Google en est un parfait exemple, avec entre autres les règles imposées pour la publication de contenus vidéos sur leur plateforme.

### Décentralisée
*Décentraliser ; synonymes : déconcentrer, dégrouper.*

Une définition à la mode... Bien que le principe est tout de même très complexe à appréhender.

Ce mode de réseau permet d'éviter de concentrer le pouvoir décisionnel d'une entité unique sur le reste du réseau. Ce, afin d'éviter les situations de monopole ou de censure. En revanche, les informations peuvent se retrouver à des endroits différents, ce qui *potentiellement* réduit le côté "safe" vs centralisé.

## Architectures

### Fédérée

Les "réseaux fédérés" sont par analogisme comme les états d'une fédération (état fédéral). Cela s'applique très bien pour expliquer cette  notion : sur un réseau fédéré, le service fourni (réseau social, blockchain...) représente l'entité parente sur le réseau : la "nation" qui "fédère" toutes les entités enfants. Les "instances" ou "noeuds" sont les "états", qui ont leurs propres particularités, mais sont toutes _fédérées_ sous la même bannière.

*On peut tout de même s'apercevoir ici qu'une certain niveau de centralisation est nécessaire à un réseau fédéré.*

> Mastodon, une alternative libre au réseau social Twitter en est un bon exemple, basé sur [ActivityPub](https://fr.wikipedia.org/wiki/ActivityPub), le protocole de réseau social fédéré.
{.is-info}

Techniquement, un réseau fédéré (social ou autre) est un type de réseau décentralisé, qui est composé de plusieurs fournisseurs de services (les instances, hébergées sur différents serveurs). Contrairement aux réseaux centralisés, les réseaux fédérés font donc reposer leur "toile" sur plusieurs instances, gérées par des entités différentes (serveur personnel d'un particulier, ou partie de stockage serveur mise à disposition par une association ou entreprise).

> Un autre exemple très connu reposant sur un modèle fédéré : le service "e-mail" !
{.is-info}

### Distribuée

L’architecture distribuée ou l'informatique distribuée désigne un système d'information, ou un réseau pour lequel l'ensemble des ressources disponibles ne se trouvent pas au même endroit ou sur la même machine. Le modèle distribué permet en fait de répartir ultimement la confiance à travers le réseau, de façon redondante et sécurisée.

> Quelques exemples de technologies reposant sur un modèle distribué :  P2P type bitcoin, torrent, tor, i2p...
{.is-info}

## Analyse

En réalité, ces définitions ci-dessus ne font à ce jour pas consensus. On peut cela dit penser que la mode _distribué_ représente l'étape ultime de la décentralisation... Mais le mode fédéré est plus ancien, plus simple à mettre en place et à comprendre, c'est pourquoi les efforts tendent à porter sur le mode fédéré, à tord sûrement :
- **Modèle fédéré** : Les utilisateurs sont inscrits sur des serveurs (instances) spécifiques de leur choix, ce qui donne à ces serveurs un aperçu des données et surtout des métadonnées de l'utilisateur, ce qui fait de ces serveurs des points de défaillance uniques ("single point of failure") tout en devant transmettre des données à d'autres serveurs par des liens de communication potentiellement dangereux voire compromis (attaque de l'homme du milieu par exemple). En outre, la majorité des utilisateurs n'exploitent pas leurs propres serveurs, ce qui fait des serveurs 'populaires' des cibles intéressantes pour les attaquants.
- **Modèle distribué** : L'acheminement des données est répartie sur de nombreux nœuds du réseau de manière redondante, sécurisée (chiffré, signé...) et, dans notre cas, indépendante du contenu. Les meilleurs systèmes distribués prennent en outre des mesures de protection des métadonnées, généralement via un routage en oignon ou un stockage en masse (consensus, blockchain, etc.).

# ROM

ROM en anglais est l’acronyme pour **R**ead **O**nly **M**emory, mémoire en lecture seule.

Android est un système d'exploitation pour smartphones/tablettes qui est installé par le constructeur de l'appareil avant l'achat, au moyen de ce que l'on appelle un firmware OEM. Quand nous souhaitons le remplacer, pour se débarrasser des surcouches du constructeur et notamment de Google, nous devons **Flasher** (installer) une **Custom ROM** (une version personnalisée d'Android telles que Lineage OS, /e/ OS, CalyxOS...).

Alors vous allez vous dire, une ROM c'est une mémoire morte en lecture seule, sur laquelle on ne peut pas réécrire ? Comment peut-on parler de flasher une ROM ? :confused:

Eh bien oui, c'est étrange, mais à l'époque les mémoires contenant le micrologiciel (firmware) d'un appareil était "flashables" (comprendre installables) avec un programmateur d'EEPROM. Depuis, cela a bien évolué et les firmwares sont désormais contenus dans des mémoires de type "Flash" réinscriptibles. L'ancienne appellation a été conservée, de sorte que l'on dit encore : "Flasher une Custom ROM" :D

# Root

De l'anglais "racine", sur les systèmes de type Unix (GNU/Linux, BSD et MacOS), "root" est le nom donné à un utilisateur du système particulier : cet utilisateur possède tous les droits sur le système. Il est souvent nommé : super utilisateur.

Généralement, le compte root est utilisé par les administrateurs systèmes. Aussi, posséder toutes les autorisations de modification/exécution sur un système est pratique mais surtout dangereux. En effet, en utilisant le compte root il est facile de corrompre le système (volontairement ou par mégarde).

Par défaut :
-   Les systèmes Unix séparent donc le compte root des autres comptes utilisateurs. Sur la plupart des distributions Linux le programme sudo permet à un utilisateur normal de surélever ses droits temporairement si celui-ci fait partie du groupe sudoers. A chaque fois qu'une opération nécessite des accès root, le mot de passe de l'utilisateur sudoers sera demandé pour que le système valide l'authentification et autorise ainsi la modification/exécution.
-   Les systèmes Windows de Microsoft quant à eux ont un compte intégré (Built-In) appelé "Administrateur". Généralement les utilisateurs ne se servent pas de ce compte, ils ont un compte utilisateur dédié qui est membre du groupe "Administrateurs". De ce fait ils peuvent lancer des programmes avec les privilèges super-utilisateur en cliquant "OUI" si ce programme a besoin de droits surélevés (cf. UAC), notez bien que contrairement à Linux, sur un Windows installé par défaut le mot de passe ne sera pas demandé !

# Rooter

Ceci consiste à reprendre le contrôle du compte root sur une machine.

Sur Android, par défaut, ce compte est désactivé et inaccessible. Rooter consiste a effectuer une manipulation sur l'appareil comme par exemple : lancer un "exploit" ou installer un recovery custom puis lancer un script. **Contrairement à l'idée reçue, la plupart du temps, pour flasher une custom ROM, sachez qu'il n'est absolument pas nécessaire de rooter un appareil, c'est même déconseillé !**

Sur Apple, on parle de "Jailbreak" qui consiste à "sortir de prison" mais c'est à peu près le même concept qu'Android.

Sur un PC, le compte Administrateur (Windows) est activé la plupart du temps. En revanche, sous Unix, le compte Root est la plupart du temps désactivé.

Il est absolument déconseillé de l'activer ou si c'est déjà le cas, de l'utiliser. Nous vous conseillons plutôt :

-   d'utiliser la commande sudo, par ex. sur les dérivés Debian/Linux installés par défaut, pour effectuer toutes vos tâches d'administration.
-   sous Windows, d'utiliser un compte utilisateur membre du groupe "Administrateurs" et d'utiliser le clic droit puis "Exécuter en tant qu'administrateur". Il est possible et conseillé, en modifiant UAC, de réactiver la demande de mot de passe lorsque vous faite une élévation de privilèges.

# SBC

Un SBC ou [Single Board Computer](https://fr.wikipedia.org/wiki/Ordinateur_%C3%A0_carte_unique) est un *ordinateur* en modèle réduit (autrement appelé nano-PC) qui tient sur un petit format de carte imprimé, comme par exemple :
- [Raspberry Pi](https://www.raspberrypi.org/)
- [OrangePi](http://www.orangepi.org/)
- [O-Droid](https://www.hardkernel.com/)
- [Arduino](https://www.arduino.cc/)
- [Libre Computer Board (LBC)](https://libre.computer/)

# Software

Est l'anglicisme pour désigner en français un "logiciel".

# SSH
Secure Shell (SSH) est un protocole de communication chiffré entre 2 machines. A l'ouverture de la session des clefs de chiffrement sont échangées afin de sécuriser la communication. 

C'est aussi un logiciel : serveur ``sshd`` et client ``ssh``. Le client est installé par défaut sur la plupart des distributions GNU/Linux.

Voici une sélection de logiciels libres qui proposent un client ssh évolué avec interface graphique et bien d'autres fonctionnalités :
| **Client SSH** | Linux | BSD | MacOS | Windows | Android | iOS
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| [Tabby Terminal](https://tabby.sh/) | :white_check_mark: | :x: | :white_check_mark: | :white_check_mark: | :x: | :x: |
| [Remmina](https://remmina.org/how-to-install-remmina/) | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :x: | :x: |
| [mRemoteNG](https://mremoteng.org/) | :x: | :x: | :x: | :white_check_mark: | :x: | :x: |
| [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) | :x: | :x: | :x: | :white_check_mark: | :x: | :x: |
| [KiTTY](https://www.9bis.net/kitty/#!index.md) | :x: | :x: | :x: | :white_check_mark: | :x: | :x: |
| [ConnectBot](https://connectbot.org/) | :x: | :x: | :x: | :x: | :white_check_mark: | :x: |
| [Blink Shell](https://blink.sh/) | :x: | :x: | :x: | :x: | :x: | :white_check_mark: |

> Note : Les distributions GNU/Linux permettent nativement en ligne de commandes d'établir des connexions SSH.
{.is-info}

# Système de fichiers (FS)

Un système de fichier (file system ou FS) peut désigner :
- la façon dont les fichiers sont organisés dans une [partition](#partition)
- ou bien la manière de ranger les dossiers dans un système d'exploitation.

## FS au sein d'une partition

Lorsque que l'on crée une partition, on doit la formater avec un système de fichiers (FS).
Celui-ci organise la façon dont les données sont stockées sur un disque.

Il existe beaucoup de [FS](https://fr.wikipedia.org/wiki/Liste_des_syst%C3%A8mes_de_fichiers) différents, parmi les plus connus:
- *ext : le premier FS pour le noyau Linux, il a été très vite _remplacé par ext2_.*
- *ext2 : utilisé dès l'apparition des distros GNU/Linux dans les années 1993, maintenant _obsolète_.*
- ext3 : évolution de ext2 dès les années 2000, ajoute la journalisation et ainsi permet la récupération des données. _Très peu utilisé_ aujourd'hui à part pour la **partition `/boot` sur un table de partition MBR**.
- ext4 : quatrième itération du FS ext et évolution de ext3, utilisé depuis 2010 par défaut dans la plupart des distro Linux et Android. Extrêmement populaire, ce FS apporte des améliorations comme une faible fragmentation des fichiers, une compatibilité avec ext3, la possibilité de stocker des fichiers plus grands sur des partitions plus volumineuses. C'est un FS stable qui est **recommandé dans la plupart des cas, notamment si votre disque dur n'est pas SSD ou inférieur à 1 To**.
- BTRFS : B-tree file system (Butter FS) a été créé en 2009 mais ne sera annoncé comme stable qu'en 2013. Ce FS est présenté comme étant le successeur de ext4. Capable de faire des instantanés (snapshots) et de gérer les sommes de contrôle ainsi que la compression native, il est comme XFS et ZFS un système de fichier avancé comparé à ext4, et commence à devenir un standard sur certaines distributions (Fedora).
- XFS : créé par Silicon Graphics dans les années 2000, c'est le système de fichier par défaut sous Red Hat Entreprise Linux. **À privilégier sur les disques de 4 To et plus.**
- ZFS/OpenZFS : créé par Sun Microsystems dans les années 2000, développé en parallèle de `ext` il est aujourd'hui **à privilégier sur les systèmes GNU/Linux si votre matériel est récent** (avec disque SSD de 1 To à 2 To, plus de 8 Go de RAM et processeur récent). FS par défaut sous Ubuntu Server.
- *FAT16 : utilisé sous MS-DOS, _obsolète_*.
- FAT32 : apparu avec Microsoft Windows 9x (95/98). Il est encore utilisé car il est **compatible avec de nombreux systèmes**.
- exFAT : c'est le successeur de FAT32, il permet notamment de s'affranchir de la limite de 4 Go pour la taille des fichiers. **À privilégier sur support externe de type clef USB ou carte SD**.
- NTFS : propriétaire Microsoft, non-libre, c'est le successeur de FAT32. **À utiliser seulement sur les OS de type Windows** car comme MS ne fournit pas les spécifications, le driver Linux ntfs-3g n'est pas aussi performant que sous Windows. Sur ces systèmes, il apporte de nombreuses améliorations comme entre autre, la journalisation, la compression, la gestion des droits (ACL) et des capacités accrues en terme de taille maximum supportée pour les partitions et fichiers. Même s'il est bien en dessous des performances et fonctionnalités apportées par ZFS et XFS !
- HFS/HFS+ : **utilisé sous Apple MacOS**


> Pour en apprendre plus sur les "filesystem", nous vous conseillons de visionner : ["Types de Filesystem : ext4, xfs, btrfs & zfs" sur la chaîne Xavki](https://yewtu.be/watch?v=F6NWxlhjeO0).
{.is-info}


## Hiérarchie d'un FS sous Linux

Linux (au contraire de Windows) est conçu pour compartimenter chaque espace, un programme pour une tâche et chaque chose à sa place :)
Lorsque l'on installe une distro Linux on installe la plupart du temps tout dans une seule partition `/` (root FS).
Cependant, il est tout à fait possible de compartimenter les partitions comme expliqué dans le tutoriel [partitionner son disque](/tutoriels/partitioning).

Les systèmes UNIX et Linux s'appuient sur un [système de fichier standardisé (Filesystem Hierarchy Standard/FHS)](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard).

Passons en revue les dossiers standards présents à la racine `/` d'un FS GNU/Linux :
- **SWAP** : Le swap est traditionnellement stocké dans une partition dédiée avec un FS de type SWAP. Mais il est tout à fait possible de stocker le swap à la racine du FS dans un fichier `/swapfile`
- **/bin** : Ce dossier (binaries, en français exécutables) contient tous les programmes essentiels. Par exemple les commandes `ls`, `cat`, `mv` et bien d'autres sont situées dans ce répertoire.
- **/boot** : Les fichiers qui permettent de démarrer (boot) le système sont placés dans ce dossier. On y retrouve le noyau (kernel) Linux et l'image ramdisk (initrd et initramfs) mais aussi GRUB et EFI (pour les BIOS de type UEFI).
- **/dev** : Sous Linux tout est fichier. Ainsi les composants matériels (devices) y sont représentés sous forme de fichiers spéciaux (device files).
- **/etc** : Contient les fichiers de configuration du système.
- **/home** : Chaque compte aura un sous-dossier ici, c'est la "maison" (home) des utilisateurs où seront stockés les fichiers et paramètres personnels de ceux-ci.
- **/lib** : les bibliothèques nécessaires au fonctionnement de `/bin` et `/sbin`.
- **/media** : point de montage dédié pour les médias externes tel que les disques USB et les images ISO.
- **/mnt** : idem que `/media` mais pour le montage _temporaire_.
- **/opt** : ce dossier est destiné à accueillir les applications installées manuellement, c'est-à-dire sans utiliser de gestionnaire de paquet tel que `dpkg`, `rpm`, `apt` ou `dnf`/`yum`.
- **/proc** : les processus en cours d'utilisation y sont représentés sous forme de fichiers.
- **/root** : c'est le dossier personnel du compte `root` :smiling_imp:.
- **/run** : vidé à chaque démarrage, on y retrouve les informations sur les processus lancés depuis le dernier boot.
- **/sbin** : comme `/bin` à la différence que ces programmes nécessitent les droits super-utilisateur `root` !
- **/srv** : contient les données partagées par la machine comme un serveur de fichier, FTP ou dépôt.
- **/sys** : les informations à propos des composants des pilotes et du noyau.
- **/tmp** : les fichiers temporaires y sont stockés, mais attention : il est vidé à chaque redémarrage !
- **/usr** : contient les données partagées par tous les utilisateurs comme les applications et utilitaires.
- **/var** : les données variables au cours de l'utilisation du système, tels que les journaux (`/var/log`), les bases de données (`/var/lib`, les files d'attente email (`/var/mail`) ou impression (`/var/spool`), le cache, les sauvegardes et certains fichiers temporaires (`/var/tmp`).

# Token

De l'anglais "token" : jeton.

En informatique, il s'agit d'un identifiant unique, qui peut tout aussi bien renvoyer :
- à un identifiant de session, lors d'une communication réseau : cookie de session, identifié par un token
- à un un jeton d'authentification : boîtier électronique générant des nombres synchronisés destiné à l'authentification, ou stockant des informations chiffrées. Par exemple, un jeton OTP (voir OTP ci-haut), dans le cadre d'une authentification à double facteur, ou multifactorielle.
- à un jeton échangeable avec contre-valeur, qui s'appuie sur une blockchain. Quelques exemples : Ethereum en cryptomonnaie, les NFT (Non Fungible Token : Jetons Non Fongibles) dans le monde de la musique...

# TOTP

De l'anglais "Time-based One Time Password", ou mot de passe à usage unique basé sur le temps.

Le principe est le même que le [One Time Password (OTP)](#otp) cité ci-haut, à ceci prêt que son fonctionnement repose sur la synchronisation de l'horloge entre le serveur d'authentification et le dispositif de l'utilisateur, généralement un ordiphone ou un dispositif de sécurité dédié. Chaque jeton généré est limité dans une temporalité pré-définie (quelques secondes ou minutes), définie fonction du temps actuel et du secret partagé.

![freeotp-exemple_neutre.jpeg](/images/freeotp-exemple_neutre.jpeg =200x){.align-right}

La minuterie régénère un nouveau jeton chaque fois que le précédent est devenu obsolète (sur les applications mobiles l'expiration du jeton change de couleur avant qu'un nouveau ne soit re-généré).

L'illustration ci-contre montre par exemple un code TOTP depuis une application mobile, avec la minuterie visible (sur la droite).

# Tracker

Un tracker ("pisteur" en français) est un outil permettant d'effectuer une télémétrie précise des logiciels ou des sites internet (consultation, comportement des utilisateurs...), ainsi qu'une collecte d'informations diverses (sur les utilisateurs).

# URL

De l'anglais "Uniform Resource Locator" : localisateur universel de ressources.

C'est par exemple l'adresse visible depuis son navigateur internet, dans la barre de recherche : typiquement https://www.exemple-de-site.com. Techniquement, d'après le Larousse, son  rôle est de :
> "*préciser la localisation d'une ressource Internet, en indiquant le protocole à adopter, le nom de la machine, le chemin d'accès et le nom du fichier.*"

A mettre en lien avec le DNS, dont vous trouverez plus de détails dans l'article [suivant](/hygiene-numerique#dns).


# Vulnérabilité

Dans le langage de la cyber sécurité, une vulnérabilité se rapporte à une faille de sécurité dans un système informatique, qui permet à un attaquant de compromettre le système vulnérable, afin de porter atteinte à la confidentialité ou l'intégrité du système.

Il s'agit le plus souvent d'erreurs dans le développement de logiciels ou matériels, liées aux mauvaises pratiques de codage. Mais il peut tout autant s'agir d'erreurs dans la mise en oeuvre d'une politique de sécurité (exemple : configuration pare-feu, mise en place réseau internet, etc.).

# Web

Plus communément connu sous l'appellation WWW ou "World Wide Web" ("toile d'araignée mondiale" si nous traduisons en français), ce terme désigne l'inter-connexion de tous sites internet entre eux. Cette inter-connexion s'effectue en fait par le biais de _liens hypertextes_ basés sur le fameux protocole _**web**_ justement : HTTP ou HyperText Transfer Protocol, et faisant *schématiquement* comme si tous ces sites étaient reliés comme dans une toile d'araignée.

# White Hat

Littéralement "Chapeau Blanc". 
Il s'agit d'un expert en cyber-sécurité, officiellement mandaté par une entité (gouvernement, entreprise, collectivité...), et qui utilise les techniques de piratage informatique pour :
- auditer, 
- renforcer la sécurité d'un système informatique, 
- réaliser des contre-attaques à l'encontre d'acteurs malveillants.

Parmi la terminologie en cyber, nous identifions 3 types : White Hat / Grey Hat / Black Hat.

Le White Hat s'oppose au Black Hat, pirate aux intentions malveillantes. Le White Hat est également appelé _Pirate éthique_ ou _Hacker Ethique_ de ce fait, d'où la création d'une discipline "hacking éthique".

Le *Grey Hat* lui se réserve le droit de naviguer entre les 2 bords !

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} <3 *L'équipe `WikiLibriste.fr`*