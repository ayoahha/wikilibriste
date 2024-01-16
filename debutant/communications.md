---
title: Les communications numériques et la vie privée
description: Cet article tente de montrer comment il est possible de communiquer sur internet tout en gardant sa vie privée...
published: true
date: 2024-01-16T13:23:34.065Z
tags: messageries, email, courriel
editor: markdown
dateCreated: 2022-11-27T12:34:35.949Z
---

# Courriel

> **Vous trouverez ci-après 2 onglets : "Pour débuter" et "Aller plus loin".
> -- L'onglet "Pour débuter" pour ceux qui ne souhaitent pas de justification ou d'analyse concernant les choix proposés.
> -- L'onglet "Aller plus loin" pour les personnes désireuses de comprendre nox choix.**
{.is-warning}


# Tabs {.tabset}
## Pour débuter

### Les fournisseurs de service courriel

Peu de fournisseurs de service courriel respectent réellement notre vie privée, voici donc une liste de ceux dignes d'intérêt :
- [Posteo *L'une des meilleures solutions, que nous recommandons en premier lieu : peu de données personnelles lors de l'inscription, un paiement cash possible (le service est payant à 1E/mois) et tournée vers une limitation de l'empreinte écologique.*](https://posteo.de/fr)
- [Disroot *Le célèbre mandataire discret, tourné vers le respect de la vie privée de ses utilisateurs. L'offre est gratuite mais limitée à un stockage de 1Go. Vous pouvez les soutenir en souscrivant à plus de stockage, ce qui leur permettra de perdurer.*](https://disroot.org/en/services/email)
- [Tutanota *Le fournisseur de service courriel allemand, tourné également vers le respect de la vie privée de ses utilisateurs. L'entreprise fournit même un service pour lanceurs d'alerte. Avec néanmoins quelques questionnements \*.*](https://tutanota.com/)
- [ProtonMail *Très connu, le fournisseur suisse propose des services non seulement de courriel, mais aussi de cloud, de calendrier partagé et de VPN. L'entreprise jouit d'une solide réputation, même si encore une fois tout n'est pas si rose \*\*.*](https://www.protonmail.com/)
{.links-list}


\* : Concernant Tutanota, il est à noter que le gouvernement allemand a réussi à les contraindre à utiliser une porte dérobée **pour tous les mails échangés en dehors des processus de chiffrement de bout en bout** (mail du domaine @tutanota vers mail d'un autre domaine (@gmail / @live, etc.), pour lequel aucun mot de passe de chiffrement n'a été créé par exemple - les courriels Tutanota :left_right_arrow: Tutanota en sont a priori exemptés : préférez donc au maximum utiliser le chiffrement).
**Source** : [Tutanota et la porte dérobée](https://www.01net.com/actualites/le-service-mail-le-plus-securise-au-mondecontraint-d-integrer-une-backdoor-pour-la-police-2012718.html).

\*\* : Pour les profils les plus à risques (activistes, avocats, opposants politiques...), il est bon de savoir que Proton AG a été obligé de livrer des adresses IP de comptes d’activistes français en 2021 à la demande des autorités. Ce qui semble vouloir dire que les adresses IP peuvent potentiellement être retrouvées... Nous préconisons dans ces cas particuliers de faire donc attention sur la confiance que vous portez à Proton AG.
**Sources** : [ProtonMail dans la tourmente](https://www.begeek.fr/protonmail-dans-la-tourmente-apres-avoir-donne-ladresses-ip-dun-activiste-aux-autorites-360546) et [ProtonMail balance des activistes parisiens](https://korii.slate.fr/tech/technologie-protonmail-balance-activistes-parisiens-youth-for-climate-arrestation-adresse-ip-suisse-europol).

---
Il est à noter que si vous possédez un modèle de menaces moyen à élevé, il est nécessaire voire primordial d'appliquer une couche de sécurité à vos échanges par courriel.

**Pour cela, nous utiliserons l'outil GnuPG (ou GPG), que nous vous présentons [ici](/intermediaire/chiffrement) et [ici](/tutoriels/gnupg).**

**Concernant les fournisseurs :**
- [Posteo](https://posteo.de/fr) : Posteo donne la possibilité d'utiliser pleinement GPG via le client web ou une application différente (cf. partie suivante).
- [Disroot](https://disroot.org/en/services/email) : Disroot vous permet également d'utiliser GPG pleinement.
- [Tutanota](https://tutanota.com/) : Tutanota permet d’ajouter un mot de passe à chaque courriel, mais également de pouvoir protéger vos courriels grâce à GPG. Néanmoins moins optimal que Posteo et Disroot car les clés ne vous appartiennent pas et sont gérées par Tutanota.
- [ProtonMail](https://www.protonmail.com/) : Ici encore, vous pouvez ajouter une protection par mot de passe ou utiliser GPG, mais cela dit, ici encore, les clés ne vous appartiennent pas et sont gérées par Proton AG.

Si toutefois vous souhaitez garder votre fournisseur actuel et que celui-ci ne proposait pas de protection et/ou si vous souhaitez garder vos comptes Google, Microsoft (ce que nous ne recommandons pas si votre modèle est élevé !), certaines solutions existent afin d’appliquer une protection bout en bout :
- [Mailvelope](https://mailvelope.com/en/) : vous pourrez grâce à Mailvelope utiliser GPG afin de protéger vos échanges courriel sans changer de fournisseur (compatible avec certaines messageries, pas toutes).
- [Enigmail](https://www.enigmail.net/index.php/en/) : est intégré à l'application Thunderbird, si vous utilisez ce gestionnaire de courriel. Il implémente PGP/GPG afin de protéger vos échanges courriel.

### Les applications
Il est recommandé d'utiliser directement les clients web fournis par votre fournisseur de service. Néanmoins, si vous souhaitez toutefois utiliser une application à part, préférez des applications à sources ouvertes voire libres, comme :
- [Thunderbird *GNU/Linux, MacOS, Windows*](https://www.thunderbird.net/fr/)
- [Evolution *GNU/Linux*](https://wiki.gnome.org/Apps/Evolution)
- [FairEmail *Android*](https://email.faircode.eu/)
- [K9-Mail *Android*](https://k9mail.app/)
{.links-list}


## Pour aller plus loin

Le courrier électronique, courriel pour franciser la chose (communément appelé "e-mail", pour 'electronic mail', par pur anglicisme) est un moyen de communication aussi ancien que les messageries. L'avènement des messageries dites "instantanées" a porté un gros coup dur au courriel. Néanmoins, celui-ci est tout de même encore beaucoup utilisé et a su s'imposer au fil du temps de par son aspect de praticité pour l'utilisateur.

Le courriel est encore massivement utilisé, notamment au sein des entreprises et des administrations, mais aussi par les journalistes, activistes et personnes ayant un besoin de sécurité de haut niveau. Cela dit, intrinsèquement, un courriel n'a pas été pensé pour être **sécurisé**, du tout, ce qui porte la confidentialité des échanges à néant ! Il faut pour cela lui adjoindre des couches de sécurité.

Il y a quelques années, l'histoire autour d'Edward Snowden a quelque peu changé les choses ; PGP a été mis en lumière et il s'avère qu'aujourd'hui, ce mécanisme est de plus en plus utilisé pour protéger les communications par courriels. Beaucoup d'outils (en ligne ou hors ligne) implémentent une façon d'utiliser des clés PGP simplement.

Cet article tente donc de présenter les aspects pratiques du courrier électronique ainsi que l'importance de la sécurité autour du courriel.

### Le courriel
#### Le service
Le principe du courriel est plutôt très simple : vous créez ce que l'on nomme une "adresse email" chez un fournisseur (gmail pour google, outlook pour microsoft, yahoo pour ne citer que les plus connus) ou une adresse peut déjà vous être fournie par votre FAI (orange, bouygues, etc.) avec vos accès internet.

Techniquement, cela fait appel à une architecture Client-Serveur : chaque courriel que vous transmettez passe par les serveurs de votre fournisseur pour ensuite être acheminé/distribué vers le destinataire (ou les destinataires).

#### Les clients courriel
Afin de pouvoir écrire et transmettre ou recevoir des courriels de façon conviviale et pratique avec une interface graphique, nous avons besoin de ce que l'on nomme un "Client courriel" ou plus simplement une application courriel. Deux types d'applications existent :
- Le webmail : qui consiste à visiter une page web comme n'importe quelle autre page internet, c'est par exemple le cas de orange.fr ou bien encore de protonmail.com qui fournit un webmail via une page internet.
- Le client alternatif : qui consiste à installer un logiciel spécifique afin de faire du traitement de courriel. C'est généralement la meilleure solution, qui permet de configurer les échanges plus finement, notamment les aspects liés à la sécurité.

#### Les Alias
Les alias courriel sont simplement des adresses dérivées de l'adresse principale ; elles renvoient dans tous les cas vers l'adresse courriel maîtresse.

> Pour aller plus loin, vous pouvez visionner la [vidéo de présentation](https://yewtu.be/watch?v=cgnsa5IMufs) de ce type de service.
> 
> Avertissement : vidéo en anglais.
{.is-info}

### Nos recommandations

1. Éviter autant que possible de créer une adresse courriel chez des fournisseurs de services issus des GAFAM, dont on sait que leur modèle économique se base sur les métadonnées et ne respectent en rien votre vie privée. 
**Exemple** : Gmail, Yahoo, Startmail...
Voici une liste de fournisseurs que nous recommandons : peu de fournisseurs de service courriel respectent réellement notre vie privée, voici donc une liste de ceux que nous estimons dignes d'intérêt :
- [Posteo *L'une des meilleures solutions, que nous recommandons en premier lieu : peu de données personnelles lors de l'inscription, un paiement cash possible (le service est payant à 1E/mois) et tournée vers une limitation de l'empreinte écologique.*](https://posteo.de/fr)
- [Disroot *Le célèbre mandataire discret, tourné vers le respect de la vie privée de ses utilisateurs. L'offre est gratuite mais limitée à un stockage de 1Go. Vous pouvez les soutenir en souscrivant à plus de stockage, ce qui leur permettra de perdurer.*](https://disroot.org/en/services/email)
- [Tutanota *Le fournisseur de service courriel allemand, tourné également vers le respect de la vie privée de ses utilisateurs. L'entreprise fournit même un service pour lanceurs d'alerte. Avec néanmoins quelques questionnements \*.*](https://tutanota.com/)
- [ProtonMail *Très connu, le fournisseur suisse propose des services non seulement de courriel, mais aussi de cloud, de calendrier partagé et de VPN. L'entreprise jouit d'une solide réputation, même si encore une fois tout n'est pas si rose \*\*.*](https://www.protonmail.com/)
{.links-list}

\* : Concernant Tutanota, il est à noter que le gouvernement allemand a réussi à les contraindre à utiliser une porte dérobée **pour tous les mails échangés en dehors des processus de chiffrement de bout en bout** (mail du domaine @tutanota vers mail d'un autre domaine (@gmail / @live, etc.), pour lequel aucun mot de passe de chiffrement n'a été créé par exemple - les courriels Tutanota :left_right_arrow: Tutanota en sont a priori exemptés : préférez donc au maximum utiliser le chiffrement).
**Source** : [Tutanota et la porte dérobée](https://www.01net.com/actualites/le-service-mail-le-plus-securise-au-mondecontraint-d-integrer-une-backdoor-pour-la-police-2012718.html).

\*\* : Pour les profils les plus à risques (activistes, avocats, opposants politiques...), il est bon de savoir que Proton AG a été obligé de livrer des adresses IP de comptes d’activistes français en 2021 à la demande des autorités. Ce qui semble vouloir dire que les adresses IP peuvent potentiellement être retrouvées... Nous préconisons dans ces cas particuliers de faire donc attention sur la confiance que vous portez à Proton AG.
**Sources** : [ProtonMail dans la tourmente](https://www.begeek.fr/protonmail-dans-la-tourmente-apres-avoir-donne-ladresses-ip-dun-activiste-aux-autorites-360546) et [ProtonMail balance des activistes parisiens](https://korii.slate.fr/tech/technologie-protonmail-balance-activistes-parisiens-youth-for-climate-arrestation-adresse-ip-suisse-europol).


2. Éviter l'utilisation d'outils "fermés" et issus des GAFAM ou autres multinationales.
**Exemple** : Vous connaissez probablement Outlook de chez microsoft, logiciel utilisé par bon nombre d'entreprises. Outlook est un client alternatif et permet donc d'éviter l'utilisation de webmail.
Si vous souhaitez utiliser un logiciel de courriel, privilégiez un outil libre et à sources ouvertes, plus susceptible de garantir une vie privée, dont voici nos recommandations :
- [Thunderbird *GNU/Linux, MacOS, Windows*](https://www.thunderbird.net/fr/)
- [Evolution *GNU/Linux*](https://wiki.gnome.org/Apps/Evolution)
- [FairEmail *Android*](https://email.faircode.eu/)
- [K9-Mail *Android*](https://k9mail.app/)
{.links-list}

> Il est à noter que bien souvent, certains vont être bloqués chez des fournisseurs peu regardant sur le traitement de la vie privée. Bien souvent ces fournisseurs proposent une application spécifique (sur iOS ou Android, voire Windows ou Linux). Une solution alternative qui peut souvent limiter le collecte de vos données est de simplement passer par votre navigateur internet plutôt que l'application fournie, y compris sur téléphone.


3. Créer plusieurs adresses courriels, par exemple, pour chaque « pan » de votre vie. Ce n’est pas nécessairement obligatoire, mais fortement recommandé. Cela contribue à améliorer votre vie privée, car si une boîte est compromise, les autres ne le seront pas forcément (sauf si vous choisissez le même mot de passe pour toutes ! Hum... Vous vouliez vraiment faire ça ? Alors relisez l'article dédié à l'hygiène numérique).
**Exemple de découpage** :
-   Un compte pour votre/vos banque(s)
-   Un compte pour votre travail (si pas déjà fait via votre société)
-   Un compte vie personnelle/familiale/shopping
-   Un compte pour les médias sociaux
*Attention : ceci n’est qu’un exemple !*

4. Si vous choisissez d'utiliser des alias, penchez-vous sur ces solutions :
-   [AnonAddy](https://anonaddy.com/) 
:arrow_right: présentation par la communauté Techlore par [ici](https://yewtu.be/watch?v=JMWfsOVrDkw) (avertissement : vidéo en anglais)
-   [SimpleLogin](https://simplelogin.io/) 
:arrow_right: présentation par la communauté Techlore par [ici](https://yewtu.be/watch?v=JMWfsOVrDkw) (avertissement : vidéo en anglais)

Grâce à ces 2 outils, vous pourrez vous créer un courriel alias, pour vous garantir un certain pseudonymat (surtout si vous utilisez une adresse courriel comme "monprenom.monnom@jevaismefairehacker.com" ;)).


### Sécuriser vos échanges courriel

Idéalement, chacun de vos échanges devrait être _chiffré_ de bout en bout, avec des clés de sécurité (chiffrement/déchiffrement) que vous **possédez**. Aujourd’hui, peu prennent en considération cet aspect de la sécurité à ce niveau. Mais pensez une seconde aux courriels que vous avez déjà transmis : vous avez sans doute déjà envoyé à un tiers une photo de votre carte d’identité, de votre permis de conduire, une copie de votre fiche de salaire. Vous avez déjà transmis un numéro de sécurité sociale, le tout sans protection par mot de passe au minimum (Aïe, ouch !)... 

Pour faire simple, « **<span class="red-text">Un courriel est tel une carte postale, numérique** » </span>; un courriel doit toujours être vu comme une carte postale sans enveloppe, et donc, à ce titre, tout le contenant se retrouve lisible par n’importe qui, bien placé entre vous et votre destinataire.

**Que diriez-vous si vous retrouviez toutes ces informations sur les darknets, vendues au plus offrant, et usurpant peut être votre identité ?**

*« Mais Gmail, Outlook etc. chiffrent déjà mes courriels maintenant, non ? »* allez-vous me dire. Oui, vous avez raison. Bon c'est déjà un bon début, mais tout comme la confiance que vous portez à ces sociétés (c’est-à-dire : nulle !), vous ne devriez pas non plus leur faire confiance sur cet aspect : en effet, s’ils chiffrent vos courriels, le problème est qu’ils détiennent les clés de sécurité (chiffrement et déchiffrement). Ce sont donc eux qui vont les générer et les gérer pour vous... Et comme une clé de sécurité est un item *_critique_*, mieux vaut avoir la main et pouvoir contrôler ces éléments vous-même. 

Il est donc recommandé d’utiliser d’autres solutions... que nous allons tenter d'expliquer tout en simplifiant au maximum (même si cela est difficile !).

_**Commençons par les fournisseurs de services courriel**_

- [Posteo](https://posteo.de/fr) et [Disroot](https://disroot.org/en/services/email) proposent tous deux l'utilisation personnelle de clés GPG/PGP, que ce soit via leur webmail qu'un client alternatif.

- [ProtonMail](https://proton.me/fr/mail) : le fournisseur suisse le plus connu dans la sphère numérique. Ils vont vous permettre une protection de vos échanges, en chiffrant et signant (au vouloir et au besoin bien-sûr) vos courriels si votre interlocuteur possède lui aussi un compte ProtonMail. C'est plutôt transparent, même si vous devrez sélectionner chiffrement/signature dans les options d'envoi ; mais l'échange des clés publiques sera invisible pour vous... Cela devient plus complexe si les 2 interlocuteurs n'ont pas le même fournisseur !
<span class="red-text">Mais tout cela s'accompagne d'inconvénients</span> :
    -   Premièrement ce n'est pas vous qui allez générer la bi-clé. Ceci est délégué à ProtonMail, qui bien sûr gardera la clé privée sur leurs serveurs ! Autant vous dire que vous devrez avoir une *confiance absolue* en ce fournisseur.
    -   Si votre interlocuteur n'utilise pas ProtonMail, vous devrez configurer l'envoi sécurisé dans les options, en ajoutant un mot de passe (cadenas en bas à gauche) :

![protonmail_symetric.png](/images/protonmail_symetric.png =400x){.align-center}

- [Tutanota](https://tutanota.com/fr/) : chez Tutanota, l'envoi/réception de courriel chiffré et signé est automatique, pour peu que votre interlocuteur ait également un compte chez eux. En effet, au contraire de ProtonMail, l'échange sera chiffré/signé automatiquement et la transmission des clés publiques sera transparente, vous n'aurez rien à faire. 
<span class="red-text">En revanche, deux points noirs encore ici</span> :
    -   Toujours le même point des clés générées et détenues par le fournisseur (pour peu qu'ils aient délégué cette fonctionnalité à une partie tierce, nous n'en savons rien !). Donc vous devrez faire une confiance absolue en Tutanota.
    -   Si votre interlocuteur n'a pas de compte Tutanota, il vous sera difficile d'utiliser PGP. Potentiellement, l'utilisation d'un mot de passe (chiffrement symétrique) pourra convenir, mais vous devrez trouver un moyen de transmettre le mot de passe de façon sécurisée !

![tutanota.png](/images/tutanota.png =500x){.align-center}

Pour terminer autour des fournisseurs, vous voyez qu'il est possible de protéger vos échanges "relativement" facilement. En revanche, point très important, ceci n'est conseillé que pour les personnes qui ne sont pas exposées et peuvent avoir une pleine confiance dans ces fournisseurs. Notez enfin que vous pouvez générer vous-même une bi-clé sur votre machine (cf. [utilisation de PGP](/intermediaire/chiffrement#pgp-gpg)) puis la transférer sur votre compte ProtonMail (Tutanota ne le permet pas) ; **cependant nous ne recommandons pas du tout cette façon de faire** (tout comme d'ailleurs ProtonMail) car vous devrez transférer votre clé privée... ce qui est contraire aux bonnes pratiques en terme d'hygiène numérique. ProtonMail ne peut certifier que le transfert se fasse d'une façon assez sécurisée et assez robuste pour garantir que la clé privée ne soit pas compromise ! À oublier donc...

> Nous ne répéterons jamais assez que la sécurité malheureusement aujourd'hui vient avec quelques contraintes dans l'utilisation des outils : il y aura toujours un choix à faire entre niveau de sécurité et facilité d'utilisation.
{.is-info}

_**Les clients courriel**_

Terminons par la solution la plus indiquée pour ceux qui ont besoin d'une sécurité maximale dans leurs échanges courriel. Il est possible ici d'utiliser un gestionnaire de courriel indépendant et gérer entièrement les clés utilisées pour protéger vos échanges, sans devoir passer par des tiers. Vous maîtrisez donc toute la chaîne de confiance, ce qui est idéal.

Cette solution nécessite néanmoins un compte courriel capable de pouvoir être géré par un client externe ; par exemple, Gmail le permet via IMAP ou POP, mais ProtonMail ne le permet pas. Alors attention ici cela reste un exemple car avec une utilisation de Gmail, ayez bien en tête que quand bien même vous protégeriez vos échanges, les informations seraient tout de même en transit sur les serveurs de Google (collecte des métadonnées) ! Donc bien entendu, nous ne recommandons pas cette solution. Il y a d'autres façons de trouver un fournisseur voire d'auto-héberger son propre serveur courriel.

Nous ne traiterons ici que d'un outil, qui est le plus connu des clients courriel sur GNU/Linux : Thunderbird. Il s'agit de l'outil le plus pratique afin de configurer PGP du fait de son intégration : avant le version 78, une extension était nécessaire afin d'intégrer PGP à Thunderbird, Enigmail [^¹]. C'est aujourd'hui de l'histoire ancienne, PGP étant complètement intégré au logiciel. Enigmail reste cela dit disponible pour la rétro compatibilité.

[^¹]: [Enigmail](http://doc.ubuntu-fr.org/enigmail)

L'idée dans cet outil sera de :
-   Générer votre paire de clés PGP, cf. [utilisation de GPG](/tutoriels/gnupg).
-   Importer votre clé (publique) dans Thunderbird
    -   Édition / Paramètres des comptes (ou Outils / Paramètres des comptes)
    -   Onglet "Chiffrement de bout en bout"
    -   Paragraphe "OpenPGP"
    -   Bouton "Ajouter une clé..."
-   Quand vous rédigerez votre courriel, vous aurez la possibilité de choisir de chiffrer et/ou signer votre courriel avec cette clé et celle de votre interlocuteur. Bien entendu, votre interlocuteur devra lui aussi avoir effectué ces étapes. Puis lui avoir transmis votre clé publique et lui de vous avoir transmis sa clé publique.

Vous trouverez ici un tutoriel intéressant et [bien documenté](https://www.zdnet.fr/pratique/comment-chiffrer-vos-e-mails-et-pourquoi-vous-devriez-le-faire-39944598.htm).


_**Les mandataires tiers**_

Une seconde possibilité vous est offerte si vous souhaitez toujours utiliser vos courriels habituels, consultables via votre navigateur internet (client webmail) : Gmail, Outlook, Yahoo, Mailbox... Bon ce n'est pas ce que l'on vous recommande, mais si votre modèle de menaces vous impose une protection de vos échanges courriel sans toutefois être critique, grâce à des extensions de navigateur, vous allez pouvoir chiffrer et signer vos courriels via PGP d'une manière assez simple.

-   [Mailvelope](https://mailvelope.com/en) : cet outil va vous permettre de générer vos clés PGP très simplement : pour ce faire, avant toute chose, cliquez sur l'icône de l'extension et sur "Let's Start". Ici, vous pourrez configurer l'outil en générant votre bi-clé :
    -   Rentrer vos données personnelles pour l'identification des clés,
    -   Cliquer sur "Avancé" puis choisir RSA 4096bits,
    -   Rentrer le mot de passe de protection de la clé privée,
    -   Si vous souhaitez rendre publique votre clé, vous pouvez laisser cochée l'import de votre clé publique sur les serveurs de Mailvelope (Mailvelope utilise le serveur de clés Ubuntu `keyserver.ubuntu.com`). Nous vous renvoyons ici à l'article sur [PGP](/intermediaire/chiffrement#pgp-gpg), afin de savoir ce que vous devez faire car ceci n'est pas sans conséquence,
    -   Aller dans les options, dans Général et cocher la fonctionnalité de signature,
    -   Si vous n'avez pas choisi le stockage de votre clé publique sur un serveur de clés, vous pouvez demander l'ajout la clé publique à chaque email,
    -   Pour ce qui est de Gmail, vous devez vérifier que l'API Google est bien cochée (car cela nécessite une connexion à votre compte Google),
    -   Revenir ensuite au gestionnaire de clés, et synchroniser. Vous recevrez un courriel sur la boîte courriel que vous souhaitez configurer,
    -   Cliquer dans le courriel sur "Afficher le message", entrez le mot de passe qui protège votre clé, pour déchiffrer le courriel, puis cliquez sur le lien de confirmation. Voilà, votre boîte courriel est configurée avec Mailvelope.

Bien entendu, votre interlocuteur devra effectuer les mêmes actions avec son client webmail, bien qu'ici il puisse utiliser un autre que le vôtre.

**Afin d'envoyer un courriel via Gmail** : vous verrez maintenant apparaître une icône Mailvelope à côté du bouton "Nouveau Message". Cliquez sur ce bouton, celui-ci ouvre l'extension et vous demande de vous connecter avec votre compte Google. Vous pourrez ensuite rédiger votre courriel dans la fenêtre Mailvelope, qui vous montrera les personnes avec qui vous pourrez protéger vos échanges, ces personnes vous ayant transmis leur clé publique.

> Une petite particularité ici est de ne pas mettre d'information sensible dans l'objet du message. En effet, celui-ci n'est pas chiffré, donc pensez à rester vague.
{.is-warning}

Pour terminer sur Mailvelope, deux points importants :
1. Il est possible d'importer votre bi-clé. Cela vous permet d'utiliser vos "sous-clés" (encore une fois nous vous renvoyons à l'[utilisation de GPG](/tutoriels/gnupg)), afin d'éviter de laisser votre clé privée maître constamment stockée sur une machine en ligne
2. Petite note sur la protection clé privée/mot de passe : dans le cas où vous générez votre bi-clé via Mailvelope, la clé privée et le mot de passe seront stockés dans votre navigateur (la clé privée stockée chiffrée bien entendu). Attention donc à bien mettre à jour votre navigateur afin d'éviter d'éventuelles vulnérabilités dans le compartiment de stockage.


-   [Flowcrypt](https://flowcrypt.com/) : tout comme mailvelope, Flowcrypt est une extension, à installer sur votre navigateur internet, qui vous permettra de générer et gérer vos clés. *Point très limitant : Flowcrypt est limité uniquement à Gmail*. A la manière de Mailvelope, un nouveau bouton apparaîtra sur votre webmail Gmail "Nouveau message sécurisé", et vous permettra sur le même principe de rédiger et transmettre votre courriel sécurisé.

_**Les Alternatives à PGP**_

Bien que PGP soit de plus en plus utilisé pour les courriels, il est tout à fait possible d'utiliser des alternatives via d'autres outils de gestions de clés asymétriques. Nous vous avons donné 2 logiciels dans la partie chiffrement, qui sont ici indiqués comme alternatives à PGP (ou GnuPG) :

-   **Kryptor** : cet outil comporte toutes les fonctionnalités nécessaires pour chiffrer mais aussi signer vos courriels. Il pourra donc vous être utile sans devoir utiliser un second outil.
**Tutoriel disponible [ici](/tutoriels/kryptor).**
-   **Age + Minisign** : ici Age qui ne comporte que la fonctionnalité de chiffrement devra être adossé à un second outil qui s'occupera des signatures [Minisign](https://jedisct1.github.io/minisign/).
**Tutoriel pour Age disponible [ici](/tutoriels/age).**

> L'un comme l'autre sont des alternatives crédibles à PGP.
{.is-success}

Pour *Kryptor*, ce sera vraisemblablement plus simple de générer et gérer une paire ou deux paires de clés (1 pour le chiffrement/déchiffrement et 1 seconde pour les signatures, afin de respecter les bonnes pratiques en cryptographie !), car il n'y aura qu'un seul gestionnaire de clés. Quand à *Age + Minisign*, deux gestionnaires de clés seront à gérer, même si Minisign propose des algorithmes à la pointe (ed25519 et blake2) et est plutôt rapide et simple.

# Messagerie

> Vous souvenez-vous de Caramail ou bien plus encore de MSN Messenger ? Ça, c'est pour les très anciens, les vieux de la vieille :)
{.is-info}

Tellement ancien, que les jeunes aujourd'hui ne connaissent pas ces noms... Mais toutes les messageries actuelles (en commençant par les plus connues : Whatsapp & Co) sont des descendantes de ces messageries instantanées.

Les messageries ont une sacrée histoire ; d'abord implémentées sous UNIX puis DOS (avec la commande NET SEND), elles connaissent une première avancée grâce au Minitel (eh oui encore lui !), avec une application appelée *Gretel* qui permettait de communiquer de pair à pair. Puis IRC a été créé et standardisé vers la fin des années 80. Cela dit, celles-ci n'étaient pas encore tout à fait des messageries dites 'instantanées', car très peu de notions d'authentification ou de détection de présence... 

Une première explosion des messageries instantanées a lieu vers la fin des années 90 lorsque AOL promeut *ICQ*, puis Yahoo son propre outil *Yahoo! Messenger* et enfin MSN avec *MSN Messenger* en 1999 (avec l'histoire qu'on lui connaît, racheté par Microsoft puis transition vers Skype, etc.). 

En parallèle, un autre service a fait parler de lui : le SMS, dont les débuts sont a priori situés en 1992. Ce n'est pas *à l'origine* à proprement parler un concurrent, car le SMS avait été créé initialement pour que les FAI puissent simplement communiquer avec leurs clients, et uniquement ça. Rien ne le prédestinait à autre chose... Mais au vu de la simplicité d'utilisation, l'interopérabilité de la technologie et parce que l'infrastructure téléphonique des opérateurs était déjà bien déployée - *le SMS utilisant le réseau  GSM [^²], alors que les messageries... le réseau internet, qui à l'époque, n'était pas aussi répandu qu'aujourd'hui encore moins sur téléphone mobile !*, le SMS a finalement percé à l'époque pour devenir ce que l'on connaît aujourd'hui !

[^²]: [Réseau](https://fr.wikipedia.org/wiki/R%C3%A9seau_de_t%C3%A9l%C3%A9phonie_mobile) de téléphonie mobile

L'explosion d'internet cela dit vers le milieu des années 2000 aura vu poindre de nouveaux outils de messagerie, bien plus performants : c'est par exemple la naissance de *Jabber/XMPP* en 2004/2005 mais surtout d'une messagerie bien connue aujourd'hui, *Whatsapp*, en 2009. Avec l'avènement des ordiphones et de l'utilisation intensive du réseau internet, rien ne pouvait résister à la mort lente des SMS ; même si de nos jours les organismes tentent de leur donner un second souffle avec des nouveaux standards (MMS ou RCS par exemple), il est vraisemblable que celui-ci soit amené à disparaître petit à petit... 

**Mais nous sommes là dans la spéculation ! Revenons-en à nos moutons : les messageries.**

## Collecte des données
Dans notre voyage, afin de regagner un peu de contrôle sur nos données et donc renforcer notre vie privée, il est essentiel de savoir quel est l'étendu du désastre sur la **collecte des données privées** nous concernant.

Voici un aperçu simple de 5 messageries-type en ce qui concerne la collecte de vos données privées :

![messageries-3.jpg](/images/messageries-3.jpg =700x){.align-center}

---

**Premier constat** : la majorité des messageries les plus connues aujourd'hui sont détenues par les GAFAM et/ou sont de sources fermées. Ce qu'il faut retenir de l'infographie ci-dessus est :
- Sachant leur politique de collecte de données (qui semble être la même partout sur toutes les messageries propriétaires), nous devrions être plus attentifs.
- Sachant également que bien qu'ils nous assurent que les données collectées ne le sont pas à des fins commerciales ou sont bien protégées, nous n'avons aucun moyen de savoir si tout cela est véridique car le code source est fermé, et les agissements de ces entreprises sont bien entendu obscures.
{.grid-list}

> Il est donc évident que **toutes ces messageries** doivent être abandonnées le plus vite possible.
{.is-danger}

Cela comprend exhaustivement :
- :arrow_right: :x: Whatsapp
- :arrow_right: :x: Meta/Facebook Messenger
- :arrow_right: :x: Instagram
- :arrow_right: :x: Snapchat
- :arrow_right: :x: Google avec tous leurs outils de messagerie :  Gmail, Hangouts, Messages, Chat, Duo, Google+...
- :arrow_right: :x: Amazon WickrMe
- :arrow_right: :x: Microsoft Skype
- :arrow_right: :x: Zoom
- :arrow_right: :x: Cisco Webex
- :arrow_right: :x: Microsoft Teams
- :arrow_right: :x: Apple iMessages
- :arrow_right: :x: Yahoo messagerie
- :arrow_right: :x: Discord
- :arrow_right: :x: Twitter
- :arrow_right: :x: Slack
- :arrow_right: :x: WeChat
- :arrow_right: :x: Viber
- :arrow_right: :x: Line
- :arrow_right: :x: Bip
- :arrow_right: :x: Les potentielles messageries de votre/vos FAI : Orange, Bouygues, SFR, Free et autres MVNO
- :arrow_right: :x: Toute autre messagerie à sources fermées
{.grid-list}

Si vous avez néanmoins besoin de plus d'informations pour vous en convaincre, voyez par vous-même : [Apple et iCloud](https://www.blogdumoderateur.com/apple-analyse-photos-icloud-pedocriminalite/), [plus récemment Whatsapp et son ultimatum](https://www.blogdumoderateur.com/whatsapp-supprime-compte-refus-partage-donnees-facebook/), ou encore [la "*modération*" sur Whatsapp](https://www.presse-citron.net/gare-a-vos-propos-sur-whatsapp-vous-etes-peut-etre-surveille/), ou [les remords du co-fondateur de WhatsApp](https://news.sophos.com/fr-fr/2018/10/03/co-fondateur-whatsapp-vendu-vie-privee-utilisateurs/) nous permettent de tirer un bilan noir.

Il est également intéressant de voir que le FBI a créé un document qui liste les données qu'ils peuvent extraire (légalement bien sûr ;) !) de la plupart des messageries sur le marché :

![fbi-messageries.png](/images/fbi-messageries.png){.align-center}

Nous retrouvons toutes les messageries mentionnées ci-dessus, tout en notant que *Signal* est la messagerie au travers de laquelle il est le plus difficile d'obtenir des informations... Nous y reviendrons !

## Les messageries controversées
Certains vont se demander pourquoi certaines messageries connues n'apparaissent pas ici. Voici les raisons :

- **Threema** : application suisse, très prisée dans le monde germanophone. Cette messagerie est payante et une partie de son code source n'est pas ouvert (côté serveur). Il est donc évident que nous ne recommanderons pas cette solution.

- **Wire** : également suisse, Wire a été créée par le fondateur de Skype. L'application est totalement open-source, et utilise les méthodes de chiffrement de Signal. Néanmoins, Wire a un modèle qui ne colle pas avec la philosophie du Libre, la société s'adressant plus particulièrement au monde professionnel qu'au grand public et donc possédant un modèle économique attirant les convoitises. Ici encore, nous ne recommandons pas forcément cette messagerie.

## Le cas délicat d'Olvid

Oui nous ne recommandons pas, à ce jour, l'application française **Olvid**... Beaucoup ici trouveront cette idée farfelue, mais voici nos raisons :
- Bien que certifiée ANSSI [^³] et ayant fait l'objet d'un second audit de sécurité [^⁴] (2020), cette application n'est pas totalement à sources ouvertes : seul le protocole de chiffrement et les clients Android/iOS le sont, l'objectif étant de faciliter les audits et bug bounty afin de perfectionner les algorithmes (qui ont été créés de zéro). Mais la partie serveur [^⁵] est à sources fermées ce qui empêche des experts indépendants de réellement les auditer.
- Les serveurs montés par les créateurs d'Olvid sont tous hébergés hors Europe (chez Amazon AWS [^⁷]), ce qui laisse songeur sur leur côté éthique.
- De plus, Olvid considère que l'adresse IP est plus une donnée technique [^⁶] qu'une donnée personnelle, ce qui dès lors devrait nous mettre la puce à l'oreille...

À ce titre, nous ne recommandons pas spécialement cette messagerie, **Session** par exemple nous semble bien plus indiquée ici.

[^³]: [ANSSI - CSPN](https://cyber.gouv.fr/produits-certifies?sort_bef_combine=field_date_de_certification_value_DESC&field_cat_target_id%5B587%5D=587) -  "Messagerie Sécurisée"
[^⁴]: [Rapport d'évaluation](https://olvid.io/assets/documents/Synacktiv-Olvid-CSPN-Olvid-0.8.2-RTE-public.pdf)
[^⁵]: [Olvid - Politique de Confidentialité](https://www.olvid.io/privacy/fr/)
[^⁶]: [Olvid et AWS](https://www.lemondeinformatique.fr/actualites/lire-olvid-la-polemique-sur-aws-ne-paas-pas-92463.html)
[^⁷]: [Olvid Serveur](https://www.olvid.io/faq/serveur-et-open-source/)

## Les messageries recommandées

### Bon rapport Praticité/Sécurité

> **Vous trouverez ci-après 2 onglets : "Pour débuter" et "Aller plus loin".
> -- L'onglet "Pour débuter" pour ceux qui ne souhaitent pas de justification ou d'analyse concernant les choix proposés.
> -- L'onglet "Aller plus loin" pour les personnes désireuses de comprendre nox choix.**
{.is-warning}


# Tabs {.tabset}
## Pour débuter
Pour vous faciliter la prise de décision, nous vous présentons, dans les prochains chapitres, les outils que nous recommandons suivant les usages que vous souhaitez en faire qui sont :
- [Signal *La meilleure des messageries centralisée, mais sujet à bien des questions...*](https://signal.org/)
- [Element *La messagerie à base Matrix pour son côté décentralisé*](https://element.io/)
- [Session *Une messagerie qui utilise les algorithmes Signal sur un réseau réparti/distribué*](https://getsession.org/)
- [Briar *La messagerie optimale pour du pair à pair (= sans intermédiaire)*](https://briarproject.org)
{.links-list}

> Attention, nous avons pris le parti de faire des choix, basés sur un modèle de sécurité strict mais aussi sur une _**facilité d'utilisation**_ au quotidien. Il existe bien entendu d'autres messageries, mais 
> (1) soit elles n'ont pas fait l'objet d'audit de sécurité (ce qui ne nous permet pas d'avoir un niveau de confiance suffisant),
> (2) soit leur modèle ne correspond pas à nos exigences,
> (3) soit elles souffrent d'une trop grande jeunesse pour une utilisation au quotidien.
{.is-info}

**Si vous souhaitez en savoir plus, jetez un oeil à l'onglet "Aller plus loin"**.

## Aller plus loin
Pour vous faciliter la prise de décision, nous vous présentons, dans les prochains chapitres, les outils que nous recommandons suivant les usages que vous souhaitez en faire qui sont :
- [Signal *La meilleure des messageries centralisée, mais sujet à bien des questions...*](https://signal.org/)
- [Element *La messagerie à base Matrix pour son côté décentralisé*](https://element.io/)
- [Session *Une messagerie qui utilise les algorithmes Signal sur un réseau réparti/distribué*](https://getsession.org/)
- [Briar *La messagerie optimale pour du pair à pair (= sans intermédiaire)*](https://briarproject.org)
{.links-list}

> Attention, nous avons pris le parti de faire des choix, basés sur un modèle de sécurité strict mais aussi sur une _**facilité d'utilisation**_ au quotidien. Il existe bien entendu d'autres messageries, mais 
> (1) soit elles n'ont pas fait l'objet d'audit de sécurité (ce qui ne nous permet pas d'avoir un niveau de confiance suffisant),
> (2) et/ou soit leur modèle ne correspond pas à nos exigences,
> (3) et/ou soit elles souffrent d'une trop grande jeunesse pour une utilisation au quotidien.
{.is-info}

### Etat des lieux du marché
Maintenant que nous avons une idée de l'étendue des dégâts, passons aux choix qui se présentent à nous. Vous avez sûrement tous entrevus ces infographies, faisant état de la majorité des messageries actuellement disponibles comparées aux messageries propriétaires :

![messageries-1.jpg](/images/messageries-1.jpg =600x)<span>&nbsp;&nbsp;&nbsp;&nbsp;</span>![messageries-2.jpg](/images/messageries-2.jpg =650x)

Ce [comparatif](https://www.securemessagingapps.com/) est également une bonne source d'informations.

---

**Deuxième constat** : il est difficile de savoir quelle messagerie vous allez pouvoir utiliser, comme cela en visualisant simplement des infographies... En effet, ces outils sont en plein essor, notamment du côté des solutions open source. Le marché n'a pas encore consolidé et nous avons aujourd'hui la possibilité d'utiliser des outils basés sur des mécanismes assez complexes à appréhender et à comprendre surtout lorsque les aspects de chiffrement ne sont pas les mêmes partout ! 

Sur la figure de droite sont schématisées les 5 grandes familles de messageries que vous pourrez retrouver sur le marché.

![messageries-5.jpg](/images/messageries-5.jpg =500x){.align-right}
Quelques explications :
1. **Service non libre, Clients et Serveurs centralisés** : pour résumer, tous les outils mentionnés dans la précédente partie "Collecte des données".
2. **Clients libres, Serveurs non libres, mode centralisé** : Telegram fait bien partie de cette catégorie ; nous ne savons pas exactement tout ce qu'il se passe sur leurs serveurs. Et les échanges passent par leurs serveurs (hormis les échange dits "Secrets"), ce qui en fait une messagerie de type **centralisée**.
3. **Clients et Serveurs libres, mode centralisé** : Signal (tout comme Wire) fait partie de cette catégorie car les échanges sont effectivement centralisés, sur leurs serveurs. Nous rediscutons de Signal dans les prochaines sections.
4. **Clients et Serveurs libres, mode distribué/décentralisé** : Ces applications sont totalement de sources ouvertes. En revanche, les échanges se feront différemment, mais non centralisés : (1) soit sur un mode distribué impliquant une multitude de serveurs et une répartition des échanges, (2) soit sur le modèle des architectures décentralisées (comme les blockchains). La différence est subtile mais bien présente : un modèle distribué peut devenir un modèle centralisé au besoin, alors qu'un modèle décentralisé ne le peut pas (et ne le doit pas !).
5. **Clients libres, communication paire à paire** : il s'agit du modèle le plus ultime d'échanges au travers des messageries ; aucune entité (humaine ou physique comme des serveurs) entre émetteur et destinataire, les messages sont directement transmis, mais une obligation d'être connecté en même temps pour pouvoir communiquer. En ce sens, les échanges ne dépendent d'aucune tierce partie, qu'ils soient propriétaires comme dans la centralisation ou personnels comme dans la fédération/décentralisation.

Cela ne veut pas dire que vous devriez opter à tous prix pour le choix 5. Il n'est pas nécessaire d'en arriver là, hormis si votre modèle de menaces l'exige, nous vous renvoyons ici à l'article sur l'[hygiène numérique](/hygiene-numerique#s%C3%A9curit%C3%A9-vie-priv%C3%A9e-et-anonymat).

**Néanmoins, nous pouvons déjà nous dire que le choix 1. est à prohiber !** 

Pour les autres choix cela dépendra de votre modèle :
- :one: Si vous avez des besoins d'anonymat extrêmes : vous devrez privilégier le choix 5. pour les échanges qui le nécessiteront.
- :two: Si votre besoin est de limiter au maximum la collecte des données et d'avoir un modèle de sécurité important, privilégiez le choix 4.
- :three: Si vous recherchez une sécurité sans vous soucier des quelques métadonnées potentiellement transférées, optez pour le choix 3 ou 2.
{.grid-list}

> _Petite note sur Telegram_ : Telegram est aujourd'hui plus utilisé comme un *réseau social*, en remplacement de Facebook ou Twitter, plutôt qu'une messagerie. 
> 
> Même si à l'origine cette application a été créée pour échanger des messages, elle a évolué avec les usages pour devenir un peu plus une plateforme de média social, et continue son évolution dans cet axe. 
>
> Notre avis pour Telegram en tant que simple messagerie : sachant qu'ils ne proposent pas "nativement" la protection bout en bout des échanges (pour cela, il est obligatoire de créer des canaux appelés "Secret", et uniquement disponible sur téléphone) et que les groupes créés ne sont pas non plus protégés de bout en bout (protection client-serveur), ***nous avons tendance à ne pas recommander Telegram _en tant que messagerie_***, mais en tant que média social, au même titre que Mastodon.
{.is-warning}


### La sécurité des messageries

Nous ne pouvons bien entendu pas parler de messagerie sans discuter de la sécurisation des échanges : c'est un peu un passage obligé pour pouvoir décider quel outil vous allez utiliser ! Nous allons tenter de faire ça simplement.

Il existe, à ce jour, 2 *types de protection* qui nous intéressent particulièrement :
- Le **chiffrement client-serveur** : dans la pratique, le client de l'émetteur initie un canal avec le serveur de l'application puis chiffre le message. Celui-ci est reçu par le serveur, déchiffré par le serveur, puis rechiffré par le serveur pour transmettre le message au client du destinataire qui le déchiffrera à son tour. Dans ce cas, l'idée ici est de faire transiter un message via un serveur : vous voyez donc qu'ici nous sommes sur un mode de _centralisation_. On peut donc facilement voir qu'il existe une entité qui sera capable de retenir à un moment donné dans la chaîne le message : le serveur. Même si celui-ci vous assure qu'il ne regarde absolument pas le contenu, il est évident que cela pose un souci en terme de vie privée, surtout si des législations viennent se mêler de ce sujet ou bien que des gouvernements soumettent des injonstions aux fournisseurs afin de déchiffrer des messages provenant de leurs serveurs (ils le peuvent car ils détiennent et gèrent les clés pour vous !).

- Le **chiffrement de bout en bout** (ou E2EE [^⁸]) : ici l'émetteur chiffre le message et le transmet directement au destinataire qui le déchiffre ; aucun intermédiaire ici. On pourrait croire que cette solution est l'ultime solution, la plus adéquate, mais, vous vous en doutez, rien n'est jamais aussi simple ! En effet, afin de pouvoir chiffrer, vous aurez besoin de "clés de sécurité" (jetez un coup d'oeil à l'article sur le [chiffrement](/intermediaire/chiffrement) pour bien comprendre l'aspect des clés de sécurité). Ces clés doivent pouvoir être générées et stockées quelque part.
    - _Messagerie centralisée_ : dans la plupart des cas, les clés sont générées par les fournisseurs du service eux-mêmes et stockés sur les serveurs. Même si certaines messageries implémentent bien entendu des mécanismes *robustes* pour stocker et échanger ces clés, il n'en reste pas moins que la clé principale est gérée chez le fournisseur du service et non par vous-même.
    - _Messagerie fédérée, décentralisée ou mode pair à pair_ : ces clés sont générées sur votre appareil et gérées sur cet appareil et non par un fournisseur tiers.
Enfin, bien entendu, le chiffrement de bout-en-bout implique dans certains cas (principalement pair à pair) que chaque protagoniste soit connecté pour émettre et recevoir. Ceci est a priori un avantage mais peut potentiellement être un inconvénient pour certains.

Pour plus de détails sur les définitions, rendez vous sur le [glossaire](/glossaire#r%C3%A9seau-infrastructure).

[^⁸]: E2EE pour "End to End Encryption".


Pour traduire, lorsque vous utilisez une application de messagerie aujourd'hui, *centralisée* et *grand public/propriétaire* (hors modèle pair à pair donc), il est souvent mis en avant le fait que celles-ci vous proposent un chiffrement bout-en-bout (E2EE), mais ce n'est pas si simple... Sur le même principe que des mandataires courriels, une majorité des messageries génèrent elles-mêmes les clés de chiffrement et les gèrent pour vous afin que tout soit transparent. **Néanmoins, cela implique plusieurs choses qui peuvent déranger** :
-   Vous êtes soi-disant propriétaire des clés, mais la réalité est que vous êtes tributaire de la société derrière cette messagerie dans la gestion de ces clés. Si les serveurs de cette messagerie sont compromis, il y a de très fortes chances que vos clés le soient également.
-   Il est évident également que du fait que ces clés soient gérées par la société derrière la messagerie, celle-ci puisse et/ou doive (injonction légale) donner accès à ces clés à n'importe quelle autorité ou entité de surveillance qui le demanderait.
-   Vous ne maîtrisez pas la robustesse des clés utilisées. Même si les sociétés communiquent sur les algorithmes utilisés, vous n'avez aucun moyen de confirmer leur utilisation.

Concernant les modèles pair à pair ou décentralisé, ces inconvénients n'existent pas : car il n'y a pas de tierces parties entre émetteur et destinataire qui gèrent vos clés, ou en tout cas elles ne gèrent pas ces clés pour vous.

Simple ! :)

### Centralisé, Signal

La messagerie *vue comme la plus sécurisée* est la plus connue à ce jour dans ce genre d'outil de communication, en tout cas au sein de la communauté numérique.

#### Petit point sur les controverses...

Signal (tout comme beaucoup d'applications aujourd'hui) a fait l'objet de beaucoup de théories. La plus importante et répandue d'entre elles étant celle qui lie Signal à la CIA. Voici en gros l'argumentaire répandu par certains :

> Entre 2013 et 2016, les développeurs ont reçu 3M de dollars du fond Open Technology Fund (OTF). L'OTF était à l'origine un programme de Radio Free Asia sous la coupe de l'US Agency Global Media (USAGM). L'USAGM est "une organisation indépendante" du gouvernement US en charge de promouvoir les intérêts américains à l'international et serait directement financée et gérée par le gouvernement US. Par ricochet, l'USAGM/Radio Free Asia étant gérés par le gouvernement US, qui ont financé l'OTF, qui a financé le développement de l'application Signal, la CIA aurait donc créé Signal !

**Tentons d'y voir plus clair** : l'USAGM (et tous ses projets dont OTF et Radio Free Asia...) promeut effectivement les intérêts US (en utilisant des capacités disruptives ou déstabilisantes, etc.), surtout dans des pays où les gouvernements ont des liens très difficiles avec le gouvernement US... Donc en plus de soutenir des médias *indépendants* dans ces pays, cela implique également le soutien du gouvernement US à des outils capables de contourner la censure et permettre à des personnes de résister à des régimes dictatoriaux.

De plus, le soutien financier de l'OTF à divers projets est du domaine public [^⁹].

[^⁹]: [Open Whisper System](https://www.opentech.fund/results/supported-projects/open-whisper-systems/) et financement.

Bien évidemment du fait de la facilité d'obtenir cette information et de vouloir faire sensation, le buzz, quelques journaux ont publié des articles concernant la messagerie, remplis de sous entendus ; ce qui, de fait, a contribué à créer cette théorie. Maintenant, examinons les faits :
- ~~Signal est open-source (y compris leur protocole de chiffrement, dérivation de clés, gestion de la confidentialité permanente, PFS etc.), ce qui implique que le code est scruté et auditable à n'importe quel moment par des experts cyber de par le monde (n'oublions pas que cette messagerie est très connue)~~ 
    - *C'est confirmé depuis fin 2021 [^¹0], [^¹1] ou [^¹2], et après de nombreuses demandes des développeurs et utilisateurs, **Signal confirme enfin qu'il ferme une partie de son code source côté Serveur**, le code source relatif au protocole reste open-source. Même si la justification est a priori recevable pour la majorité des libristes, cela constitue donc un _relatif danger_ pour certains utilisateurs...*
    - *...Car en terme de surveillance de masse, il est plus simple et plus intéressant pour les gouvernements d'utiliser des outils à sources fermées (ex. : le scandale des backdoors [^¹3] sur les routeurs Cisco qui n'est qu'un exemple). Nous ne sommes pas en train de dire que c'est le cas pour Signal, mais de dire qu'a priori personne ne pourra le prouver puisqu'une partie du code est fermé !*
    - *Cela dit, il est aussi bien plus simple d'installer un petit spyware sur des téléphones (cf. le scandale PRISM [^¹4], ou encore ce scandale au Canada [^¹5])*

[^¹0]:[Signal - sources fermées](https://signal.org/blog/keeping-spam-off-signal/), justifications données par les développeurs de Signal. 
[^¹1]: [Signal arrête de se soucier de la vie privée](https://pocketnow.com/like-whatsapp-signal-just-jumped-the-shark-and-stops-caring-so-much-about-privacy/) de ses utilisateurs.
[^¹2]: [Lemmy](https://lemmy.ml/post/55595) forum.
[^¹3]: [Les révélations de Snowden](https://www.infoworld.com/article/2608141/snowden--the-nsa-planted-backdoors-in-cisco-products.html) sur les backdoors Cisco.
[^¹4]: [PRISM](https://www.theverge.com/2013/7/17/4517480/nsa-spying-prism-surveillance-cheat-sheet) et ses répercutions.
[^¹5]: [Spyware](https://www.politico.com/news/2022/06/29/canada-national-police-spyware-phones-00043092) lié à la police au canada.


- Une multitude de projets open source sont financés par des entités similaires. L'OTF a par exemple financé beaucoup d'autres projets dont nous discutons dans tous nos articles : *Tor Project*, *K9-Mail*, *F-Droid*, *Certbot*, et même *Tails OS* [^¹6]. Et bien d'autres projets open source sont financés en partie par des agences ou des organismes qui peuvent avoir quelques liens avec des gouvernements ; *d'ailleurs, les messageries mentionnées dans notre article peuvent avoir reçu des fonds de gouvernements : par exemple, Element aux UK et Session en Australie...*.

[^¹6]: [Tails OS](https://tails.boum.org/sponsors/index.en.html) et financement.


Il nous semble évident que ceci est un débat sans fin... Il est toujours *intéressant et très utile* d'avoir un regard critique et de se poser des questions sur les financements, mais nous ne devrions pas, de notre point de vue, établir des raccourcis simplistes simplement car ils correspondent à des croyances. *Signal* a été financé par d'autres entités et mécènes : récemment le co-fondateur de Whatsapp a octroyé 50M en prêt à 0% aux développeurs de Signal, devenant également CEO de la Signal Foundation ! 

**Il y a effectivement des faits valides qui expliquent pourquoi et comment Signal a pu émerger et en arriver là, ce qui ne prouve ou n'implique en aucun cas l'existence d'une backdoor créée par la CIA pour cibler ses utilisateurs !**

> Comme tout sujet lié au numérique, tout n'est pas si rose, vous vous en doutez bien, et nous avons des raisons **plus techniques** d'être vigilant envers Signal...
{.is-info}


#### ... Revenons sur terre

Signal est donc cette messagerie dite "sécurisée" dont ses développeurs ont créé leur propre protocole de communication, repris d'ailleurs par beaucoup d'autres messageries (Whatsapp par exemple), suite à l'ouverture des sources de ce protocole. Protocole audité en 2016 par des experts indépendants [^¹7], qui aujourd'hui confirme sa robustesse à une bonne partie des attaques. Les développeurs sont d'ailleurs très réactifs lorsqu'il s'agit de corriger certaines failles de sécurité. C'est un projet très bien maintenu et très bien géré.

[^¹7]: [Audit](https://eprint.iacr.org/2016/1013.pdf) du protocole Signal.


**_Néanmoins, comme évoqué plus haut, tout n'est pas si rose :_**
En dehors du fait que nouvellement une partie du code source côté Serveur est maintenant fermé, voici les points techniques sujets à débat :

### Tabs {.tabset}
#### Le côté centralisé
Signal repose sur une **infrastructure centralisée**.

C'est une décision prise à l'origine afin d'accélérer l'adoption de la messagerie aux utilisateurs non technophiles (M. et Mme Michu en somme), mais au détriment des aspects sécuritaires et d'anonymisation. Et il semble qu'ils n'évolueront pas sur ce point, les développeurs étant convaincus que le modèle centralisé est le meilleur (probablement pour leurs finances !).

En réalité, il s'agit d'une grande infrastructure cloud de serveurs, hébergés dans des datacenters Amazon à travers tous les US. Dit comme ceci, en effet, cela est peu reluisant ! Ce choix fait par les développeurs n'est pas incompréhensible, car cela permet une grande disponibilité de l'application, et des messages échangés qui peuvent être stockés (chiffrés !) en attendant que les personnes se connectent pour les lire, et une facilité dans la gestion de groupes de communication sécurisés.

Oui mais voilà, cette centralisation apporte certains inconvénients au niveau vie privée et fiabilité.

#### Le numéro de téléphone
Signal exige que tout compte soit lié à un **numéro de téléphone**.

Nous avons déjà discuté des métadonnées dans l'article sur l'[hygiène numérique](/hygiene-numerique#les-m%C3%A9tadonn%C3%A9es-quest-ce-que-cest). L'importance des métadonnées a été prise en compte pas les développeurs, ce qui est un bon point (ils arrivent à protéger et/ou obfusquer la majorité de ces données). Néanmoins, il est depuis 2016 devenu évident que Signal collecte les numéros de téléphone associés à un compte [^¹8] ainsi qu'une seconde donnée qui est la '*dernière connexion d'un compte X à un serveur*'.

[^¹8]: [Signal collecte](https://signal.org/bigbrother/eastern-virginia-grand-jury) des numéros de téléphone associés à un compte.

Pour beaucoup, lier le numéro de téléphone est un problème et met à mal le modèle de vie privée prétenduement mis en avant par la messagerie. En effet, un numéro de téléphone est dans la plupart des cas lié à une carte SIM, carte qui de facto est reliée à un propriétaire qui aura dû présenter son identité (en tout cas en Europe c'est la cas). Signal ayant abandonné récemment la gestion des SMS/MMS, la communauté n'a pas compris pourquoi il était toujours obligatoire d'enregistrer un numéro de téléphone. Sans compter que ce numéro de téléphone est révélé à chacun des contacts que vous avez accepté dans l'application.

Et bien entendu, sur le point de la collecte, nous n'avons pas le choix que de faire confiance aux développeurs ! Idem sur le sujet des ordonnances reçues par Signal demandant une divulguation d'informations. À l'heure où nous écrivons ces lignes, il n'y a pas de raison valable de douter de leur bonne foi, mais il est important de se demander jusqu'à quel point nous sommes prêts à faire confiance à la messagerie ; il est évident que des adversaires comme un état ou des groupements de pirates malveillants soutenus par des états ont des capacités importantes de collecte et d'aggrégation et de corrélation de (méta)données, même en ne ciblant pas directement Signal mais en passant par Amazon. Signal est donc bien plus vulnérable à ce type d'attaque que d'autres solutions, _du fait de son infrastructure centralisée_.

#### Le protocole de sécurité
Il y a tout de même quelques doutes sur le **protocole** en lui-même.

Pour les plus experts d'entre vous, et ceux ayant le courage de creuser un peu plus le sujet du protocole, un chercheur de l'ANSSI a rédigé un rapport sur *les protocoles* de messageries qu'utilise Signal, rapport très intéressant [^¹9].

[^¹9]: [OMEMO - Analyse](https://cyber.gouv.fr/publications/chiffrement-de-messagerie-quasi-instantanee-quel-protocole-se-vouer).


Tout comme nous, et bien d'autres collectifs, il analyse le réel niveau de sécurisation de Signal et pose des questions plus que légitimes au regard des évolutions récentes de la messagerie...

### Décentralisé

Ici nous avons 2 outils, aux objectifs différents :
- Element met l'accent sur le côté temps-réel et interopérabilité, **et constitue plus un réseau social qu'une messagerie** (*à l'instar de Telegram*).
- Session quant à lui reste focus sur la sécurisation des échanges et l'anonymat (relatif).

Bien que ces 2 solutions se reposent sur la décentralisation (à un certain niveau cela dit) et implémentent un chiffrement bout en bout, il y a donc bien une grande différence entre les 2 messageries, qui ne seront pas destinées aux mêmes usages...

#### Element
[Element](https://element.io/) est basé sur le protocole et le réseau Matrix. Ce réseau est un réseau fédéré, décentralisé jusqu'à un certain point, et est surtout axé sur l'**interopérabilité** : c'est-à-dire la capacité de recevoir des communications d'autres messageries (Whatsapp, Telegram, Signal...) et d'autres protocoles, via ce qu'ils appellent des *ponts*. C'est la grande force de Matrix, même si cela vient avec des inconvénients, vous vous en doutez...

Côté sécurisation des échanges, Matrix permet le chiffrement bout en bout et utilise les mêmes méthodes de chiffrement que Signal (le côté centralisation en moins) ; ce n'est pas l'objectif prioritaire de Matrix car il n'impose pas le chiffrement par défaut, d'ailleurs certaines applications qui utilisent Matrix ne fournissent pas de chiffrement (par exemple Nio, Fractal...), mais *Element* l'implémente et l'impose.

Néanmoins, quelques cas de figure problématiques peuvent apparaître dans son utilisation :
- La complexité vient en fait du choix des serveurs, car si certaines personnes ne se trouvent pas sur les mêmes serveurs, les messages seront dupliqués sur tous les serveurs. Pour peu que ces serveurs soient basés aux États-Unis, en France, Allemagne, etc. ceci peut potentiellement poser un problème en terme de vie privée. Et pour peu que ces serveurs ne permettent pas le pseudonymat, vous pouvez donc permettre à des serveurs de collecter des métadonnées !

- Il est certainement très utile de créer des ponts, car vos proches ne veulent peut-être pas changer de messagerie par exemple ! Mais le problème est que si votre interlocuteur utilise une application qui ne chiffre pas (Fractal ou Nio par exemple), vos messages peuvent potentiellement se retrouver sur des serveurs, non protégés, en clair. Problématique !

- Certaines données ne seront pas chiffrées, comme les images de profils, les réactions et les pseudonymes. Les appels voix et vidéo ne sont pas non plus protégés de bout en bout, utilisant Jitsi (a priori, cela devrait évoluer avec l'adoption de la VoIP). Cela dit, nous restons à des appels de groupes non authentifiés, il faudra donc éviter de passer des appels privés avec cette application, car n'importe qui pourra se connecter !

**En conclusion, cette messagerie ne doit pas être utilisée si votre modèle doit être strict, mais plus pour le côté interopérabilité et réseau. Également, veillez à bien choisir les serveurs sur lesquels vous vous connecterez : certains demandent une adresse e-mail... Dans ce cas, changez de serveur !**

_**Ressources d'intérêts**_
- Audit de sécurité : [Audit indépendant du protocole Matrix en 2016](https://matrix.org/blog/2016/11/21/matrixs-olm-end-to-end-encryption-security-assessment-released-and-implemented-cross-platform-on-riot-at-last) et statuant sur des capacités correctes dans la sécurisation, si correction des divers bugs remontés (je vous rassure, depuis les divers bugs de sécurité sont corrigés !).

#### Session
[Session](https://getsession.org/) est, quant à lui, un fork récent de Signal. Mais plutôt que de proposer une centralisation, Session propose de passer par un réseau décentralisé appelé Lokinet/Oxen (qui est un équivalent de Tor), qui implémente une blockchain. Alors rassurez-vous tout ceci est transparent pour les utilisateurs, et vous n'aurez pas non plus à acheter des cryptomonnaies :).

L'idée derrière l'utilisation de ce réseau est d'apporter une **confidentialité** et un **anonymat** accrus :
- Session ne demande aucun numéro de téléphone ou adresse courriel ou autre identifiant reliant à une identité. La messagerie utilise un identifiant unique relié aux paires de clés.
- Session s'assure que les adresses IP ne peuvent être en aucun cas liées à des messages lus ou reçus, grâce à la façon dont est implémenté Lokinet ("requêtes en oignon", relire l'article [dédié](/debutant/vpn-tor#tor)).

Enfin, il vous sera possible de créer des groupes de discussions, publics et privés. Cela dit, veillez à éviter absolument la création de groupes "publics" qui bien qu'ouverts à plus de 100 personnes ne permettent pas d'assurer la protection des échanges (groupe ouverts "par design").

**Pour conclure, nous pouvons apercevoir ici que Session sera plus dirigée vers des échanges entre personnes plutôt que dans des groupes (Element serait à privilégier dans ce cas !).**

_**Ressources d'intérêts**_
- Audit de sécurité [^²1] et concluant "The overall security level of this application is good and makes it usable for privacy-concerned people" qui donne en français : Le niveau de sécurité global de l'application est bonne et la rend utilisable pour les personnes ayant un intérêt pour leur vie privée.
- Papier Blanc [^²0]

[^²1]: [Audit d'Oxen en 2021](https://getsession.org/session-code-audit).
[^²0]: [WhitePaper](https://arxiv.org/pdf/2002.04609.pdf) Session.


----

> Ainsi vous l'aurez compris, si votre modèle n'est pas spécialement et essentiellement tourné vers l'anonymat et la sécurité à tout prix, Element est déjà une bonne base.
>
> Dans le cas où l'anonymat est un axe important, Session sera plus indiqué.
{.is-info}

*Bien entendu, rien n'empêche d'utiliser les 2 puisque ce sont 2 outils que nous recommandons.*

### Pair-à-pair

Avant d'en venir à l'outil recommandé lui-même, parlons un peu technique.

#### Le modèle Pair-à-Pair

Une communication pair-à-pair (nous utiliserons l'acronyme **P2P** dans la suite) comporte beaucoup d'avantages mais vient la plupart du temps avec quelques inconvénients dans les usages.

Le modèle P2P permet une grande résistance à la fuite de métadonnées ; aucune entité ne doit être présente entre émetteur et récepteur et le modèle rend compliqué l'interception par des adversaires, ce qui engendre des difficultés dans les tâches de collectes de données de tierces parties. De plus, du moment que vous pouvez établir la communication, vous pouvez échanger, sinon il n'est pas possible d'établir une communication.

Mais tout cela a un prix : la **synchronicité**.
- Parce qu'il n'y a pas de serveurs entre émetteur et destinataire pour stocker et relayer vos messages, il est indispensable qu'émetteur et destinataire soient connectés _en même temps_, tout comme d'ailleurs un appel téléphonique : il ne vous sera pas possible d'établir des communications *asynchrones*. Qui aujourd'hui utilise des communications synchrones ? De nos jours, nos échanges peuvent se faire sans avoir besoin que l'autre soit en ligne, c'est-à-dire en communications *asynchrones*. Revenir à un modèle comme cela peut vite devenir difficile pour certains. Les plus anciens peuvent se rappeler AIM, ICQ, ou MSN Messenger pour se dire qu'à l'époque c'était obligatoire : nous devions être sans cesse connectés ou bien devions mettre en place des rendez-vous :) (les plus jeunes, ne vous moquez pas !). Mais nous avons bien conscience que peu de gens se souviennent de cela... *Paradoxalement cela pourrait être un point positif : et nous faire revenir à un modèle plus sain dans nos communications où nous ne devrons pas être à tout instant disponibles.*

- Également, la synchronicité rend très compliqué l'échange en "groupe". Que se passerait-il si une personne du groupe n'était pas en ligne ?! Vous verrez que chaque outil propose des solutions différentes à ce problème.

- Il est important également de noter que le statut "En ligne"/"Hors ligne" sera la seule information directement visible par n'importe qui.

- Également, un compte sera lié à un seul appareil. Il n'y pas de synchronisation inter-équipements puisque pas de serveurs, vous ne pourrez pas retrouver vos données sur un nouvel appareil si vous le perdez... Toutes les données (messages, contacts...) seront stockés chiffrés sur un seul appareil et vous devrez manuellement transférer ces données sur un second appareil.

- Enfin, ces applications sont connues pour bien utiliser la batterie de l'appareil, point important pour certains, surtout avec d'anciens téléphones ou ordinateurs portables !

--------

**L'utilisation de Tor dans ce contexte :**
Bien que le modèle P2P nous permet une résistance à la collecte de métadonnées, cela n'empêche pas des adversaires à fortes ressources d'atteindre ces (méta)données. Ils ont un contrôle ou des capacités leur permettant d'effectuer ces tâches. Afin de réduire le risque, nous pourrions donc utiliser Tor.

Nous l'avons vu dans d'autres articles, Tor va nous permettre d'ajouter une couche d'anonymat. Dans notre contexte actuel il s'agira d'augmenter l'anonymat dans nos communications, de sorte que même si nous sommes ciblés, nos adversaires aient beaucoup, beaucoup de mal à retracer les destinataires avec qui nous échangeons.

Attention tout de même, rappelez-vous bien que Tor n'est pas infaillible (Tor vient d'ailleurs avec de possibles failles dans son réseau [^²2], et nous l'avons aussi évoqué dans les autres articles) et il conviendra de prendre en compte les risques identifiés sur Tor afin de ne pas se retrouver désanonymisés.

[^²2]: [Failles](https://status.torproject.org/) dans le réseau Tor.

> A noter que dans certains endroits, si vous êtes seuls à utiliser Tor, cela peut mener à une désanonymisation tout simplement en analysant le réseau : votre IP ayant contacté un serveur d'entrée Tor, c'est très simple et plutôt fâcheux. On évitera donc d'utiliser ce genre d'applications (et même Tor) dans des endroits hors centres urbains par exemple... Alors vous pourriez me dire : même chose avec Signal, et je vous répondrai : oui vous avez raison ! Mais ces outils apportent tout de même des avantages non négligeables par rapport à Signal.
{.is-danger}

---------

**Les avantages :**
Les applications fonctionnant sur ce modèle P2P ne demandent pas de numéro de téléphone, adresse courriel, ou autre identifiant permettant de rattacher une personne/un utilisateur à son identité. Il est donc tout à fait possible d'utiliser ces applications sur un ordinateur, un téléphone sans carte SIM, ou un téléphone classique sans avoir besoin de lier la carte SIM à l'application.

#### L'outil Briar

[Briar](https://briarproject.org)

Briar est une application open-source, développée par Briar Project, un ensemble de développeurs, hackers et activistes, principalement en Europe. L'application propose bien entendu des échanges P2P, mais l'objectif de Briar est également de permettre des communications si internet tombe : il est donc possible d'échanger directement avec des contacts via Wifi ou Bluetooth, votre interlocuteur devra en revanche être proche de vous. Briar permet également de créer un réseau à part entre différents utilisateurs de l'application, de sorte à acheminer les messages en passant par des contacts comme point de relais.

Son utilisation reste identique en mode chat ou groupe, à ceci près que chaque participant devra être en ligne. Cependant, il est important de bien comprendre son fonctionnement intrinsèque afin de cerner ses objectifs : oui Briar apporte une sécurité très importante dans les échanges, est très résistant à la collecte des métadonnées, mais en revanche Briar **ne fournit pas d'anonymat** ou en tout cas pas à un niveau très important : nous vous conseillons de bien lire ce que les développeurs ont ajouté sur leur wiki [^²4], notamment sur cette question d'anonymat (adresse Bluetooth, IP, etc.).

> Toujours lire les manuels d'utilisation, les documentations ou les FAQ :) !

_**Ressources d'intérêts**_
Briar a fait l'objet d'un audit en 2017 [^²3] : voici le [rapport PDF](https://briarproject.org/raw/BRP-01-report.pdf).

[^²4]: [Briar - wiki](https://code.briarproject.org/briar/briar/-/wikis/FAQ).
[^²3]: [Audit](https://briarproject.org/news/2017-beta-released-security-audit/) de sécurité de Briar.

# D'autres projets ?

D'autres solutions de messageries, moins connues ou plus récentes existent. Nous faisons état ci-dessous de quelques-unes qui méritent de s'y intéresser, bien que pour certaines trop "jeunes" pour être utilisées au quotidien. 

Cela doit rester à la discrétion des utilisateurs de faire confiance ou non en ces outils :
- [Molly *un fork de Signal*](https://molly.im)
- [Cwtch *équivalent de Briar, et solution très intéressante, à regarder de près*](https://cwtch.im/)
- [SimpleX *messagerie qui monte, auditée **\*** en 2022. Uniquement disponible sur Android et iOS*](https://simplex.chat/)
- [Berty *équivalent de Element, en cours d'audit*](https://berty.tech)
{.links-list}

\* Audit de [SimpleX](https://simplex.chat/blog/20221108-simplex-chat-v4.2-security-audit-new-website.html).

## XMPP-Jabber
- [Conversations ** *Concurrence Element et/ou Session*](https://conversations.im/)
- [Snikket *Concurrence Element et/ou Session*](https://snikket.org/)
{.links-list}

\** Analyse de risques partie E2EE OMEMO [^²5]

[^²5]: [Analyse de risques OMEMO](https://conversations.im/omemo/audit.pdf).

## A suivre
Plus confidentiels et pour des profils aux besoins d'anonymat et de sécurité avancés :
- [Speek *transit des échanges via Tor*](https://speek.network/)
- [Delta Chat *une messagerie via e-mail !*](https://delta.chat/en/)
{.links-list}

Nous pouvons mentionner également :
- [TinFoil Chat *qui nécessite tout de même une infrastructure pour une utilisation complète (séparation de l'émetteur et du récepteur, etc.). Pour des profils plutôt initiés ou à l'aise avec l'outil numérique :)*](https://github.com/maqp/tfc)
{.links-list}

# Vidéo conférence

## Jitsi Meet
- [Jitsi Meet](https://meet.jit.si/)
{.links-list}

Disponible :
- Sur ordinateur via un navigateur
- Sur téléphone avec l'application dédiée

## Jami
- [Jami](https://jami.net/)
{.links-list}

Disponible :
- Sur ordinateur via l'application dédiée
- Sur ordinateur via un navigateur
- Sur téléphone avec l'application dédiée
- Sur une box Android TV

## Nextcloud Talk
- [Talk](https://nextcloud.com/fr/talk/)
{.links-list}

Disponible :
- Sur ordinateur via l'application dédiée
- Sur ordinateur via un navigateur
- Sur téléphone avec l'application dédiée

*Note : nécessite cela dit de se créer un compte Nextcloud pour avoir accès à la partie Talk.*

## BigBlueButton
- [BBB](https://bigbluebutton.org/)
{.links-list}

Disponible uniquement sur ordinateur via un [navigateur](https://demo.bigbluebutton.org/gl/).

*Note : conférence limitée à 60 minutes, dû à la charge des serveurs et au grand nombre d'utilisations de l'outil.*


---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo*
<br>