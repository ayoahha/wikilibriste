---
title: Utiliser un VPN et/ou Tor
description: Cet article aborde les très importants concepts de VPN et TOR...
published: true
date: 2024-03-13T10:56:19.038Z
tags: vpn, tor
editor: markdown
dateCreated: 2023-04-14T10:56:48.029Z
---

Nous abordons ici quelques notions sur des services dont vous entendrez souvent parler : les VPN ou Virtual Private Network, et le réseau Tor, ou réseau en oignon :)

> Ici encore, attention de bien comprendre la problématique du mandataire unique et les risques potentiels si vous n’hébergez pas vous-même la solution.
{.is-info}

---
[Aller directement à nos recommandations](#nos-recommandations).

# Les technologies
## VPN

Démocratisé il y a quelques années et qui aujourd’hui fait couler beaucoup d’encre, le VPN ou « Virtual Private Network » (Réseau Privé Virtuel) est un mécanisme qui vous permet d’encapsuler vos données dans un « tunnel » sécurisé (on parle de tunneling, ou tunnélisation). Ce tunnel est initié entre le « client » qui est l’initiateur de la communication et un « serveur » qui va recevoir les informations protégées, et les router vers la bonne destination.

![Principes d'une installation VPN classique](/images/vpn-principe.png =600x){.align-center}

À l’origine, les VPNs ont été conçus afin d’aider les grandes entreprises et agences étatiques à créer des « accès à distance » pour leurs collaborateurs, via une connexion hautement sécurisée, tout en passant par des réseaux publics. L'idée est de permettre un accès distant aux contenus d'une entité, que l'on soit à côté ou à l'autre bout du monde, le tout sur un réseau public (internet).

_Ainsi par exemple_ : M. Smith, agent du renseignement basé à Bangkok, ayant besoin d’informations sensibles, se connecte sur son ordinateur par le biais d’un VPN, afin d’avoir accès aux serveurs de l’agence directement. Les serveurs étant basés à Brême. Ainsi il peut lire des documents comme s’il était à Brême, dans les locaux.

Ce mécanisme s’est étendu au grand public, et d’une façon un peu différente de celle d’origine : vous, le client, initiez une communication (un tunnel) avec un serveur d’une société mandataire qui vous a vendu un service VPN (NordVPN, Cyberghost VPN, ProtonVPN...). Ce mandataire est donc en charge de router vos informations vers la bonne direction.

> Ainsi le destinataire auquel vous vous adressez reçoit une communication venant d’un serveur VPN avec l'adresse IP du serveur, et non de vous directement (et de votre adresse IP).
{.is-success}


![Technologie VPN grand public](/images/vpn_today.png =600x){.align-center}

Mais tout cela s’accompagne d’inconvénients : ce mandataire, même s’il vous assure qu’il pratique une politique renforcée de confidentialité et de vie privée, qu'il vous assure un anonymat et/ou implémente une « no-log policy » (c’est-à-dire ne gardant pas les journaux de vos connexions et votre adresse IP sur ses serveurs), vous n’avez aucun moyen de confirmer ces dires, car vous ne pouvez avoir accès à ces sociétés. Celles-ci sont d’ailleurs tout à fait capables de changer de politique du jour au lendemain, ou pire, de vous mentir. Également, ce mandataire ne peut refuser de collaborer avec des agences étatiques si leurs serveurs sont présents dans des pays où les lois les y obligent (USA, UK, France, Allemagne par exemple), voire y adjoindre une politique d’espionnage.

Ainsi, si le concept de VPN grand public a permis à beaucoup de contourner le géoblocage ou géorestriction et la censure, la confiance en ces mandataires s’est petit à petit érodée : ces entreprises, rachetées les unes par les autres par des consortiums, deviennent de plus en plus importantes et la confiance que nous pouvons leur accorder aujourd’hui n’est plus aussi grande que par le passé. Par ailleurs, il s’est avéré que certains mandataires avaient menti sur leur politique « no-log ».

Le choix d'un VPN pour un particulier, est par conséquent une tâche qui nécessite de récolter un ensemble d'éléments permettant d'établir une confiance relative et raisonnable envers le service. Nous reviendrons sur ce point, après la présentation du réseau Tor.

_Note 1_ : Vous ne trouverez dans cet article aucune mention des services VPN présentés par des streamers comme Cyberghost, Surfshark, ExpressVPN, Kickmyass, Hide me, PureVPN (la liste est longue, mais grosso modo dès qu'un streamer en fait mention, vous pouvez être sûr que l'outil est plus marketing qu'autre chose) ; pour une raison évidente : ces services n'offrent pas le niveau de vie privée "_minimal_" attendu d'un tel service, de par la mécanique même du lien affilié = pistage via le lien affilié, courriel exigé pour bénéficier de la remise... De même, de nombreux services présentés par ces mêmes streamers ont une politique agressive, qui se reflète à travers leur politique de vie privée, le fait de ne pas utiliser de logiciel à code source ouvert, etc. Nous ne connaissons pas non plus complètement les personnes ou les groupes qui détiennent ces mandataires (via rachats successifs, cf. image ci-dessous), ni leurs intentions ; il est tout à fait possible qu’ils tracent les données afin de faire du profilage, même s’ils rétorquent le contraire. Qui peut vérifier ?!

Pour illustrer ces propos, ci-dessous une illustration qui montre le rachat successif de sociétés de VPN par le groupe Kape Technologies. Groupe initialement versé dans les logiciels publicitaires et de piratage de navigateurs :

![screenshot_20220910-000714.png](/images/screenshot_20220910-000714.png =800x){.align-center}

_**Explications**_ : le changement de direction de ce groupe s'est opéré en 2018 vers une entreprise dite de cybersécurité. C'est pourquoi avec un consortium qui a un tel passé, une politique de rachat aussi agressive, et des sites de revue de VPN clairement orientés - vu qu'[incentivés](https://fr.wiktionary.org/wiki/incentive) - il est essentiel d'être vigilant dans le choix d'un VPN. Nous vous invitons à poursuivre cette partie, avec les conseils que nous prodiguons en fin de l'article sur le réseau Tor.

---------------
Également, un développeur nous propose une [mindmap](https://embed.kumu.io/9ced55e897e74fd807be51990b26b415#vpn-company-relationships) permettant de visualiser tous les liens qu'entretiennent les VPNs entre certaines entités. A peu près tous les VPNs du marché sont présents dans cette infographie.

---------------
_Note 2_ : NordVPN n’apparaîtra pas non plus. Ce mandataire est systématiquement mis en avant par les streamers : hormis la législation, en dehors des "14 eyes", 3 signaux d'alarme doivent attirer l'attention de l'audience : 
(1) Le code source de l'application NordVPN n'est pas ouvert : un logiciel propriétaire n'offrant pas de transparence sur les attendus de l'application, on ne peut s'assurer de l'honnêteté des pratiques de la firme.
(2) De plus, la sécurisation de leur infrastructure est à questionner, ayant fait l’objet de quelques fuites de données récemment [^¹] mais aussi [^²].
(3) Qui plus est, ce n'est pas nécessairement celui qui fait le plus de bruit qui est le meilleur.

[^¹]: [Plusieurs trous de sécurité openvpn](https://www.silicon.fr/plusieurs-trous-securite-openvpn-178559.html)
[^²]: [Nordvpn le fournisseur VPN confirme avoir été piraté](https://www.zdnet.fr/actualites/nordvpn-le-fournisseur-vpn-confirme-avoir-ete-pirate-39892559.htm)


> Certains services, comme Mullvad ou IVPN, beaucoup plus discrets, offrent à la fois anonymisation à la souscription et au règlement, transparence avec leur politique de vie privée et le choix de l'open-source, ainsi qu'un niveau de sécurité supérieur avec l'authentification à double facteur qui n'oblige pas l'utilisateur à utiliser un courriel.
{.is-info}

-------------
_Note 3_ : Nous ne faisons pas non plus apparaître la solution ProtonVPN, car pour rappel Proton AG a été critiqué récemment pour avoir délivré des adresses IP d’activistes. Même si ce mandataire paraît être de confiance, il n’est plus forcément recommandé d’utiliser les solutions Proton quand on est exposé (politiquement ou journalistiquement, ainsi que pour les activistes !).

Nous reparlerons de ces services un peu plus loin...

## TOR

Tor pour « The Onion Router », vous allez comprendre pourquoi... À l’origine, ce réseau était utilisé par des agents du renseignement US ; le concept ayant en effet été développé dans des laboratoires militaires américains dans les années 90. Ce n’est qu’à partir de 2004 que cette technologie fut libérée au grand public, puis connue sous le nom de The Tor Project.

La technologie de « routage en oignon » repose sur le principe de routage via des relais, relais par lesquels l’information passe successivement. Dans ce mécanisme, les données sensibles de l’émetteur (adresse IP...) ne sont connues que par le premier relais (que l’on nomme noeud d’entrée), et la destination demandée par l’émetteur n’est connue que par le dernier relais (nommé noeud de sortie). Entre ces 2 relais, l’information passe par un relais intermédiaire et complique considérablement le traçage. Afin de protéger les informations en transit, le message est chiffré autant de fois que le nombre de relais (en l'occurrence ici 3 pour Tor), de sorte à obtenir une protection par couches, qui schématiquement ressemblent aux couches d’un ... oignon !

![Principes du réseau Tor](/images/tor.png =600x){.align-center}

Cependant, comme tout mécanisme, le réseau Tor possède aussi ses inconvénients :
-   le relais d’entrée sait potentiellement vous identifier, même s’il ne peut pas lire le contenu de l’information en transit car l’information est protégée (chiffrée par couches), il reçoit les quelques données non protégées comme votre adresse IP publique et quelques autres métadonnées.
-   le relais de sortie connaît le destinataire, même s’il ne connaît pas l’émetteur (vous), et peut également potentiellement accéder au contenu car celui-ci a été dépourvu de toutes les couches de sécurité Tor, et donc potentiellement le contenu est non chiffré ; l’exception ici est si la communication est effectuée avec un protocole sécurisé de bout en bout (par exemple visiter un site en HTTPS (S pour Secure)), auquel cas cette partie de la communication sera protégée et non lisible par le noeud de sortie.

Vous comprenez donc que cette technique permet d’augmenter votre anonymat ; en effet le destinataire à qui vous vous adressez ne peut savoir que c’est vous qui lui parlez. Mais elle ne permet pas nécessairement de protéger de bout en bout les informations en transit, car tout dépend du protocole de départ.

Qui plus est, le réseau Tor n’utilise aucune infrastructure complexe et importante pour ses relais mais uniquement des personnes _**volontaires**_, qui hébergent des serveurs Tor afin de router les communications. Bien que cette solution présente l'avantage certain - au contraire des mandataires VPNs - de ne pas avoir la même entreprise gérant tous les serveurs, elle possède cependant quelques inconvénients : il est vraisemblable que parmi ces volontaires, certains n’ont pas forcément des intentions louables. Ou que par exemple une personne étant désignée comme noeud de sortie fasse en fait l’objet d’espionnage, ou bien qu'une agence étatique monte une ribambelle de serveurs (de sorte à augmenter les probabilités que les échanges passent par ces serveurs !). Auquel cas, vos communications sont potentiellement compromises. Également, le grand revers de la médaille de ce réseau est la lenteur des communications. De par les mécanismes utilisés, il est évident que faire transiter l’information par plusieurs endroits successifs avant d’arriver à bon port ne peut que rajouter de la latence dans les échanges.

> Enfin, il n’est pas recommandé d’utiliser le réseau Tor pour vous connecter à des comptes utilisateurs, GAFAM ou autre... Par exemple : se connecter à Facebook ou à Gmail en utilisant le réseau Tor.
{.is-danger}


**Attention, cela ne veut pas dire que c'est impossible, mais ayez bien en tête que tout ce que vous ferez, sur votre compte Facebook par exemple, sera traçable et identifiable comme venant de _vous, vu que personnellement identifié, avec photos, etc_. En ce sens, vous cassez le principe du réseau Tor qui est l’anonymat.**

## Pour finir...

### Alors quelle différence entre Tor et VPNs me direz-vous ?

> **Eh bien, assez schématiquement : Tor renforce votre anonymat (le « qui vous êtes »), un VPN renforce votre protection (le « ce que vous faites »).**
{.is-info}

Alors vous pourriez me dire : *« Je viens de réfléchir et j’ai trouvé une solution : dans ce cas je vais utiliser un VPN + le réseau Tor et ainsi, je serai 100% anonyme et sécurisé ! ».*

- À ceci, nous vous répondrons : ce n’est pas aussi simple que cela en a l’air !

Ce n’est pas parce que vous combinez différents mécanismes de sécurité que vous augmentez automatiquement votre niveau de sécurité : en revanche, vous augmentez de fait significativement la complexité dans vos communications. Une mauvaise combinaison ou une mauvaise configuration VPN+Tor peut potentiellement engendrer une diminution dans le niveau de sécurité, voire induire des failles de sécurité critiques. Concernant l'anonymat, même constat : une mauvaise utilisation ou configuration peut mener à une désanonymisation plus rapide.

Le seul cas dans lequel un VPN serait recommandé à l’usage de concert avec Tor est le cas du blocage de votre FAI des serveurs Tor. En effet, la liste des serveurs est publique et il est tout à fait possible pour un FAI de bloquer les adresses IP publiques de ces serveurs ; dans ce cas, le seul moyen de contourner ce problème est d’utiliser un VPN pour naviguer sur Tor. Cet article ne discute pas plus de cet aspect : en revanche, si vous êtes intéressés par ce sujet :
-   Les développeurs de Tor font un état des lieux sur cette utilisation ici : [Tor Project - TorPlusVPN](https://gitlab.torproject.org/legacy/trac/-/wikis/doc/TorPlusVPN)
-   Whonix (distribution GNU/LInux "virtualisée", basée sur le réseau Tor) propose un article très détaillé sur cet aspect, que nous vous conseillons de lire très attentivement : [Whonix.org - Introduction](https://www.whonix.org/wiki/Tunnels/Introduction)
-   Tails (autre distribution GNU/Linux basée sur Tor, plébiscitée par les activistes et journalistes) propose également dans sa FAQ un avis sur la question : [Tails](https://tails.boum.org/support/faq/index.en.html#index20h2)

# Nos recommandations

Voici les outils d'aide à la décision par la communauté Techlore :
-   Ai-je besoin d'un VPN ? [https://www.doineedavpn.com/](https://www.doineedavpn.com/)
-   Sélectionner un VPN selon mon profil et mes besoins : politique "no-log" avérée ? En dehors des coalitions contraignantes côté vie privée (cf. 14 eyes) ?  etc.
  :arrow_right: Détail des principaux services VPN [par ici](https://techlore.tech/vpn) (site en anglais : utiliser votre service de traduction favori) ; avec un accent particulier à mettre entre autres sur les colonnes suivantes :
	  - "14 eyes"
	  - "Analytics concerns"
	  - "Misleading Security Marketing"
	  - "Security History"
	  - "Privacy History"
	  - "Anon Payment"
	  - "Anon Signup"

Quoi qu'il en soit, rassurez-vous, nous avons fait le travail pour vous ;). Notre collectif ne recommande à ce jour que quelques services VPN (mentionnés ci-après), qui combinent plusieurs aspects que nous estimons impératifs pour choisir son mandataire VPN. Voici les exigences à respecter, qui sont de notre point de vue "**non négociables**" :
> ~~ **Application à code source ouvert** : permet de s'assurer que l'application fait ce qu'on en dit.
> ~~ **Politique de vie privée** et philosophie générale.
> ~~ **Pas d'antécédent ou déboire connu**.
> ~~ Possibilité de régler **anonymement en espèces ou en cryptomonnaie Monero**.
> ~~ Possibilité de se connecter de façon pleinement privée, avec un identifiant qui n'est ni un courriel, ni un numéro de téléphone.
{.is-success}

Les mandataires suivants remplissent toutes ces conditions :
- [Mullvad VPN *Un mandataire très sérieux, domicilié en Suède (14-eyes), et audité en 2021 (avec succès) \** ](https://mullvad.net)
- [IVPN *Certainement les meilleures prestations après Mullvad, qui plus est domicilié hors des 14-eyes*](https://www.ivpn.net)
- [AzireVPN *Basé en Suède (14-eyes) et propriétaires de leurs serveurs*](https://www.azirevpn.com/fr)
- [OVPN *Une bonne solution alternative basée en Suède (14-eyes)*](https://www.ovpn.com)
- [AirVPN *Infrastructure importante et solution correcte*](https://airvpn.org)
- [Safing.io *Et leur outil Portmaster/SPN ou "Safing Privacy Network" intéressant*](https://safing.io/)
{.links-list}

---
Pour ce qui est de **Tor**, plusieurs cas de figure s'offrent à des profils intermédiaires ou initiés :
- Pour un premier niveau, et sous **_certaines conditions_** l'utilisation de **Tor Browser** peut être faite.

> **Cela dit, dans **TOUS** les cas, il conviendra de faire attention aux usages avec ce navigateur :**
> ~~ Ne pas installer d'extensions dans le navigateur Tor, au risque de casser son modèle de sécurité/anonymat.
> ~~ Ne pas se connecter à des comptes qui concernent notre identité réelle (courriel, messagerie, réseau social), ou une identité virtuelle qui peut facilement être reliée à l'identité réelle, afin d'éviter de transmettre des identifiants.
> ~~ Ne pas utiliser Bittorrent ni autre logiciel de torrent.
{.is-warning}

Enfin, pour contourner un éventuel blocage (d'un moteur de recherche ou d'un FAI), vous pourrez utiliser les **_ponts_** mis à disposition par Tor, par ordre de préférence :
- Meek azure
- Snowflake
- Obfs4

![ponts_tor.jpg](/images/ponts_tor.jpg =600x){.align-center}

![tor_-_ponts_intégrés.png](/images/tor_-_ponts_intégrés.png =600x){.align-center}

- Pour aller plus loin, il est essentiel de se pencher sur les aspects Anonymat, nous renvoyons donc vers l'article dédié à [limiter le pistage](/hygiene-numerique#anonymat-avanc%C3%A9) en ligne.

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo, Nemtech*
<br>