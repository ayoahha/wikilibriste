---
title: Le système DNS expliqué
description: Cet article traite du système de noms de domaine et de sa configuration afin de recouvrer sa vie privée sur internet...
published: true
date: 2024-11-05T21:07:59.755Z
tags: dns, nom de domaine, url, tld, sous-domaine, reverse dns
editor: markdown
dateCreated: 2023-06-19T11:57:54.490Z
---

DNS ou « système de noms de domaine » (Domain Name System chez nos amis anglais) est un mécanisme particulièrement intéressant pour les réseaux.

Nous allons le voir, le DNS, c'est un peu l'**annuaire inversé** des sites internet : quand on sélectionne une [URL](/glossaire#url), ou qu'on la tape dans une barre de recherche, le DNS se charge de la transcrire en adresse IP (exemple : 144.76.131.212) pour contacter le site.

Rentrons dans les détails : nous allons nous intéresser plus particulièrement à l’utilisation sur le réseau internet, car son usage en est le parfait exemple. Lorsque nous naviguons sur internet, nous souhaitons visiter des sites internet. Pour y accéder, nous allons entrer un texte que nous appelons URL qui contient le nom du site. Mais comment savoir quel serveur contacter pour afficher le site en question ou autrement dit, comment retrouver l’adresse IP du serveur associée à ce nom du site ?

![Principes du DNS (Version simple)](/images/dns-1.png =600x){.align-center}

> C’est ici qu’entre en jeu le DNS.
{.is-info}

# Le mécanisme

Le mécanisme en lui-même est assez simple : le DNS permet de traduire (on parle de « résolution ») des noms de sites, appelés noms de domaine, en adresses IP. Souvenez-vous lorsque nous parlions d’adresses IP : nous avons défini ces adresses avec des suites de chiffres (et maintenant de chiffres et de lettres pour IPV6 !) incompréhensibles ! Les noms de domaine vont donc être plus compréhensibles.
*Par exemple : google.com, wikilibriste.fr sont des noms de domaine. Bien plus mémorisables et utilisables au quotidien que 8.8.8.8 ou 132.54.23.109 (adresse IP fictive pour wikilibriste).*

Pour les petits malins : oui il est possible de procéder à l’inverse. C’est-à-dire résoudre une adresse IP vers un nom de domaine qui lui est associé ! Cela s’appelle une « résolution inverse » ou reverse DNS.

Alors comment retrouver l’adresse IP ? Prenons l’architecture même de 2 URLs :
**-- www.google.com**
**-- wiki.wikilibriste.fr** (URL fictive utilisée pour l'exemple, notre URL réelle étant wikilibriste.fr)
Nous allons la découper en plusieurs parties afin de bien comprendre la mécanique :
-   Nous avons les domaines de premier niveau ou TLD (Top Level Domain) : ce sera les .com, .fr, .org, .de (on parle alors ici de domaines géographiques) voire des domaines plus exotiques comme .io, .tech, .tartanpion etc.
-   Nous avons ensuite les domaines de second niveau : le nom du site ou nom de domaine en lui-même c’est-à-dire par exemple « google » ou « wikilibriste » dans notre cas.
-   Puis nous avons les sous-domaines : généralement, nous voyons « www » devant les URLs (c’est très courant), ceci afin d’identifier les serveurs web, mais nous pourrions tout à fait avoir d’autres sous-domaines : mail, forum, wiki par exemple ! Eh oui, dans l’URL wiki.wikilibriste.fr, le sous-domaine associé est "wiki" afin d'identifier un serveur spécifique pour wiki.

Vous l’aurez compris, le DNS est une part essentielle d’internet. Sans lui, vous en seriez à entrer des adresses IP dans votre navigateur internet toute la journée ! Pas cool quand même...

Pour plus d'explications à ce sujet, vous pouvez visionner la vidéo
- **"DNS - La surveillance de masse facile" par *"Paf LeGeek"***

<iframe id='ivplayer' width='640' height='360' src='https://inv.nadeko.net/embed/S1f4NB72lMQ?iv_load_policy=1&t=5' style='border:none;'></iframe>



## Pourquoi parlons-nous de DNS ?

Eh bien simplement, car ce mécanisme bien que particulièrement utile n’est pas dénué de failles : il est tout à fait possible pour un attaquant de vous diriger vers une copie d’un site détourné afin de vous voler des informations personnelles. Des contre-mesures sont aujourd’hui mises en place mais elles ne couvrent pas tous les aspects de cette attaque. Sachant qu’aujourd’hui la majeure partie des échanges DNS est en clair (n’est pas chiffré), n’importe qui peut lire les requêtes DNS et ainsi réorienter une partie du trafic. Pour plus de détails, vous pouvez faire vos recherches sur les concepts de "*DNS poisoning*" ou "*spoofing*".

-   Vous avez sûrement entendu en 2016/2017 le nom d’un type d’attaque bien particulière : DOS (Denial Of Service) ou attaque par « déni de service ». Oui c’est barbare ! Vous allez comprendre : cette attaque utilise des petits logiciels appelés _botnet_ (voir plus loin partie Malware), et qui pour certains d'entre eux, chargés sur une machine cible permet de lancer une multitude de requêtes (1 million en 1 seconde par exemple) afin de le ralentir drastiquement, voire le faire tomber et l’ "ouvrir" afin d’obtenir des droits d’accès administrateur. Il existe même une attaque DDoS ou Distributed Denial Of Service ; celle-ci au lieu d’utiliser une seule machine hôte cible, utilise un ensemble de machines hôtes qui ensemble lancent les requêtes en même temps... Vous imaginez aisément les dégâts. C’est ce qu’il s’est passé en 2017 avec l’attaque via un botnet nommé Mirai [^⁵] sur un mandataire de services DNS dynDNS par exemple : certains sites internet très connus (et surtout très utiles pour certaines sociétés) étaient tout simplement injoignables. Mais ce n’est pas la seule victime du botnet Mirai...
-   Sans oublier nos chers amis institutionnels et Fournisseurs d'Accès Internet qui, du fait de l'architecture même du DNS, peuvent tracer vos requêtes et retrouver votre IP, voire faire du profilage y compris dans certains cas où vous utilisez un VPN (cf. "DNS leakage")...

[^⁵]: [Botnet mirai](https://news.sophos.com/fr-fr/2017/01/20/botnet-mirai-origine-attaques-ddos/) : origine et attaques DDOS.

La sécurisation des requêtes DNS est aujourd'hui même en plein chantier ; en effet, les organes de standardisation et de contrôle d'internet mettent à jour les standards, mais cela prend du temps. Pendant ce temps, nos requêtes DNS sont la plupart du temps transmises sans protection (en clair). Et les serveurs DNS utilisés (souvent ceux de votre FAI ! Mais nous pouvons citer les plus utilisés comme ceux de Google ou de Cloudflare) n'ont aucunement l'intention de respecter votre vie privée.

**Néanmoins**, oui nous allons un peu vous rassurer après ce tableau noir :-), il est aujourd'hui possible d'apporter un peu de vie privée à ces requêtes et de confort, car des mandataires tiers aux objectifs louables ont créé des serveurs DNS respectant (a priori !) notre vie privée, ajoutant des listes noires d'IP publicitaires, et implémentant des mécanismes de sécurisation des échanges même si encore en cours de standardisation (cf. DNS over TLS ou DoT, DNS over HTTPS ou DoH, DNSCrypt, DNS over SSH etc. pour les intéressés).

Ainsi, afin de contourner au maximum les faiblesses citées ci-dessus, il est de plus en plus recommandé d'ajuster notre utilisation des DNS :
:one: soit pointer directement vers des serveurs de mandataires tiers qui tiennent compte de notre *vie privée*, parmi lesquels des solutions dans l'esprit du libre, par exemple :
- [Quad9](https://quad9.net/fr/),
- [FDN](https://www.fdn.fr),
- ou bien encore [LibreDNS](https://libredns.gr).

Côté instance à but lucratif, _Mullvad DNS_ est à mentionner.

:two: soit héberger chez nous un serveur DNS de résolution capable de résoudre une partie des requêtes DNS (l'autre partie étant toujours traitée par des serveurs tiers), comme par exemple 
- une solution [PiHole](https://pi-hole.net/)
- ou même [CoreDNS](https://coredns.io/) et [SDNS](https://sdns.dev/)

pour créer ses propres résolveurs.

> Pour les amateurs de tests et de performances, [DNSPerf](https://www.dnsperf.com/#!dns-resolvers) vous permettra de regarder les performances des différents serveurs DNS existants (libres et non libres), à titre indicatif bien entendu.
{.is-info}

> Comme toujours en cyber-sécurité, ces 2 solutions ne sont pas parfaites, et sont donc à ajuster en fonction de notre modèle de menaces - élément que nous allons détailler à suivre.
{.is-warning}

# La démarche

Vous l'aurez compris, vous devez porter une attention particulière aux serveurs DNS vers lesquels vous pointez lorsque vous naviguez sur internet : **par défaut, les FAI proposent, pour la plupart, leurs propres DNS**. Si aucun changement n'est effectué de votre part, votre box est à priori déjà configurée pour atteindre leurs serveurs DNS.

Dans l'éventualité où vous souhaitez apporter une relative vie privée et un relatif anonymat, il est plutôt judicieux de ne pas faire confiance à votre FAI !

## Configuration

Il va donc s'agir d'apporter des modifications sur votre environnement local (que nous appelons très souvent "réseau local"). Différentes approches peuvent être envisagées :
-   Si vous souhaitez que TOUS les équipements de votre réseau local privé atteignent des serveurs DNS respectueux, il faudra modifier les adresses IP directement dans la page de configuration de votre box FAI. Ainsi, tous les équipements connectés (via câble Ethernet ou WiFi) pourront atteindre les nouveaux serveurs DNS.

-   Si vous souhaitez qu'uniquement quelques équipements soient configurés, il faut modifier les adresses directement sur ces équipements. Tous les systèmes d'exploitation, que ce soit bureautique ou serveur (Windows, Linux, MacOS, Unix, BSD...) proposent de configurer les serveurs DNS. Ainsi, votre équipement demandera explicitement au routeur FAI d'utiliser les adresses IP demandées, et non celles configurées sur le routeur.
*Néanmoins ici, il faut bien s'assurer que le routeur applique la règle (en utilisant "nslookup" par exemple) :* *certains utilisateurs ont remonté que des FAI imposaient de passer par leurs DNS même si d'autres étaient configurés...*

- Il est également possible de configurer son navigateur afin de pointer vers le bon serveur DNS.

**Nous reviendrons sur ces configurations plus loin.**

## Les acteurs d'intérêt

Voici quelques acteurs qui proposent des services de serveurs DNS, respectueux de votre vie privée et qui, de plus, peuvent bloquer certaines publicités, par ordre de préférence et de performances :

| - | Adresses IP (Linux ou Routeur) | URL DNS Privé (Android) ^1^ | URL Navigateur HTTPs (Linux) ^2^ |
|----------|----------|----------|----------|
| [Quad9](https://www.quad9.net/service/service-addresses-and-features/) | 9.9.9.9 (IPv4)<br> 2620:fe::fe (IPv6) | dns.quad9.net | https://dns.quad9.net/dns-query |
| [LibreDNS](https://libredns.gr) | 116.202.176.26 <br> 2a01:4f8:1c0c:8274::1 (IPv6) | noads.libredns.gr | https://doh.libredns.gr/dns-query |
| [FDN](https://www.fdn.fr/actions/dns/) | 80.67.169.12 (IPv4) <br> 2001:910:800::12 (IPv6) | ns0.fdn.fr | https://ns0.fdn.fr/dns-query |
| [FDN](https://www.fdn.fr/actions/dns/) | 80.67.169.40 (IPv4) <br> 2001:910:800::40 (IPv6) | ns1.fdn.fr | https://ns1.fdn.fr/dns-query |
| [Mullvad](https://mullvad.net/en/help/dns-over-https-and-dns-over-tls/) | 194.242.2.3 (IPv4) ^3^ <br> 2a07:e340::3 (IPv6) ^3^ | dns.mullvad.net<br>adblock.dns.mullvad.net | https://dns.mullvad.net/dns-query<br>https://adblock.dns.mullvad.net/dns-query |
| [DNS Adblock List](https://techcomputerservices.blogspot.com/2019/06/dns-adblock-list-update-juin-2019.html?m=1) | Vous trouverez sur ce site une liste de serveurs<br>DNS (IPs) intéressants pour le blocage des<br>publicités intempestives. |


^1^ : "DNS Privé" est la fonction qui permet le chiffrement des requêtes DNS (DNS over TLS depuis Android 9) ou de sélectionner le fournisseur DNS de son choix, différent de celui proposé par défaut par l'opérateur de réseau mobile.
- **Cette fonction se trouve généralement dans les "Paramètres" :arrow_right: "Réseau et Internet" :arrow_right: "DNS Privé".**

^2^ : "DNS over HTTPS" est souvent l'intitulé de la fonction utilisée par les navigateurs internet pour gérer la résolution DNS personnalisée.
- **Il est essentiel de bien faire comprendre au navigateur qu'il s'agit d'une requête DNS :arrow_right: en ajoutant en fin d'URL "dns-query".**

^3^ : _Attention_ : les adresses IP DNS de Mullvad sont plutôt capricieuses : il est parfois possible qu'aucune requête ne passe (c'est à dire ne soit résolue) ce qui peut mener à un blocage de votre navigation. Préférez plutôt donc utiliser les URLs localement. Cette page explique comment configuer le service : https://mullvad.net/en/help/dns-over-https-and-dns-over-tls

## Les procédures

Il existe donc différentes façons de configurer les serveurs DNS sur son réseau ou sa/ses machines. Nous vous présentons toutes ces procédures dans cette partie :

### Local au navigateur

Il est possible afin de simplifier au maximum la configuration DNS de modifier uniquement les paramètres de son navigateur afin que chaque requête (recherche, site internet visité...) passe par un serveur DNS spécifique.

Cependant, nous alertons l'audience sur certains points à garder à l'esprit : sur votre machine, vous accédez certes à internet via votre navigateur, mais il se peut que certaines applications aient également un accès à internet. C'est par exemple le cas de Telegram ou Signal (Desktop), de votre Centre de Logiciels (ex. GNOME Software), d'une application de vidéoconférence, d'une application de développement, et bien d'autres.

**Dans le cas où vous paramétrez les DNS uniquement dans votre navigateur, ces autres applications pointeront toujours vers les DNS d'origine de votre FAI.**

Ceci est l'inconvénient majeur de la première solution...
> **Si vous désirez couvrir la totalité des applications de votre machine, vous pouvez directement passer au deuxième niveau de paramétrage (et sauter ce niveau actuel), c'est à dire au système lui-même**.
{.is-info}

#### Tabs {.tabset}
##### Base Firefox

> Cette configuration vous est présentée dans le [tutoriel](/tutoriels/librewolf#facultatif) spécifique à Librewolf, même si applicable sur tous les navigateurs sur base Firefox.
{.is-success}

##### Base Chromium
Voici la configuration pour tout navigateur ayant une base Chromium (ex. : les impressions écrans suivantes sont basées sur le navigateur Chromium) :

![ug-param-1](/images/ug-param-1.png){.align-center}
![ug-param-2](/images/ug-param-2.png){.align-center}

- Cliquez à gauche sur la partie "Confidentialité et sécurité"

![chro-dns-1](/images/chro-dns-1.png){.align-center}
![chro-dns-2](/images/chro-dns-2.png){.align-center}

> Testons notre configuration pour vérifier que nous pointons bien vers le DNS de Mullvad, cf. cette [partie](#auto-audit) :
> 
> ![chro-dns-3](/images/chro-dns-3.png){.align-center}
{.is-success}

##### Base Ungoogled Chromium
Ungoogled Chromium est différent de Chromium, voici pourquoi il existe une configuration différente.

> Cette configuration vous est présentée dans le [tutoriel](/tutoriels/ungoogled-chromium#facultatif) spécifique à Ungoogled Chromium.
{.is-success}

### Local au système

Comme nous l'avons mentionné ci-haut, il peut être plus intéressant de configurer globalement son système afin de faire pointer toutes les requêtes (que ce soit votre navigateur, mais aussi toute autre application ayant besoin d'internet) vers des serveurs DNS tiers.

Ici encore, nous devons garder en tête qu'il ne s'agit pas de la solution optimale : en effet, nos maisons intègrent de plus en plus de produits avec accès vers internet. Il peut s'agir d'une TV (même si nous conseillons de ne pas activer l'accès internet sur ces objets!), d'une BOX TV (Nvidia Shield, Mi TV, etc.), d'une tablette pour les enfants, d'une imprimante, d'un NAS, et bien d'autres équipements, qui ne sont pas votre machine ordinateur.

**Dans le cas où vous paramétrez les DNS uniquement pour votre machine, ces autres équipements pointeront toujours vers les DNS d'origine de votre FAI.**

Ceci est l'inconvénient de cette seconde solution...
Alors vous pouvez nous rétorquer : "Dans ce cas, je vais paramétrer les DNS de TOUS mes équipements !". Certes, mais certains équipements n'offrent pas la possibilité de modifier les serveurs DNS ;)

> **Si vous désirez couvrir la totalité des équipements de votre réseau local, vous pouvez passer au troisième niveau de paramétrage.**
{.is-info}

---
> La présente section couvre les 2 principaux DE des distributions Linux, GNOME, Cinnamon et KDE, que ce soit Ubuntu, Zorin, Mint, Debian, Fedora, etc. Pour d'autres environnements (ex. XFCE), référez-vous à la documentation du DE ou contactez la communauté.


#### Tabs {.tabset}
##### GNOME
Configurer les serveurs DNS sur GNOME est on ne peut plus simple !

- La configuration suivante se base sur une version 44.x de GNOME, même si cette configuration peut également être applicable à une version 43.x voire 42.x, avec quelques différences mineures (nous partons également du principe que toutes les mises à jour de votre système ont été faites au préalable).

Voici la procédure :
1. Rendez-vous dans les "Paramètres" de GNOME :
![](/images/gnome-dns-1.png){.align-center}

2. Deux options s'offrent à vous :
2-1. Si vous êtes connectés via votre Wi-Fi, il est nécessaire de modifier les paramètres Wi-Fi (et non réseau - filaire) :
![](/images/gnome-dns-2_0.png){.align-center}
![](/images/gnome-dns-2_1.png){.align-center}
![](/images/gnome-dns-2_2.png){.align-center}
![](/images/gnome-dns-2_3.png){.align-center}

> **Attention : les adresses IPs entrées ci-dessus le sont à titre indicatif. Vous pouvez entrer les adresses de votre choix, sélectionnées [ici](#les-acteurs-dint%C3%A9r%C3%AAt)**.
{.is-info}

2-2. En revanche, si vous êtes connectés via un câble (ethernet), il est nécessaire de modifier les paramètres réseau (filaire) :
 
![](/images/gnome-dns-3_0.png){.align-center}
![](/images/gnome-dns-3_1.png){.align-center}
![](/images/gnome-dns-3_2.png){.align-center}
![](/images/gnome-dns-3_3.png){.align-center}

> Redémarrez votre machine, et vérifiez que la configuration est bien appliquée :
> 
> ![](/images/gnome-dns-4.png){.align-center}
{.is-success}

##### Cinnamon
Nous fournissons la procédure pour Linux Mint qui vient avec l'environnement Cinnamon.

- La configuration suivante se base sur une version 21.1 de Linux Mint avec Cinnamon en version 5.6.8 (nous partons également du principe que toutes les mises à jour de votre système ont été faites au préalable).

Voici la procédure :
1. Cliquez en bas à droite sur l'icône réseau ou WiFi (1) puis rendez-vous dans les "Paramètres réseau" ou "Paramètres Wi-Fi" de Cinnamon (2) :

![](/images/cin-dns-1.png){.align-center}

> Attention, vu que la configuration est la même sur réseau filaire ou Wi-Fi, nous ne montrons que la configuration sur réseau filaire. Si vous êtes en Wi-Fi, appliquez ces changements pour les Paramètres Wi-Fi

2. La modification des paramètres réseau (filaire) se fait comme suit :

![](/images/cin-dns-2.png){.align-center}
![](/images/cin-dns-3.png){.align-center}
![](/images/cin-dns-4.png){.align-center}
![](/images/cin-dns-5.png){.align-center}
![](/images/cin-dns-6.png){.align-center}

> **Attention : les adresses IPs entrées ci-dessus le sont à titre indicatif. Vous pouvez entrer les adresses de votre choix, sélectionnées [ici](#les-acteurs-dint%C3%A9r%C3%AAt)**.
{.is-info}

> Redémarrez votre machine, et vérifiez que la configuration est bien appliquée :
> 
> ![](/images/cin-dns-7.png){.align-center}
{.is-success}

##### KDE
Nous fournissons la procédure pour un environnement de bureau KDE.

- La configuration suivante se base sur une version KDE 5.27.x, mais peut tout à fait convenir sur des versions un peu plus anciennes (nous partons également du principe que toutes les mises à jour de votre système ont été faites au préalable).

Voici la procédure :
1. Rendez-vous dans les "Paramètres" KDE, puis à gauche, cliquez sur la partie "Connexions" (1) :

![](/images/kde-dns-1.png){.align-center}

> Attention, vu que la configuration est la même sur réseau filaire ou Wi-Fi, nous ne montrons que la configuration sur réseau filaire. Si vous êtes en Wi-Fi, appliquez ces changements pour les Paramètres Wi-Fi

2. La modification des paramètres réseau (filaire) se fait comme suit :

![](/images/kde-dns-2.png){.align-center}
![](/images/kde-dns-3.png){.align-center}

**Veillez à bien sélectionner "Automatique (adresses uniquement)"** :

![](/images/kde-dns-4.png){.align-center}
![](/images/kde-dns-5.png){.align-center}
![](/images/kde-dns-6.png){.align-center}

> **Attention : les adresses IPs entrées ci-dessus le sont à titre indicatif. Vous pouvez entrer les adresses de votre choix, sélectionnées [ici](#les-acteurs-dint%C3%A9r%C3%AAt)**.
{.is-info}

> Redémarrez votre machine, et vérifiez que la configuration est bien appliquée :
> 
> ![](/images/kde-dns-7.png){.align-center}
{.is-success}

### Sur son réseau local
Dernière solution de configuration, afin d'appliquer les modifications à tous les appareils connectés de votre réseau.

Il est nécessaire de modifier les paramètres de votre box internet fournie par votre FAI, cela inclut donc que vous sachiez accéder à l'interface de paramétrage.

> Nous tentons de vous donner un maximum d'indications, cependant du fait de la multitude de box sur le marché, nous ne pouvons être exhaustifs ; il vous appartient donc de chercher dans des documentations ou des tutoriels si vous bloquez, ou de faire appel à la communauté.

#### Tabs {.tabset}
##### BBOX
Cette procédure est issue de la solution proposée sur le forum Bouygues Telecom, pour une Box Ultym, [ici](https://www.assistance.bouyguestelecom.fr/s/forum/question/0D5080000BUPDTeCQP/comment-changer-les-dns-par-d%C3%A9faut-de-ma-bbox-).

1. Ouvrez votre navigateur, et rendez-vous à cette adresse : [https://mabbox.bytel.fr/firewall.html](https://mabbox.bytel.fr/firewall.html)
2. Vous seront demandés le login et le mot de passe afin d'entrer dans la configuration de votre box.
3. Ajoutez une règle de pare-feu comme suit :

![](/images/bouyg-dns-1.png){.align-center}

4. Rendez-vous ensuite à cette adresse : [https://mabbox.bytel.fr/dhcp.html](https://mabbox.bytel.fr/dhcp.html)
5. Ajoutez une option comme suit :

![](/images/bouyg-dns-2.png){.align-center}

> Cela peut différer quelque peu sur votre Box, veuillez donc vous référer à la documentation ou faire appel à la communauté.
> 
> **Redémarrez votre box pour finaliser la configuration.**
{.is-info}

##### Freebox

Voici la procédure pour les Freebox Pop et Delta (cela peut différer sur les Freebox Revolution, mais les intitulés devraient être les mêmes) :
1. Ouvrez votre navigateur, et rendez-vous à cette adresse : [http://mafreebox.freebox.fr/](http://mafreebox.freebox.fr/)
2. Vous serons demandés le login et le mot de passe afin d'entrer dans la configuration de votre box.
3. Entrez dans les "Paramètres de la Freebox", vous obtenez ceci :

![](/images/fbox-dns-1.png){.align-center}

4. Rendez-vous dans la partie "DHCP", vous obtenez ceci :

![](/images/fbox-dns-2.png){.align-center}

5. Dans la section "DNS", entrez autant d'adresses IP que désiré, comme suit :

![](/images/fbox-dns-3.png){.align-center}

> **Attention : les adresses IPs entrées ci-dessus le sont à titre indicatif. Vous pouvez entrer les adresses de votre choix, sélectionnées [ici](#les-acteurs-dint%C3%A9r%C3%AAt)**.
{.is-info}

6. Cliquez sur "Appliquer".


> **Redémarrez votre box pour finaliser la configuration.**
{.is-info}

##### Orange Box

Sur les dernières Livebox (depuis 4), il est impossible de modifier ses DNS dans l'interface d'administration.

Les choix sont donc malheureusement restreints pour ces box :
- Vous pouvez configurer sur chaque équipement de votre réseau les DNS (cf. seconde solution).
- Vous pouvez configurer une solution de type [Pi-Hole](#devenez-votre-propre-dns) que nous présentons ci-après.

##### SFR Box

Concernant les box SFR, il se peut que certaines box (anciennes) n'acceptent pas la modification des DNS (les champs restent grisés et la modification est impossible, dû à la politique stricte de SFR !) ; dans ce cas :
- Vous pouvez configurer sur chaque équipement de votre réseau les DNS (cf. seconde solution).
- Vous pouvez configurer une solution de type [Pi-Hole](#devenez-votre-propre-dns) que nous présentons ci-après.


Néanmoins, sur certaines Box, NB8 par exemple, il est possible de configurer les DNS comme suit :

1. Rendez-vous sur l'interface de configuration de la box : généralement, tapez ceci dans la barre d'URL de votre navigateur [http://192.168.1.1](http://192.168.1.1) (ou [http://192.168.0.1](http://192.168.0.1)).
2. (Optionnel) Allez dans le menu "Maintenance", puis onglet "Administration". Vous serons demandés le login et le mot de passe afin d'entrer dans la configuration de votre box.
3. Rendez-vous dans le menu "LAN" :arrow_right: "Serveur DHCP" :arrow_right: "Editer", puis dans les champs suivants :
	1. DNS primaire : entrez l'adresse IP que vous aurez sélectionnée [ici](#les-acteurs-dint%C3%A9r%C3%AAt)
	2. DNS secondaire : généralement les fournisseurs tiers fournissent une second adresse IP. Si c'est le cas, entrez cette seconde adresse ici, sinon laissez vide
4. Cliquez sur "Sauvegarder".

> Cela peut différer quelque peu sur votre Box, veuillez donc vous référer à la documentation ou faire appel à la communauté.
> 
> **Redémarrez votre box pour finaliser la configuration.**
{.is-info}

## Devenez votre propre DNS
Bien sûr, vous pouvez tout à fait monter votre propre serveur DNS (résolveur DNS).

> Ceci fait l'objet d'un tutoriel bien spécifique dédié à la solution [Pi-Hole](/tutoriels-serveur/pi-hole).
{.is-success}


## Auto audit

> Afin de vérifier que vous pointez bien vers le bon serveur DNS, vous pouvez utiliser l'outil [DNS Leak test](https://www.dnsleaktest.com/).
>
> Faites un test "Standard" et après un "Test Complete", vérifiez l'ISP (Internet Service Provider et le pays si besoin), qui doit correspondre avec le DNS choisi.
{.is-info}


---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo, Nemtech*
<br>