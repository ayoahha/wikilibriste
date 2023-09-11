---
title: Les gestionnaires de mots de passe
description: Cet article traite des gestionnaires de mots de passe et les outils recommandés...
published: true
date: 2023-06-21T14:09:11.169Z
tags: chiffrement, mots de passe, gestionnaire, debutant, intermédiaire, débutant, intermediaire
editor: markdown
dateCreated: 2022-11-25T13:43:14.323Z
---

Cet article va s'intéresser à un outil qui est assez méconnu du grand public : les gestionnaires de mots de passe.

Avoir une politique très robuste de mot de passe est aujourd'hui devenu **obligatoire** et crucial du fait de la multiplication des services nécessitant une authentification via la paire "Login"/"Mot de passe". Il est pratiquement de nos jours impossible d'utiliser un service sans cette protection.

Nous avons préalablement posé les bases concernant cette politique, à savoir utiliser un mot de passe **unique**. Il est évident qu'appliquer cette bonne pratique implique de retenir des dizaines de mots de passe différents, ce qui pour le cerveau humain est pratiquement impossible. 

> Plutôt que d'écrire tous ses mots de passe dans un cahier ou sur une feuille volante (on évitera cette pratique n'est-ce pas ?!), c'est ici qu'entrera en jeu le gestionnaire de mots de passe.
{.is-info}


Les solutions à oublier
=======================

Ne tournons pas autour du pot : Exit les solutions reposant sur le "cloud" (pratiquement toutes les solutions du marché !) :
- :x: Dashlane
- :x: 1Password
- :x: Lastpass
- :x: Nordpass
- :x: Enpass
- :x: Psono
- Bitwarden (uniquement sa solution en ligne, hors auto-hébergement donc)
- Nous en oublions peut être...
{.grid-list}

Exit également les solutions proposées dans des "packs" :
- :x: Avast
- :x: BitDefender
- :x: Symantec
- :x: Eset
- Etc.
{.grid-list}

et tout autre service similaire proposé dans des solutions anti-virus ou protection d'ordinateur.

Exit enfin les gestionnaires des navigateurs internet :
- :x: Firefox
- :x: Chrome
- :x: Opera
{.grid-list}

et autres navigateurs, qui reposent tous sur des solutions de types "cloud" (en ligne).

**La grande majorité de ces solutions impliquent de graves failles de sécurité** : en effet, ces applications déchiffrent à la volée, ne laissent aucun choix dans les algorithmes (parfois obsolètes!) et surtout stockent les informations sur leurs serveurs en oubliant parfois que ces informations sont liées à des mots de passe, **item critique** pour les utilisateurs, serveurs qui parfois font l'objet de fuites de données ([LastPass, My1Login, NeedMyPassword, PasswordBox, et RoboForm](https://www.usenix.org/sites/default/wp-content/uploads/sites/34/conference/protected-files/sec14_slides_li-zhiwei.pdf), [Roform incident](https://thehackernews.com/2014/07/critical-vulnerability-and-privacy.html), [MyPasswords, Informaticore, LastPass, Keeper, F-Secure Key, Dashlane, Keepsafe, Avast Passwords, et 1Password : une multitude de gestionnaires et leurs failles](https://team-sik.org/trent_portfolio/password-manager-apps/), [Lastpass mise à jour de sécurité](https://blog.lastpass.com/2016/07/lastpass-security-updates.html/), [Lastpass et son extension](https://blog.lastpass.com/2017/03/security-update-for-the-lastpass-extension.html/), [OneLogin : Un attaquant a obtenu accès à un pack de mots de passe AWS](https://www.onelogin.com/blog/may-31-2017-security-incident), [Keeper : le service expose des mots de passe](https://bugs.chromium.org/p/project-zero/issues/detail?id=1481&desc=3), [Firefox confirme une brèche révélant des mots de passe](https://support.mozilla.org/en-US/kb/firefox-password-manager-alerts-breached-websites) [Lastpass incident de sécurité 2022](https://blog.lastpass.com/2022/11/notice-of-recent-security-incident/), ... on va peut être s'arrêter là !). Sans parler de la revente de vos métadonnées...

> **Ces solutions sont donc À FUIR absolument.**
{.is-warning}


La seule façon à ce jour **_validée et certifiée_** est d'utiliser un logiciel à sources ouvertes, et de stocker ses mots de passe sur une base que vous garderez sur votre équipement et dont les informations ne seront pas divulguées sur un réseau (on parle donc de gestion hors-ligne, ou offline).

Cela réduit drastiquement le nombre de solutions, encore plus lorsque nous nous adressons au grand public : à ce jour, 2 outils _simples_ seulement permettent de respecter cette exigence.

Nous en reparlons plus loin.

La sécurité autour des mots de passe
====================================

Robustesse
----------

Vous vous êtes peut être demandé si le mot de passe que vous avez choisi était bien assez robuste pour être considéré comme un mot de passe *fort*.

Nous sommes capables de définir la robustesse d'un mot de passe, ou aussi appelée _**entropie**_. L'entropie se définit comme la résistance du mot de passe à une attaque par énumération (aussi appelée attaque "force brute"). Calculer l'entropie est assez simple : il s'agit d'un rapport entre la longueur du mot de passe (en nombre de caractères) et le nombre de symboles possibles dans l'énumération (30, 60, 90...).

Heureusement, des [outils](http://cryptologie.free.fr/crypto/entropie.html) permettent de les calculer :)
Ou celui de l'[ANSSI](https://www.ssi.gouv.fr/administration/precautions-elementaires/calculer-la-force-dun-mot-de-passe/).

> **Pour ce qui est de la valeur minimum à obtenir et recommandée par les experts** :
> L'entropie minimum à atteindre est **80/90**.
> L'entropie optimale est **110/130**.
{.is-success}


Algorithme
----------

Tout comme fait dans d'autres articles, nous allons présenter rapidement les aspects techniques sur les algorithmes que vous devrez utiliser afin d'assurer la sécurité de votre base de données de mots de passe :

-   **Chiffrement de la base de données :**
    -   Préférez :
        -   _Avec accélération matérielle_ : AES (Rijndael) 256 bits minimum, avec CBC ou GCM, avec HMAC-SHA-2 ou HMAC-SHA-3 pour les digests signatures (ce que Keepass utilise par défaut) ; Préférez SHA-3 tout de même.
        <span class="red-text"><strong>Une note concernant HMAC-SHAx</strong> : si vous souhaitez utiliser un token physique (type Yubikey, Nitrokey...), il est possible que ces tokens ne supportent que *HMAC-SHA1*. Par conséquent, vous devrez accepter l'utilisation de cet algorithme, le temps que le token soit compatible avec les successeurs.</span>
        -   _Sans accélération matérielle_ : idem ci-dessus ou si disponible :
            -   ChaCha20 ou XChaCha20
            -   Serpent
            -   TwoFish
    -   On évite tout le reste.

-   **Dérivation de clés/Hashs pour stockage mots de passe :**
    -   Préférez Argon2 ou Scrypt (si Argon n'est pas proposé).
    **Attention** avec Argon2d, visiblement vulnérable à certaines attaques par canaux auxiliaires ("side channel attack"). Préférez donc **Argon2id**.
    -   Bcrypt si ces 2 algorithmes ne sont pas disponibles.
    -   PBKDF2 en dernier recours, avec un facteur d'itération de 600000 au minimum de concert avec HMAC-SHA256, ou de 1300000 minimum avec HMAC-SHA1.
    -   On évite l'utilisation seule de SHA-3, SHA-2, SHA-1, MD5, qui sont moins adaptés dans ce cas de figure. Ou alors SHA-3 (512) avec une implémentation bien spécifique et robuste (étirement, salage, etc...).

Les outils
==========

Comme évoqué ci-avant, très peu d'outils respectent l'exigence d'avoir une base hors ligne (en local chez soi) et d'une solution libre et open-source sur laquelle des audits de sécurité auront pu être publiés publiquement. 

**Par ordre de niveau de sécurité, voici les 2 solutions recommandées :**

Keepass
-------

[Keepass](https://keepass.info/)

Le seul gestionnaire de mots de passe certifié[^¹] par l'ANSSI (l’Agence Nationale de la Sécurité des Systèmes d’Information) qui est l'agence en charge des recherches en cybersécurité et des audits de sécurité en France. Keepass est certifié depuis 2010 (version 2.10) et continue à être audité. De plus, le BSI, qui est l'équivalent de l'ANSSI en Allemagne, a de son côté également audité[^²] et recommandé l'application aux PME en 2018.

Au-delà, des audits ont été menés lors du tout premier FOSSA européen ("Free and Open Source Software Audit") en 2016 puis en 2019[^³], ainsi que par nos amis suisses[^⁴]. Tous ces audits ont permis de conclure au niveau élevé de sécurité de l'application.

> **Ce qui en fait donc le candidat idéal pour gérer vos mots de passe. De plus, Keepass vous permet de générer aléatoirement des mots de passe, et de calculer l'entropie.**
{.is-success}

[^¹]: [Keepass](https://www.ssi.gouv.fr/entreprise/certification_cspn/keepass-version-2-10-portable/) certification.
[^²]: [BSI](https://www.allianz-fuer-cybersicherheit.de/SharedDocs/Downloads/Webs/ACS/DE/BSI-CS/BSI-CS_003.html)  audit.
[^³]: [Audit 2016](https://joinup.ec.europa.eu/sites/default/files/ckeditor_files/files/DLV%20WP6%20-02-%20Summary%20of%20the%20evaluation%20of%20results%20_KeePass_published.pdf).
[^⁴]: [Audit Suisse](https://www.bit.admin.ch/bit/de/home/dokumentation/kundenzeitschrift-eisbrecher/eisbrecher-archiv/kundenzeitschrift-eisbrecher-ausgabe-68/keepass.html).

Malheureusement, l'outil ne jouit pas d'une interface élégante et c'est son *gros point noir* : cette interface paraît plutôt très austère ! C'est pourquoi certains développeurs ont eu la brillante idée de créer des forks, qui non seulement possèdent les mêmes caractéristiques en terme de sécurité, mais proposent une interface un peu plus jolie :) :
-   [KeepassXC](https://keepassxc.org/) pour une utilisation sur ordinateur fixe/mobile
-   [KeepassDX](https://www.keepassdx.com/) pour une utilisation sur Android

> Nous avons créé un [tutoriel spécial](/tutoriels/keepass) pour vous guider sur KeepassXC. N'hésitez pas à le consulter.
{.is-success}

Bitwarden
---------
[Bitwarden](https://bitwarden.com/)

Nous évoquions plus haut dans les solutions à fuir le logiciel *Bitwarden* ; nous évoquions cela dit leur solution "cloud" ([^⁵] et leur réponse ici [^⁶]). Ils proposent en revanche une solution alternative qui s'apparente à la gestion en local d'une base de mots de passe.

[^⁵]: [Bitwarden Flaw security](https://palant.info/2023/01/23/bitwarden-design-flaw-server-side-iterations/) - côté Serveur.
[^⁶]: [Bitwarden répond](https://portswigger.net/daily-swig/bitwarden-responds-to-encryption-design-flaw-criticism) - et modifie ses paramètres de sécurité !

C'est cette fonction qu'il faudra regarder. Néanmoins, cette fonction sera réservée à ceux qui auront des connaissances et les moyens de créer un serveur, de le maintenir et de l'utiliser d'une façon assez sécurisée : on évite d'ouvrir ce serveur vers l'extérieur, on durcit l'OS, etc. de sorte à réduire la surface d'attaque.

Soyez bien conscients que cette fonction n'est pas aussi sécurisée qu'une base en local sur la machine comme Keepass le propose. En effet, cela implique des requêtes sur votre réseau local, réseau qui peut potentiellement être infiltré ; attention ceci est vraiment peu probable, mais le risque n'est pas nul, surtout si vous avez l'habitude de télécharger tout et n'importe quoi, ou avez un certain profil public.

> **Il s'agira de notre deuxième recommandation.**
{.is-warning}


Les objectifs
-------------

Avec ces 2 outils donc, il vous sera possible de faire plusieurs choses :
- retenir et stocker **TOUS** vos mots de passe, phrases de passe et phrases de récupération, données de cartes de crédit si nécessaire, potentiellement vos clés de sécurité, etc.
- générer des mots de passe forts, avec une entropie élevée et qui correspond au minimum aujourd'hui admis.
- (**seulement Keepass**) choisir les algorithmes qui vous conviendront le mieux, et qui seront les plus adaptés à votre machine et à ses capacités.

Votre base de données sera bien entendu protégée (chiffrée) : en effet, vous n’aurez ici qu’un seul et unique mot de passe à retenir ; dans ce cas, ce mot de passe doit être extrêmement fort et gardé le plus secret possible. 

Il sera aussi possible de multiplier les bases de données pour éviter que si votre mot de passe est corrompu toute la base le soit. La contrepartie étant de retenir plusieurs mots de passe forts.

*_Exemple_ : une base pour les banques et une autre pour le reste.*


Générateurs de mots de passe
============================

Deux outils, aussi appelés "*stateless password generator*", sont disponibles également :
-   [Lesspass](https://www.lesspass.com/)
-   [Spectre](https://spectre.app) qui est le successeur du _très critiqué_ masterpassword
*Note : Pour Spectre, à l'heure où nous écrivons cet article, la seule application Spectre disponible est sur Apple Store ! Les autres applications sont toujours en développement, bien que les applications masterpassword sont toujours disponibles...*

Ces outils vous permettront de générer des mots de passe, basés sur quelques informations personnelles (adresse du site, identifiant...), sans avoir besoin de les stocker quelque part et donc retrouvables (i.e. recalculables) à n'importe quel moment. 

**Même si sur le papier cela semble pratique et a priori une bonne idée, retenez bien que pour l'instant aucun audit de sécurité indépendant n'a encore été effectué sur ces solutions.**

Nous attirons le lecteur sur un risque vraisemblable :
- *La falsification du site internet* : un attaquant peut très bien usurper l'identité du site (expiration du certificat par ex.) et/ou rediriger quelqu'un vers un site miroir qu'il aura reconstruit. Dès lors, vous rentrez votre mot de passe maître et les données et l'attaquant pourra retrouver les mots de passe que vous aurez recherchés.

**Attention également lors du renouvellement/changement de mots de passe : pour Lesspass, il y a un compteur qui peut être incrémenté ; mais pour Spectre, il sera difficile de renouveler et plus d'informations seront à mémoriser.**


> Néanmoins, ces outils peuvent être intéressants pour certains types de site, hors banques et sites sensibles donc. Pour autant, nous recommandons tout de même Keepass et Bitwarden.
{.is-info}


Conclusion
==========

Afin de terminer cet article, rappelons donc dans l'ordre les outils recommandés :
1. :one: Keepass
2. :two: KeepassDX / KeepassXC
3. :three: Bitwarden hors ligne (base auto hébergée)
4. :four: Lesspass
5. :five: Spectre
{.grid-list}

> Bien entendu, nous ne dirons jamais assez que des applications _sans faille_ cela n'existe pas et n'existera jamais. Ce type de logiciel peut très bien contenir des failles qui seront découvertes dans quelques temps... Il est donc important de garder une très bonne hygiène numérique et de bonnes pratiques d'isolation.
{.is-warning}

# Annexe
Pour continuer sur ce sujet, il existe quelques autres alternatives, mais elles sont réservées à ceux qui ont de solides connaissances, voilà pourquoi elles n'apparaissent pas dans cet article. **Si vous estimez que la chose est utile, n'hésitez surtout pas à commenter cet article et nous le demander...**

- Nous pouvons citer par exemple [Pass](https://www.passwordstore.org/), le gestionnaire de base d'Unix, en ligne de commandes ! Eh oui, car chez \*nix, nous aimons réellement les lignes de commandes :)
Le client [Android](https://github.com/android-password-store/Android-Password-Store) est également de la partie.

> Non seulement vous devrez maîtriser la ligne de commandes, mais vous devrez également maîtriser la gestion GPG (cf. article dédié).
> Attention toutefois, **la faiblesse de la cryptographie asymétrique pour la gestion de mots de passe est à prendre en considération, compte tenu des futurs dangers notamment liés au quantique [^7].**
{.is-info}

[^7]: [Pass](https://rot256.dev/post/pass/) et aspects cryptographiques.

- Nous pouvons également citer un outil récent, basé sur Age : [pa](https://github.com/biox/pa), qui automatise l'utilisation de age avec un gestionnaire de mot de passe Unix.

> Encore une fois, ici, vous devrez maîtriser les aspects liés au chiffrement (cf. article dédié) et avoir connaissance des faiblesses de la cryptographie asymétrique pour la gestion de mots de passe.
{.is-info}

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo*
<br>