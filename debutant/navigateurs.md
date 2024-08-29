---
title: Les navigateurs web
description: Un article liés aux navigateurs internet et leur durcissement...
published: true
date: 2024-08-29T15:55:21.053Z
tags: navigateur, web, internet, privacy, vie privée, chrome, firefox, debutant, intermédiaire, débutant, intermediaire
editor: markdown
dateCreated: 2022-11-25T18:38:25.687Z
---

Un navigateur web [^¹] (web browser en anglais, ou simplement navigateur), est un logiciel qui permet d'afficher le contenu d'une page en ligne ou locale et d'explorer le web international ou WWW (World Wide Web) autrement dit la "toile d'araignée mondiale".

[^¹]: [Navigateur web](https://fr.wikipedia.org/wiki/Navigateur_web)

> A ne pas confondre avec un [Moteur de recherche](/debutant/moteurs-recherche) (search engine en anglais) qui lui se charge d'indexer le contenu de la plupart des pages sur le web !
{.is-info}

> Nous _déconseillons l'utilisation_ de : Google Chrome, Microsoft Edge / Internet Explorer, Apple Safari, Opera, Samsung Internet et autres navigateurs propriétaires installés sur ordinateurs ou smartphones.
> 
> **Ils ne ne sont ni libres, ni open-source et ne respectent pas votre vie privée !**
{.is-danger}

Sachez que la part de marché des navigateurs web [^²] basés sur Google Chromium (moteur Blink) est de plus de 65 % en 2022. Si vous ne souhaitez pas la voir croître et donc ne pas alimenter Google, **nous vous conseillons d'utiliser un navigateur basé sur Mozilla Firefox (moteur de rendu Gecko)**.

[^²]: [Part de marché](https://fr.wikipedia.org/wiki/Parts_de_march%C3%A9_des_navigateurs_web) des navigateurs web dans le monde.

# Pour Ordinateurs

[Aller directement à nos recommandations](#nos-recommandations)

## Liste des navigateurs d'intérêt

| Navigateur Web | Editeur | Systèmes supportés | Moteur de rendu | Licence | Open Source | Installation |  Commentaires |
|----------|----------|----------|----------|----------|----------|----------|----------|
| Firefox | Mozilla <br>Foundation | GNU/Linux<br>BSD<br>Windows<br>MacOS<br> | Gecko | Libre MPL2 | Oui | Depuis votre logithèque Linux ou<br>[instructions sur le site](https://www.mozilla.org/fr/firefox/new/) | Firefox de la fondation Mozilla est controversé pour ses "anti-fonctionnalités", ses traqueurs et la mise en avant de moteurs de recherches non libres, <br>mais il contribue à faire exister une alternative face à l’hégémonie de Google !<br>Il est possible de re-paramétrer Firefox afin de s'affranchir de ces anti-fonctions mais cela reste fastidieux à mettre en place. Le projet s'appelle [Arkenfox](https://github.com/arkenfox/user.js/wiki).<br>Quelques guides ou outils pour faciliter sa mise en place sont disponibles :<br>- Guide [firefox-hardening](https://github.com/trinityprivacy/firefox-hardening)<br>- Outil [Arkenfox-Soft](https://github.com/trytomakeyouprivate/Arkenfox-softening)<br>- Outil [Betterfox](https://github.com/yokoffing/BetterFox)<br>- Henri de [Techlore](https://yewtu.be/watch?v=F7-bW2y6lcI) a publié une vidéo sur ce sujet également. <br><br>_Quelques précisions_ :<br>- Firefox Fenix est la version mobile de Firefox. Voir section dédiée.<br>- Firefox ESR (Extended Support Release) cible les entreprises mais constitue souvent le navigateur par défaut dans les distributions GNU/Linux. |
| Mullvad Browser | Mullvad AB | GNU/Linux<br>Windows<br>MacOS<br> | Gecko | Libre MPL2 | Oui | Depuis votre logithèque Linux ou<br>[instructions sur le site](https://mullvad.net/fr/browser) | Petit nouveau en provenance de Mullvad, le mandataire VPN très connu et de The Tor Project, à l'origine du fameux Tor Browser.<br>Sur une base Firefox "durcie" (hardened) avec une intégration de Tor afin de réduire le fingerprinting |
| LibreWolf | Librewolf <br>Community | GNU/Linux<br>BSD<br>Windows<br>MacOS<br> | Gecko | Libre MPL2 | Oui | Depuis votre logithèque Linux ou<br>[Instructions sur le site](https://librewolf.net/installation/) | Un fork de Firefox axé sur la sécurité et la vie privée. À privilégier si vous voulez lutter contre la suprématie de Google et recherchez un certain niveau<br>de "durcissement" de Firefox. |
| Ungoogled-Chromium | Ungoogled <br>Software | GNU/Linux<br>BSD<br>Windows<br>MacOS<br> | Blink | Libre BSD3 | Oui | Depuis votre logithèque Linux ou<br>[Instructions sur le site](https://github.com/ungoogled-software/ungoogled-chromium#downloads) | Rapide, dépourvu de traceurs et aucune télémétrie.<br>Il s'agit de développeurs tiers et même s'il leur suffit d'adapter les patchs Chromium, les mises à jour peuvent avoir quelques jours de retard.<br>Note : éviter le navigateur nommé Chromium (de Google) ! |
| Iridium Browser | NetITwork | GNU/Linux<br>Windows<br>MacOS<br> | Blink | Libre BSD3 | Oui |  [Instructions sur le site](https://iridiumbrowser.de/downloads/) | Quelques soucis de mises à jour il y a quelques temps l'avaient mis en retrait. C'est cependant réglé et l'équipe est plutôt réactive concernant les mises à jour.<br>Il prend pour base Chromium qu'il durcit au maximum et supprime la télémétrie. Lui reste tout de même quelques petits points, heureusement configurables<br>pour supprimer totalement la télémétrie : cf. [cette page](https://spyware.neocities.org/guides/iridium)  |
| Brave | Brave Software<br>Inc. | GNU/Linux<br>Windows<br>MacOS<br> | Blink | Libre MPL2 | Oui |  Pour PC [instructions sur le site](https://brave.com/download/) | Créé par Brendan Eich, le co-fondateur de Mozilla et le créateur de JavaScript. Brave est rapide, bloque les pisteurs, permet de naviguer sur le réseau Tor<br> (via navigation privée) et intègre son propre moteur de recherche [Brave Search](https://search.brave.com/).<br>- Cependant Brave est controversé dans la communauté car les agissements de ses développeurs n'ont pas été très transparents et le navigateur collecte <br>quelques données qu'il ne devrait pas : [^3], [^4], [^5], [^6], [^7], [^8], [^9] et [^10]<br>- <span class="red-text">Même s'il est fort probable que Brave ait évolué sur ces aspects car ils semblent écouter leur communauté, il est important de peser les "pour" <br>et les "contre" pour l'utilisation de ce navigateur.</span> |
| Vivaldi | Vivaldi <br>Technologies | GNU/Linux<br>Windows<br>MacOS<br> | Blink | Propriétaire | Non <br>(pas entièrement) |  Pour PC [instructions sur le site](https://vivaldi.com/fr/download/) | Vivaldi est le navigateur le plus paramétrable sur le marché. Ses performances sont louées par la communauté.<br>Cela dit, le gros handicap de ce navigateur est qu'il n'est pas entièrement open source (son interface utilisateur est sous licence propriétaire et à sources <br>fermées) et on ne peut pas dire qu'ils aient fait des efforts concernant la vie privée de leurs utilisateurs : utilisation de Google SafeBrowsing et autres joyeusetés...<br>Même si cela peut encore évoluer dans le bon sens... |
| Tor Browser | The Tor <br>Project | GNU/Linux<br>BSD<br>Windows<br>MacOS<br> | Gecko | Libre Diverse | Oui |  Depuis votre logithèque Linux ou<br>[instructions sur le site](https://www.torproject.org/download/) | Développé dans le cadre du projet Tor et basé sur Firefox ESR, ce navigateur dispose d'une sécurité renforcée et permet de parcourir le web via un circuit <br>"en oignon" et ses multiples proxies d'anonymisation.<br>Il ralentit cependant la navigation et est loin d'être parfait. Il est conseillé de ne l'utiliser que si vous voulez conserver un certain anonymat ou pour parcourir <br>les sites en .onion dans un environnement sécurisé (Whonix par ex.) |
| Pale Moon | Moonchild <br>Productions | GNU/Linux<br>Windows | Goanna | Libre MPL2 | Oui |  [Instructions GNU/Linux](https://linux.palemoon.org/)<br>[Instructions Windows](https://www.palemoon.org/download.shtml) | Basé sur Firefox ESR avec un moteur de rendu forké sur Gecko, il ressemble à la version des années 2010. Il supporte encore Flash Player.<br> Malheureusement, le navigateur ne fait pas que des bons choix ces derniers temps, et n'arrive pas à rattraper son retard. <br>De plus le départ de certaines personnes du projet font que celui-ci n'est plus tout à fait une alternative crédible :( ! |
| Links | Twibright <br>Labs | GNU/Linux<br>Windows<br>MacOS<br> | Terminal Text | Libre GPL2 | Oui |  Depuis les dépôts | Navigateur en mode texte, parfait sur un serveur. Il permet de naviguer en couleur, télécharger en HTTP, HTTPS et FTP. |
{.dense}

[^3]: [Brave Browser](https://www.reddit.com/r/privacytoolsIO/comments/gytwmd/brave_browser_privacytoolsio_and_the_negativity/) discussions sur ses points négatifs
[^4]: [Pourquoi Brave est-il décrié?](https://www.reddit.com/r/privacytoolsIO/comments/i7tfgp/why_is_there_a_negative_stigma_against_brave/)
[^5]: [Brave Browser Controversies](https://wikiless.org/wiki/Brave_(web_browser)#Controversies)
[^6]: [Brave Browser Analyse](https://spyware.neocities.org/articles/brave)
[^7]: [The shady world of Brave selling copyrighted data for AI training](https://stackdiary.com/brave-selling-copyrighted-data-for-ai-training/)
[^8]: [Brave installe ses services VPN sans consentements](https://www.ghacks.net/2023/10/18/brave-is-installing-vpn-services-without-user-consent/)
[^9]: [Brave et liens affiliés - Crypto](https://www.theverge.com/2020/6/8/21283769/brave-browser-affiliate-links-crypto-privacy-ceo-apology)
[^10]: [Brave revend des données pour entrainer des IA](https://stackdiary.com/brave-selling-copyrighted-data-for-ai-training/)


## Nos recommandations

Le marché des navigateurs suit un peu sur le même chemin que les moteurs de recherche malheureusement. Le marché est tel que nous n'en recommandons que très peu :
- [Ungoogled Chromium *est probablement un des choix à faire. Il est néanmoins nécessaire de le configurer correctement \**](https://github.com/ungoogled-software/ungoogled-chromium#downloads)
- [Librewolf *est une excellente alternative sur base firefox, même si quelques requêtes Mozilla sont encore présentes au démarrage*](https://librewolf.net/installation/)
- [Mullvad Browser *est ici encore une très bonne alternative sur base firefox, jeune certes, mais fournissant toutes les fonctionnalités nécessaires*](https://mullvad.net/fr/browser)
{.links-list}

\* : Voir notre [tutoriel](/tutoriels/ungoogled-chromium) afin de configurer correctement Ungoogled Chromium.

> _Note sur Tor Browser_ : nous ne recommandons pas forcément ce navigateur pour un usage quotidien, **mais pour des recherches ciblées**. S'il est utilisé sur un support adéquat comme Whonix et Tails, cela vous apporte une sécurité supplémentaire...
> *Tor Project a énormément travaillé sur le contournement du fingerprinting, probablement au détriment de la sécurité. De plus n'importe quel autre navigateur est capable de visiter les sites .onion ou d'utiliser le réseau Tor (pour peu que vous le configuriez correctement : en effet, par ex. Proxy Tor ou Orbot+RPV sur téléphone etc.) et ceux-ci ne souffrent pas de versions de retard (et donc de failles héritées de ces versions)*.
{.is-info}

# Pour Téléphones

[Aller directement à nos recommandations](#nos-recommandations-1)

## Liste des navigateurs d'intérêt

| Navigateur Web | Editeur | Systèmes supportés | Moteur de rendu | Licence | Installation |  Commentaires |
|----------|----------|----------|----------|----------|----------|----------|
| Mull | Divested Mobile | Android | Gecko | Libre AGPL3 | Installer [F-Droid](https://f-droid.org/F-Droid.apk) et installer ensuite Mull depuis F-Droid | Mull est à Android ce que LibreWolf est aux ordinateurs. Rapide, dépourvue de trackers, très peu de télémétrie. |
| Fennec | F-droid | Android | Gecko | Libre MPL2 | Installer [F-Droid](https://f-droid.org/F-Droid.apk) et installer ensuite Fennec depuis F-Droid | Fennec est un fork de Mozilla Fenix, avec la suppression d'une partie de la télémétrie. Il possède toujours <br>des connexions avec Mozilla et Google et n'est donc pas entièrement dépourvu de trackers. |
| Tor Browser | The Tor Project | Android | Gecko | Libre MPL2 | Installer [F-Droid](https://f-droid.org/F-Droid.apk) puis activer le dépôt **Guardian** et installer <br>ensuite Tor Browser depuis F-Droid | Voir ci-haut. |
| Brave | Brave Inc. | Android | Blink | Libre MPL2 | Installer [F-Droid](https://f-droid.org/F-Droid.apk) puis depuis celui-ci installer [AuroraStore](https://f-droid.org/en/packages/com.aurora.store/)<br>et enfin depuis Aurora Store, installer Brave | Voir ci-haut. |
| ~~Bromite~~ | Calyx Institute | Android | Blink | Libre GPL3 | Installer [F-Droid](https://f-droid.org/F-Droid.apk) puis activer le [dépôt](https://www.bromite.org/fdroid) et installer ensuite <br>Bromite depuis F-Droid | Bromite est à Android ce que Ungoogled-Chromium est aux ordinateurs. Installé par défaut sur CalyxOs.<br><span class="red-text">**Note 1 : Les développeurs de Bromite ont cessé les développements de l'application (cf. leur message [ici](https://github.com/bromite/bromite/discussions/2573)). <br>Bromite ne doit plus être utilisé.**</span> <br><span class="red-text">**Note 2 : Un fork a été fait par quelques développeurs, qui appellent maintenant l'application [Cromite](https://github.com/uazo/cromite). <br>Nous recommandons néanmoins d'attendre avant d'utiliser Cromite afin d'avoir le plus de recul possible <br>sur le sérieux de l'équipe.**</span> |
| Vanadium | Graphene | Android | Blink | Libre GPL3 | - | [Vanadium](https://github.com/GrapheneOS/Vanadium) n'est disponible que sur GrapheneOS et est basé lui aussi sur Ungoogled-Chromium. |
| Vivaldi | Vivaldi <br>Technologies | Android | Blink | Non <br>(pas entièrement) |  Pour PC [instructions sur le site](https://vivaldi.com/fr/download/) | Voir ci-haut. |
{.dense}

## Nos recommandations

Le marché des navigateurs sur mobile est encore pire que celui sur PC fixe :
- [Vanadium *pour la sécurité (uniquement disponible sur Pixels)*](https://github.com/GrapheneOS/Vanadium)
- [Mull *est l'alternative crédible sur base Gecko*](https://gitlab.com/divested-mobile/mull-fenix)
{.links-list}

# Extensions
Les extensions (aussi nommées Plug-in, Add-on) sont des modules tiers externes, développés par des personnes autres que l'équipe en charge du navigateur et s'ajoutent au navigateur afin d'enrichir ses fonctionnalités.

> Attention toutefois à ne pas surcharger le navigateur en extensions, d'une part pour éviter de ralentir le logiciel mais aussi pour réduire l'unicité du navigateur (cf. "fingerprint").
{.is-danger}

## Anti-pistage
Dans cette catégorie, la plus importante, nous nommons cela génériquement les "anti-traceur", car ce type d'extension est en fait celle qui vous permettra de couper tous les liens de collecte par des tiers de façon plus ou moins robuste :

- [uBlock Origin](https://github.com/gorhill/uBlock) : L'un des meilleurs dans ce domaine. Bloque les publicités et les traceurs et permet d'ajouter des règles de filtrage strictes et spécifiques si nécessaire. *(Attention, uBlock tout court est une arnaque.)*
	- [uBlock Origin *Adblocker*](https://addons.mozilla.org/firefox/addon/ublock-origin/) Pour navigateurs sur base Firefox (*Déjà pré-installé sur Librewolf*)
	- [uBlock Origin *Adblocker*](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm) Pour navigateurs sur base Chromium
	- [uBlock Origin *Adblocker*](https://github.com/gorhill/uBlock-for-firefox-legacy/releases) Pour navigateurs Pale Moon
	{.links-list}
- [AdGuard](https://adguard.com/fr/welcome.html) : Une alternative crédible à uBlock Origin. Au délà de bloquer également les publicités et les traceurs, AdGuard ajoute quelques protections additionnelles comme par exemple éviter les fuites d'IP (WebRTC protection, même s'il est possible de l'activer directement par le navigateur).
	- [AdGuard *Adblocker*](https://addons.mozilla.org/fr/firefox/addon/adguard-adblocker/) Pour navigateurs sur base Firefox
	- [AdGuard *Adblocker*](https://chrome.google.com/webstore/detail/adguard-adblocker/bgnkhhnnamicmpeenaelnjfhikgbkllg) Pour navigateurs sur base Chromium
	{.links-list}
- [Decentraleyes](https://decentraleyes.org/) : Pas une alternative à uBlock Origin ou AdGuard mais plutôt un *complément*. Cette extension permet simplement de réduire voire supprimer les requêtes vers des sites tiers qui fournissent des librairies, en profitant pour stocker vos données personnelles au passage. **Attention à bien le configurer avec uBlock Origin**.
	- [Decentraleyes *Anti-CDN*](https://addons.mozilla.org/fr/firefox/addon/decentraleyes/) Pour navigateurs sur base Firefox
	- [Decentraleyes *Anti-CDN*](https://chrome.google.com/webstore/detail/decentraleyes/ldpochfccmkkmhdbclfhpagapcfdljkj) Pour navigateurs sur base Chromium
	- [Decentraleyes *Anti-CDN*](https://addons.palemoon.org/addon/decentraleyes/) Pour navigateurs Pale Moon
	{.links-list}
- [LocalCDN](https://codeberg.org/nobody/LocalCDN) : Une alternative plus puissante de Decentraleyes. LocalCDN est en fait un fork de Decentraleyes, plus complet en termes de librairies tierces gérées. **Attention à bien le configurer avec uBlock Origin**.
	- [LocalCDN *Anti-CDN*](https://addons.mozilla.org/fr/firefox/addon/localcdn-fork-of-decentraleyes/) Pour navigateurs sur base Firefox
	- [LocalCDN *Anti-CDN*](https://chrome.google.com/webstore/detail/localcdn/njdfdhgcmkocbgbhcioffdbicglldapd) Pour navigateurs sur base Chromium
	{.links-list}

Sans doute la plus puissante et plus complète des extensions,  mais _**réservé aux utilisateurs initiés**_ : 
- **uMatrix** : Il s'agit en fait plus d'un "*Pare-Feu Navigateur*" qu'un simple Adblocker, ce qui en fait une extension qui combine uBlock Origin et LocalCDN... Il est possible de finement régler la configuration de chaque site visité : par défaut, uMatrix n'autorise que le strict nécessaire, ce qui rend la majorité des sites illisibles cela dit. À vous donc d'activer les blocs nécessaires pour rendre la lisibilité correcte ou accepter de ne pas visiter le site en question (c'est un choix possible !).
	- [uMatrix *localFW*](https://addons.mozilla.org/en-US/firefox/addon/umatrix/) Pour navigateurs sur base Firefox
	- [uMatrix *localFW*](https://chrome.google.com/webstore/detail/umatrix/ogfcmafjalglgifnmanfmnieipoejdcf) Pour navigateurs sur base Chromium
	- [nMatrix *localFW*](https://addons.palemoon.org/addon/ematrix/) Pour navigateurs Pale Moon
	{.links-list}

> uMatrix semble ne plus être maintenu, cela dit l'utilisation d'internet n'a pas évolué depuis ! Les mécanismes restent les mêmes.
> Pour ceux qui croient également que uBlock Origin reprend toutes les fonctionnalités de uMatrix, c'est faux ; uMatrix permet bien plus et plus finement de gérer les sites web.
{.is-info}

## URLs
- [ClearURLs](https://docs.clearurls.xyz/1.23.0/) Permet le nettoyage des URLs de tous paramètres intrusifs.
	- [ClearURLs *URLs*](https://addons.mozilla.org/fr/firefox/addon/clearurls/) Pour navigateurs sur base Firefox
	- [ClearURLs *URLs*](https://chrome.google.com/webstore/detail/clearurls/lckanjgmijmafbedllaakclkaicjfmnk) Pour navigateurs sur base Chromium
	{.links-list}
- [Redirector](http://einaregilsson.com/redirector/) Redirigent Youtube, Twitter, Instagram vers des alternatives libres. Redirector nécessite une configuration manuelle, en ajoutant les URLs de redirection.
	- [Redirector *URLs*](https://addons.mozilla.org/fr/firefox/addon/redirector/) Pour navigateurs sur base Firefox
	- [Redirector *URLs*](https://chrome.google.com/webstore/detail/redirector/ocgpenflpmgnfapjedencafcfakcekcd) Pour navigateurs sur base Chromium
	{.links-list}
- [Libredirect](https://libredirect.github.io/) Redirigent Youtube, Twitter, Instagram vers des alternatives libres. Libredirect est déjà préconfiguré avec des URLs de redirection.
	- [Libredirect *URLs*](https://addons.mozilla.org/fr/firefox/addon/libredirect/) Pour navigateurs sur base Firefox
	- [Libredirect *URLs*](https://github.com/libredirect/libredirect/releases) Extension qui devra s'installer depuis les sources, car non disponible dans le store Google.
	{.links-list}


> Pour Libredirect sur base chromium :
> ~~ Télécharger la version Zip sur le dépôt github puis dézipper là.
> ~~ Se rendre dans `chrome://extensions` et activer le mode développeur.
> ~~ Rafraichir la page, puis cliquez sur 'Charger l'extension non empaquetée'.
> ~~ Choisissez le dossier extrait précédemment. 
> L'extension devrait se charger et s'ouvrir.
{.is-info}

## Cookies
- [I still don't care aboot cookies](https://github.com/OhMyGuus/I-Still-Dont-Care-About-Cookies) Bloque les bannières (parfois intrusives !) de certains sites vous proposant l'utilisation des cookies. 
**Nous réintégrons cette extension, qui est un fork de "I don't care about cookies" racheté récemment par Avast (et qui intègre un identifiant publicitaire !). Un développeur a donc décidé de continuer l'extension sans intégrer de traceur**.
	- [ISDCAC *Cookies*](https://addons.mozilla.org/fr/firefox/addon/istilldontcareaboutcookies) Pour navigateurs sur base Firefox
	- [ISDCAC *Cookies*](https://chrome.google.com/webstore/detail/i-still-dont-care-about-c/edibdbjcniadpccecjdfdjjppcpchdlm) Pour navigateurs sur base Chromium
	- [IDCAC *Cookies*](https://addons.palemoon.org/addon/i-dont-care-about-cookies/) Pour navigateurs Pale Moon
	{.links-list}
- [Cookie AutoDelete](https://mybrowseraddon.com/cookie-auto-delete.html) Détruit les cookies à la fermeture du navigateur (**il est à noter que Firefox propose nativement une option permettant la suppression des cookies à la fermeture du navigateur**)
	- [Cookie AutoDelete *Cookies*](https://addons.mozilla.org/fr/firefox/addon/cookie-autodelete/) Pour navigateurs sur base Firefox
	- [Cookie AutoDelete *Cookies*](https://chrome.google.com/webstore/detail/cookie-autodelete/fhcgjolkccmbidfldomjliifgaodjagh) Pour navigateurs sur base Chromium
	{.links-list}

## Scripts
- [NoScript](https://noscript.net/) _Destiné aux utilisateurs avertis_, il permet de désactiver site par site les scripts lancés (notamment javascript). Attention car de nombreux sites peuvent donc ne plus fonctionner normalement.
	- [NoScript *Javascript*](https://addons.mozilla.org/fr/firefox/addon/noscript/) Pour navigateurs sur base Firefox
	- [NoScript *Javascript*](https://chrome.google.com/webstore/detail/noscript/doojmbjmlfjjnbmnoijecmcbfeoakpjm) Pour navigateurs sur base Chromium
	{.links-list}


# Ressources d'intérêt
- [AdBlock Tester](https://adblock-tester.com/) afin d'effectuer un test de votre contournement des moyens publicitaires.
- [Coveryourtracks](https://coveryourtracks.eff.org/) un outil proposé par l'EFF afin de tester la robustesse de votre navigateur.

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): marmotte, Ayo*
<br>