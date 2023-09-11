---
title: Limiter le pistage en ligne
description: Cet article vous présente toutes les solutions afin de limiter au mieux la traçage de vos données...
published: true
date: 2023-04-20T15:33:39.614Z
tags: tracking, hygiene, pistage, traçage, tracage
editor: markdown
dateCreated: 2023-02-11T14:56:08.272Z
---

Cette seconde partie, non moins importante, vous permettra à terme d'adopter de nouvelles habitudes pour laisser le moins de traces possibles sur internet. Ce, afin de renforcer votre vie privée et si nécessaire votre anonymat.

> Même si nous devons bien vous avertir de nouveau qu'il est extrêmement difficile d'y arriver **totalement**, sauf à accepter de faire des compromis très importants dans votre vie de tous les jours !
{.is-info}

# L’importance des données personnelles

Naviguer sur Internet constitue le réel trésor pour quiconque souhaite voir ce que vous faites dans l’espace numérique. Les sites internet suivent (pratiquement tous) votre activité via des mécanismes de télémétrie et de traçage, parfois à des fins marketing : centres d'intérêt, lieux où vous passez votre temps, relationnel, travail, données démographiques, données géographiques, etc.

Ces données constituent même parfois le cœur de métier de certaines entreprises : par exemple pour Google, et certains publicistes...

Comme vous le voyez, ce trésor pour les entreprises, l’est également pour tout pirate informatique ou [troll](https://fr.wikipedia.org/wiki/Troll_(Internet)) souhaitant nuire ; en effet, il est a priori simple, pour un pirate ou même un simple "troll" légèrement compétent, de recueillir des données sensibles en surveillant la navigation d’une personne.

> Nous vous laissons imaginer maintenant le potentiel des entités avec des ressources illimitées !
{.is-danger}

L'idée est donc de limiter autant que possible l'exposition de vos données personnelles et de vos [métadonnées](/hygiene-numerique#les-m%C3%A9tadonn%C3%A9es-quest-ce-que-cest), en adoptant des pratiques qui renforcent votre vie privée.

# Une histoire de cookies

Les cookies sont des fichiers numériques stockés en local sur votre appareil [(exemple pour Windows ici)](https://www.malekal.com/ou-sont-stockes-les-cookies-dans-windows-10-11-pour-tous-les-navigateurs-internet/), et permettent de stocker une ou plusieurs de vos activités, quel que soit le type de terminal utilisé (ordinateur, téléphone...). Il peut s’agir par exemple d’activités liées à la consultation d’un site internet (état de la connexion, préférences utilisateurs...), de la lecture d’un courriel ou encore de l’installation d’une application mobile sur votre téléphone ou console de jeux vidéos. Les cookies ont cependant été popularisés par les navigateurs internet, et voici pourquoi :

- Même si une grande partie des cookies sont nécessaires au bon fonctionnement de certaines applications ou sites internet, ces cookies sont devenus avec le temps un moyen de collecter également des informations essentielles sur vous. Quoi de mieux qu'un navigateur internet sur lequel nous passons la plupart de notre temps quotidien ?! Utilisés par des entreprises marketing peu scrupuleuses, celles-ci vont jusqu’à dresser des profils personnels suivant vos informations et vos habitudes Profils vendus par la suite à d’autres entreprises à des fins de publicités ciblées, voire pire...

- Ces données accumulées d’année en année peuvent constituer une mine d’informations sur votre personne et par conséquent des pans entiers de votre vie privée ; ceci parfois sans votre consentement, ou non porté à votre connaissance. Il n’est donc pas impossible non plus que ces données tombent entre de mauvaises mains, comme nous l’entendons régulièrement, chez LinkedIn par exemple [^¹1] ou encore Microsoft [^¹2]...

[^¹1]: [LinkedIn](https://www.breakflip-awe.com/internet/actualites/fuite-donnees-linkedin-de-quoi-s-agit-il-et-qui-est-concerne-5473) fuite de données.
[^¹2]: [Microsoft](https://www.frandroid.com/marques/microsoft/1273327_lapsus-microsoft-confirme-la-fuite-massive-de-donnees) qui confirme la fuite massive de données.

Enfin, si nous allons encore plus loin, il n'est pas impossible non plus que des agences de renseignement fassent du profilage grâce à ces données, surtout depuis les lois qui donnent pleins mandats à ces agences, et votées depuis quelques années sur fond de terrorisme. Toutes ces pratiques forment ce que l'on appelle le Capitalisme de surveillance [^³] que Shoshana Zuboff décrit dans son ouvrage [^⁴].

[^³]: [Capitalisme de surveillance](https://www.monde-diplomatique.fr/2019/01/ZUBOFF/59443)
[^⁴]: [Shoshana Zuboff](https://www.zulma.fr/livre/lage-du-capitalisme-de-surveillance/)

---
**Afin de pallier ce traçage systématique, et suivant les compétences de chacun, certains mécanismes peuvent vous permettre, plus ou moins facilement, de contrer ces problèmes d’anonymat et de protection de votre vie privée.**

# Les mécanismes expliqués !

Seront dans un premier temps présentés les outils orientés vie privée et/ou anonymat que sont le VPN ainsi que le réseau Tor, avant de poursuivre sur les outils utiles pour réaliser des communications privées (PGP), lutter contre la censure (les DNS et leur rôle), ainsi que la sécurité de l'information.

## VPN et Tor

Nous avons dédié un article spécifique sur ces 2 mécanismes [ici](/debutant/vpn-tor).

## Proxy
Nous donnons une définition dans le [glossaire](/glossaire#proxy).

## PGP / OpenPGP / G(nu)PG

Nous avons dédié une partie spécifique dans l'article sur [le chiffrement](/intermediaire/chiffrement). Nous vous invitons donc fortement à la lire.

## DNS

DNS ou « système de noms de domaine » (Domain Name System chez nos amis anglais) est un mécanisme particulièrement intéressant pour les réseaux.

Nous allons le voir, le DNS, c'est un peu l'**annuaire inversé** des sites internet : quand on sélectionne une [URL](/glossaire#url), ou qu'on la tape dans une barre de recherche, le DNS se charge de la transcrire en adresse IP (exemple fictif : 127.126.12.22) pour contacter le site.

Rentrons dans les détails : nous allons nous intéresser plus particulièrement à l’utilisation sur le réseau internet, car son usage en est le parfait exemple. Lorsque nous naviguons sur internet, nous souhaitons visiter des sites internet. Pour y accéder, nous allons entrer un texte que nous appelons URL qui contient le nom du site. Mais comment savoir quel serveur contacter pour afficher le site en question ou autrement dit, comment retrouver l’adresse IP du serveur associée à ce nom du site ?

![Principes du DNS (Version simple)](/images/dns-1.png =600x){.align-center}

C’est ici qu’entre en jeu le DNS.

Le mécanisme en lui-même est assez simple : le DNS permet de traduire (on parle de « résolution ») des noms de sites, appelés noms de domaine, en adresses IP. Souvenez-vous lorsque nous parlions d’adresses IP : nous avons défini ces adresses avec des suites de chiffres (et maintenant de chiffres et de lettres pour IPV6 !) incompréhensibles ! Les noms de domaine vont donc être plus compréhensibles.
*Par exemple : google.com, wikilibriste.fr sont des noms de domaine. Bien plus mémorisables et utilisables au quotidien que 8.8.8.8 ou 132.54.23.109 (adresse IP fictive pour wikilibriste).*

Pour les petits malins : oui il est possible de procéder à l’inverse. C’est-à-dire résoudre une adresse IP vers un nom de domaine qui lui est associé ! Cela s’appelle une « résolution inverse » ou reverse DNS.

Alors comment retrouver l’adresse IP ? Prenons l’architecture même de 2 URLs :
**-- www.google.com**
**-- wiki.wikilibriste.fr** (URL fictive utilisée pour l'exemple, notre URL réelle étant wikilibriste.fr)
Nous allons la découper en plusieurs parties afin de bien comprendre la mécanique :
-   Nous avons les domaines de premier niveau ou TLD (Top Level Domain) : ce sera les .com, .fr, .org, .de (on parle alors ici de domaines géographiques) voire des domaines plus exotiques comme .io, .tech, .tartanpion etc.
-   Nous avons ensuite les domaines de second niveau : le nom du site ou nom de domaine en lui-même c’est-à-dire par exemple « google » ou « wikilibriste » dans notre cas.
-   Puis nous avons les sous-domaines : généralement nous voyons « www » devant les URLs (c’est très courant), ceci afin d’identifier les serveurs web, mais nous pourrions tout à fait avoir d’autres sous domaines : mail, forum, wiki par exemple ! Eh oui, dans l’URL wiki.wikilibriste.fr, le sous-domaine associé est "wiki" afin d'identifier un serveur spécifique pour wiki.

Vous l’aurez compris, le DNS est une part essentielle d’internet. Sans lui, vous en seriez à entrer des adresses IP dans votre navigateur internet toute la journée ! Pas cool quand même...

Pour plus d'explications, vous pouvez voir la vidéo de *"Paf LeGeek"* à ce sujet :
- [DNS](https://invidious.snopyta.org/watch?v=S1f4NB72lMQ) La surveillance de masse facile
{.links-list}

<span class="blue-text">**Alors pourquoi parlons-nous de DNS ?**</span>

Eh bien simplement car ce mécanisme bien que particulièrement utile n’est pas dénué de failles : il est tout à fait possible pour un attaquant de vous diriger vers une copie d’un site détourné afin de vous voler des informations personnelles. Des contre-mesures sont aujourd’hui mises en place mais elles ne couvrent pas tous les aspects de cette attaque. Sachant qu’aujourd’hui la majeure partie des échanges DNS est en clair (n’est pas chiffré), n’importe qui peut lire les requêtes DNS et ainsi réorienter une partie du trafic. Pour plus de détails vous pouvez faire vos recherches sur les concepts de "*DNS poisoning*" ou "*spoofing*".

-   Vous avez sûrement entendu en 2016/2017 le nom d’un type d’attaque bien particulière : DOS (Denial Of Service) ou attaque par « déni de service ». Oui c’est barbare ! Vous allez comprendre : cette attaque utilise des petits logiciels appelés _botnet_ (voir plus loin partie Malware), et qui pour certains d'entre eux, chargés sur une machine cible permet de lancer une multitude de requêtes (1 million en 1 seconde par exemple) afin de le ralentir drastiquement, voire le faire tomber et l’ "ouvrir" afin d’obtenir des droits d’accès administrateur. Il existe même une attaque DDoS ou Distributed Denial Of Service ; celle-ci au lieu d’utiliser une seule machine hôte cible, utilise un ensemble de machines hôtes qui ensemble lancent les requêtes en même temps... Vous imaginez aisément les dégâts. C’est ce qu’il s’est passé en 2017 avec l’attaque via un botnet nommé Mirai [^⁵] sur un mandataire de services DNS dynDNS par exemple : certains sites internet très connus (et surtout très utiles pour certaines sociétés) étaient tout simplement injoignables. Mais ce n’est pas la seule victime du botnet Mirai...
-   Sans oublier nos chers amis institutionnels et Fournisseurs d'Accès Internet qui, du fait de l'architecture même du DNS, peuvent tracer vos requêtes et retrouver votre IP, voire faire du profilage y compris dans certains cas où vous utilisez un VPN (cf. "DNS leakage")...

[^⁵]: [Botnet mirai](https://news.sophos.com/fr-fr/2017/01/20/botnet-mirai-origine-attaques-ddos/) : origine et attaques DDOS.

La sécurisation des requêtes DNS est aujourd'hui même en plein chantier ; en effet, les organes de standardisation et de contrôle d'internet mettent à jour les standards, mais cela prend du temps. Pendant ce temps, nos requêtes DNS sont la plupart du temps transmises sans protection (en clair). Et les serveurs DNS utilisés (souvent ceux de votre FAI ! Mais nous pouvons citer les plus utilisés comme ceux de Google ou de Cloudflare) n'ont aucunement l'intention de respecter votre vie privée.

_**Néanmoins**_, oui nous allons un peu vous rassurer après ce tableau noir :-), il est aujourd'hui possible d'apporter un peu de vie privée à ces requêtes et de confort, car des mandataires tiers aux objectifs louables ont créé des serveurs DNS respectant (a priori !) notre vie privée, ajoutant des listes noires d'IP publicitaires, et implémentant des mécanismes de sécurisation des échanges même si encore en cours de standardisation (cf. DNS over TLS ou DoT, DNS over HTTPS ou DoH, DNSCrypt, DNS over SSH etc. pour les intéressés).

Ainsi afin de contourner au maximum les faiblesses citées ci-dessus, il est de plus en plus recommandé d'ajuster notre utilisation des DNS :
(1) soit pointer directement vers des serveurs de mandataires tiers qui tiennent compte de notre *vie privée*, parmi lesquels des solutions dans l'esprit du libre [CoreDNS](https://coredns.io/), [SDNS](https://sdns.dev/), [Quad9](https://quad9.net/fr/). Côté instance à but lucratif, Mullvad DNS est à mentionner.
(2) soit héberger chez nous un serveur DNS de résolution capable de résoudre une partie des DNS (l'autre partie étant toujours traitée par des serveurs tiers), comme par exemple une solution PiHole (+ Unbound)

Pour les amateurs de tests et de performances, [DNSPerf](https://www.dnsperf.com/#!dns-resolvers) vous permettra de regarder les performances des différents serveurs DNS existants (libres et non libres), à titre indicatif bien entendu.

> Comme toujours en cyber-sécurité, ces 2 solutions ne sont pas parfaites, et sont donc à ajuster en fonction de notre modèle de menaces - élément que nous allons détailler à suivre.
{.is-warning}


# Protégez votre vie privée

## Le navigateur

Utiliser un navigateur internet permettant de respecter votre vie privée. Celui-ci limitera fortement votre exposition sur internet ainsi que la collecte d'informations vous concernant.

Nous vous renvoyons vers l'article sur les [Navigateurs Web](/debutant/navigateurs), qui vous guidera dans le choix, afin de bien paramétrer votre navigateur et y adjoindre facultativement des extensions afin de renforcer le modèle de sécurité.

## Les moteurs de recherche

Sur ce navigateur, et afin d'éviter d'être *tracé* par des parties tierces, évitez l'utilisation de moteurs de recherche trop curieux, ou trop lâches dans leur gestion des données et métadonnées. 

Pour cela voir l'article sur [les moteurs de recherche](/debutant/moteurs-recherche), afin de changer pour un moteur respectueux de votre vie privée.

## Les applications de courriels

Veuillez lire l'article dédié aux [courriel](/debutant/communications#courriel) respectueux de vos données qui est tout à fait complet et ne mérite pas d'être paraphrasé :).

## Les applications de messagerie

Veuillez lire l'article dédié aux [messageries](/debutant/communications#messagerie) respectueuses de vos données qui est tout à fait complet et ne mérite pas d'être paraphrasé :).

## Les réseaux sociaux

Configurez toujours vos réseaux sociaux afin d'améliorer votre vie privée en dé-sélectionnant les paramètres d'envoi automatique de données vers les serveurs de ces entreprises : ces paramètres peuvent généralement se trouver dans "Confidentialité et Sécurité" ou "Vie privée et Confidentialité" etc.

Faites un tour sur **_tous les paramètres_** de tous vos réseaux sociaux et vérifiez qu'aucune donnée, même des données de "diagnostic" n'est transmise. Ne minimisez rien, y compris sur des réseaux qui à priori respectent votre vie privée.

# Adoptez un modèle de sécurité renforcé

## Premier niveau : le VPN

Bien que choisir un navigateur optimisé et renforcé d’extensions, il existe toujours un risque qu’une personne malveillante puisse avoir accès à votre activité numérique et à votre position géographique, en observant les données en transit sur le réseau internet. La probabilité est faible certes, mais le risque est non nul...

Référez-vous à notre article [dédié](/debutant/vpn-tor).

## Second niveau : les DNS

> Si vous n'utilisez pas de service VPN via des mandataires (cf. ci-dessus), qui vous permettent de pointer vers leurs DNS, alors cette partie doit être lue avec attention :
{.is-warning}
  
En ce qui concerne les DNS, vous devez porter une attention particulière aux serveurs DNS vers lesquels vous pointez lorsque vous naviguez sur internet : par défaut les FAI proposent pour la plupart leurs propres DNS. Et si aucun changement n'est apporté, votre box est à priori déjà configurée pour atteindre leurs serveurs DNS. Dans l'éventualité où vous souhaitez apporter une relative vie privée et un relatif anonymat, il est judicieux de ne pas faire confiance à votre FAI. Il va donc s'agir d'apporter des modifications :

-   Si vous souhaitez que TOUS les équipements de votre réseau local privé atteignent des serveurs DNS respectueux, il faudra modifier les adresses IP directement dans la page de configuration de votre box FAI. Ainsi tous les équipements connectés (via câble Ethernet ou WiFi) pourront atteindre les nouveaux serveurs DNS.

-   Si vous souhaitez que uniquement quelques équipements soient anonymisés, il faut modifier les adresses directement sur cet équipement. Tous les systèmes d'exploitation, que ce soit bureautique ou serveur (Windows, Linux, MacOS, Unix, BSD...) proposent de configurer les aspects DNS. Ainsi, votre équipement demandera explicitement au routeur FAI d'utiliser les adresses IP demandées, et non celles configurées sur le routeur. 
*Néanmoins ici, il faut bien s'assurer que le routeur applique la règle (en utilisant "Nslookup" par exemple) :* *certains utilisateurs ont remonté que des FAI imposaient de passer par leurs DNS même si d'autres étaient configurés...*

Voici quelques adresses IP à renseigner, de serveurs DNS respectueux de la vie privée, qui de plus peuvent bloquer certaines publicités :

| - | Adresses IP | URLs Noeud |
|----------|----------|----------|
| [Quad9](https://www.quad9.net/service/service-addresses-and-features/) | 9.9.9.9 (IPv4)<br> 2620:fe::fe (IPv6) | dns.quad9.net |
| [Mullvad](https://mullvad.net/en/help/dns-over-https-and-dns-over-tls/) | 194.242.2.3 (IPv4) <br> 2a07:e340::3 (IPv6) | adblock.doh.mullvad.net |
| [LibreDNS](https://libredns.gr) | 116.202.176.26 <br> 2a01:4f8:1c0c:8274::1 (IPv6) | doh.libredns.gr/ads (Desktop) <br> noads.libredns.gr (Android) |
| [FDN](https://www.fdn.fr/actions/dns/) | 80.67.169.12 (IPv4) <br> 2001:910:800::12 (IPv6) | ns0.fdn.fr |
| [FDN](https://www.fdn.fr/actions/dns/) | 80.67.169.40 (IPv4) <br> 2001:910:800::40 (IPv6) | ns1.fdn.fr |


Également, vous trouverez sur le site suivant une seconde liste de serveurs DNS qui est mise à jour assez souvent :

- [DNS Adblock List](https://techcomputerservices.blogspot.com/2019/06/dns-adblock-list-update-juin-2019.html?m=1)

Bien sûr vous pouvez tout à fait monter votre propre serveur DNS (résolveur DNS).

## Niveau subsidiaire...

...mais néanmoins crucial : les métadonnées !

Veillez à supprimer toutes les **[métadonnées](/hygiene-numerique#les-m%C3%A9tadonn%C3%A9es-quest-ce-que-cest)** liées aux ressources (images, vidéos, documents) que vous partagez en ligne, que cela soit via courriel ou sur vos réseaux sociaux. Par exemple, pour les images, vous pouvez supprimer les données EXIF avant de les partager partout. Pour les documents vérifiez que vos nom/prénom ,ou même initiales et autres, ne soient pas inscrits dans les propriétés du document, etc. Voici quelques outils afin de supprimer les métadonnées de fichiers PDF, documents, vidéos (tous les outils suivants ne traitent pas les vidéos...), photos :
- [Exifcleaner](https://exifcleaner.com/) (Fonctionne aussi sur les documents Microsoft Office !) qui implémente la librairie [ExifTool](https://exiftool.org/) et offre une interface graphique
- [PDFparanoia](https://pypi.org/project/pdfparanoia/) outil complet pour le nettoyage des fichiers PDF
- [Metadatacleaner](https://metadatacleaner.romainvigier.fr/) le nettoyeur de Métadonnées niveau débutant, avec interface graphique, par Romain Vigier
- [Mat2](https://0xacab.org/jvoisin/mat2) (**M**etadata **A**nonymisation Tool v **2** - Outil d'anonymisation de Métadonnées version 2) nettoyeur de métadonnées niveau intermédiaire ou avancé
:arrow_right: Attention c'est un outil qui nécessite quelques connaissances ; à lancer dans une machine virtuelle par exemple pour plus d'anonymat.

# Le cas Tor Browser

« [Tor Browser](https://www.torproject.org/download/) » est un navigateur capable de vous donner accès au réseau Tor, dont nous avons déjà présenté le fonctionnement intrinsèque et l'objectif : l'anonymat comme garant de votre vie privée, et l'accès à des services web "cachés" (le web profond : nous parlons de ce second point plus tard dans l'article).

Le sujet autour de Tor Browser est assez complexe et débattu dans la communauté et dépend grandement de votre modèle :
1. **Si votre niveau de menaces ne va pas plus loin que quelques multinationales _pompes à données_ ou des recherches sensibles**, alors vous pouvez utiliser le navigateur Tor dans votre environnement pour des recherches et ceci afin de renforcer votre vie privée. 
*Pour ce cas d'utilisation, une mise en contexte et les bonnes pratiques, dans le cadre de son utilisation, seront prochainement disponibles depuis la section [tutoriels](/tutoriels/tor)*

2. **Si en revanche votre modèle impose un anonymat important** et que votre niveau de menaces concerne des "agences étatiques" ou des groupes à fortes ressources, il est nécessaire d'éviter son utilisation dans le contexte 1, et passer sur un modèle bien plus robuste (cf. partie suivante sur Tails, Whonix, etc.).
*Un tutoriel est également en cours de réflexion, comme pour le cas 1.*

---

> **Cela dit dans **TOUS** les cas, il conviendra de faire attention aux usages avec ce navigateur :**
> Ne pas installer d'extensions dans le navigateur Tor, au risque de casser son modèle de sécurité.
> Ne pas se connecter à des comptes qui concernent notre identité réelle (courriel, messagerie, réseau social), ou une identité virtuelle qui peut facilement être reliée à l'identité réelle, afin d'éviter de transmettre des identifiants.
> Ne pas utiliser Bittorrent ni autre logiciel de torrent.
{.is-warning}

Enfin, pour contourner un éventuel blocage (d'un moteur de recherche ou d'un FAI), vous pourrez utiliser les _**ponts**_ mis à disposition par Tor, par ordre de préférence :
- Meek azure
- Snowflake
- Obfs4

![ponts_tor.jpg](/images/ponts_tor.jpg =600x){.align-center}

![tor_-_ponts_intégrés.png](/images/tor_-_ponts_intégrés.png =600x){.align-center}

# Anonymat avancé

Obtenir un niveau plus avancé d'anonymat n'est pas chose aisée...

**Néanmoins, de premières pistes peuvent être envisagées avec une utilisation assez _classique_. Ici encore, il s'agit d'un second niveau d'anonymat, celui-ci ne sera donc pas total.**

## Whonix

[Whonix](https://www.whonix.org/) / [Qubes OS](https://www.qubes-os.org/) : L'utilisation de Qubes (avec Whonix pré-installé d'origine dans une machine virtuelle) ou d'un système d'exploitation Linux _[durci](/glossaire#durcissement)_ via la solution _Whonix_ permet un niveau de sécurité et un anonymat renforcés.

Sous Qubes OS (dans la Machine Virtuelle Whonix-WS) ou plus généralement sous Whonix, les requêtes [DNS](#dns) passent par Tor. Cela assure donc une anonymisation globale des requêtes. Attention en revanche si vous ne passez pas par ces outils, de bien configurer des adresses de serveurs DNS respectueux et d'assurer une protection des requêtes (que ce soit DoH, DoT, DNSCrypt ou DNSSEC...) :

- soit sur votre routeur FAI (bien vérifier également que ce routeur applique convenablement l'utilisation de ces IP, cf. DNS leak)
- soit sur votre propre serveur DNS :arrow_right: attention ici encore de bien comprendre ce mécanisme : implémenter une solution de type *PiHole* par exemple déporte uniquement le serveur résolveur chez vous, mais les requêtes vers les serveurs récursifs auront toujours lieu sur internet. Donc si vous ne protégez pas ces requêtes ou si vous ne cachez pas votre IP, il sera possible de vous désanonymiser !

## Tails

[Tails OS](https://tails.boum.org/) : la version ultime de l’anonymat, au-delà de votre navigateur internet, est l’utilisation de Tails OS.

Installé sur une clé USB et lancé depuis un appareil hôte - ordinateur portable ou PC x86 en 64 bits, quel que soit le système d'exploitation, le SE (Système d'Exploitation) hôte étant ignoré -, ce système d’exploitation est un système défini comme « amnésique ». C’est-à-dire qu’aucune donnée (hormis celle que vous souhaitez) ne persiste à l’extinction du système, ni en mémoire "RAM", ni sur disque dur/SDD (les clés USB fonctionnant sur la mémoire RAM "non persistante", l'avantage de ce système se situe là, vous l'aurez compris).

Ce système vous permet ainsi de créer un cocon numérique, peu importe le matériel que vous utilisez ; nul besoin d’utiliser votre ordinateur personnel. Par exemple très utile si vous vous connectez dans des lieux publics. Attention toutefois à bien comprendre les bases de l’outil. Réservé tout de même aux personnes à l’aise avec les aspects cyber et l’informatique en général.

*_Pour l’exemple_ : Tails ne s’utilise jamais en machine virtuelle. Si vous êtes intéressés par les machines virtuelles, veuillez utiliser plutôt Whonix !*

> Attention ici de bien maîtriser les outils informatiques en général, principalement GNU/Linux/BSD et les aspects durcissement.
{.is-warning}


# Anonymat total

Pour finir, si votre modèle impose un **anonymat total**, vous allez devoir adopter des pratiques spécifiques qui seront probablement des contraintes dans votre vie de tous les jours :
- vous devrez utiliser un matériel totalement anonyme : paiement cash de tous les matériels (ou par crypto monnaies _anonymes_)
- connexion et utilisation des matériels hors de chez vous, loin, dans des endroits publics, entourés de beaucoup de personnes
- aucun compte permettant de vous identifier
- utilisation totale du pseudonymat
- vos téléphones/tablettes... restent à la maison (aucun téléphone sur vous)
- assez contre-intuitif : évitez l'utilisation de clés de sécurité type signature pouvant vous identifier (*souvenez-vous du diagramme des 3 cercles évoqué plus haut : faire des compromis* !). Souvenez-vous de n'utiliser que du pseudonymat, y compris pour des signatures électroniques.

Vous arrivez à un usage très compliqué au quotidien !

Ce modèle de menaces extrême est d'ailleurs plutôt dédié aux militants,  activistes, opposants politiques, journalistes d'investigation... Vous l'aurez compris, probablement inadapté pour la majorité des personnes. Nous nous devions néanmoins d'envisager toutes les possibilités, face à notre audience. Mais ce modèle nécessite une réflexion profonde et une structure d'utilisation sur mesure... et sort donc du cadre de notre wiki !

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo*
<br>