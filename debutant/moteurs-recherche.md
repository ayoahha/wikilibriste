---
title: Les moteurs de recherche
description: Article liés aux moteurs de recherche internet et le côté respect de la vie privée...
published: true
date: 2024-02-25T09:53:12.421Z
tags: privacy, vie privée, moteurs, recherche, debutant, intermédiaire, débutant, intermediaire
editor: markdown
dateCreated: 2022-11-25T18:45:28.462Z
---

Un moteur de recherche, "search engine" en anglais, est un outil qui vous permet de rechercher sur le web à l'aide de mots clefs.

L'outil aura auparavant indexé une multitude de sites à travers la toile afin de vous afficher les résultats les plus appropriés sous forme d'une page avec des liens hypertextes, ainsi qu'une description sommaire de leur contenu.

> A ne pas confondre avec un [Navigateur web](/debutant/navigateurs) ("web browser" en anglais), qui lui se charge d'afficher le contenu des pages lorsque vous naviguez sur le web.
{.is-info}


Le moteur de recherche le plus connu est, bien entendu, "Google Search" et à lui seul détient plus de 90% du marché [^¹] mondial ! Si bien que les propriétaires de sites Internet sont en quelque sorte obligés de se plier aux règles d'indexation du géant des GAFAM pour avoir une visibilité sur la toile mondiale. Certains n'hésitent pas à payer en échange, ce qui est évidemment l'un des buts de Google Ads, Trends...

[^¹]: [Google Search](https://gs.statcounter.com/search-engine-market-share) tue le marché.

# Nos recommandations
[Aller directement à nos recommandations](#pour-conclure).

# Analyses

## Blâme comportement

Le moteur de recherche de Google stocke entre autres les données suivantes :

-   votre adresse IP
-   votre emplacement
-   votre système d'exploitation, navigateur et sa version (via le user-agent)
-   vos cookies et identifiants uniques
-   les termes / mots que vous saisissez en temps réel

Il est également à préciser qu'il ne s'agit pas du seul moteur de recherche qui conserve ces données : Bing (Microsoft), Yahoo Search, Baidu, Yandex également sont concernés.

Alors évidemment, nous n'irons pas plus loin et ne citerons pas les moteurs en lien direct avec des multinationales connues pour collecter toutes sortes de données privées, ou des pays pratiquant une quelconque censure nationale assumée, comme :
- Google Search
- Microsoft Bing
- Yahoo Search
- Ask\. com
- Baidu
- Yandex

Inutile de dire que nous ne recommandons absolument pas ces moteurs de recherche.

**Nous allons plutôt analyser les alternatives crédibles (enfin présentées comme telles) à tous ces moteurs anti-vie privée...**

## Avertissements

### DuckDuckGo
[DuckDuckGo](https://duckduckgo.com/) est très certainement le moteur de recherche alternatif le plus connu et finalement le plus controversé. Il croise différentes sources pour donner des résultats pertinents. Il utilise l'indexation de Bing (Microsoft) et a été _justement_ pendant un temps sujet de controverses pour ses liens avec Microsoft [^²] et [^³] qui a fait scandale dans la communauté.

[^²]: [DDG et le problème Microsoft](https://help.duckduckgo.com/duckduckgo-help-pages/company/ads-by-microsoft-on-duckduckgo-private-search/#:~:text=At%20that%20point%2C%20Microsoft%20Advertising%20will%20use%20your%20full%20IP%20address%20and%20user%2Dagent%20string%20so%20that%20it%20can%20properly%20process%20the%20ad%20click%20and%20charge%20the%20advertiser), ouvertement mis en avant sur leur site.
[^³]: [DDG et le traçages des utilisateur](https://metro.co.uk/2022/05/27/private-browser-duckduckgo-found-to-actually-be-tracking-users-16722038/).

DDG a réussi une parfaite illusion... Le moteur est adopté par une grande partie du public, y compris sur Tor Browser. Et pourtant les signaux sont présents :
- Le créateur a déjà vendu les données d'utilisateurs de son ancien réseau social "Names Database"
- Bien que leur politique de vie privée annonce qu'ils ne "stockent aucune information personnelle", ce n'est pas le cas des recherches elles-mêmes, procédé qui par le passé avait déjà fait beaucoup de dégâts, comme rappelé ici :
> "*Le problème le plus sérieux est que beaucoup de personnes recherchent leurs propres nom/prénom, ou ceux de leurs amis ou entourages, afin de vérifier quelles informations sont disponibles sur eux ou leurs proches sur internet. Combinez cela avec des requêtes de site pour adultes et vous créez un embarras assez sérieux. Combinez cela avec une recherche comme "acheter du cannabis" et vous obtenez une preuve criminelle dans certains pays. Combinez cela avec une adresse postale, un numéro de sécurité sociale, etc. et vous avez un vol d'identité probablement qui arrivera un jour. Les possibilités sont infinies.*" [^⁴] surtout avec les moyens actuels !

Non seulement DDG stockent vos requêtes, mais celles-ci s'accompagnent d'autres informations d'intérêts pour eux, même s'ils prétendent anonymiser ces informations. Un article écrit par DDG ne disait-il pas : "*The only truly anonymized data is **no data***" [^⁵] traduction : "Les seules données véritablement anonymes sont celles qui n'existent pas" ?
**Visiblement ils n'appliquent pas leurs propres conseils.**

Très récemment (Mars 2022), DDG a annoncé appliquer une censure sur les résultats des recherches [^⁶]. On est loin d'un modèle tout à fait sain.

[^⁴]: [Stockage des requêtes](https://techcrunch.com/2006/08/06/aol-proudly-releases-massive-amounts-of-user-search-data/) de recherches.
[^⁵]: [Data anonymization](https://spreadprivacy.com/data-anonymization/), par DuckDuckgo.
[^⁶]: [DDG et la Censure](https://www.developpez.com/actu/331759/DuckDuckGo-procede-au-deferencement-des-sites-qui-seraient-associes-a-la-desinformation-russe-mais-certains-utilisateurs-crient-a-la-censure-et-demandent-au-moteur-de-recherche-de-revoir-son-action/).

> DuckDuckGo a annoncé avoir pris des mesures concernant la télémétrie. Cela dit depuis la mise en place de leur politique de censure, et l'évolution négative de leur politique de collecte de données, nous ne recommandons plus ce moteur de recherche.
{.is-danger}

### Brave Search
[Brave search](https://search.brave.com/) est le moteur de recherche de la société Brave Inc., moteur "*respectueux de la vie privée*" d'après leur cahier des charges. Il implémente son propre moteur d'indexation (au contraire de Duckduckgo), donc dans 99% des cas, il ne fait pas appel à ceux de Google ou Bing (hormis pour les images, qui sont indexées sur Bing) ; pour les 1% restants, il fait appel aux autres moteurs de recherche même s'il prétend le faire de façon privée [^⁷] bien entendu. Également, récemment Brave Search a annoncé mettre à jour leur modèle de financement vers de la publicité [^⁸], même si non ciblée et respectueuse de notre vie privée, bien entendu.

Après avoir exposé l'enveloppe, voyons ce qu'elle contient :
- Lorsque nous regardons leur politique de vie privée [^⁹], nous lisons ceci : "*Vous pouvez rechercher 'bar autour de moi' Brave Search utilisera l'adresse IP transmise par votre équipement mais sans la partager ni la stocker. Cela signifie que nous ne pouvons pas rapprocher votre recherche à vous même ou avoir votre localisation.*" Rien de plus n'est dit sur une quelconque collecte de données. Super ! Sauf qu'une page bien particulière, nommée 'usage metrics' [^¹0] est présente et fait état de ceci :

[^⁷]: [Brave - Privacy](https://search.brave.com/help/independence)
[^⁸]: [Brave - Publicité](https://brave.com/private-search-ads/)
[^⁹]: [Brave - Politique de Vie Privée](https://search.brave.com/help/privacy-policy)
[^¹0]: [Brave - Données stockées](https://search.brave.com/help/usage-metrics)


> [Le moteur] "*est relativement nouveau et à ce titre nous sommes encore en train d'apprendre comment les personnes interagissent avec le site, ainsi que les performances. Spécifiquement, nous espérons apprendre les éléments suivants :*
> -   *Nombre de visites quotidiennes / hebdomadaires / mensuelles*
> -   *Nombre de visites récurrentes*
> -   *Nombre de requêtes par jour*
> -   *Combien de temps vous utilisez Brave Search*
> -   *Moyenne de la taille de vos requêtes*
> -   *Combien d'utilisateurs choisissent de laisser un commentaire sur Brave Search*
> -   *Le système d'exploitation que les utilisateurs utilisent (par ex. : macOS, Windows, etc.)*
> -   *Le navigateur que vous utilisez (par ex. : Brave, Chrome, Safari, etc)*
> -   *Les cliques et les vues sur les publicités qui apparaissent sur Brave Search*
> -   *Le pays associé aux cliques et vues*".

**C'est tout de même une liste assez conséquente... la jeunesse n'excuse pas tout !**

- Pour effectuer des recherches sur Brave Search via Tor, il est maintenant nécessaire d'activer le Javascript et WebAssembly, ce qui augmente le risque de désanonymisation.

> Brave n'en est pas à son coup d'essai, et ce n'est probablement pas fini (cf. notre article sur les [navigateurs](/debutant/navigateurs)). Enfin, même si la pertinence de leurs résultats est correcte, nous doutons qu'il utilise réellement son propre index (puisque les résultats sont souvent les mêmes que ceux de Google. Coïncidence ?)... il y a de très fortes chances qu'il applique les mêmes modes de censure que Google. Nous ne recommandons bien évidemment pas.
{.is-danger}

### Qwant

[Qwant](https://www.qwant.com/) est un moteur de recherche Français, à l'origine projet aux intentions plus que louables : renforcer la vie privée de ses utilisateurs lors des recherches web. Néanmoins, il apparaît que celui-ci n'a pas tout à fait tenu ses promesses [^¹1], [^¹2], [^¹3], [^¹4] et [^¹5]. Côté technique, il reprend donc les résultats de recherche de Bing (Microsoft), et coopère également avec ces derniers pour l'affichage de publicités.

Avons-nous besoin réellement d'aller plus loin ? Tentons-un coup d'oeil à leur [politique de vie privée](https://about.qwant.com/legal/confidentialite/) :
> "*Qwant stocke pour 7 jours les mots-clés entrés associés à un unique identifiant calculé sur le User Agent de votre navigateur et une empreinte salée (salted hash) de votre adresse IP. Après cette période, les mots clés ne sont plus associés à cet identifiant et sont stockés pour 12 mois à des fins d'analyses statistiques.*", plus loin :
> "*Qwant peut aussi collecter et transférer à son partenaire* [Microsoft] *votre adresse IP complète. Cette donnée est transférée à ce partenaire dans l'Union Européenne et peut être stockée ... pour un maximum de 18 mois.*"

**Je pense que nous pouvons nous arrêter là.**

[^¹1]: [Qwant le faux espoir](https://www.developpez.com/actu/303643/Qwant-le-faux-espoir-de-la-French-Tech-Le-moteur-de-recherche-souverain-mais-dependant-a-plus-de-60-pourcent-de-Bing-est-au-coeur-d-un-scandale-d-Etat)
[^¹2]: [Qwant scandale financier](https://effisyn-sds.com/2022/04/06/qwant-un-nouveau-scandale-financier-pour-la-macronie)
[^¹3]: [Qwant vilain petit canard](https://start.lesechos.fr/innovations-startups/tech-futur/qwant-comment-le-moteur-de-recherche-est-passe-despoir-a-vilain-petit-canard-de-la-french-tech-1206618)
[^¹4]: [Le moteur de recherche](https://www.ouest-france.fr/high-tech/huawei/le-moteur-de-recherche-francais-qwant-finance-par-huawei-pourquoi-cette-alliance-interroge-a9780406-cddc-11eb-baa9-ef1451863c79) français qwant financé par Huawei
[^¹5]: [Pour tout comprendre](https://www.leprogres.fr/france-monde/2019/09/23/pour-tout-comprendre-des-polemiques-autour-de-qwant) des polémiques autour de qwant

> L'adresse IP, le user-agent et les mots clefs de la recherche sont donc transmis : cela fait tout de même beaucoup. Ainsi nous ne recommandons par ce moteur de recherche bien entendu.
> Qui plus est, eux aussi ont sombré dans la censure [^¹6].
{.is-danger}

[^¹6]: [Qwant censure](https://twitter.com/QwantCom/status/1498755728877801472)


## Mention médiocre

-- **Les autres "experts de la vie privée"** --
<span class="red-text">:warning: **Ceci est volontairement ironique** :warning:</span>

### Swisscows
[Swisscows](https://swisscows.com/) possède ses serveurs en Suisse. Ils proposent un service "anonyme" via leur propre index, et ne "stockent aucune donnée personnelle de ses utilisateurs". Il intègre également des filtres de contenus sensibles.

A première vue, ce moteur semble partir sur de bons rails. Regardons maintenant leur politique de vie privée de plus près [^¹7] :
- Nous sommes dubitatifs quant à l'information concernant leur propre index de recherche, en effet : 
> "*Nous travaillons actuellement avec Bing et nous sommes très transparents à propos de cette coopération.*"

**Donc à priori ils travaillent avec Microsoft, même si visiblement ils ne partageraient pas d'information avec eux**...

[^¹7]: [Swisscows Privacy Policy](https://swisscows.com/en/privacy)

- La fonction de filtres de contenus sensibles implique qu'ils vérifient tout de même les requêtes transmises (notamment leur contenu) :
> "*Nous collectons les données des requêtes de recherches pour être capable de filtrer les spams et les recherches abusives. Malheureusement, nous sommes obligés de surveiller et bloquer les robots spam, sinon le traitement de ces demandes nous coûterait de l'argent et des ressources.*"

**Bon, cela part d'une bonne intention, mais vous auriez pu le dire explicitement dès le début que vous surveilliez les requêtes !**

- Ensuite, nous voyons cette phrase aux lourdes conséquences :
> "Après 7 jours nous supprimons toutes vos informations personnelles (comme votre adresse IP et le user agent) des données de recherche."

**Ah, donc finalement vous collectez des données très personnelles ?**

- On termine sur le fait que le moteur ne fonctionne absolument pas sans Javascript. Pour un moteur clamant l'anonymat des requêtes, on a vu mieux.

> Inutile de vous dire que nous ne recommandons pas Swisscows.
{.is-danger}

### Ecosia
[Ecosia](https://www.ecosia.org) se décrit comme le moteur de recherche "qui plante des arbres". Base son index sur les résultats Bing, et assure ne pas se soucier de vos données mais plutôt des arbres !

En regardant de plus près leur politique de vie privée [^¹8], nous nous rendons compte que le moteur n'est pas si privé que cela par défaut :

> "*Afin de fournir des services essentiels tels que les paramètres de langue et la protection contre le spam (voir ci-dessous), nous collectons votre adresse IP pendant sept jours maximum avant de la supprimer.*" 

ou encore :

> "*Nous ne recueillons qu'une quantité limitée de données pour améliorer nos services. Si vous ne souhaitez pas nous donner accès à ces données, vous êtes libre d'activer « Do Not Track » à partir des paramètres de votre navigateur.*".

Puis nous lisons que :

> "*Ecosia utilise les cookies pour enregistrer vos paramètres, notamment pour savoir quelle langue d’affichage privilégier.* [...]".

Inutile d'aller plus loin, sachant également qu'ils ont récemment opter pour intégrer Cloudflare dans leur infrastructure.

> Ce moteur aurait pu être une alternative de choix, alliant éthique environnementale et vie privée, mais leur politique n'est pas encore à la hauteur. Non recommandé.
{.is-danger}

[^¹8]: [Ecosia](https://info.ecosia.org/privacy)

### Discrete Search
Nous n'allons pas passer du temps à analyser leur moteur, celui ci ne fonctionnera tout simplement pas sur Librewolf, Ungoogled Chromium, Tor, Pale Moon... Bref il est inutile d'en parler.

### Lilo
Ce moteur n'est pas open-source, c'est déjà un gros point négatif pour nous. Mais ce moteur visiblement est solidaire et éthique, ça a l'air vraiment pas mal... Tentons un rapide coup d'oeil à leur [politique](https://www.lilo.org/votre-vie-privee-avec-lilo/) de vie privée (notamment la section "Lorsque vous utilisez Lilo Moteur de Recherche") :

> "*Lorsque vous effectuez une recherche sur Lilo, nous sommes amenés à traiter différentes informations pour afficher les réponses à vos recherches de manière pertinente, lutter contre la Fraude, respecter nos obligations légales et vous attribuer les précieuses gouttes d’eau associées à vos recherches* 😊
>
> *Il s’agit des informations suivantes : le navigateur que vous utilisez (le User Agent) ; vos préférences de session (afficher les résultats en français par exemple) ; votre adresse IP ; La zone géographique approximative à l’origine de la recherche (déduite de l’adresse IP) ; et éventuellement des données sur votre comportement de navigation, comme le temps écoulé entre 2 clics par exemple (toujours dans l’objectif de vérifier que l’utilisateur n’est pas un robot qui clique à la vitesse de la lumière 😉)*.
>
> *Afin de vous fournir des résultats pertinents et de générer du revenu que nous pourrons transformer en argent pour financer les gouttes d’eau, nous avons un partenariat avec Microsoft Bing (qui respecte le Règlement Général sur la Protection des Données) pour la fourniture des résultats de recherche et des publicités. C’est pourquoi Lilo peut être amené à transmettre ces mêmes données à ce partenaire. Dans ce cas, conformément à sa politique de confidentialité, ce partenaire peut être amené à conserver ces données sur une période maximum de 18 mois.*"

> Bien, tout est dit. Au suivant...
{.is-danger}

## Mention passable

### StartPage
[StartPage](https://www.startpage.com/) est un moteur de recherche fondé sur la "*protection stricte de la vie privée*"" car d'après eux "*La vie privée est un droit fondamental de l'être humain*" ! Il emprunte les résultats du moteur de recherche Google, que StartPage indexe, et font comme Lilo en coupant le pistage publicitaire ciblé, semble-t-il. Cependant, certains utilisateurs de Tor et/ou de VPN peuvent rencontrer des difficultés, car StartPage bloque certaines adresses IP de serveurs connus.

Alors, ce navigateur serait-il l'heureux élu ? Tentons de creuser un peu plus dans leur politique de vie privée [^¹9] :
> "*Nous n'enregistrons pas votre adresse IP*"

**Une intention très louable.**

> "*Nous ne servons aucun cookie de suivi ou d'identification*"

**Alors tout va bien.**

> "*Nous mesurons le trafic global et d'autres statistiques - strictement anonymes. Ces statistiques peuvent inclure le nombre de fois où notre service est accédé par un certain système d'exploitation, un type de navigateur, une langue, etc., mais nous ne savons rien des utilisateurs individuels.*"

**Ouch... syndrôme Duckduckgo ?**

> "*Afin de permettre la prévention de la fraude par clic, certaines informations système non nominatives sont partagées* [...]"

**Re-ouch... Nous allons devoir faire confiance à StartPage sur le côté "informations non nominatives" car ils ne disent pas du tout en quoi ces données consistent !**

[^¹9]: [Startpage Privacy Policy](https://www.startpage.com/fr/privacy-policy)

Pour terminer, StartPage a récemment été racheté par une société de publicité, *System1*. Même s'ils assurent ne pas changer de politique, il va falloir leur faire confiance encore sur ce point, à l'heure où la confiance est rompue, cela fait un peu beaucoup. Bon après, tout n'est pas si terrible, pour le moment, bien que les résultats soient réellement mauvais, probablement parce que Google applique une censure massive [^²0].

[^²0]: [Google censorship campaign](https://www.naturalnews.com/2019-04-09-leaked-memos-prove-google-is-a-massive-criminal-enterprise-felony-election-meddling-and-racketeering.html)

À part cela, StartPage marche parfaitement sans Javascript, et fournit une fonction "*mode anonyme*" qui vous permettra de visiter des sites sans révéler votre "identité".

> Bien que l'affaire ne soit pas si noire, nous avons du mal à recommander ce moteur de recherche. Donc si vous faites confiance en des sociétés lucratives (parfois évoluant sur leur politique), ce moteur peut vous convenir. Autrement, passez votre chemin !
{.is-warning}

#### MetaGer
[Metager](https://metager.org/) est un méta-moteur de recherche (agrégation de plusieurs sources) avec accent sur la recherche "anonyme", notamment via un proxy. Il s'agit d'une organisation à but non lucratif, qui utilise l'"énergie verte" pour leurs serveurs. Attention, car les résultats sont donnés sans filtre ni classement par clic, et peuvent parfois paraître inconsistants.

Rentrons dans le vif du sujet :
- Ceci :
> "Pour protéger notre service de la congestion, nous devons limiter le nombre de requêtes de recherche par connexion Internet. Dans ce seul but, nous stockons l'adresse IP complète et un horodatage pour un maximum de 96 heures."

- Et ceci :
> "Pour recevoir cette publicité, nous transmettons à nos partenaires publicitaires les deux premiers blocs de l'adresse IP ainsi que certaines parties non identifiables du user agent."

- Ou ceci :
> "Lors de la visite des sites web du domaine "suma-ev.de" \*, les données suivantes sont collectées et stockées pendant une semaine au maximum : Votre adresse IP, Nom et URL du fichier récupéré, Date et heure de l'accès..."
*\* : SUMA-EV est l'association derrière Metager*

Ne nous plaisent guère en terme de vie privée !  Néanmoins, ils sont clairs et concis sur leurs pratiques et n'annoncent pas clairement qu'ils ne récoltent pas de données personnelles sur leur page d'accueil, donc nous savons à quoi nous en tenir.

> Hormis leur politique de vie privée peu reluisante, il est à noter que les résultats de recherche sont d'un _bon niveau_, notamment via le site miroir allemand [Metager.de](https://metager.de) qui inclut les résultats Yandex. Ceci est d'autant plus vrai pour les images. MetaGer propose également un bon outil de proxy anonyme et fonctionne très bien sans Javascript. Donc tout n'est pas forcément à jeter... du moment que vous leur faites confiance !
{.is-warning}

### Gibiru
[Gibiru](https://www.gibiru.com) "Unfiltered Private search" ou recherche privée non filtrée en français. Il interroge directement l'index Google, sans filtre, mais agit comme un proxy en utilisant leur propre VPN, ceci afin de ne rien partager sur l'utilisateur avec Google. Ces requêtes et les informations personnelles qui y seraient associées ne sont visiblement d'ailleurs pas stockées sur les serveurs de Gibiru à en croire leur politique de vie privée [^²1].

[^²1]: [Gibiru Privay Policy](https://gibiru.com/privacy-policy/#privacy-policy)

> Gibiru a bien évolué depuis quelques années. La mise en place de leur proxy/VPN est *relativement* jeune et permet d'obtenir les résultats Google avec un niveau de vie privée intéressant. Le tout est la confiance que nous mettons dans ce moteur !
{.is-info}

## Mention Très Bien
Oui bon alors, vous allez me dire : "en fait, tous les moteurs de recherche sont des vendus !". En effet, la grande majorité des moteurs n'ont au final que faire de votre vie privée, ce qui restreint réellement les choix... Mais heureusement, quelques moteurs ou méta-moteurs peuvent être dignes de confiance, pour le moment :

### La valeur sûre - SearX(NG)

[SearX](https://searx.github.io/searx/) est un moteur de recherche libre, qui agrège les index de plusieurs moteurs. Il marche par instance, et peut donc être auto-hébergé par vos propres soins, ou alors être accédé sur des instances hébergées par des entités particulières. Fonctionne parfaitement sans Javascript. La version NG améliore la gestion des images.

Vous trouverez sur [cette page](https://searx.space/) toutes les instances SearX. Attention cependant, elles sont tenues par des particuliers, des fondations, des entreprises. Vous ne savez pas forcément ce qu'ils font de vos informations personnelles ! SI vous en avez les compétences, vous pouvez héberger une instance vous-même.

> SearX est le must côté open-source dont la pertinence des résultats est équilibrée.
{.is-success}

### Le petit jeune - Whoogle

[Whoogle Search](https://pypi.org/project/whoogle-search/) est un méta moteur de recherche qui indexe en priorité les résultats de Google, le côté tracking en moins. C'est un moteur qui, à l'instar de SearX, fonctionne par instance (vous pouvez d'ailleurs en déployer une vous-même plus ou moins facilement !).

> Whoogle constitue certainement une des surprises surtout si l'on recherche les résultats de l'index de Google ! Ne lui reste plus qu'à simplifier encore son approche afin qu'une grande communauté l'adopte et qu'il corrige ses défauts de jeunesse : il est par exemple souvent possible d'être bloqué à un moment donné (les robots Google bloquant les requêtes). Problème en cours de résolution, mais bloquant !
{.is-info}

### Le "trublion" - Mojeek

[Mojeek](https://www.mojeek.com) est un méta-moteur de recherche basé au Royaume-Uni. Il possède son propre index. Il s'agit pour l'instant du moteur le plus respectueux de votre vie privée.

**Malheureusement, ce moteur n'est pas *open-source* et ne compte pas le devenir dans un avenir proche**. Mais ce ne serait pas immuable d'après leur équipe : 
> "*Nous n'avons en effet pas ouvert Mojeek. Il est très difficile pour un moteur de recherche de l'être complètement du fait du référencement ; en effet, un moteur ouvert offrirait plus de chance à la manipulation d'acteurs cherchant à jouer le classement dans les résultats. Cela dit, nous apprécions grandement les initiatives à sources ouvertes, comme cURL et Linux, et en tirons profit. Nous n'excluons donc pas la possibilité d'ouvrir certains de nos codes source à l'avenir, si nous y voyons un avantage. Le facteur déterminant ici est qu'une telle initiative profite à la fois aux utilisateurs et à l'entreprise.*" ; Mojeek Dev

> Si vous n'avez pas de problème avec les sources fermées, c'est probablement le moteur qu'il vous faut, même si nous devons bien l'avouer les résultats de recherche sont assez imprécis.
{.is-info}


# Pour conclure
Nous avons tenté d'être le plus transparent possible, et de limiter le choix aux meilleures options.

Pour synthétiser :

-  **[SearX](https://searx.github.io/searx/)** reste la meilleure alternative, pour une personne plus adaptable et investie, et en sélectionnant avec une bonne instance _sans Cloudflare_. Voici les instances que nous recommandons :
     - https://searx.tiekoetter.com 🇩🇪 
     - https://search.unlocked.link 🇫🇮
     - https://spot.ecloud.global  🇫🇷 (instance maintenue par la eFoundation de la ROM /e/OS ;))
-  **[Mojeek](https://www.mojeek.com/)** pour toute personne ayant un intérêt pour leur vie privée, mais ne soyez pas trop regardant sur les résultats et sur le code source propriétaire !
- **[Gibiru](https://gibiru.com/)** reste une alternative crédible, notamment pour les résultats Google.
- Concernant **StartPage**, c'est à vous de décider si vous leur faites confiance, de notre côté ce sera non. 
*Nous préférons dans ce cas **MetaGer**, pour les images par exemple*.

{.grid-list}

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): marmotte, Ayo*
<br>