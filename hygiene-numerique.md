---
title: Améliorez votre hygiène numérique
description: Reprenez le contrôle de votre vie numérique et de vos données...
published: true
date: 2024-01-16T13:56:40.537Z
tags: web, internet, privacy, vie privée, pgp, gpg, numérique, informatique, données, anonymat, sécurité, réseau, vpn, tor, proxy, email, courriel, virus, malware, darknet, mot de passe, authentification, clé, cyber
editor: markdown
dateCreated: 2022-11-27T12:39:05.392Z
---

Le réseau internet est, de nos jours, devenu un espace important voire vital dans la vie de certaines personnes. Les relations amicales ou familiales, le travail, le journalisme, l’activisme, le commerce, le marketing et bien d’autres domaines sont dorénavant liés profondément au numérique.

C’est ainsi que les individus sont amenés à fournir des informations personnelles, parfois sensibles, et plus encore parfois critiques : nom, prénom, adresse postale, date de naissance, numéro de sécurité sociale, photo d’identité, permis de conduire, numéro de carte bancaire...

La protection de ces données personnelles est aujourd’hui devenue un enjeu crucial. L’explosion d’internet, et par extension la convergence des réseaux depuis une vingtaine d’années - qui bien que bénéfiques sur le plan du partage du savoir et de la connaissance - a engendré des dérives auxquelles il est aujourd’hui urgent de remédier. En effet, ces dérives amènent non seulement des pirates informatiques malveillants ou des entités à fortes ressources (agences de renseignement, groupes de pirates subventionnés...) à récolter des données personnelles afin d’en tirer profit (économique ou social comme le profilage), mais il est de plus en plus évident que des gouvernements s’appuient sur cette problématique afin de mettre en oeuvre des politiques d’espionnage de masse, rendant la liberté de mouvement ou d’opinion de plus en plus restreinte.

Il devient donc indispensable aujourd’hui de se pencher sérieusement sur son environnement personnel numérique et sur les données que l’on fournit à des entreprises contre leurs services (courriers électroniques dits "courriels", navigation par géo-localisation, achats/ventes en ligne, voyages, restauration, etc.).

L’enjeu n’est plus seulement de faire attention à soi-même, mais devient de plus en plus un objectif collectif !

> Une bonne entrée en matière, afin d'appréhender les raisons, est de visiter ce site internet : 
> [Je n'ai rien à cacher !](https://jenairienacacher.fr/)
{.is-info}

### Afin de reprendre la main sur votre espace numérique, cet article tente de vous guider en vulgarisant au maximum les terminologies techniques et le comportement à tenir afin d'arriver à une hygiène informatique plus saine.


# Comprendre les bases

Afin de bien comprendre les aspects évoqués tout au long de cet article, il est essentiel de comprendre les bases du monde numérique, communément et par défaut appelées "informatique", ainsi que ses tenants et ses aboutissants.

> **Attention, cette partie peut être copieuse et technique, bien que vulgarisée. Nous vous conseillons donc de prendre un café, un thé ou un chocolat (ou simplement de l’eau pour les plus pur(e)s d'entre nous), de respirer un bon coup et de vous concentrer lorsque vous lirez les sections suivantes (relire plusieurs fois les sections qui vous demandent plus d'attention) !**
{.is-warning}


## Chiffrement, kézako ?

Vous avez sûrement déjà entendu parler de « confidentialité des données » ou encore de « chiffrement des données », une terminologie en vogue aujourd’hui, surtout depuis l’application de la RGPD en 2016, le fameux [Règlement Général sur la Protection des Données](https://www.cnil.fr/fr/reglement-europeen-protection-donnees). Pourtant cette notion est très ancienne !

*Mais qu’est-ce concrètement ce « chiffrement » et à quoi sert-il ?*

- **Nous vous renvoyons vers l'article [dédié](/intermediaire/chiffrement) au chiffrement afin d'y voir un peu plus clair sur ces sujets**


## Accès aux informations ou authentification

L’authentification est un mécanisme important qui permet de confirmer la légitimité de la demande d’accès à une information. Pour mieux comprendre, voici deux exemples :
-  Vous souhaitez accéder à votre ordinateur, vous le démarrez et à l'écran vous est proposée une page d'authentification. En effet, celui-ci est protégé par un mot de passe dit "de session". Si vous entrez le bon mot de passe, la légitimité est donc prouvée et l’accès au bureau et à vos documents vous est donné (sinon l’accès vous est refusé, vous avez compris !). En ce sens, vous avez prouvé que vous **CONNAISSEZ** le secret pour avoir accès à votre session.
-  C’est le même mécanisme lorsque vous souhaitez avoir accès à votre compte e-mail (ou à votre compte Telegram etc.). La seule différence ici est que vous prétendez être le titulaire d’une adresse courriel (ou bien n° de téléphone, ou n° de contrat, ou...). À vous de prouver, avec le bon mot de passe, que vous **CONNAISSEZ** le bon secret et ainsi avoir accès au compte.

> Ces deux exemples ci-dessus constituent une authentification à 1 facteur, c'est-à-dire via un mot de passe.
{.is-info}

Ce procédé est très ancien, mais la plupart des experts en sécurité de l’information se sont très vite aperçus qu’un seul facteur constituait une brèche dans le principe d’authentification : en effet, un mot de passe peut être aujourd’hui facilement connu ou déduit (par exemple en tentant toutes les combinaisons possibles jusqu'à l'obtenir - méthode "brute force"). Encore plus si celui-ci est faible (nous verrons plus loin comment gérer cet aspect !), et c'est malheureusement souvent le cas !

C’est pourquoi vous entendez souvent parler de « 2FA » ou « MFA » ; en anglais 2FA ou (2)Two Factor Authentication, MFA ou Multi Factor Authentication. Ces techniques permettent de renforcer la sécurité de la demande d’accès, en ajoutant des étapes supplémentaires. Cette notion s’appuie sur des « facteurs » d’authentification dont le schéma de détermination est le suivant :

1.  Quelque chose que vous CONNAISSEZ
2.  Quelque chose que vous DÉTENEZ
3.  Quelque chose que vous ÊTES
4.  Le LIEU où vous vous trouvez

> Sachant qu’il est tout à fait possible d’activer un ou plusieurs facteurs en même temps (les 4 ne sont pas obligatoires).
{.is-success}

### Le Mot de passe

*Un mécanisme que tout le monde redoute...*
:'( Qui n’a jamais râlé en tentant de retrouver le bon mot de passe devant son site de vente en ligne préféré ?
:'( Qui n’a jamais cédé à la tentation du post-it sur son écran d’ordinateur pour se remémorer son mot de passe de session ?
:'( Qui n’a jamais écrit tous ses mots de passe sur une feuille de papier ou pire sur un outil numérique de type Google, synchronisé sur des serveurs ?

> En termes statistiques, plus de 80% des fuites de données liées à des piratages informatiques sont liées aux mots de passe.

> Jetez un oeil à des mots de passe tout à fait inutiles et encore utilisés de nos jours ici [^⁷], malheureusement, en espérant que vos mots de passe n'y figurent pas. Sinon, changez le(s) _immédiatement_.
{.is-warning}

[^⁷]: [Liste des mots de passe](https://nordpass.com/fr/most-common-passwords-list/) les plus communs

Voilà pourquoi ce sujet est essentiel. Pour bien comprendre l’utilité d’un mot de passe, intéressons-nous à son histoire.

Dans les années 60, un brillant ingénieur (oui, oui, brillant !) du MIT a eu besoin de donner accès à des étudiants à une partie des ressources du système informatique de l'université. Néanmoins, il fallait trouver une solution pour identifier ces étudiants et ainsi leur donner accès aux ressources. C’est ainsi qu’il créa le _mot de passe_ (« password » en anglais). Malheureusement à peine créé, et déjà détourné : un étudiant ayant besoin de beaucoup de ressources pour sa thèse a trouvé le moyen d’avoir le mot de passe des autres étudiants et ainsi avoir plus de ressources... eh oui, les mots de passe étaient stockés en clair dans un fichier !

Si le procédé a vite été détecté, l’auteur non. Celui-ci n’a avoué que 20 ans plus tard.

Ainsi, nous pouvons, de cette histoire, en déduire deux conclusions majeures, qui sont aujourd’hui le socle de l’utilisation d’un mot de passe :
1.  Le mot de passe doit être créé de sorte que seul son créateur puisse le retrouver et il doit être assez **_fort_** pour résister à toute déduction (manuelle ou par le biais d'algorithme(s)). Bien sûr, cela demande aujourd’hui une sacrée dose de réflexion !
2.  Les mots de passe stockés sur un appareil doivent l'être de façon **_sécurisée_** et jamais _en clair_. Aujourd’hui, tout mot de passe stocké est, dans la plupart des cas, protégé par des mécanismes de hachage, voire d’autres mécanismes (comme le [salage](https://wikimonde.com/article/Salage_(cryptographie)) par exemple).

### Les facteurs d'authentification

Nous avons déjà appréhendé le premier facteur (l’exemple du mot de passe) plus haut, mais d’autres types de facteurs « que vous connaissez » existent : le code PIN par exemple.

Également, vous utilisez très souvent le mécanisme à 2 facteurs (2FA) sans probablement le savoir : votre carte bancaire associée à son code secret constitue en fait une 2FA : le facteur 1, que vous CONNAISSEZ, est le code secret (assimilable à un code PIN), et le facteur 2, que vous DÉTENEZ, est la carte bancaire.

Lorsqu’il s’agit de décrire le mécanisme qui permet de vérifier le facteur que vous DÉTENEZ, il est souvent mention de la carte bancaire. Mais, ce n’est pas le seul item :
-   une smartcard pour sécuriser l’authentification sur votre ordinateur professionnel,
-   un badge d’accès à votre entreprise,
-   une clé de sécurité (aussi appelée token physique de sécurité, [YubiKey](https://www.yubico.com/) ou [Nitrokey](https://www.nitrokey.com/fr) par exemple),
-   un token logiciel (généralement un _certificat_).

Un autre exemple d’authentification à 2 facteurs : vous avez un compte sur un site de vente en ligne. Lorsque vous souhaitez payer un bien, vous utilisez votre carte bancaire. Lors de la transaction entre le site vendeur et votre banque, très souvent votre banque vous demandera de rentrer un numéro unique et temporaire de 4 à 6 chiffres reçu sur votre téléphone par SMS ou par e-mail. Le téléphone constitue ici le facteur que vous DÉTENEZ, et le numéro unique ce que vous CONNAISSEZ. Nous sommes bien ici en face d’une authentification 2FA (facteurs 1- et 2-).

> Attention : ce procédé utilisant le SMS/e-mail est juste ajouté à des fins de compréhension, il s’agit d’un mécanisme en fait peu sécurisé. Nous en rediscuterons plus tard...
{.is-warning}

Le troisième facteur, le facteur d’inhérence, est souvent assimilé à l’empreinte digitale. Il s'agit ici de la biométrie : un ensemble de technologies et procédés de reconnaissance, d’authentification et d’identification des personnes à partir de certaines de leurs caractéristiques physiques ou comportementales. Ce facteur lié à l'inhérence n'est donc pas limité qu’à l’empreinte d'un doigt. Il est associé principalement à toute biométrie, incluant empreinte digitale, mais aussi reconnaissance faciale, reconnaissance vocale, reconnaissance d’iris... allant même jusqu’à inclure la reconnaissance par comportement biométrique (exemple : la démarche d'une personne), ou la dynamique de frappe sur un clavier.

Un exemple ici est le fait d’utiliser votre empreinte digitale pour déverrouiller votre téléphone : le téléphone correspond au facteur que vous DÉTENEZ, votre empreinte au facteur que vous ÊTES (facteurs 1- et 3-).

*Note : concernant le facteur biométrique lié à l'empreinte digitale, et stocké sur votre appareil (votre téléphone par exemple) : il s'agit d'une représentation mathématique de l'empreinte de votre doigt, non pas d'une photo fidèle, pixel pour pixel de votre empreinte digitale. Néanmoins, au vu du caractère restreint du nombre de possibilités de changer son authentification biométrique sur smartphone (10! Pour les 10 doigts des deux mains), un PIN fort est plutôt recommandé pour ceux qui ont bonne mémoire. En effet, en cas de piratage du PIN, on peut changer son code plus de 10 fois, et les possibilité sont exponentielles.*

Un dernier exemple pour vous montrer l’étendue des possibilités de l’authentification multifactorielle (MFA). Souvent aperçus dans les films d’action, certains procédés d’authentification existent bel et bien, pour des données extrêmement critiques (par exemple un OIV en France ou Organisme d’Importance Vitale).

Voici le scénario : un utilisateur souhaite accéder à un datacenter où des données critiques sont entreposées, voici ce qui pourrait être fait :
-   L’utilisateur possède un badge d’accès : ceci constitue le facteur de possession (ce que vous détenez).
-   Lors du badgeage à la porte d’entrée du datacenter, un appareil demande à l’utilisateur un code PIN à 9 chiffres : ceci constitue le facteur de savoir (ce que vous connaissez) ;
-   Puis l’appareil laisse place à un second appareil, d’identification biométrique à reconnaissance d’iris : ceci constitue le facteur d’inhérence (ce que vous êtes).

Voici à quoi ressemblerait une 3FA !

Le dernier facteur est encore peu utilisé de nos jours, et seulement pour des situations sensibles ou des entreprises ayant des données critiques ou des personnes à protéger. Ce facteur s’appuiera sur l’adresse IP d’où part la demande d’authentification, voire sa géolocalisation.

### Alors, quel est le futur des mots de passe ?

La question est judicieuse, à l'heure où tous les experts tentent de trouver une solution pour améliorer l'authentification par mot de passe.

Nous entendons de plus en plus parler de fonctions ou procédés « passwordless ». Ce procédé vise à autoriser un accès à un utilisateur sans qu’il ne rentre aucun mot de passe.

*« Bon OK, ça j’avais compris en traduisant de l’anglais, mais concrètement... »*

Concrètement, nous avons déjà vu dans la partie précédente l’authentification multifactorielle (MFA). Mais attention cependant de ne pas confondre les 2 mécanismes : le MFA ajoute « n » couches d'authentification en plus de l’authentification par mot de passe, le passwordless lui n’a pas besoin d’un secret connu (facteur 1, c'est à dire le **mot de passe**, par exemple) mais implique l’utilisation des autres facteurs pour s’authentifier :
-   Quelque chose que vous DÉTENEZ
-   Une de vos CARACTÉRISTIQUES PHYSIQUES
-   OÙ vous vous situez

_Par exemple_ : utilisation d’un token physique de sécurité, utilisation de l’empreinte digitale...

Il est également tout à fait possible d’utiliser ces facteurs en même temps, auquel cas nous nommerons ce procédé « MFA-passwordless » !

*« Youpi c’est la fin des mots de passe !! ».*

Alors, pas tout à fait, gardons notre sang-froid... Même si théoriquement il est vrai que ce mécanisme permet de se passer d'un facteur encombrant lors de l’authentification, certains points sont encore problématiques : par exemple, le vol de votre token physique de sécurité implique une compromission totale de votre compte, associé à ce moyen d'authentification (si en plus ce token fait office de moyen d’authentification pour plusieurs de vos comptes, tous ces comptes sont potentiellement compromis !). Également, cela ne protège pas non plus contre des failles connues comme le [SIM swapping](https://en.wikipedia.org/wiki/SIM_swap_scam), ou certains logiciels malveillants. Aussi, nous savons que certains lecteurs d’empreintes digitales ou lecteurs d’empreintes de visage peuvent être contournés (cf. compromission des technologies Apple touchID  et faceID [^⁸], par exemple). Même si les grandes entreprises commencent à implémenter ce procédé, celui-ci n’est toujours pas très répandu. Les difficultés d’implémentation dans les infrastructures sont assez importantes car le coût d’implémentation est énorme.

[^⁸]: [FaceID hack](https://siecledigital.fr/2017/11/13/chercheurs-face-id-masque-iphone-x-hack/)

Donc une chose est sûre, le mot de passe n’est pas encore prêt de disparaître. Vous en avez pour un petit moment encore !

## Malware, Virus, Trojan...

Il est intéressant de savoir faire la différence entre les types de menaces que nous pouvons rencontrer, ou qui sont à l’origine d’une compromission : un « malware » (**mal**icous soft**ware**) est un terme anglais qui désigne un logiciel malveillant. Ici, le terme logiciel se rapporte à tout programme informatique, document ou fichier qui est stocké sur un disque dur ou transmis via un réseau.

Voici une idée des principaux types de malwares existants à ce jour :
-   Les virus : qui sont des bouts de codes informatiques attachés à des programmes informatiques eux-mêmes. Un virus est créé pour infecter un équipement et se propager à d’autres équipements (finalement un peu à la manière d’un réel virus qui se propage dans le corps humain d'une personne à une autre !). L’idée est d’effectuer toutes sortes d’opérations afin de corrompre la ou les machines cibles : altération, réécriture, suppression de données... Le résultat est un équipement instable et lent.
-   Les chevaux de Troie (« Trojan » en anglais) : un programme informatique qui a l’air tout à fait normal, à ceci près qu’il cache une fonction malveillante dans ses entrailles. Par exemple, une personne télécharge un lecteur vidéo d’un site internet inconnu, pensant trouver un outil capable de lire un format de fichier, mais donnant au final un accès complet à un attaquant sur la machine cible ; c'est l'idée d'un cheval de Troie.
-   Les "rootkits" : un joli _ensemble de programmes malveillants_ - dissimulés et vus comme normaux par des anti-virus, qui permet de donner un accès libre à distance à un attaquant. Alors, comme cela, la différence entre un Trojan et un Rootkit n'est pas évidente... Mais quand un trojan est plus susceptible d'être détecté par un anti-virus classique, un rootkit sait se dissimuler plus encore, et est très complexe à entièrement supprimer de la machine infectée. Il mérite un outil de détection particulier.
-   Les rançongiciels (« ransomware » en anglais) : là encore un joli logiciel malveillant qui vient chiffrer vos données personnelles. Cela rend donc vos données illisibles, sauf si vous détenez la clé (de déchiffrement). C’est là que l’attaquant entre en jeu et vous demande de payer une somme (une rançon donc) en échange de la clé de déchiffrement ou du mot de passe. La menace sera souvent de diffuser publiquement les informations si vous n’acceptez pas de payer cette rançon. Voilà pourquoi c'est assez problématique pour les entreprises par exemple.
-   Les logiciels espions (plus connus sous le nom de « spywares ») : sont des logiciels capables de collecter et transmettre toutes informations utiles sur un utilisateur ou un système : mots de passe, activité internet ou réseau privé, appuis sur les touches clavier, etc. Représentés par 2 types : les « keyloggers » ou enregistreur de frappes qui journalisent toutes les touches tapées sur votre système et les « adware » qui vont sournoisement vous afficher des publicités afin de vous pousser à cliquer sur l'une d'entre elle et ainsi voler des données confidentielles que vous pourriez donner (carte bancaire, etc.).
-   Les bots et botnets : vous avez tous déjà entendu parler des "bots", ou plus simplement appelés "robots internet". Un robot est un logiciel qui automatise des tâches sur internet. Par exemple : il existe des bots pour les gamers, des bots sur Telegram, des socials bots... Il en existe de toutes sortes, mais ceux qui nous intéressent ici sont les _bots malveillants_. Des bots malveillants sont bien sûr conçus pour automatiser des tâches d'intrusion et de compromission d'une ou plusieurs machines ; dans le dernier cas, on parlera de "botnets", car les bots sont reliés en réseau. Plusieurs types :
		:arrow_right: des bots qui aspirent des pages internet et les données associées afin d'en générer des copies frauduleuses,
		:arrow_right: des bots servant à des attaques DoS ou DDoS (Denial of Service ou Distributed DoS),
		:arrow_right: des bots qui scrutent les sites internet à la recherche d'adresses courriel en clair ou d'adresses postales...,
		:arrow_right: des spambots (affichage de publicités intempestives (spams)),
		 etc.
-   Il existe bien sûr d’autres types de malwares comme par exemple les _backdoors_, les fileless malwares, les logiciels malveillants sur téléphone portable...

> Vous voyez ici qu’il ne faut pas confondre virus et malware qui sont _deux notions différentes_ bien que liées : en effet, les virus sont une forme de malware (logiciel malveillant).
{.is-info}


Par extension, nous utilisons souvent le terme d’anti-virus, bien que réducteur, car les anti-virus aujourd’hui sont capables de détecter bien plus que les virus. Mais, nous voyons apparaître, depuis quelques années maintenant, des logiciels de type « anti-malware » : ces logiciels bien que pouvant se rapprocher des anti-virus détectent plus de types de malwares, via des mécanismes différents (signature vs méthode heuristique ; dont ce n’est pas l’objet de l’article). Ils sont de toute manière tout à fait complémentaires.

Nous reparlons de ces outils plus loin dans l'article...

*Note : Vous avez maintenant les clés pour vous la péter avec vos amis :-) !*

## Les métadonnées, qu'est-ce que c'est ?

Nous entendons beaucoup parler de "métadonnées" de nos jours... Mais à quoi se raccroche ce terme ?

Tentons de définir cela : une métadonnée est une information concernant une donnée (en gros une donnée sur une donnée !).

Cette information peut inclure des choses comme :
-  l'émetteur et le destinataire d'un message, 
-  la date de transmission et/ou d'envoi effectif, 
-  l'adresse IP, 
-  la géolocalisation
-  des identifiants de machine ou équipements
-  des versions de logiciels ou système d'exploitation
-  d'autres informations...

**Tout le trafic internet génère ce type de données, et nous dirions même que sans cela, internet ne pourrait pas tout à fait fonctionner.**

La plupart du temps, ces données ne peuvent pas faire l'objet d'une protection ou tout du moins une protection complète, car celles-ci sont parfois primordiales pour communiquer ! Il n'est pas si évident de fournir des applications permettant de sécuriser ou tout du moins obfusquer [^⁶] ces informations ; prenons un exemple pour illustrer cela : nous avons défini au début qu'une adresse IP était tout comme votre adresse postale sur internet, continuons sur ce chemin... 

[^⁶]: [Obfusquer](https://fr.wiktionary.org/wiki/obfusquer) définition.

Mettons ici que vous souhaitez transmettre un message à votre cousin. Par analogie, vous souhaiteriez donc transmettre une lettre à l'intérieur d'une enveloppe. Votre écrit serait donc sécurisé, mais sur cette enveloppe vous allez devoir inscrire l'adresse postale de votre cousin, pour que La Poste puisse savoir qui est le destinataire...

Vous voyez où nous voulons en venir : oui, cette adresse postale est en fait une **métadonnée** ! Difficile ici de sécuriser (chiffrer par exemple) cette adresse, car La Poste pourrait ne pas pouvoir lire cette destination et donc votre lettre pourrait ne pas arriver.

Voilà pourquoi certaines informations ne peuvent être protégées, en tout cas de façon simple ! Il existe bien entendu des techniques pour sécuriser et limiter les métadonnées non protégées, et certaines applications peuvent y arriver par design : par exemple la messagerie "Signal" ne fournit que très peu de métadonnées non protégées : les serveurs stockent de façon permanente uniquement les numéros de téléphone associés à un compte Signal, et la dernière connexion avec ce compte. Rien de plus...
**Il est important de noter ici que bien entendu si ce numéro de téléphone vous est attribué, il sera possible de savoir si vous utilisez Signal, même si personne ne pourra avoir le contenu de vos messages bien entendu (hormis potentiellement des entités à fortes ressources financières et logistiques !).**

Le sujet des métadonnées est un sujet extrêmement débattu dans la communauté, car même si certains s'intéressent à leur sécurisation, d'autres au contraire militent pour ne pas protéger ces informations voire en ajouter certaines... Certains dénoncent même cette course à la métadonnée :

> "We kill people based on metadata..." - Traduction : "nous tuons des gens grâce aux métadonnées...", d'après le Général Michael Hayden, ancien directeur de la NSA entre 1999 et 2005 et directeur de la CIA de 2006 à 2009.

Oui vous avez bien lu, un ancien directeur d'une agence étatique a bien évoqué cela ! Voilà pourquoi l'enjeu de la collecte des métadonnées est critique et important pour notre vie privée, mais aussi notre sécurité.

La bonne nouvelle est que nous sommes aujourd'hui capable de limiter cette collecte...

## Hacking, piratage, ne pas confondre !

**Une bonne fois pour toute, remettons l'église au milieu du village !**

Le piratage fait référence à toute activité visant à compromettre un ordinateur, téléphone, une machine en usine, un serveur, un réseau informatique entier, voire une personne (cas de l'ingénierie sociale). Au contraire de ce que la plupart des gens pensent, le piratage n’est pas systématiquement malveillant, mais une partie est en effet effectuée par des cybercriminels et a pour conséquence de compromettre la vie privée de la (ou des) cible(s).

Le « hacking » se rapporte à toute activité permettant de détourner un objet de sa fonction première. Un hacker s’intéresse avant tout au détournement, à la bidouille, au jeu, aux défis intellectuels...

Eh oui, vous voyez, un _hacker_ n’est pas forcément un pirate informatique ! Vous trouverez par exemple beaucoup de personnes détournant des objets de la vie quotidienne pour une autre utilité : ces personnes sont aussi des hackers et on les appelle des « life-hackers ». Cette confusion vient en partie des journalistes et autres pseudo-experts qui ont utilisé ce terme afin de désigner les cybercriminels uniquement, en omettant toute la partie bienveillante ou positive. Ce terme est resté ancré dans l’inconscient collectif, en des termes négatifs.

Attention donc à la confusion avec la terminologie :
-   Un cybercriminel est un pirate informatique malveillant
-   Un pirate informatique peut être bienveillant (un "pentester" par exemple - **pen**etration **test**ing = tests d'intrusion : auditer la sécurité informatique)
-   Un hacker peut être un pirate informatique (cf. terminologie [White Hat / Grey Hat / Black Hat](/glossaire#white-hat) du glossaire).
Il peut néanmoins être un "bidouilleur", qui installe un système alternatif à la place de celui d'un robot cuiseur, une calculatrice [^¹] ou une imprimante [^²], pour relever le défi d'y jouer à des jeux vidéos :)

[^¹]: [Doom](https://www.phonandroid.com/doom-fonctionne-meme-sur-une-calculatrice-alimentee-par-des-patates.html) fonctionne sur une calculatrice
[^²]: [Une imprimante](https://www.tomsguide.fr/un-hacker-pirate-une-imprimante-en-installant-le-jeu-doom/) utilisée pour jouer à Doom

# Définir son modèle de menaces

Tenter de protéger TOUTES ses informations personnelles, TOUT le temps, de TOUT le monde, peut s'avérer être une tâche ardue voire épuisante ! Pas de panique, la sécurité numérique est un long '''voyage '''qui doit s'adapter à votre profil et évoluer selon vos utilisations. La sécurité numérique n'est pas limitée aux seuls outils ou services que vous utilisez, elle commence par l'anticipation et la compréhension des menaces existantes et de la façon de s'en prémunir. Par définition :

> Un modèle de menaces ("Threat Model") correspond à l'identification et la compréhension des menaces les plus probables qui peuvent vous impacter. Ainsi, vous serez plus à même de mettre en place les contre-mesures adéquates.

J'en conviens, c'est une définition un peu "barbare", mais tentons d'y voir plus clair sur ce sujet intéressant. En sécurité numérique :
-   une menace se définit par un événement possible et redouté qui saperait vos efforts dans la protection de vos données ;
-   les contre-mesures sont toutes les actions entreprises afin d'écarter ces menaces.

Nous pouvons donc en déduire que grâce à l'identification des menaces que vous rencontrerez potentiellement, il sera possible d'y appliquer des actions récurrentes ou ponctuelles (grâce à des outils ou manuellement) sur votre vie numérique.

Mais avant tout cela, tentons de comprendre la finalité...

## Sécurité, vie privée et anonymat

Trois termes extrêmement importants lorsque nous cherchons à comprendre comment nous sommes interconnectés et comment les choses se déroulent dans notre sphère numérique ; trois concepts différents, qui se rejoignent pourtant, et dont voici une définition :
-   La **vie privée**, ou appelée chez nos amis anglo-saxon « Privacy », se rapporte à tout ce qui a trait au contrôle de nos informations personnelles.
-   La **sécurité**, ou « Security », se réfère à la protection de ces informations personnelles, _globalement_ pour se prémunir d'accès non autorisés.
-   L’**anonymat**, ou « Anonymity », représente le fait de cacher l’auteur d’un échange et des informations.
  (*À ne pas confondre avec pseudonymat qui est l'utilisation d'une identité fictive*).

Afin d’atteindre un certain degré de sécurité, de vie privée et d’anonymat, il est essentiel aujourd’hui de se pencher véritablement sur nos activités numériques. Voyons ces 3 aspects comme 3 cercles qui se chevauchent, les centres de ces 3 cercles représentant le degré maximal de protection :

```diagram
PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB2ZXJzaW9uPSIxLjEiIHdpZHRoPSI1MDFweCIgaGVpZ2h0PSI0NzZweCIgdmlld0JveD0iLTAuNSAtMC41IDUwMSA0NzYiIGNvbnRlbnQ9IiZsdDtteGZpbGUgaG9zdD0mcXVvdDtlbWJlZC5kaWFncmFtcy5uZXQmcXVvdDsgbW9kaWZpZWQ9JnF1b3Q7MjAyMi0xMi0wMlQxMjozMzowNS43ODRaJnF1b3Q7IGFnZW50PSZxdW90OzUuMCAoWDExOyBMaW51eCB4ODZfNjQpIEFwcGxlV2ViS2l0LzUzNy4zNiAoS0hUTUwsIGxpa2UgR2Vja28pIENocm9tZS8xMDcuMC4wLjAgU2FmYXJpLzUzNy4zNiZxdW90OyBldGFnPSZxdW90O3hmZGlEemVsbFZTOWQxaVlDWkhfJnF1b3Q7IHZlcnNpb249JnF1b3Q7MjAuNi4wJnF1b3Q7IHR5cGU9JnF1b3Q7ZW1iZWQmcXVvdDsmZ3Q7Jmx0O2RpYWdyYW0gaWQ9JnF1b3Q7TVphSFhOamh0d1Z1anpwZXkzMnAmcXVvdDsgbmFtZT0mcXVvdDtQYWdlLTEmcXVvdDsmZ3Q7N1poYmI1c3dGTWMvRFkrVHdGeENIbk5oWGFUMW9xYnJ0RWNERGxnMW1EbE9rKzdUN3hoTXVGYWQxTFNacWo1aC84K3hzYy8vWjZQRXNCZlo0VUxnSXIza01XRUdNdU9EWVM4TmhDeGsrdkJReWxPbFRDeXpFaEpCWTUzVUNHdjZoMml4VHR2Um1HdzdpWkp6Sm1uUkZTT2U1eVNTSFEwTHdmZmR0QTFuM2JjV09DRURZUjFoTmxSLzBsaW1sZXFqU2FOL0l6Uko2emRiM3JTS1pMaE8xanZacGpqbSs1WmtCNGE5RUp6THFwVWRGb1NwNHRWMXFjWjlmU1o2WEpnZ3VmeVhBYWdhOElqWlR1L05RQjZEb2ZNTmh4bGdnZkpKNzlyN3ZlTjE0TXUyOUdRR0NjZ3B3TmQ1RTRkV29wL2xSR0V0cklQRmo5dlZYVkFIWUZWaFB4bTA2c1cxakRwclFMQjZNQms2ODMxS0pWa1hPRktSUFhBR1dpb3pCajBMbW5oYlZNNXY2SUhFYXRtVXNRVm5YSlFUMmJGTC9OZ0JmU3NGZnlDdGlJOUMyL01nd21GeUtoV2lFMVBOeUdpU1F5ZUMwaExJblQ4U0lTbEFNZE9Ca0V2Sk16V2xHcGduYzkxZk9tWWpmaWNidFNyenVMbTJWOW8rTlRFNXRDVHQzUVhoR1pIaUNWTHFxS2M1MGdjSitXN1YzemRZMnFiT1NWdElIa1dzajBKeW5MdWhCUm9hbUhGNDdHZmhHZmo2YXBydVY4Q05lWE83dWcrQ1oyRVo0K3F0QUNJV0lEUVpBMmpxVFd3OEFsQ2ZGOG1MaG9zNzFhbElPUUVYeU8xeVlkVTM1N3R3NGJ3akY3T3I2NnRmbDdPNy80S0pqUitSS0Jwakl2UmR4elU3VEhnbnVGUk9nSXA5MWl2RUhVR2w1dzU4SWd2VjVDSTQrbFFRUWVGZHFtSkw3ZDVOSTcxa1k0aWpoMFR3WFI1Zjd5U2pPZEg2S2FwcGRxdnBvR0UxMFVneDBRbHE2UTFxYWFuVnVJT0t3bDVrdHlLQ3dGSERZWmxRWXJtVHZEcDhGZmN2VVpyUk9HYWxNWnptc3R5RE96ZmNaZStJNUZ6VnVuYzZ0Rmo2b1E3VnFiNk5xQWUyTTNJSHVxTmN2OTZLeVFmRDJqMGoxdjRuMW0wcm5ETmlQZjFnV052VDNyZlBIZGJ5cmJDdWJmdmtXbnZoVEx0ZTJHL0dOWFNiWDlobHJQVS9oUjM4QlE9PSZsdDsvZGlhZ3JhbSZndDsmbHQ7L214ZmlsZSZndDsiPjxkZWZzLz48Zz48ZWxsaXBzZSBjeD0iMTUwIiBjeT0iMzI1IiByeD0iMTUwIiByeT0iMTUwIiBmaWxsLW9wYWNpdHk9IjAuNyIgZmlsbD0iI2Q1ZThkNCIgc3Ryb2tlPSIjODJiMzY2IiBzdHJva2Utb3BhY2l0eT0iMC43IiBwb2ludGVyLWV2ZW50cz0iYWxsIi8+PGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTAuNSAtMC41KSI+PHN3aXRjaD48Zm9yZWlnbk9iamVjdCBwb2ludGVyLWV2ZW50cz0ibm9uZSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5IiBzdHlsZT0ib3ZlcmZsb3c6IHZpc2libGU7IHRleHQtYWxpZ246IGxlZnQ7Ij48ZGl2IHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzdHlsZT0iZGlzcGxheTogZmxleDsgYWxpZ24taXRlbXM6IHVuc2FmZSBmbGV4LWVuZDsganVzdGlmeS1jb250ZW50OiB1bnNhZmUgY2VudGVyOyB3aWR0aDogMjk4cHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogNDMycHg7IG1hcmdpbi1sZWZ0OiAxcHg7Ij48ZGl2IGRhdGEtZHJhd2lvLWNvbG9ycz0iY29sb3I6IHJnYigwLCAwLCAwKTsgIiBzdHlsZT0iYm94LXNpemluZzogYm9yZGVyLWJveDsgZm9udC1zaXplOiAwcHg7IHRleHQtYWxpZ246IGNlbnRlcjsiPjxkaXYgc3R5bGU9ImRpc3BsYXk6IGlubGluZS1ibG9jazsgZm9udC1zaXplOiAxMnB4OyBmb250LWZhbWlseTogSGVsdmV0aWNhOyBjb2xvcjogcmdiKDAsIDAsIDApOyBsaW5lLWhlaWdodDogMS4yOyBwb2ludGVyLWV2ZW50czogYWxsOyB3aGl0ZS1zcGFjZTogbm9ybWFsOyBvdmVyZmxvdy13cmFwOiBub3JtYWw7Ij48Zm9udCBzdHlsZT0iZm9udC1zaXplOiAyNHB4OyI+PGI+U0VDVVJJVEU8L2I+PC9mb250PjwvZGl2PjwvZGl2PjwvZGl2PjwvZm9yZWlnbk9iamVjdD48dGV4dCB4PSIxNTAiIHk9IjQzMiIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPlNFQ1VSSVRFPC90ZXh0Pjwvc3dpdGNoPjwvZz48ZWxsaXBzZSBjeD0iMjQwIiBjeT0iMTUwIiByeD0iMTUwIiByeT0iMTUwIiBmaWxsLW9wYWNpdHk9IjAuNyIgZmlsbD0iI2UxZDVlNyIgc3Ryb2tlPSIjOTY3M2E2IiBzdHJva2Utb3BhY2l0eT0iMC43IiBwb2ludGVyLWV2ZW50cz0iYWxsIi8+PGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTAuNSAtMC41KSI+PHN3aXRjaD48Zm9yZWlnbk9iamVjdCBwb2ludGVyLWV2ZW50cz0ibm9uZSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5IiBzdHlsZT0ib3ZlcmZsb3c6IHZpc2libGU7IHRleHQtYWxpZ246IGxlZnQ7Ij48ZGl2IHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzdHlsZT0iZGlzcGxheTogZmxleDsgYWxpZ24taXRlbXM6IHVuc2FmZSBmbGV4LXN0YXJ0OyBqdXN0aWZ5LWNvbnRlbnQ6IHVuc2FmZSBjZW50ZXI7IHdpZHRoOiAyOThweDsgaGVpZ2h0OiAxcHg7IHBhZGRpbmctdG9wOiA0N3B4OyBtYXJnaW4tbGVmdDogOTFweDsiPjxkaXYgZGF0YS1kcmF3aW8tY29sb3JzPSJjb2xvcjogcmdiKDAsIDAsIDApOyAiIHN0eWxlPSJib3gtc2l6aW5nOiBib3JkZXItYm94OyBmb250LXNpemU6IDBweDsgdGV4dC1hbGlnbjogY2VudGVyOyI+PGRpdiBzdHlsZT0iZGlzcGxheTogaW5saW5lLWJsb2NrOyBmb250LXNpemU6IDEycHg7IGZvbnQtZmFtaWx5OiBIZWx2ZXRpY2E7IGNvbG9yOiByZ2IoMCwgMCwgMCk7IGxpbmUtaGVpZ2h0OiAxLjI7IHBvaW50ZXItZXZlbnRzOiBhbGw7IHdoaXRlLXNwYWNlOiBub3JtYWw7IG92ZXJmbG93LXdyYXA6IG5vcm1hbDsiPjxiPjxmb250IHN0eWxlPSJmb250LXNpemU6IDI0cHg7Ij5WSUUgUFJJVkVFPC9mb250PjwvYj48L2Rpdj48L2Rpdj48L2Rpdj48L2ZvcmVpZ25PYmplY3Q+PHRleHQgeD0iMjQwIiB5PSI1OSIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPlZJRSBQUklWRUU8L3RleHQ+PC9zd2l0Y2g+PC9nPjxlbGxpcHNlIGN4PSIzNTAiIGN5PSIzMjUiIHJ4PSIxNTAiIHJ5PSIxNTAiIGZpbGwtb3BhY2l0eT0iMC42IiBmaWxsPSIjZjhjZWNjIiBzdHJva2U9IiNiODU0NTAiIHN0cm9rZS1vcGFjaXR5PSIwLjYiIHBvaW50ZXItZXZlbnRzPSJhbGwiLz48ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMC41IC0wLjUpIj48c3dpdGNoPjxmb3JlaWduT2JqZWN0IHBvaW50ZXItZXZlbnRzPSJub25lIiB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiByZXF1aXJlZEZlYXR1cmVzPSJodHRwOi8vd3d3LnczLm9yZy9UUi9TVkcxMS9mZWF0dXJlI0V4dGVuc2liaWxpdHkiIHN0eWxlPSJvdmVyZmxvdzogdmlzaWJsZTsgdGV4dC1hbGlnbjogbGVmdDsiPjxkaXYgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGh0bWwiIHN0eWxlPSJkaXNwbGF5OiBmbGV4OyBhbGlnbi1pdGVtczogdW5zYWZlIGZsZXgtZW5kOyBqdXN0aWZ5LWNvbnRlbnQ6IHVuc2FmZSBjZW50ZXI7IHdpZHRoOiAyOThweDsgaGVpZ2h0OiAxcHg7IHBhZGRpbmctdG9wOiA0MzJweDsgbWFyZ2luLWxlZnQ6IDIwMXB4OyI+PGRpdiBkYXRhLWRyYXdpby1jb2xvcnM9ImNvbG9yOiByZ2IoMCwgMCwgMCk7ICIgc3R5bGU9ImJveC1zaXppbmc6IGJvcmRlci1ib3g7IGZvbnQtc2l6ZTogMHB4OyB0ZXh0LWFsaWduOiBjZW50ZXI7Ij48ZGl2IHN0eWxlPSJkaXNwbGF5OiBpbmxpbmUtYmxvY2s7IGZvbnQtc2l6ZTogMTJweDsgZm9udC1mYW1pbHk6IEhlbHZldGljYTsgY29sb3I6IHJnYigwLCAwLCAwKTsgbGluZS1oZWlnaHQ6IDEuMjsgcG9pbnRlci1ldmVudHM6IGFsbDsgd2hpdGUtc3BhY2U6IG5vcm1hbDsgb3ZlcmZsb3ctd3JhcDogbm9ybWFsOyI+PGI+PGZvbnQgc3R5bGU9ImZvbnQtc2l6ZTogMjRweDsiPkFOT05ZTUFUPC9mb250PjwvYj48L2Rpdj48L2Rpdj48L2Rpdj48L2ZvcmVpZ25PYmplY3Q+PHRleHQgeD0iMzUwIiB5PSI0MzIiIGZpbGw9InJnYigwLCAwLCAwKSIgZm9udC1mYW1pbHk9IkhlbHZldGljYSIgZm9udC1zaXplPSIxMnB4IiB0ZXh0LWFuY2hvcj0ibWlkZGxlIj5BTk9OWU1BVDwvdGV4dD48L3N3aXRjaD48L2c+PGVsbGlwc2UgY3g9IjE1MCIgY3k9IjMyNSIgcng9IjEwIiByeT0iMTAiIGZpbGw9InJnYigyNTUsIDI1NSwgMjU1KSIgc3Ryb2tlPSJyZ2IoMCwgMCwgMCkiIHBvaW50ZXItZXZlbnRzPSJhbGwiLz48cGF0aCBkPSJNIDE0MCAzMjUgTCAxNjAgMzI1IiBmaWxsPSJub25lIiBzdHJva2U9InJnYigwLCAwLCAwKSIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiBwb2ludGVyLWV2ZW50cz0iYWxsIi8+PHBhdGggZD0iTSAxNTAgMzE1IEwgMTUwIDMzNSIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJyZ2IoMCwgMCwgMCkiIHN0cm9rZS1taXRlcmxpbWl0PSIxMCIgcG9pbnRlci1ldmVudHM9ImFsbCIvPjxyZWN0IHg9IjEwMCIgeT0iMzAwIiB3aWR0aD0iNTAiIGhlaWdodD0iMzAiIGZpbGw9Im5vbmUiIHN0cm9rZT0ibm9uZSIgcG9pbnRlci1ldmVudHM9ImFsbCIvPjxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKC0wLjUgLTAuNSkiPjxzd2l0Y2g+PGZvcmVpZ25PYmplY3QgcG9pbnRlci1ldmVudHM9Im5vbmUiIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIHJlcXVpcmVkRmVhdHVyZXM9Imh0dHA6Ly93d3cudzMub3JnL1RSL1NWRzExL2ZlYXR1cmUjRXh0ZW5zaWJpbGl0eSIgc3R5bGU9Im92ZXJmbG93OiB2aXNpYmxlOyB0ZXh0LWFsaWduOiBsZWZ0OyI+PGRpdiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94aHRtbCIgc3R5bGU9ImRpc3BsYXk6IGZsZXg7IGFsaWduLWl0ZW1zOiB1bnNhZmUgY2VudGVyOyBqdXN0aWZ5LWNvbnRlbnQ6IHVuc2FmZSBjZW50ZXI7IHdpZHRoOiAxcHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogMzE1cHg7IG1hcmdpbi1sZWZ0OiAxMjVweDsiPjxkaXYgZGF0YS1kcmF3aW8tY29sb3JzPSJjb2xvcjogcmdiKDAsIDAsIDApOyAiIHN0eWxlPSJib3gtc2l6aW5nOiBib3JkZXItYm94OyBmb250LXNpemU6IDBweDsgdGV4dC1hbGlnbjogY2VudGVyOyI+PGRpdiBzdHlsZT0iZGlzcGxheTogaW5saW5lLWJsb2NrOyBmb250LXNpemU6IDEycHg7IGZvbnQtZmFtaWx5OiBIZWx2ZXRpY2E7IGNvbG9yOiByZ2IoMCwgMCwgMCk7IGxpbmUtaGVpZ2h0OiAxLjI7IHBvaW50ZXItZXZlbnRzOiBhbGw7IHdoaXRlLXNwYWNlOiBub3dyYXA7Ij4xMDAlPC9kaXY+PC9kaXY+PC9kaXY+PC9mb3JlaWduT2JqZWN0Pjx0ZXh0IHg9IjEyNSIgeT0iMzE5IiBmaWxsPSJyZ2IoMCwgMCwgMCkiIGZvbnQtZmFtaWx5PSJIZWx2ZXRpY2EiIGZvbnQtc2l6ZT0iMTJweCIgdGV4dC1hbmNob3I9Im1pZGRsZSI+MTAwJTwvdGV4dD48L3N3aXRjaD48L2c+PGVsbGlwc2UgY3g9IjM1MCIgY3k9IjMyNSIgcng9IjEwIiByeT0iMTAiIGZpbGw9InJnYigyNTUsIDI1NSwgMjU1KSIgc3Ryb2tlPSJyZ2IoMCwgMCwgMCkiIHBvaW50ZXItZXZlbnRzPSJhbGwiLz48cGF0aCBkPSJNIDM0MCAzMjUgTCAzNjAgMzI1IiBmaWxsPSJub25lIiBzdHJva2U9InJnYigwLCAwLCAwKSIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiBwb2ludGVyLWV2ZW50cz0iYWxsIi8+PHBhdGggZD0iTSAzNTAgMzE1IEwgMzUwIDMzNSIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJyZ2IoMCwgMCwgMCkiIHN0cm9rZS1taXRlcmxpbWl0PSIxMCIgcG9pbnRlci1ldmVudHM9ImFsbCIvPjxyZWN0IHg9IjMwMCIgeT0iMzAwIiB3aWR0aD0iNTAiIGhlaWdodD0iMzAiIGZpbGw9Im5vbmUiIHN0cm9rZT0ibm9uZSIgcG9pbnRlci1ldmVudHM9ImFsbCIvPjxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKC0wLjUgLTAuNSkiPjxzd2l0Y2g+PGZvcmVpZ25PYmplY3QgcG9pbnRlci1ldmVudHM9Im5vbmUiIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIHJlcXVpcmVkRmVhdHVyZXM9Imh0dHA6Ly93d3cudzMub3JnL1RSL1NWRzExL2ZlYXR1cmUjRXh0ZW5zaWJpbGl0eSIgc3R5bGU9Im92ZXJmbG93OiB2aXNpYmxlOyB0ZXh0LWFsaWduOiBsZWZ0OyI+PGRpdiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94aHRtbCIgc3R5bGU9ImRpc3BsYXk6IGZsZXg7IGFsaWduLWl0ZW1zOiB1bnNhZmUgY2VudGVyOyBqdXN0aWZ5LWNvbnRlbnQ6IHVuc2FmZSBjZW50ZXI7IHdpZHRoOiAxcHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogMzE1cHg7IG1hcmdpbi1sZWZ0OiAzMjVweDsiPjxkaXYgZGF0YS1kcmF3aW8tY29sb3JzPSJjb2xvcjogcmdiKDAsIDAsIDApOyAiIHN0eWxlPSJib3gtc2l6aW5nOiBib3JkZXItYm94OyBmb250LXNpemU6IDBweDsgdGV4dC1hbGlnbjogY2VudGVyOyI+PGRpdiBzdHlsZT0iZGlzcGxheTogaW5saW5lLWJsb2NrOyBmb250LXNpemU6IDEycHg7IGZvbnQtZmFtaWx5OiBIZWx2ZXRpY2E7IGNvbG9yOiByZ2IoMCwgMCwgMCk7IGxpbmUtaGVpZ2h0OiAxLjI7IHBvaW50ZXItZXZlbnRzOiBhbGw7IHdoaXRlLXNwYWNlOiBub3dyYXA7Ij4xMDAlPC9kaXY+PC9kaXY+PC9kaXY+PC9mb3JlaWduT2JqZWN0Pjx0ZXh0IHg9IjMyNSIgeT0iMzE5IiBmaWxsPSJyZ2IoMCwgMCwgMCkiIGZvbnQtZmFtaWx5PSJIZWx2ZXRpY2EiIGZvbnQtc2l6ZT0iMTJweCIgdGV4dC1hbmNob3I9Im1pZGRsZSI+MTAwJTwvdGV4dD48L3N3aXRjaD48L2c+PGVsbGlwc2UgY3g9IjI0MCIgY3k9IjE1MCIgcng9IjEwIiByeT0iMTAiIGZpbGw9InJnYigyNTUsIDI1NSwgMjU1KSIgc3Ryb2tlPSJyZ2IoMCwgMCwgMCkiIHBvaW50ZXItZXZlbnRzPSJhbGwiLz48cGF0aCBkPSJNIDIzMCAxNTAgTCAyNTAgMTUwIiBmaWxsPSJub25lIiBzdHJva2U9InJnYigwLCAwLCAwKSIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiBwb2ludGVyLWV2ZW50cz0iYWxsIi8+PHBhdGggZD0iTSAyNDAgMTQwIEwgMjQwIDE2MCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJyZ2IoMCwgMCwgMCkiIHN0cm9rZS1taXRlcmxpbWl0PSIxMCIgcG9pbnRlci1ldmVudHM9ImFsbCIvPjxyZWN0IHg9IjE4OSIgeT0iMTIwIiB3aWR0aD0iNTAiIGhlaWdodD0iMzAiIGZpbGw9Im5vbmUiIHN0cm9rZT0ibm9uZSIgcG9pbnRlci1ldmVudHM9ImFsbCIvPjxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKC0wLjUgLTAuNSkiPjxzd2l0Y2g+PGZvcmVpZ25PYmplY3QgcG9pbnRlci1ldmVudHM9Im5vbmUiIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIHJlcXVpcmVkRmVhdHVyZXM9Imh0dHA6Ly93d3cudzMub3JnL1RSL1NWRzExL2ZlYXR1cmUjRXh0ZW5zaWJpbGl0eSIgc3R5bGU9Im92ZXJmbG93OiB2aXNpYmxlOyB0ZXh0LWFsaWduOiBsZWZ0OyI+PGRpdiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94aHRtbCIgc3R5bGU9ImRpc3BsYXk6IGZsZXg7IGFsaWduLWl0ZW1zOiB1bnNhZmUgY2VudGVyOyBqdXN0aWZ5LWNvbnRlbnQ6IHVuc2FmZSBjZW50ZXI7IHdpZHRoOiAxcHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogMTM1cHg7IG1hcmdpbi1sZWZ0OiAyMTRweDsiPjxkaXYgZGF0YS1kcmF3aW8tY29sb3JzPSJjb2xvcjogcmdiKDAsIDAsIDApOyAiIHN0eWxlPSJib3gtc2l6aW5nOiBib3JkZXItYm94OyBmb250LXNpemU6IDBweDsgdGV4dC1hbGlnbjogY2VudGVyOyI+PGRpdiBzdHlsZT0iZGlzcGxheTogaW5saW5lLWJsb2NrOyBmb250LXNpemU6IDEycHg7IGZvbnQtZmFtaWx5OiBIZWx2ZXRpY2E7IGNvbG9yOiByZ2IoMCwgMCwgMCk7IGxpbmUtaGVpZ2h0OiAxLjI7IHBvaW50ZXItZXZlbnRzOiBhbGw7IHdoaXRlLXNwYWNlOiBub3dyYXA7Ij4xMDAlPC9kaXY+PC9kaXY+PC9kaXY+PC9mb3JlaWduT2JqZWN0Pjx0ZXh0IHg9IjIxNCIgeT0iMTM5IiBmaWxsPSJyZ2IoMCwgMCwgMCkiIGZvbnQtZmFtaWx5PSJIZWx2ZXRpY2EiIGZvbnQtc2l6ZT0iMTJweCIgdGV4dC1hbmNob3I9Im1pZGRsZSI+MTAwJTwvdGV4dD48L3N3aXRjaD48L2c+PC9nPjxzd2l0Y2g+PGcgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5Ii8+PGEgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMCwtNSkiIHhsaW5rOmhyZWY9Imh0dHBzOi8vd3d3LmRpYWdyYW1zLm5ldC9kb2MvZmFxL3N2Zy1leHBvcnQtdGV4dC1wcm9ibGVtcyIgdGFyZ2V0PSJfYmxhbmsiPjx0ZXh0IHRleHQtYW5jaG9yPSJtaWRkbGUiIGZvbnQtc2l6ZT0iMTBweCIgeD0iNTAlIiB5PSIxMDAlIj5UZXh0IGlzIG5vdCBTVkcgLSBjYW5ub3QgZGlzcGxheTwvdGV4dD48L2E+PC9zd2l0Y2g+PC9zdmc+
```

**Oui, alors on ne se moque pas : je ne suis pas webdesigner :D !**

---
Assez schématiquement, nous pouvons nous apercevoir qu'il va être **extrêmement difficile** si ce n'est **impossible** de se placer à l'interjection des 3 axes de protection en espérant le 100% sur chaque pan de protection.

**_Pour illustrer_** :
  - Une méthode pour protéger sa vie privée pourrait être une fonction anti-traceurs dans un navigateur (uBlock), 
  - Une méthode pour assurer un niveau de sécurité pourrait être un mot de passe, 
  - Et enfin l'utilisation de Tor pourrait être un outil afin d'obtenir un *relatif* anonymat.
{.grid-list}

> Souvent, les personnes confondent Vie Privée et Sécurité ; la frontière est mince, mais ces notions renvoient tout de même à des aspects différents de la protection des données : la protection de notre vie privée concerne ce que nous **sommes prêts à donner** comme informations sur nous aux autres personnes, tandis que la sécurité concerne ce que nous allons **entreprendre pour rendre inaccessibles** nos informations ; deux aspects différents, deux objectifs bien distincts...
{.is-info}

De fait, multiplier les mécanismes pro-vie-privée, multiplier les équipements ou applications de sécurité (pare-feu, IDS/IPS, honeypot, anti-malware, proxy, host IDS, etc.) et autres procédés d’anonymat ne signifie pas automatiquement une plus grande protection des données, de vie privée et une amélioration de l'anonymat. Au contraire, parfois, complexifier votre approche en terme de cyber-sécurité est le meilleur moyen pour faire grossir la liste des potentielles failles de sécurité ou vulnérabilités. On appelle cela **augmenter sa surface d'attaque** : Plus vous avez d'équipements, de services ou de logiciels, plus le nombre de vulnérabilités augmente, donc plus la probabilité d'avoir une faille exploitable augmente également.

_Plutôt que d'avoir l'objectif d'atteindre le triptique vie privée intégrale + sécurité intégrale + anonymat intégral, l'idée est d'établir des **compromis** entre sécurité, vie privée, anonymat et facilité d'utilisation._

Souvent vous souhaitez utiliser l'outil le plus sécurisé et à la mode, néanmoins vous n'êtes pas prêt à accepter le côté austère et compliqué de l'outil, ni les conditions d'utilisation drastiques ! En d'autres termes, si votre objectif est d'utiliser les outils les plus sécurisés du moment, vous devrez sacrifier énormément sur le côté simplicité et facilité d'utilisation au quotidien. Et quand bien même, rien ne sera totalement sécurisé...

> **Voilà pourquoi établir son modèle de menaces peut nous aider à identifier les outils et les procédés les plus adéquats pour notre profil de sécurité.**
{.is-success}


Vous allez donc devoir porter votre attention sur les menaces les plus probables que vous pourriez rencontrer dans votre vie numérique de tous les jours et celles qui vous semblent les plus importantes à vos yeux (attention ici à ne pas non plus entrer dans une paranoïa excessive !).

## Établir son modèle de menaces

Établir son modèle de menaces n’est pas aisé, mais nous allons tenter de simplifier ensemble cette procédure afin de vous y aider...

### Contre qui ?

La première question à se poser sera : contre qui je souhaite me protéger ?

Évidemment ici, il est assez compliqué pour celui qui ne se tient pas informé du monde numérique de connaître et encore moins de comprendre les potentiels adversaires auxquels nous pourrions faire face. À tout le moins, nous pouvons nous dire qu'il existe des *hackers malveillants* qui peuvent en avoir après nos données, mais pour la suite, cela reste flou...

Voici pourquoi nous vous avons fait une liste des adversaires auxquels nous pourrions faire face dans la vie de tous les jours :
1. Votre patron ou vos collègues
2. Votre ex ( :) ) ou votre famille
3. Des entreprises (type petite ou moyenne entreprise, moyens limités)
4. Des multinationales (type GAFAM, BATX, à fort pouvoir de collusion)
5. Des gouvernements (par le biais d'agences gouvernementales)
6. Des cybercriminels (que ce soient des [script-kiddies](https://fr.wikipedia.org/wiki/Script_kiddie), hackers malveillants seuls ou en groupe)

### Quelles données ?

Ensuite vient la question des éléments, que nous qualifions à suivre d' "items", que vous allez devoir protéger des yeux curieux et/ou malveillants. Faites une liste exhaustive des données qui, perdues ou volées, constitueraient un problème.

Voici une liste d'éléments :
1. vos courriels
2. votre liste de contact
3. vos messageries instantanées
4. votre position géographique
5. vos fichiers (ou certains d'entre eux)
6. votre réseau local (wifi, routeurs, NAS, etc.)
7. vos métadonnées
8. vos stockages de données en ligne ("clouds")
9. votre ordinateur (ou vos partitions...)
10. vos photos/vidéos

### Analyse des risques

> Un "risque" se définit comme la probabilité qu'une **menace spécifique** ait un **impact** sur l'un de vos items. 

Ouch, c'est un peu barbare encore une fois ! Voici la traduction par un exemple : votre opérateur téléphonique a la capacité d'accéder à des données vous concernant, mais cela dit le risque qu'ils viennent les dévoiler publiquement sur un réseau social afin de détruire votre réputation en ligne est plutôt faible, vous en conviendrez.

Vous l'aurez sûrement compris, après avoir répondu aux deux premières questions, il est important de distinguer entre
-  ce qui pourrait arriver 
-  et la probabilité que cela arrive réellement

> Exemple : il existe la menace que votre immeuble puisse s'effondrer, mais le risque que cela arrive est plus important au Japon, car plus sujets aux tremblements de terre qu'en France !
{.is-info}

Évaluer le risque est également quelque chose de personnel et subjectif ; certains vont trouver des menaces inacceptables peu importe la probabilité d’occurrence, d'autres vont choisir d'ignorer les risques de type faible, car ils estimeront que la menace n'est pas un problème pour eux. L'idée est donc de lister quelles sont pour vous les menaces les plus importantes, celles que vous allez prendre en compte sérieusement, et celles au contraire trop rares ou trop compliquées à combattre pour s'inquiéter.

**C'est ici la question la plus complexe, elle doit coller au maximum à votre profil (vos menaces, vos usages...).**

Un très bon guide est déjà en ligne, sur [guide.boum.fr/choisir les réponses adaptées](https://guide.boum.org/hors-connexions-choisir-des-reponses-adaptees-introduction.html). Inutile de paraphraser donc ce guide qui est très complet du point de vue d'un utilisateur lambda.

Ce guide doit être lu **avec recul** sans forcément parler d'outils pour le moment. L'idée est ici de comprendre la logique globale de la réflexion à avoir afin d'établir une stratégie : évaluer les menaces sera donc une analyse concernant les données à protéger, ainsi que sur le type d'acteurs qui pourraient concrètement en avoir après nos données. À partir de là, nous pouvons établir les moyens potentiels de nos adversaires, et donc créer notre propre stratégie de protection.

> **Les sections suivantes pourront justement vous donner un aperçu des possibilités et outils afin de mettre en place cette stratégie...**
{.is-success}

# Eviter le hacking

Cette partie est **essentielle**, et vous fournit les meilleures pratiques en matière d'hygiène informatique afin de ne laisser que très peu d'ouverture (on parle d'une surface d'attaque minimale) à de potentiels *adversaires* et éviter au maximum des *vols de données* ou encore des *usurpations d'identité*.

Rentrons dans le vif du sujet, afin de devenir difficilement piratable :

## Les mots de passe

### Politique de mots de passe puissante

Nous l’avons vu plus haut, créer un mot de passe extrêmement puissant peut déjà vous couvrir face à la majorité des tentatives d'intrusions. Choisir un mot de passe comme « 1234 », « Choupette1982 », « Misssunshine » ou « Pepperonipizza2000! » et bien d’autres relève aujourd’hui de l’hérésie informatique (malheureusement on le voit encore trop souvent !) :-(

![motdepasse2023.png](/images/motdepasse2023.png =600x){.align-center}

-   pré-requis minimum : **20 caractères**
 :arrow_right: Cela s'atteint même aisément avec une technique simple - la phrase de passe -, évoquée juste à la suite. 
-   Au minimum, un mélange de lettres minuscules-majuscules, de chiffres, et de caractères spéciaux. Afin de renforcer encore plus vos mots de passe :
    -  On évite la majuscule en début de mot de passe.
    -  On évite le caractère spécial en fin de mot de passe.
    -  On évite les chiffres en début et fin de mot de passe.
    -  On évite les suites de chiffres (tels « 1234 » ou « 54321 ») ou les suites de lettres (type « abcde »).
    -  On évite les dates d'anniversaire, ou dates importantes. 
    -  On évite les prénoms des enfants, le nom de son toutou, les hobbies et toute activité personnelle qui peuvent facilement se retrouver sur les réseaux.
  {.grid-list}
-   Créer votre propre façon d’obfusquer votre mot de passe, par exemple : « jsistorienvoia » peut devenir « js%stor%envo%a » (on ajoute un % à la place du i).
-   Il est également possible voire même _tout à fait conseillé_ aujourd'hui d’utiliser des « **phrases de passe** » (passphrase). Par exemple : « suis bois orchidee cheval ». Une phrase de passe consiste à choisir une suite de mots formant une phrase mais n’ayant aucun sens, avec l'objectif de pouvoir le mémoriser simplement. On pourrait tout aussi bien combiner.
  **On estime qu'une suite de 5 mots serait suffisante pour être à l'abri des attaques les plus courantEs sur les mots de passe : on obtient 64 bits d'entropie et avec une puissance de calcul d'1 Milliard de passphrases testées par seconde, cela prendrait 900 ans avec les moyens actuels et futurs proches ! On recommande, cela dit, 6 mots à ceux qui sont particulièrement exposés, afin d'obtenir une meilleure couverture.**
  Une technique afin de choisir vos mots : le lancé de dés ou [diceware](https://fr.wikipedia.org/wiki/Diceware).
- Enfin dernière technique relativement récente : la stratégie du mot de passe en double aveugle. Dénomination assez barbare mais finalement plutôt simple ! Il s'agit ici de découper les mots de passe en 2 parties, la partie courte et la partie longue ; la partie longue étant stockée dans un gestionnaire de mots de passe ou retenue de tête (bon courage!) et la partie courte sera **unique** et pourra être aisément gardée en mémoire (code PIN ou mot simple). Scinder en 2 un mot de passe (avec une partie courte pouvant être mémorisée simplement) peut complexifier la tâche d'un attaquant pour retrouver ce mot de passe, y compris même s'ils sont réussi à avoir le mot de passe long..
  **Exemple : mettons que votre partie courte soit "abcd5". Nous créons un mot de passe avec notre gestionnaire, par ex. "sdf6#ds5!f65s78)". Le mot de passe intégral sera donc en fait "sdf6#ds5!f65s78)abcd5".**

### Mots de passe UNIQUES

Choisissez un mot de passe UNIQUE pour chaque compte que vous créez.

Chaque site nécessitant un compte avec un couple [nom d’utilisateur ; mot de passe] doit contenir un mot de passe unique, qui n’a jamais été utilisé sur un autre de vos comptes. La raison est très simple : vous évitez en choisissant un mot de passe unique, dans le cas éventuel d'une fuite de données (qui arrive plus souvent que vous ne le pensez), de retrouver ce mot de passe sur les darknets, compromettant ainsi **TOUS** vos comptes ! La situation est en fait encore pire en ayant un mot de passe unique (quand bien même il serait "ultra-secure"!!) : 
- "ultra-secure" (comme le disent certains :|) ou pas, si votre mot de passe est dévoilé, peu importe sa robustesse !
- Et généralement, nous ne sommes pas avertis rapidement de ces fuites de données, donc vous mettez à risque la totalité de vos comptes (qui pour certains peuvent être sensibles) sans forcément le savoir et prendre des mesures (changement de mot de passe). 
- Ah également : dans le cas d'une fuite, vous devrez changer le mot de passe de **TOUS** vos comptes.

**Donc on se répète : _un mot de passe UNIQUE pour chacun de vos comptes_. Ici également, c'est un pré-requis essentiel (non négociable).**

> Attention, veillez à ne pas tester vos mots de passe sur des sites internet qui proposent ce service, y compris sur des sites de sociétés très connues, et y compris s'ils vous disent qu'ils ne collectent pas les données. Vous ne savez pas qui est concrètement derrière ces sites internet, et quels seraient les algorithmes ou les codes implémentés, voire dans le pire cas qui pourrait intercepter la requête avec le mot de passe à l’intérieur ! Un mot de passe est un secret, et doit le rester pour tout le monde, y compris votre conjoint(e) ou vos enfants.
{.is-danger}

Alors je sais, vous vous dites "Non mais attends, créer un mot de passe ultra fort est déjà presque impossible à retenir, si je dois en choisir un pour chaque site ou compte, c'est impossible !!" :)

**Et vous avez entièrement raison...**

### Gestionnaire de mots de passe

**... Voici pourquoi utiliser un gestionnaire de mots de passe est fortement recommandé.**

Nous vous renvoyons ici vers l'[article dédié](/debutant/gestionnaire-mots-passe) à ces outils.

## Authentification 
### L'authentification multi factorielle

Activez partout où cela est possible les authentifications à plusieurs facteurs, au minimum 2FA. Attention cependant à l’utilisation du 2FA avec SMS ou courriel : il doit être limité uniquement aux cas où vous n’avez pas d'alternative. Si l'on vous donne le choix, préférez d’autres méthodes comme l’OTP (One-Time Password) via des outils libres (on évitera les Google Auth, Microsoft Auth etc.), disponibles dans l'[article dédié](/debutant/logiciel-alternative-libre) aux alternatives libres et open source. 

### Les mécanismes d’authentification

Ne jamais vous authentifier en utilisant les mécanismes d’authentification des GAFAM ou autres pompes à données : Facebook, Google, Microsoft etc.

Bien que ces méthodes soient très pratiques à l'usage, cela comporte un risque : comment être sûr que le site en question est de confiance, comment être sûr que celui-ci ne va pas tout simplement collecter vos données personnelles voire même vos identifiants ? Vous ne pouvez pas. Il est donc préférable de créer un compte unique.

**Voilà aussi pourquoi un gestionnaire de mots de passe est utile. Utilisez-le donc afin de simplifier la chose !**

## Le moins d’informations personnelles

De manière générale, évitez de donner trop d’informations personnelles sur des sites internet qui n’en ont pas réellement besoin (âge, date de naissance, adresse postale, lieu de naissance, numéro de sécurité sociale, etc.).
-   Twitter par exemple n’a pas besoin de votre adresse postale, pourquoi la donnez-vous ?
-   Google non plus.
-   Facebook n’a pas besoin de savoir non plus de quelle ville vous venez actuellement.
-   Votre « Forum des choses pratiques » n’a pas non plus besoin de savoir quel âge vous avez
-   Si vous remplissez des questionnaires en ligne ils n’ont pas besoin de connaître votre adresse ou sinon vous devez vous méfier de ce que cela implique (tous professionnels qu’ils soient !)...

Cela est valable pour tous les sites, et encore plus pour les réseaux sociaux, car aucun de ces sites n’est et ne sera à l’abri d’une fuite de données (même s’ils prétendent le contraire).

**Protéger votre identité et votre vie privée est crucial.**

### Adresse postale

> Arrêtez de donner votre adresse postale réelle autant que faire se peut
{.is-info}

Oui je sais cela reste compliqué en France. Parfois, souvent, il n’est pas possible de le faire donc vous n’aurez pas le choix, mais si possible, préférez donner une adresse postale d’un point relais ou d’une boîte postale (vous pouvez louer une boîte postale) lorsque vous le pouvez.

**Cela évite lors de fuites de données de retrouver votre adresse postale un peu partout sur les sites d'échanges entre pirates malveillants.**

Une dernière chose, on évitera de rentrer ses adresses postales de domicile et de travail dans des applications de géolocalisation (type GPS), voire dans votre système de navigation de voiture (Tomtom, etc.) !

Mais ça, vous le faisiez déjà, n’est-ce pas ?

### Les fameuses questions de sécurité

Nous voyons parfois des sites internet qui demandent à ses utilisateurs de sélectionner parmi un nombre de questions pré-établies et d’y adjoindre une réponse personnelle, ceci afin de renforcer la sécurité. Par exemple : quelle est le nom de jeune fille de votre mère ? Quel est votre animal préféré ? Et bien d'autres. Par réflexe, nous avons pratiquement toujours l'habitude de dire la vérité...

Mais vous êtes-vous déjà demandés si vous étiez véritablement obligés de répondre avec de réelles informations ?

La réponse est : _NON, absolument pas_ !

Vous n’êtes pas tenus de donner une information personnelle véridique, vous pouvez tout simplement inventer une réponse. En ce sens, ne pas donner trop d’informations personnelles peut éviter qu’une fuite de données un jour puisse avoir un impact négatif sur votre vie privée.

Ceci se rapporte également aux adresses postales que vous donnez sur tous les sites, bien entendu...

En ce qui concerne donc ces questions de sécurité associées à des réponses secrètes : ne donnez jamais de réponses secrètes en lien avec vous ou votre vie privée (nom de jeune fille de votre mère, sport favoris, dessert préféré, cocktail favori...). Préférez utiliser des réponses aléatoires, et éventuellement celles-ci peuvent être stockées sur votre gestionnaire de mots de passe, pourquoi pas.

### Les petites annonces

Arrêtez de mettre vos adresses courriels ou vos numéros de téléphone dans le texte de vos petites annonces, ou vous vous exposez à des campagnes de spam à volonté, voire pire !

## Les courriels

Protégez vos échanges par courriel, a minima ceux que vous jugez critiques.

Rendez-vous sur l'article [dédié](/debutant/communications#courriel).

## Les messageries

Sur le même principe que vos échanges par courriel, vos échanges par messagerie se doivent d'être protégés... Notre collectif recommande l'utilisation exclusive d'une messagerie sécurisée avec chiffrement de bout-en-bout et respectueuse de vos données privées.

Si votre modèle demande un anonymat, c'est aussi possible même si plus complexe à mettre en place.

Ce sujet est discuté en détails dans l'article dédié aux [messageries](/debutant/communications#messagerie), que nous vous conseillons de lire très attentivement :)

## Les liens hypertextes / URLs

> Ne jamais cliquer sur des liens (hypertextes) contenus dans les courriels.
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

## Les mises à jour

> Toujours effectuer les mises à jour de sécurité dès qu’elles sont disponibles.
{.is-info}

Les pirates informatiques malveillants se basent pratiquement tout le temps sur les failles de sécurité des logiciels. Vous entendez tous les jours que des logiciels ou des systèmes d’exploitation ont reçu des « patchs (entendre correctifs) de sécurité », afin de combler une vulnérabilité (corriger une faille de sécurité). Eh bien, il s’agit exactement de cela : patcher pour combler les failles dont les développeurs se sont aperçus, et qui exposent potentiellement vos données ou autre chose.

Il est aujourd’hui assez simple de vérifier s’il existe des mises à jour de sécurité donc n’attendez pas avant de les faire, surtout lorsque celles-ci sont critiques. Nous recommandons ainsi d'activer les mises à jour automatiques depuis votre système d'exploitation favori (libre ! comme GNU/Linux, ou un Android dégooglisé, nous l'espérons ;-)), dans cette démarche de sécurisation proactive.

Pour le reste des mises à jour classiques, elles peuvent potentiellement attendre, même si le plus tôt sera le mieux.

## Les fichiers et leur intégrité

Ceci est un rappel, mais évitez de télécharger des exécutables directement ou dans des archives, que ce soit Linux (via des fichiers ELF ou "Executable Linkable File") ou Windows (via des fichiers à l'extension .exe ou .msi).
  
Et dans le cas d'un téléchargement depuis un site internet, plutôt que depuis un centre logiciel : toujours télécharger depuis le site officiel de l'éditeur logiciel dudit programme.
*_Astuce toute simple_ : depuis mon moteur de recherche préféré, je tape wikipedia + nom_du_programme_à_télécharger (ou bien je demande conseil sur une communauté, comme celle-ci). Depuis l'article Wikipedia, je retrouve le lien vers l'[URL](/glossaire#url) de l'éditeur logiciel ; le but étant de télécharger un fichier authentique, en allant directement à la source.*

En prolongement et pour tous types de fichiers (.iso, .img, ...), vérifiez **TOUJOURS**, lorsque disponible, l'intégrité du fichier téléchargé. Cela se fait via une vérification de la "signature" ou de "la somme de contrôle" dudit fichier.
  
**Voir l'article sur le [chiffrement, l'intégrité et les signatures](/intermediaire/chiffrement).**
**Ainsi que le tutoriel [dédié](/tutoriels/verifier-integrite).**

## Sur les antivirus et antimalware

Concernant l'utilisation d'un anti-virus ou anti-malware, même si certains malwares modernes aujourd'hui ne sont plus détectables facilement, il est toujours possible de détecter des malwares connus et moins sophistiqués, ce qui est déjà une bonne chose (soyons pragmatiques). Dites-vous bien qu'un anti-virus ne vous protégera pas des agences à 3 lettres bien connues !

La bonne (première) pratique est si possible de télécharger des fichiers sur un environnement isolé, comme une machine virtuelle Linux (pour plus de facilité) par exemple, via VirtualBox ou VMWare. Cela s'accompagne également d'une utilisation particulière, qui ne risque pas de mettre à mal votre modèle de menaces :

-   N'utilisez pas de solutions commerciales, type Norton, BitDefender, Kaspersky... qui implémentent de toute manière une télémétrie vers leurs entreprises ainsi que des sociétés tierces.
-   **_Si vous avez un modèle de menaces nécessitant une sécurité et un anonymat accru :_** n'utilisez pas les fonctions de protection en temps réel de ces outils ; au delà même de la question de l'utilité réelle de ce genre de fonctions, celles-ci sont exécutées avec des privilèges hauts et, de facto, peuvent être utilisées comme un vecteur d'attaque.
-   Préférez les solutions open-source et hors ligne, afin d'utiliser ces outils comme prévus à l'origine : scanner régulièrement les fichiers de votre système, ou que vous voudriez scanner en cas de doute sur une potentielle infection. Nous avons rédigé un [tutoriel](/tutoriels/distro-protect) afin de vous guider dans ces tâches. Pour synthétiser, nous recommandons :
    -   pour la détection de logiciels malveillants (malwares) :
	    - [ClamAV](https://www.clamav.net/) et [ClamTk](https://gitlab.com/dave_m/clamtk/) son interface graphique,
    	- [RFXN Linux Malware](http://www.rfxn.com/projects/linux-malware-detect/) (Linux uniquement),
  		- [Hypatia](https://gitlab.com/divested-mobile/hypatia) (Android uniquement),
    -   pour la détection de rootkits (cf. [ici](/hygiene-numerique#malware-virus-trojan)) : [Chkrootkit](http://www.chkrootkit.org/) ou [RkHunter](https://rkhunter.sourceforge.net/) (Linux uniquement). 
-   Si vous ne souhaitez pas installer un outil sur votre ordinateur, vous pouvez potentiellement vous aider de solutions web. Attention ici cependant de ne pas mettre des fichiers contenant des informations personnelles (les vôtres ou ceux d'autres personnes) ou sensibles sur ces sites internet :
    -   [VirusTotal](https://www.virustotal.com/gui/home/upload) (petite mise en garde sur cet outil : leur politique de vie privée est assez problématique cependant car ils stipulent que "tout fichier que vous leur soumettrez seront gardés, partagés voire utilisés à des fins commerciales". Voilà pourquoi il est important de ne pas transmettre de fichiers potentiellement sensibles.)
    -   [Hybrid analysis](https://hybrid-analysis.com/)
-   D'autres outils sont disponibles sur ce dépôt, pleins de ressources fabuleuses concernant les malwares : [awesome-malware-analysis](https://github.com/rshipp/awesome-malware-analysis).

> **Attention de bien garder en tête cependant que ces outils ne sont pas la panacée, et ne pourront pas détecter 100% des malwares existants ou futurs. Il est donc important de mettre en place les bonnes pratiques et de bien faire attention aux autres parties de cet article.**
{.is-warning}

## Les WiFi publics

> Bannissez tous les WiFi publics (hormis certains cas bien précis).
{.is-info}

Les gares, aéroports, cafés, hôtels, restaurants... qui proposent des Wifi partagés sont aussi des lieux idéaux pour tous cybercriminels afin de s’introduire sur votre machine. ÉVITEZ absolument ces WiFi. Voici quelques alternatives :

-   Vous avez sûrement tous un téléphone portable dernier cri Android (ou Apple... Quoi ?!! Vous avez encore un produit Apple ?!! ;-)). Utilisez donc leurs fonctions de « point d’accès sans-fil » avec votre téléphone en 4G/5G afin d’éviter de vous connecter sur les WiFi publics.
-   Si vous voulez tout de même vous connecter sur des WiFi publics pour des problématiques d'anonymat, l’utilisation d’un VPN dans ce cas précis est ABSOLUMENT NÉCESSAIRE.

## Annexe

Pour terminer sur cette partie déjà bien fournie, il existe quelques sites pour savoir si une adresse courriel ou un nom d’utilisateur a déjà fait l’objet de fuite : visitez ce site [<https://haveibeenpwned.com/>](https://haveibeenpwned.com/). Néanmoins, il ne regroupe que les attaques majeures, et, à ce titre, ne doit pas être vu comme le site de référence ultime des fuites en ligne...

# Limiter le pistage

Cette nouvelle partie, non moins importante, vous permettra à terme d'adopter de nouvelles habitudes pour laisser le moins de traces possibles sur internet. Ce, afin de renforcer votre vie privée et si nécessaire votre anonymat.

> Même si nous devons bien vous avertir de nouveau qu'il est extrêmement difficile d'y arriver **totalement**, sauf à accepter de faire des compromis très importants dans votre vie de tous les jours !
{.is-info}

## L’importance des données personnelles

Naviguer sur Internet constitue le réel trésor pour quiconque souhaite voir ce que vous faites dans l’espace numérique. Les sites internet suivent (pratiquement tous) votre activité via des mécanismes de télémétrie et de traçage, parfois à des fins marketing : centres d'intérêt, lieux où vous passez votre temps, relationnel, travail, données démographiques, données géographiques, etc.

Ces données constituent même parfois le cœur de métier de certaines entreprises : par exemple pour Google, et certains publicistes...

Comme vous le voyez, ce trésor, pour les entreprises, l’est également pour tout pirate informatique ou [troll](https://fr.wikipedia.org/wiki/Troll_(Internet)) souhaitant nuire ; en effet, il est a priori simple, pour un pirate ou même un simple "troll" légèrement compétent, de recueillir des données sensibles en surveillant la navigation d’une personne.

> Nous vous laissons imaginer maintenant le potentiel des entités avec des ressources illimitées !
{.is-danger}

L'idée est donc de limiter autant que possible l'exposition de vos données personnelles et de vos [métadonnées](/hygiene-numerique#les-m%C3%A9tadonn%C3%A9es-quest-ce-que-cest), en adoptant des pratiques qui renforcent votre vie privée.

## Une histoire de cookies

Les cookies sont des fichiers numériques stockés en local sur votre appareil [(exemple pour Windows ici)](https://www.malekal.com/ou-sont-stockes-les-cookies-dans-windows-10-11-pour-tous-les-navigateurs-internet/), et permettent de stocker une ou plusieurs de vos activités, quel que soit le type de terminal utilisé (ordinateur, téléphone...). Il peut s’agir par exemple d’activités liées à la consultation d’un site internet (état de la connexion, préférences utilisateurs...), de la lecture d’un courriel ou encore de l’installation d’une application mobile sur votre téléphone ou console de jeux vidéos. Les cookies ont cependant été popularisés par les navigateurs internet, et voici pourquoi :

- Même si une grande partie des cookies sont nécessaires au bon fonctionnement de certaines applications ou sites internet, ces cookies sont devenus avec le temps un moyen de collecter également des informations essentielles sur vous. Quoi de mieux qu'un navigateur internet sur lequel nous passons la plupart de notre temps quotidien ?! Utilisés par des entreprises marketing peu scrupuleuses, celles-ci vont jusqu’à dresser des profils personnels suivant vos informations et vos habitudes, profils vendus par la suite à d’autres entreprises à des fins de publicités ciblées, voire pire...

- Ces données, accumulées d’année en année, peuvent constituer une mine d’informations sur votre personne et par conséquent des pans entiers de votre vie privée ; ceci parfois sans votre consentement, ou non porté à votre connaissance. Il n’est donc pas impossible non plus que ces données tombent entre de mauvaises mains, comme nous l’entendons régulièrement, chez LinkedIn par exemple [^¹1] ou encore Microsoft [^¹2]...

[^¹1]: [LinkedIn](https://www.breakflip-awe.com/internet/actualites/fuite-donnees-linkedin-de-quoi-s-agit-il-et-qui-est-concerne-5473) fuite de données.
[^¹2]: [Microsoft](https://www.frandroid.com/marques/microsoft/1273327_lapsus-microsoft-confirme-la-fuite-massive-de-donnees) qui confirme la fuite massive de données.

Enfin, si nous allons encore plus loin, il n'est pas impossible non plus que des agences de renseignement fassent du profilage grâce à ces données, surtout depuis les lois qui donnent pleins mandats à ces agences, et votées depuis quelques années sur fond de terrorisme. Toutes ces pratiques forment ce que l'on appelle le Capitalisme de surveillance [^³] que Shoshana Zuboff décrit dans son ouvrage [^⁴].

[^³]: [Capitalisme de surveillance](https://www.monde-diplomatique.fr/2019/01/ZUBOFF/59443)
[^⁴]: [Shoshana Zuboff](https://www.zulma.fr/livre/lage-du-capitalisme-de-surveillance/)

---
**Afin de pallier ce traçage systématique, et suivant les compétences de chacun, certains mécanismes peuvent vous permettre, plus ou moins facilement, de contrer ces problèmes d’anonymat et de protection de votre vie privée.**

## Les mécanismes expliqués !

Seront dans un premier temps présentés les outils orientés vie privée et/ou anonymat que sont le VPN ainsi que le réseau Tor, avant de poursuivre sur les outils utiles pour réaliser des communications privées (PGP), lutter contre la censure (les DNS et leur rôle), ainsi que la sécurité de l'information.

### VPN et Tor
Nous avons dédié un article spécifique sur ces 2 mécanismes [ici](/debutant/vpn-tor).

### DNS
Nous avons dédié un article spécifique sur ce mécanisme [ici](/debutant/dns).

### Proxy
Nous donnons une définition dans le [glossaire](/glossaire#proxy).

### PGP / OpenPGP / G(nu)PG
Nous avons dédié une partie spécifique dans l'article sur [le chiffrement](/intermediaire/chiffrement). Nous vous invitons donc fortement à la lire.

## Protégez votre vie privée

### Le navigateur

Utilisez un navigateur internet permettant de respecter votre vie privée. Celui-ci limitera fortement votre exposition sur internet ainsi que la collecte d'informations vous concernant.

Nous vous renvoyons vers l'article sur les [Navigateurs Web](/debutant/navigateurs), qui vous guidera dans le choix, afin de bien paramétrer votre navigateur et y adjoindre facultativement des extensions afin de renforcer le modèle de sécurité.

### Les moteurs de recherche

Sur ce navigateur, et afin d'éviter d'être *tracé* par des parties tierces, évitez l'utilisation de moteurs de recherche trop curieux, ou trop lâches dans leur gestion des données et métadonnées. 

Pour cela, voir l'article sur [les moteurs de recherche](/debutant/moteurs-recherche), afin de changer pour un moteur respectueux de votre vie privée.

### Les applications de courriels

Veuillez lire l'article dédié aux [courriels](/debutant/communications#courriel) respectueux de vos données qui est tout à fait complet et ne mérite pas d'être paraphrasé :).

### Les applications de messageries

Veuillez lire l'article dédié aux [messageries](/debutant/communications#messagerie) respectueuses de vos données qui est tout à fait complet et ne mérite pas d'être paraphrasé :).

### Les réseaux sociaux

Configurez toujours vos réseaux sociaux afin d'améliorer votre vie privée en dé-sélectionnant les paramètres d'envoi automatique de données vers les serveurs de ces entreprises : ces paramètres peuvent généralement se trouver dans "Confidentialité et Sécurité" ou "Vie privée et Confidentialité" etc.

Faites un tour sur **tous les paramètres** de tous vos réseaux sociaux et vérifiez qu'aucune donnée, même des données de "diagnostic" n'est transmise. Ne minimisez rien, y compris sur des réseaux qui, a priori, respectent votre vie privée.

## Adoptez un modèle de sécurité renforcé

### Premier niveau : les DNS

Si vous n'utilisez pas de service VPN via des mandataires (cf. ci-après), qui vous permettent de pointer vers leurs serveurs DNS, alors il peut être important de configurer spécifiquement les DNS vers lesquels pointer afin de limiter le pistage...

Référez-vous à notre article [dédié](/debutant/dns).

### Second niveau : le VPN

Bien que choisir un navigateur optimisé et renforcé d’extensions, il existe toujours un risque qu’une personne malveillante puisse avoir accès à votre activité numérique et à votre position géographique, en observant les données en transit sur le réseau internet. La probabilité est faible certes, mais le risque est non nul...

Référez-vous à notre article [dédié](/debutant/vpn-tor).

### Niveau subsidiaire...

...mais néanmoins crucial : les métadonnées !

Veillez à supprimer toutes les **[métadonnées](/hygiene-numerique#les-m%C3%A9tadonn%C3%A9es-quest-ce-que-cest)** liées aux ressources (images, vidéos, documents) que vous partagez en ligne, que cela soit via courriel ou sur vos réseaux sociaux. Par exemple, pour les images, vous pouvez supprimer les données EXIF avant de les partager partout. Pour les documents, vérifiez que vos nom/prénom, ou même initiales et autres, ne soient pas inscrits dans les propriétés du document, etc. Voici quelques outils afin de supprimer les métadonnées de fichiers PDF, documents, vidéos (tous les outils suivants ne traitent pas les vidéos...), photos :
- [Exifcleaner](https://exifcleaner.com/) (Fonctionne aussi sur les documents Microsoft Office !) qui implémente la librairie [ExifTool](https://exiftool.org/) et offre une interface graphique
- [PDFparanoia](https://pypi.org/project/pdfparanoia/) outil complet pour le nettoyage des fichiers PDF
- [Metadatacleaner](https://metadatacleaner.romainvigier.fr/) le nettoyeur de Métadonnées niveau débutant, avec interface graphique, par Romain Vigier
- [Mat2](https://0xacab.org/jvoisin/mat2) (**M**etadata **A**nonymisation Tool v **2** - Outil d'anonymisation de Métadonnées version 2) nettoyeur de métadonnées niveau intermédiaire ou avancé
:arrow_right: Attention c'est un outil qui nécessite quelques connaissances ; à lancer dans une machine virtuelle par exemple pour plus d'anonymat.

## L'anonymat

### Le cas Tor Browser

Le sujet autour de Tor Browser est assez complexe et débattu dans la communauté et dépend grandement de votre modèle :
1. **Si votre niveau de menaces ne va pas plus loin que quelques multinationales _pompes à données_ ou des recherches sensibles**, alors vous pouvez utiliser le navigateur Tor (Tor Browser, capable d'atteindre le réseau Tor) dans votre environnement pour des recherches et ceci afin de renforcer votre vie privée.

Référez-vous dans ce cas à notre article [dédié](/debutant/vpn-tor).

2. **Si en revanche votre modèle impose un anonymat important** et que votre niveau de menaces concerne des "agences étatiques" ou des groupes à fortes ressources, il est nécessaire d'éviter son utilisation dans le contexte 1, et passer sur un modèle bien plus robuste.

### Anonymat avancé

Obtenir un niveau plus avancé d'anonymat n'est pas chose aisée...

**Néanmoins, de premières pistes peuvent être envisagées avec une utilisation assez _classique_. Ici encore, il s'agit d'un second niveau d'anonymat, celui-ci ne sera donc pas total.**

#### Whonix

[Whonix](https://www.whonix.org/) / [Qubes OS](https://www.qubes-os.org/) : L'utilisation de Qubes (avec Whonix pré-installé d'origine dans une machine virtuelle) ou d'un système d'exploitation Linux _[durci](/glossaire#durcissement)_ via la solution _Whonix_ permet un niveau de sécurité et un anonymat renforcés.

Sous Qubes OS (dans la Machine Virtuelle Whonix-WS) ou plus généralement sous Whonix, les requêtes [DNS](#dns) passent par Tor. Cela assure donc une anonymisation globale des requêtes. Attention en revanche si vous ne passez pas par ces outils, de bien configurer des adresses de serveurs DNS respectueux et d'assurer une protection des requêtes (que ce soit DoH, DoT, DNSCrypt ou DNSSEC...) :

- soit sur votre routeur FAI (bien vérifier également que ce routeur applique convenablement l'utilisation de ces IP, cf. DNS leak)
- soit sur votre propre serveur DNS :arrow_right: attention ici encore de bien comprendre ce mécanisme : implémenter une solution de type *PiHole* par exemple déporte uniquement le serveur résolveur chez vous, mais les requêtes vers les serveurs récursifs auront toujours lieu sur internet. Donc si vous ne protégez pas ces requêtes ou si vous ne cachez pas votre IP, il sera possible de vous désanonymiser !

#### Tails

[Tails OS](https://tails.boum.org/) : la version ultime de l’anonymat, au-delà de votre navigateur internet, est l’utilisation de Tails OS.

Installé sur une clé USB et lancé depuis un appareil hôte - ordinateur portable ou PC x86 en 64 bits, quel que soit le système d'exploitation, le SE (Système d'Exploitation) hôte étant ignoré -, ce système d’exploitation est un système défini comme « amnésique ». C’est-à-dire qu’aucune donnée (hormis celle que vous souhaitez) ne persiste à l’extinction du système, ni en mémoire "RAM", ni sur disque dur/SDD (les clés USB fonctionnant sur la mémoire RAM "non persistante", l'avantage de ce système se situe là, vous l'aurez compris).

Ce système vous permet ainsi de créer un cocon numérique, peu importe le matériel que vous utilisez ; nul besoin d’utiliser votre ordinateur personnel. Par exemple très utile si vous vous connectez dans des lieux publics. Attention toutefois à bien comprendre les bases de l’outil. Réservé tout de même aux personnes à l’aise avec les aspects cyber et l’informatique en général.

*_Pour l’exemple_ : Tails ne s’utilise jamais en machine virtuelle. Si vous êtes intéressés par les machines virtuelles, veuillez utiliser plutôt Whonix !*

> Attention ici de bien maîtriser les outils informatiques en général, principalement GNU/Linux/BSD et les aspects durcissement.
{.is-warning}


### Anonymat total

Pour finir, si votre modèle impose un **anonymat total**, vous allez devoir adopter des pratiques spécifiques qui seront probablement des contraintes dans votre vie de tous les jours :
- vous devrez utiliser un matériel totalement anonyme : paiement cash de tous les matériels (ou par crypto monnaies _anonymes_)
- connexion et utilisation des matériels hors de chez vous, loin, dans des endroits publics, entourés de beaucoup de personnes
- aucun compte permettant de vous identifier
- utilisation totale du pseudonymat
- vos téléphones/tablettes... restent à la maison (aucun téléphone sur vous)
- assez contre-intuitif : évitez l'utilisation de clés de sécurité type signature pouvant vous identifier (*souvenez-vous du diagramme des 3 cercles évoqué plus haut : faire des compromis* !). Souvenez-vous de n'utiliser que du pseudonymat, y compris pour des signatures électroniques.

Vous arrivez à un usage très compliqué au quotidien !

Ce modèle de menaces extrême est d'ailleurs plutôt dédié aux militants,  activistes, opposants politiques, journalistes d'investigation... Vous l'aurez compris, probablement inadapté pour la majorité des personnes. Nous nous devions néanmoins d'envisager toutes les possibilités, face à notre audience. Mais ce modèle nécessite une réflexion profonde et une structure d'utilisation sur mesure... et sort donc du cadre de notre wiki !

# Aller plus loin

Cette partie est dédiée à toute personne souhaitant aller plus loin dans la sécurisation de ses données, de ses communications, et son anonymat. Elle représente un aperçu des possibilités associées aux « bonnes pratiques ».

> Nous faisons ici état d’outils qui sont actuellement parfois en phase de recherche ou de tests. Il convient en priorité d’être à l’aise avec l’outil informatique en général, sur les aspects réseau, intrusion, vulnérabilités. Encore une fois, utiliser des outils que l’on ne maîtrise pas engendre une augmentation de sa surface d'attaque et donc potentiellement une diminution dans son niveau de sécurité ! Lisez les documentations...
{.is-danger}

## Stockage de données et "clouds" sécurisés

La difficulté aujourd'hui dans le fait de stocker toutes sortes de fichiers ou programmes, que ce soient nos photos de mariage ou d'anniversaire, nos documents de compte, etc. réside dans les capacités dudit **stockage**. Il s'agit d'une problématique très sérieuse, et qui peut s'avérer extrêmement coûteuse (notamment pour les entreprises). À titre personnel, vous estimez que dépenser des centaines d'euros dans un disque dur de 8 To (Téraoctet, qui correspond à 1 024 Gigaoctets) voire dans une solution NAS ("Network Attached System"), difficile à configurer n'est pas à l'ordre du jour. Vous souhaitez donc peut-être faire appel à un tiers afin de pouvoir stocker vos fichiers personnels, en toute sécurité.

Pour être honnête avec vous, nous ne recommandons sérieusement pas cette solution. En effet, faire appel à un tiers pour ce service revient à peu de choses près aux problématiques des VPNs actuels : assez peu en qui donner une confiance relative, après avoir fait sa petite étude sérieuse du sujet. 

Dans la plupart des cas, on se retrouve avec une entreprise, qu'on ne ne connaît pas entièrement, dont on ignore les méthodes, et sur lesquelles on n'a pas le contrôle en pratique : centralisation des données, gestion des serveurs de stockage... On n'en sait rien, on n'est pas en situation de contrôle ! 

Les 2 solutions pertinentes, et viables en terme de vie privée sont :
1.  L'utilisation de plusieurs disques durs externes de bonne capacité : aujourd'hui le coût de ces disques a fortement chuté, et il est tout à fait possible de se procurer des disques à des prix intéressants. Voir large, penser long terme : une capacité d'un minimum de 2 To est à envisager, avoir 2 disques est le minimum. Maintenant, nous sommes d'accord, cela implique que vous y pensiez de façon récurrente (tous les mois par exemple), et que vous vous souveniez des manipulations à faire ; oui on sait c'est embêtant, qui plus est vous êtes tributaire d'une possible panne d'un de vos disques (d'où l'idée d'en avoir plusieurs pour éviter des pertes de données) !
2.  Il existe une autre manière, qui requiert là encore de mettre "les mains dans le cambouis" et à un certain coût : les NAS. Ces petites et plus grosses bêtes, connectées sur notre réseau privé (en local donc), permettent de stocker d'importantes quantités de données et d'assurer une haute disponibilité dans le cas où les disques tombent en panne (nous vous renvoyons au principe des disques montés en [RAID](https://fr.wikipedia.org/wiki/RAID_(informatique)) par exemple). Cela dit, là encore vous devrez configurer correctement cet équipement en termes de sécurité et de durcissement, afin qu'on ne s'y introduise pas. D'un autre côté, il est tout à fait possible [d'automatiser les sauvegardes](/debutant/sauvegarde) !

C'est à vous de décider quelle peut être la façon de faire, suivant vos besoins et votre modèle de menaces.

Si toutefois vous décidiez de faire confiance à certains tiers, il existe des bonnes pratiques à respecter scrupuleusement :
-   Adieu les Google Drive, Microsoft OneDrive, Apple iCloud et autres "drives" ou "clouds" comme Dropbox. Ou en lien avec les GAFAM et BATX (Xiaomi etc.), dont on ne sait rien puisque propriétaire, et surtout ayant fait l'objet ces dernières années d'attaques et de vols de données. Sans parler des solutions faisant l'objet d'une surveillance massive...
-   Chiffrer avec un logiciel libre comme [Cryptomator](https://cryptomator.org/) systématiquement ses documents ou répertoires avant de les transférer sur un cloud public, qui ne propose pas de protection particulière mais pourrait être de confiance. Le contenu de nos données est ainsi protégé, qui plus est nous serons seul propriétaire de nos clés de sécurité et ne serons pas tributaire d'une entité tierce. Pour des entités de confiance, nous recommandons :
    -   Pour des documents et de la collaboration en ligne : [Cryptpad](https://cryptpad.fr/)
    -   Pour de petits documents, photos... (max 100Mo gratuit) : [Crypt.ee](https://crypt.ee)
    -   Pour une solution tout-en-un : 
	    - [Nextcloud](https://nextcloud.com/fr/)
	    - [Ksuite](https://www.infomaniak.com/fr/ksuite) de Infomaniak : copié-collé des solutions propriétaires existantes, avec **des petits plus** (à l'heure où cet article est écrit, en offre gratuite de base [légende : cette solution est rendue possible de par leur offre payante auprès des entreprises en parallèle : un modèle économique solide évite les dérives en termes de monétisation des données] : 15 go de stockage, mail, **vidéo-conférence** (basée sur [Jisti Meet](/debutant/video-conf)), **messagerie instantanée** (prochainement))... Le tout, hébergé en Suisse, et fourni avec des applications sous licence libre, et de bonnes pratiques en termes de vie privée. Le bémol : à la différence de Nextcloud, nécessite de lier un numéro de téléphone pour des raisons avancées de sécurité (double authentification), plutôt que d'utiliser la technologie [OTP](/glossaire#otp) (à chacun d'anticiper l'évolution éventuelle de leur politique de gestion des données).
  
    -   Pour un stockage de sauvegardes et autres fichiers lourds : [Filen.io](https://filen.io/)
-   Une autre solution, qui comporte, cela dit, un certain coût financier ou en temps, ainsi que de solides connaissances, serait de soi-même héberger une solution Nextcloud :
    -   Sur un NAS personnel chez vous,
    -   Sur un VPS (Virtual Private Server). Fournisseurs de confiance recommandables, en tout cas traitant a priori vos données avec respect :
        -   [Njal.la](https://njal.la/servers/)
        -   [1984.is](https://1984.hosting/product/vps/)
        -   [Privex.io](https://www.privex.io/)
-   Si malgré tout, vous persistez à vouloir utiliser vos clouds Google, Microsoft, etc... et à ne pas vouloir générer et gérer vos clés de sécurité, une dernière alternative est possible, bien que moins pertinente : utiliser [Cryptomator](https://cryptomator.org/) afin de protéger vos données stockées sur ces clouds.
 
*Évidemment, vous l'aurez bien compris, nous vous recommandons les solutions autres que celles propriétaires, ne serait-ce qu'en terme de sécurité offerte par les communs libres (un code source ouvert permet des correctifs plus rapides), d'éthique et de modèle de société : rester sur un statu quo ne change pas le paradigme actuel d'une société fondée sur le capitalisme de surveillance. Quoi qu'il en soit, le choix final vous revient, notre rôle est avant tout pédagogique et non coercitif.*

## DVPN - Decentralized VPN

Pour ceux qui souhaitent utiliser pleinement les capacités du web 3.0 (nous ne rentrons pas dans les détails du web3 dans cet article), l’utilisation d’un « decentralized VPN » (VPN décentralisé ou dVPN) peut être envisagé. En somme, il s’agit d’utiliser la [blockchain](/glossaire#blockchain) afin de fournir un service VPN, dans lequel vous êtes partie prenante ; en effet, l'accès aux réseaux décentralisés de ces outils nécessitera une contrepartie :
- soit moyennant des micro-paiements en cryptomonnaie, 
- soit en hébergeant des serveurs.

**<span class="red-text">Néanmoins, ce mécanisme en est encore à ses balbutiements et nous n’avons pas assez de recul. Qui plus est, vous devrez comprendre le fonctionnement des cryptomonnaies et les risques inhérents.</span>**

Si vous êtes tout de même intéressé(e), voici quelques réseaux dont les communautés sont actives :
-   Sentinel : réseau de DVPN et son client Velocity VPN. Basé sur le [token](/glossaire#token) COSMOS.
-   Nym : Nym est une application basée sur un mixnet. Basé sur le token NYM.
-   Mysterium : et son client Mysterium VPN, le plus connu. Basé sur le token MYST, même s'ils acceptent d'autres tokens comme BTC, ETH, LTC.
-   Deeper DPN : Solutions hardware proposées à la vente pour la participation au réseau (attention plutôt onéreuses !) et afin d'accéder à leur réseau. Basé sur le token DPR.
-   Orchid : réseau de routage en oignon, et client VPN multi bonds. Basé sur le token OXT.

## I2P - L'autre Tor

Afin de bien comprendre en quoi I2P peut nous être utile, intéressons-nous tout d'abord aux applications d'internet et donc principalement aux _WEBs_.

Oui vous avez bien lu, j'ai ajouté un "s" à Web (nous vous renvoyons ici au [glossaire](/glossaire#web) pour la terminologie).

Pour rappel la différence entre internet et le Web :
-   Comme nous l'avons déjà défini, internet est un réseau (de réseaux)
-   Le Web, quant à lui, est l'outil d'inter-connexion des sites internet

Concernant le Web, il en existe donc plusieurs :
- Web visible (aussi appelé Web surfacique) : correspond à tout ce qui est indexé par les moteurs de recherche, et donc *_recherchable_* et accessible sur n'importe quel moteur de recherche. Par exemple : wikipedia.com ou encore orange.fr etc.
- Web invisible : représente toute la part des sites et pages internet qui ne sera jamais indexée par les moteurs de recherche et donc inaccessible publiquement.

Voici comment nous représentons généralement le Web :

![Le web profond](/images/deepweb.png =600x){.align-center}

Vous vous apercevez ici que le "Web visible" que vous connaissez bien ne représente qu'une petite partie du réseau mondial, c'est-à-dire entre 4 et 5% : "c'est le côté visible de l'iceberg" !

Nous y venons donc, le "Web invisible" est, quant à lui, également découpé en plusieurs parties. Il est communément admis de représenter ces parties ainsi :
- Le Web profond (Deep Web en anglais) : est une partie du Web invisible, pour ne pas dire une très grande partie (90%) qui gère tous les contenus non indexables de tous les sites internet : il peut s'agir par exemple de votre page d'accès à votre mandataire de courriel comme Gmail ou ProtonMail (imaginez que l'on puisse tous accéder à cette page et voir vos courriels !), ou bien des pages spécifiques liées à votre banque en ligne. Ou bien des contenus éducatifs d'universités qu'il ne faut pas rendre public forcément... Toutes ces pages ou sites ne seront jamais indexés et donc non *recherchables et non accessibles*. Ce qui se comprend...
- Les dark Webs (pas forcément de traduction française !) : ils contiennent toute la part cachée d'internet (environ 5-6%), également bien entendu non indexée par des moteurs de recherche habituels ; il y a du bon et du moins bon. 
  Le bon côté de ces dark Webs est le fait que certaines personnes puissent avoir la capacité de contourner les censures mises en place dans des pays autoritaires et donner un peu de liberté, et surtout d'anonymat. 
  De l'autre côté, le plus sombre, certaines zones des dark Webs sont en effet liées à la cyber-criminalité, où l'on peut retrouver des sites marchands illégaux et d'autres choses peu reluisantes.
  >"Tirer sur l'ambulance", en ne mettant en avant que l'aspect sombre du darkweb serait néanmoins contre-productif : ce serait omettre le rôle essentiel que les outils qui y sont liés (les "darknets", détaillés plus bas) jouent dans la société, étant donné que de nombreux journalistes et lanceurs d'alerte utilisent par exemple Tor. Notamment via l'outil Tails (voir : Devenez difficile à tracer/Parlons Technique/Anonymat avancé plus haut), ou via les messageries chiffrées. 
  Mettre un terme à ce genre de réseau signifierait un nouveau coup contre la liberté d'expression (ce serait par ailleurs difficile à réaliser, de par son aspect décentralisé). La décentralisation est l'amie des libertés publiques ; il faut donc savoir raison garder et ne pas réagir sur le coup de l'émotion. Par ailleurs, on n'est pas en mesure de savoir quelle part des "dark-markets" est réelle, et quelle part propose des services qui sont des arnaques plutôt que de véritables services criminels...
  Faire des dons, ou militer pour l'usage de Tor - ou tout autre darknet - reste un enjeu démocratique.
  
*Note : la terminologie dark Web peut varier de temps en temps, et il est parfois admis qu'il existe encore plus profond que le Dark Web !*

Mais quelle est la raison de tout ce blabla ?

Car afin d'accéder à ces dark Webs, il faut obligatoirement utiliser des services spécifiques, via des domaines de premiers niveaux spécifiques (allez relire la partie sur les DNS !) - non accessibles sur l'internet "classique" (la résolution DNS ne fonctionnera pas ici) - sur des réseaux spécifiques (vous vous souvenez, internet, réseau de réseaux...) appelés **DARKNETs**. Voici donc les services et réseaux les plus connus :
-   **Tor** : Eh oui, le plus connu de ces réseaux bien entendu, afin de surfer anonymement sur le web classique. Mais également accéder au darknet confidentiel Tor, avec des URL qui terminent en .onion (ce que l'on appelle des Top Level Domain - TLD)
-   **I2P** : tiens donc, le voilà ! Tout comme Tor, il permet de naviguer sur le web classique de façon anonyme. Mais il fournit également des services plus confidentiels de forum, courriel, etc sur le darknet I2P avec ses TLD en .i2p

> Bien entendu, ces deux darknets ont chacun leurs avantages et leurs inconvénients.
{.is-info}

D'autres darknets existent bien sûr. Ils ne sont pas forcément utilisés pour rendre la navigation anonyme sur l'internet classique, mais plus pour avoir accès à leur réseau, en dehors de l'espace surfacique du net. Parmi les plus connus, citons :
-   **Freenet**, l'un des plus robustes et plus recommandés des darknets.
-   **Lokinet, maintenant devenu Oxen** (sur lequel la messagerie décentralisée Session se base !)
-   **GNUnet**
-   **AnonNet**
-   **Riffle**

Et bien d'autres...

# The end... ?

Nous arrivons enfin à la fin de cet article, très dense... 
En espérant que vous n'avez pas trop mal à la tête !

### Ce qu'il faut retenir

La complexité des mécanismes en jeu, dans la protection de ses données, poussent la plupart des personnes à abandonner leur protection ou à donner mandat à un/des tiers afin d’assurer cette protection. 

***Ceci doit être aujourd'hui reconsidéré...***

S'il ne devait y rester qu'un leitmotiv à se remémorer tous les matins en se brossant les dents :

-   Chiffrement de bout en bout (E2EE) partout,
-   Aucune confiance à aucun service extérieur,
-   Pseudonymat au maximum,
-   Contrôle perpétuel de ses données,
-   Mise à jour régulière de votre modèle de menaces.
  
En tout cas, bravo ! Nous avons passé le plus dur, en faisant un tour d'horizon qui se veut le plus exhaustif, tout en étant le plus vulgarisé possible. Nous sommes conscients que cette débauche d'informations nouvelles ne peut pas être retenue et assimilée en une seule fois. C'est pourquoi, nous vous invitons à passer du _pourquoi_ au _comment_ en vous rendant sur toutes les autres pages du wiki... Vous allez le voir, en faisant les choses, on passe rapidement d'un aspect théorique qui peut paraître complexe, à des nouvelles habitudes qui deviennent des automatismes, ancrées dans notre quotidien.

> **Il est essentiel aujourd'hui de reprendre la main sur son espace numérique et sur la manière dont nous utilisons les outils numériques mis à notre disposition.**
{.is-warning}

A ce titre, il est important de garder en tête qu'aucun mécanisme ni aucune technologie ne nous assurera une sécurité optimale de l'information, tout en assurant une vie privée et un anonymat à 100%. Ces aspects dépendent aussi, avant tout, de nous-mêmes et de l'hygiène numérique que nous adoptons.

Pour conclure, nous avons en début d'article mentionné que la protection de notre sphère numérique était un voyage et non une destination ; si tout ce que vous avez fait jusqu'alors ne correspond pas aux précédentes sections, ne vous blâmez pas !

L'important est d'y aller par étapes successives, et de choisir les outils et mécanismes qui correspondent le plus à vos besoins. Vous ferrez des erreurs, tant mieux, mais vous apprendrez surtout à maîtriser votre espace numérique, tout comme maîtriser sa voiture ou son vélo est essentiel afin d'utiliser le réseau routier (et ne s'apprend pas du jour au lendemain) !

Enfin, nous terminerons par la fameuse maxime à ne jamais oublier :

> **"Si c'est gratuit (en tout cas pour les logiciels propriétaires), il y a de fortes chances que vous soyez le produit !"** (Citation bien connue)

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo*
<br>