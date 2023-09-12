---
title: Eviter le hacking
description: Cet article vous présente toutes les choses à entreprendre pour éviter un piratage et une utilisation frauduleuse de vos informations
published: true
date: 2023-04-20T15:29:48.983Z
tags: hygiene, hacking, piratage
editor: markdown
dateCreated: 2023-02-11T14:53:36.201Z
---

Cette partie est **essentielle**, et vous fournit les meilleures pratiques en matière d'hygiène informatique afin de ne laisser que très peu d'ouverture (on parle d'une surface d'attaque minimale) à de potentiels *adversaires* et éviter au maximum des *vols de données* ou encore des *usurpations d'identité*.

Rentrons dans le vif du sujet, afin de devenir difficilement piratable :

# Les mots de passe

## Politique de mots de passe puissante

Nous l’avons vu plus haut, créer un mot de passe extrêmement puissant peut déjà vous couvrir face à la majorité des tentatives d'intrusions. Choisir un mot de passe comme « 1234 », « Choupette1982 », « Misssunshine » ou « Pepperonipizza2000! » et bien d’autres relève aujourd’hui de l’hérésie informatique (malheureusement on le voit encore trop souvent !) :-(

![sortirgafam21.png](/images/sortirgafam21.png =600x){.align-center}

-   pré-requis minimum : **20 caractères** :arrow_right: 
Cela s'atteint même aisément avec une technique simple - la phrase de passe -, évoquée juste à la suite. 
-   Au minimum un mélange de lettres minuscules-majuscules, de chiffres, et de caractères spéciaux. Afin de renforcer encore plus vos mots de passe :
    -  On évite la majuscule en début de mot de passe
    -  On évite le caractère spécial en fin de mot de passe
    -  On évite les chiffres en début et fin de mot de passe
    -  On évite les suites de chiffres tels « 1234 » ou « 54321 » ou les suites de lettres type abcde
    -  On évite les dates d'anniversaire, ou dates importantes 
    -  On évite les prénoms des enfants, le nom de son toutou, les hobbies et toute activité personnelle qui peuvent facilement se retrouver sur les réseaux.
  {.grid-list}
-   Créer votre propre façon d’obfusquer votre mot de passe, par exemple : « jsistorienvoia » peut devenir « js%stor%envo%a » (on ajoute un % à la place du i)
-   Il est également possible voire même _tout à fait conseillé_ aujourd'hui d’utiliser des « **phrases de passe** » (passphrase), par exemple : « suis bois orchidee cheval ». Une phrase de passe consiste à choisir une suite de mots formant une phrase mais n’ayant aucun sens, avec l'objectif de pouvoir le mémoriser simplement. On pourrait tout aussi bien combiner.
  **On estime qu'une suite de 5 mots serait suffisante pour être à l'abri des attaques les plus courants sur les mots de passe : on obtient 64 bits d'entropie et avec une puissance de calcul d'1 Milliard de passphrases testées par seconde, cela prendrait 900 ans avec les moyens actuels et futurs proches ! On recommande, cela dit, 6 mots à ceux qui sont particulièrement exposés, afin d'obtenir une meilleure couverture.**
  Une technique afin de choisir vos mots : le lancé de dés ou [diceware](https://en.wikipedia.org/wiki/Diceware).

## Mots de passe UNIQUES

Choisissez un mot de passe UNIQUE pour chaque compte que vous créez

Chaque site nécessitant un compte avec un couple [nom d’utilisateur ; mot de passe] doit contenir un mot de passe unique, qui n’a jamais été utilisé sur un autre de vos comptes. La raison est très simple : vous évitez en choisissant un mot de passe unique, dans le cas éventuel d'une fuite de données (qui arrive plus souvent que vous ne le pensez), de retrouver ce mot de passe sur les darknets, compromettant ainsi **TOUS** vos comptes ! La situation est en fait encore pire en ayant un mot de passe unique (quand bien même il serait "ultra-secure"!!) : 
- "ultra-secure" (comme le disent certains :|) ou pas, si votre mot de passe est dévoilé, peu importe sa robustesse !
- Et généralement nous ne sommes pas avertis rapidement de ces fuites de données, donc vous mettez à risque la totalité de vos comptes (qui pour certains peuvent être sensibles) sans forcément le savoir et prendre des mesures (changement de mot de passe). 
- Ah également : dans le cas d'une fuite, vous devrez changer le mot de passe de **TOUS** vos comptes.

**Donc on se répète : _un mot de passe UNIQUE pour chacun de vos comptes_. Ici également, c'est un pré-requis essentiel (non négociable)**

> Attention, veillez à ne pas tester vos mots de passe sur des sites internet qui proposent ce service, y compris sur des sites de sociétés très connues, et y compris s'ils vous disent qu'ils ne collectent pas les données. Vous ne savez pas qui est concrètement derrière ces sites internet, et quels seraient les algorithmes ou les codes implémentés, voire dans le pire cas qui pourrait intercepter la requête avec le mot de passe à l’intérieur ! Un mot de passe est un secret, et doit le rester pour tout le monde, y compris votre conjoint(e) ou vos enfants.
{.is-danger}

Alors je sais, vous vous dites "Non mais attends, créer un mot de passe ultra fort est déjà presque impossible à retenir, si je dois en choisir un pour chaque site ou compte, c'est impossible !!" :)

**Et vous avez entièrement raison : ...**

## Gestionnaire de mots de passe

**... Voici pourquoi utiliser un gestionnaire de mots de passe est fortement recommandé.**

Nous vous renvoyons ici vers l'[article dédié](./gestionnaire-mots-passe.md#) à ces outils.

# Authentification 
## L'authentification multi factorielle

Activez partout où cela est possible les authentifications à plusieurs facteurs, au minimum 2FA. Attention cependant à l’utilisation du 2FA avec SMS ou courriel : il doit être limité uniquement aux cas où vous n’avez pas d'alternative. Si l'on vous donne le choix, préférez d’autres méthodes comme l’OTP (One-Time Password) via des outils libres (on évitera les Google Auth, Microsoft Auth etc.), disponibles dans l'[article dédié](./logiciel-alternative-libre.md#) aux alternatives libre et open source. 

## Les mécanismes d’authentification

Ne jamais vous authentifier en utilisant les mécanismes d’authentification des GAFAM ou autres pompes à données : Facebook, Google, Microsoft etc.

Bien que ces méthodes soient très pratiques à l'usage, cela comporte un risque : comment être sûr que le site en question est de confiance, comment être sûr que celui-ci ne va pas tout simplement collecter vos données personnelles voire même vos identifiants ? Vous ne pouvez pas. Il est donc préférable de créer un compte unique.

**Voilà aussi pourquoi un gestionnaire de mots de passe est utile. Utilisez-le donc afin de simplifier la chose !**

# Le moins d’informations personnelles

De manière générale, évitez de donner trop d’informations personnelles sur des sites internet qui n’en ont pas réellement besoin (âge, date de naissance, adresse postale, lieu de naissance, numéro de sécurité sociale, etc.).
-   Twitter par exemple n’a pas besoin de votre adresse postale, pourquoi la donnez-vous ?
-   Google non plus.
-   Facebook n’a pas besoin de savoir non plus de quelle ville vous venez actuellement.
-   Votre « Forum des choses pratiques » n’a pas non plus besoin de savoir quel âge vous avez
-   Si vous remplissez des questionnaires en ligne ils n’ont pas besoin de connaître votre adresse ou sinon vous devez vous méfier de ce que cela implique (tous professionnels qu’ils soient !)...

Cela est valable pour tous les sites, et encore plus pour les réseaux sociaux, car aucun de ces sites n’est et ne sera à l’abri d’une fuite de données (même s’ils prétendent le contraire).

**Protéger votre identité et votre vie privée est crucial.**

## Adresse postale

> Arrêtez de donner votre adresse postale réelle autant que faire se peut
{.is-info}

Oui je sais cela reste compliqué en France. Parfois, souvent, il n’est pas possible de le faire donc vous n’aurez pas le choix, mais si possible, préférez donner une adresse postale d’un point relais ou d’une boîte postale (vous pouvez louer une boîte postale) lorsque vous le pouvez.

**Cela évite lors de fuites de données de retrouver votre adresse postale un peu partout sur les sites d'échanges entre pirates malveillants.**

Une dernière chose, on évitera de rentrer ses adresses postales de domicile et de travail dans des applications de géolocalisation (type GPS), voire dans votre système de navigation de voiture (Tomtom, etc.) !

Mais ça vous le faisiez déjà n’est-ce pas ?

## Les fameuses questions de sécurité

Nous voyons parfois des sites internet qui demandent à ses utilisateurs de sélectionner parmi un nombre de questions pré-établies et d’y adjoindre une réponse personnelle, ceci afin de renforcer la sécurité. Par exemple : quelle est le nom de jeune fille de votre mère ? Quel est votre animal préféré ? Et bien d'autres. Par réflexe, nous avons pratiquement toujours l'habitude de dire la vérité...

Mais vous êtes-vous déjà demandés si vous étiez véritablement obligés de répondre avec de réelles informations ?

La réponse est : _NON, absolument pas_ !

Vous n’êtes pas tenus de donner une information personnelle véridique, vous pouvez tout simplement inventer une réponse. En ce sens, ne pas donner trop d’informations personnelles peut éviter qu’une fuite de données un jour puisse avoir un impact négatif sur votre vie privée.

Ceci se rapporte également aux adresses postales que vous donnez sur tous les sites, bien entendu...

En ce qui concerne donc ces questions de sécurité associées à des réponses secrètes : ne donnez jamais de réponses secrètes en lien avec vous ou votre vie privée (nom de jeune fille de votre mère, sport favoris, dessert préféré, cocktail favori...). Préférez utiliser des réponses aléatoires, et éventuellement celles-ci peuvent être stockées sur votre gestionnaire de mots de passe, pourquoi pas.

## Les petites annonces

Arrêtez de mettre vos adresses courriels ou vos numéros de téléphone dans le texte de vos petites annonces, ou vous vous exposez à des campagnes de spam à volonté, voire pire !

# Les courriels

Protégez vos échanges par courriel, à minima ceux que vous jugez critiques.

Rendez-vous sur l'article [dédié](./communications.md##courriel).

# Les messageries

Sur le même principe que vos échanges par courriel, vos échanges par messagerie se doivent d'être protégés... Notre collectif recommande l'utilisation exclusive d'une messagerie sécurisée avec chiffrement de bout-en-bout et respectueuse de vos données privées.

Si votre modèle demande un anonymat, c'est aussi possible même si plus complexe à mettre en place.

Ce sujet est discuté en détails dans l'article dédié aux [messageries](./communications.md##messagerie), que nous vous conseillons de lire très attentivement :)

# Les liens hypertextes / URLs

> Ne jamais cliquer sur des liens (hypertextes) contenus dans les courriels :
{.is-info}

Si ce lien vous amène sur un écran où vous devez rentrer vos identifiants, il est préférable de se méfier et de fermer ce site. Puis de vous connecter en allant directement vous-même sur le site en question (la seule exception étant le renouvellement de mot passe).

![](/images/phishing_ex.png =600x){.align-center}
***Extrait d'un courriel pour une campagne de hameçonnage***

*:warning: Attention aux coquilles dans le corps de texte des courriels, qui trahissent les emails issus de campagnes de hameçonnage (détaillé ci-après)*
  
De nos jours, il est très facile de copier une page des sites bien connus (Facebook, Decathlon...) pour aspirer vos données d’authentification, voire vos données bancaires : on appelle cela l'attaque par hameçonnage (ou "phishing attack").

*Exemple : vous recevez un courriel (visiblement très professionnel, aucune faute...) de Decathlon vous annonçant que vous pouvez participer à un jeu vous permettant de gagner un bon d'achat exceptionnel pour le dernier vélo électrique à la mode. Vous cliquez sur le lien, qui vous amène sur une page Decathlon tout à fait légitime, puis vous jouez, vous gagnez et enfin on vous demande de rentrer vos coordonnées bancaires, arguant qu’il leur faut faire un retrait de 2 euros afin de faire une empreinte de votre carte pour payer les frais de transports, mais que tout vous sera remboursé par la suite. Le piège s’est refermé, vous renseignez les données. Puis vous voyez un remboursement de 2 euros quelques jours suivants, ce qui vous rassure ; en revanche, les jours qui suivent vous vous apercevez que des retraits de 200 euros, 500 euros ont été effectués. Vous faites opposition mais bien sûr il est trop tard puisque les cybercriminels ont déjà récolté l’argent...*

Cette histoire est tirée d’une réelle campagne de phishing !

> **Ne sous-estimez JAMAIS les cybercriminels, c'est ainsi qu'ils trouvent leur motivation. Ne sur-estimez jamais la façon dont vous pensez pouvoir réagir. Cela peut arriver à n’importe qui, et encore plus à celui qui est trop confiant.**
{.is-warning}

# Les mises à jour

> Toujours effectuer les mises à jour de sécurité dès qu’elles sont disponibles :
{.is-info}

Les pirates informatiques malveillants se basent pratiquement tout le temps sur les failles de sécurité des logiciels. Vous entendez tous les jours que des logiciels ou des systèmes d’exploitation ont reçu des « patchs (entendre correctifs) de sécurité », afin de combler une vulnérabilité (corriger une faille de sécurité). Eh bien, il s’agit exactement de cela : patcher pour combler les failles dont les développeurs se sont aperçus, et qui exposent potentiellement vos données ou autre chose.

Il est aujourd’hui assez simple de vérifier s’il existe des mises à jour de sécurité donc n’attendez pas avant de les faire, surtout lorsque celles-ci sont critiques. Nous recommandons ainsi d'activer les mises à jour automatiques depuis votre système d'exploitation favori (libre ! comme GNU/Linux, ou un Android dégooglisé, nous l'espérons ;-)), dans cette démarche de sécurisation proactive.

Pour le reste des mises à jour classiques, elles peuvent potentiellement attendre, même si le plus tôt sera le mieux.

# Les fichiers et leur intégrité

Ceci est un rappel, mais évitez de télécharger des exécutables directement ou dans des archives, que ce soit Linux (via des fichiers ELF ou "Executable Linkable File") ou Windows (via des fichiers à l'extension .exe ou .msi).
  
Et dans le cas d'un téléchargement depuis un site internet, plutôt que depuis un centre logiciel : toujours télécharger depuis le site officiel de l'éditeur logiciel dudit programme.
*_Astuce toute simple_ : depuis mon moteur de recherche préféré, je tape wikipedia + nom_du_programme_à_télécharger (ou bien je demande conseil sur une communauté, comme celle-ci). Depuis l'article Wikipedia, je retrouve le lien vers l'[URL](./glossaire.md##url) de l'éditeur logiciel ; le but étant de télécharger un fichier authentique, en allant directement à la source.*

En prolongement et pour tous types de fichiers (.iso, .img, ...), vérifiez **TOUJOURS**, lorsque disponible, l'intégrité du fichier téléchargé. Cela se fait via une vérification de la "signature" ou de "la somme de contrôle" dudit fichier.
  
**Voir l'article sur le [chiffrement, l'intégrité et les signatures](./chiffrement.md#).**
**Ainsi que le tutoriel [dédié](./verifier-integrite.md#).**

# Sur les antivirus et antimalware

Concernant l'utilisation d'un anti-virus ou anti-malware, même si certains malwares modernes aujourd'hui ne sont plus détectables facilement, il est toujours possible de détecter des malwares connus et moins sophistiqués, ce qui est déjà une bonne chose (soyons pragmatiques). Dites-vous bien qu'un anti-virus ne vous protégera pas des agences à 3 lettres bien connues !

La bonne (première) pratique est si possible de télécharger des fichiers sur un environnement isolé, comme une machine virtuelle Linux (pour plus de facilité) par exemple, via VirtualBox ou VMWare. Cela s'accompagne également d'une utilisation particulière, qui ne risque pas de mettre à mal votre modèle de menaces :

-   N'utilisez pas de solutions commerciales, type Norton, BitDefender, Kaspersky... qui implémentent de toute manière une télémétrie vers leurs entreprises ainsi que des sociétés tierces.
-   _**Si vous avez un modèle de menaces nécessitant une sécurité et un anonymat accru**_ : n'utilisez pas les fonctions de protection en temps réel de ces outils ; au delà même de la question de l'utilité réelle de ce genre de fonctions, celles-ci sont exécutées avec des privilèges hauts et de facto peuvent être utilisées comme un vecteur d'attaque.
-   Préférez les solutions open-source et hors ligne, afin d'utiliser ces outils comme prévus à l'origine : scanner régulièrement les fichiers de votre système, ou que vous voudriez scanner en cas de doute sur une potentielle infection. Nous avons rédigé un [tutoriel](./distro-protect.md#) afin de vous guider dans ces tâches. Pour synthétiser nous recommandons :
    -   pour la détection de logiciels malveillants (malwares) :
	    - [ClamAV](https://www.clamav.net/) et [ClamTk](https://gitlab.com/dave_m/clamtk/) son interface graphique
    	- [RFXN Linux Malware](http://www.rfxn.com/projects/linux-malware-detect/) (Linux uniquement)
  		- [Hypatia](https://gitlab.com/divested-mobile/hypatia) (Android uniquement)
    -   pour la détection de rootkits (cf. [ici](./hygiene-numerique.md##malware-virus-trojan)) : [Chkrootkit](http://www.chkrootkit.org/) ou [RkHunter](https://rkhunter.sourceforge.net/) (Linux uniquement) 
-   Si vous ne souhaitez pas installer un outil sur votre ordinateur, vous pouvez potentiellement vous aider de solutions web. Attention ici cependant de ne pas mettre des fichiers contenant des informations personnelles (les vôtres ou ceux d'autres personnes) ou sensibles sur ces sites internet :
    -   [VirusTotal](https://www.virustotal.com/gui/home/upload) (petite mise en garde sur cet outil : leur politique de vie privée est assez problématique cependant car ils stipulent que "tout fichier que vous leur soumettrez seront gardés, partagés voire utilisés à des fins commerciales". Voilà pourquoi il est important de ne pas transmettre de fichiers potentiellement sensibles.)
    -   [Hybrid analysis](https://hybrid-analysis.com/)
-   D'autres outils sont disponibles sur ce dépôt pleins de ressources fabuleuses concernant les malwares : [awesome-malware-analysis](https://github.com/rshipp/awesome-malware-analysis)

> **Attention de bien garder en tête cependant que ces outils ne sont pas la panacée, et ne pourront pas détecter 100% des malwares existants ou futurs. Il est donc important de mettre en place les bonnes pratiques et de bien faire attention aux autres parties de cet article.**
{.is-warning}

# Les WiFi publics

> Bannissez tous les WiFi publics (hormis certains cas bien précis) :
{.is-info}

Les gares, aéroports, cafés, hôtels, restaurants... qui proposent des Wifi partagés sont aussi des lieux idéaux pour tous cybercriminels afin de s’introduire sur votre machine. ÉVITEZ absolument ces WiFi. Voici quelques alternatives :

-   Vous avez sûrement tous un téléphone portable dernier cri Android (ou Apple... Quoi ?!! Vous avez encore un produit Apple ?!! ;-)). Utilisez donc leurs fonctions de « point d’accès sans-fil » avec votre téléphone en 4G/5G afin d’éviter de vous connecter sur les WiFi publics.
-   Si vous voulez tout de même vous connecter sur des WiFi publics pour des problématiques d'anonymat, l’utilisation d’un VPN dans ce cas précis est ABSOLUMENT NÉCESSAIRE.

# Conclusion

Pour terminer sur cette partie déjà bien fournie, il existe quelques sites pour savoir si une adresse courriel ou un nom d’utilisateur a déjà fait l’objet de fuite : visitez ce site [<https://haveibeenpwned.com/>](https://haveibeenpwned.com/). Néanmoins il ne regroupe que les attaques majeures, et à ce titre ne doit pas être vu comme le site de référence ultime des fuites en ligne...

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo*
<br>