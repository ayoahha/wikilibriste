---
title: Auto-hébergement
description: Nous apprendrons ici ce qu'est la pratique de l'auto-hébergement, et comment mettre en place son propre serveur pour héberger les services Internet que nous souhaitons, en toute simplicité.
published: true
date: 2023-07-15T12:35:55.456Z
tags: serveur, hébergement
editor: markdown
dateCreated: 2023-01-16T11:17:05.659Z
---


> "*L'auto-hébergement est une pratique consistant à héberger ses services réseau sur ses propres machines ou sur des serveurs dédiés virtuels.*"

# Définition

Cette pratique s'oppose à l'utilisation de services d'hébergements chez un prestataire, qui est le modèle que nous utilisons le plus souvent au quotidien, et que nous imposent notamment les GAFAM.

L'auto-hébergement est une pratique encore courante dans la majorité des entreprises, et peut également intéresser les particuliers pour diverses raisons, surtout avec les possibilités qui nous sont offertes aujourd'hui. Il permet notamment d'avoir le contrôle et la responsabilité de ses propres données.

L'auto-hébergement offre donc la possibilité de trouver des alternatives à des applications comme Google Drive, Office365, Youtube ou de contribuer à l'agrandissement des réseaux sociaux décentralisés comme ceux du [Fediverse](https://fediverse.party/), sans avoir à payer d'abonnement aux entreprises qui développent ces logiciels, que ce soit explicitement, ou avec nos données personnelles.

Par définition, si nous faisons attention aux services que nous installons sur notre serveur, nos données sont là où nous avons décidé qu'elles soient. Si vous cherchez une solution pour protéger vos données, mais que les services respectueux de votre vie privée coûtent trop cher, que vous n'aimez pas vraiment cette idée de payer un tel service, que vous ne voulez pas vraiment faire confiance à cette entreprise ou association, **l'auto-hébergement est fait pour vous**.

**Plusieurs systèmes d'exploitation proposent de faciliter l'auto-hébergement d'applications :**

- [Yunohost](https://yunohost.org/) : basé sur Debian [^¹], il automatise l'installation de plus de 400 applications, officiellement supportées.
- [UCS-Univention](https://www.univention.com/products/ucs/) : utilise des conteneurs docker : il est plutôt orienté pour un usage en entreprise avec une intégration LDAP complète.
- [UmbrelOS](https://umbrel.com) : utilise des conteneurs docker : encore assez (trop ?) récent et donc de potentiels bugs peuvent exister...
- [NextcloudPi](https://nextcloudpi.com/) : image clé en main pour installer Nextcloud sur un RaspberryPi (appelé Rpi pour simplifier) ; cependant, cela limite le RPi à faire tourner Nextcloud (et ses extensions), et aucun autre service.

[^¹]: Distribution GNU/Linux, disponible aussi bien sur serveur que pour ordinateurs personnels. Réputée pour sa stabilité et son niveau de sécurisation, elle est la distribution parente, dont sont issues Ubuntu et ses dérivés. C'est également le socle favori de nombreuses distributions orientées cyber sécurité ou vie privée. Pour plus de détails, aller sur le [site officiel](https://www.debian.org/) de Debian. Cet [article](/debutant/linux-distributions) traite également des différentes distributions Linux, dont Debian.

# Règles de sécurité

#### **:warning: Ne continuez pas sans comprendre cette section :warning:**

> **Il est très important ici de faire un point sur la sécurité quand on héberge un service qui est accessible via Internet.**
{.is-danger}

Il y a une différence fondamentale entre un ordinateur personnel (communément appelé "station de travail") et un serveur : 
- **l'ordinateur personnel n'est normalement par défaut pas accessible depuis Internet**, bien qu'il puisse de lui-même faire des requêtes vers Internet. Mais il n'est pas possible pour "Internet" de faire des requêtes vers votre ordinateur, sauf faille au niveau de vos équipements (votre box) ou choix particuliers de votre part.
- **Le serveur en revanche est accessible depuis Internet**. C'est pour cela que n'importe qui pourra s'y connecter grâce à une URL. Cela implique de nombreuses choses au niveau de la sécurité.
{.grid-list}

La box de votre [FAI](/glossaire#fai) est configurée par défaut pour ne laisser passer aucune "connexion entrante", c'est-à-dire connexion qui viendrait d'Internet, pour faire des requêtes à un de vos appareils. Or, pour un serveur, nous allons devoir ouvrir des "ports" pour dire à la box que si quelqu'un fait une requête depuis Internet sur tel port de la box, il faudra la rediriger vers tel appareil/serveur spécifiquement (et tel port de cet appareil).

> La sécurité de cet appareil n'est donc plus du tout assurée par la box, mais par l'appareil en lui-même, car la box redirige toutes les demandes vers cet appareil et ne fait rien d'autre.
{.is-warning}

Le problème, c'est que si un attaquant arrive à pénétrer sur cet appareil, il se retrouve sur notre réseau local, et pourrait commencer à s'introduire sur nos autres appareils personnels connectés à cette même box.

De fait, tout dépend du niveau de sécurité que nous allons appliquer ! **Il est donc très important de s'imposer certaines règles** :
 - **Les mots de passes doivent être _très_ solides sur cette machine** : le mieux serait un long mot de passe aléatoire, au moins pour tous les utilisateurs qui ont des droits administrateur. Car si les mots de passe des administrateurs sont retrouvés, nous accorderions beaucoup de droits à un attaquant. Nous vous invitons à lire l'article sur [Keepass](/tutoriels/keepass) pour générer et retenir des mots de passe très complexes en toute sécurité et facilement.

 - **Les mises à jour doivent être très régulières** : en effet, si une faille vient à être découverte sur l'un des services que nous hébergeons, ou sur l'application d'hébergement, un attaquant verra très vite si notre système a été mis à jour ou s'il est vulnérable à cette faille. S'il est vulnérable, il lui faudra peu de temps pour prendre contrôle de votre appareil. Les mises à jour s'imposent donc. Sur des applications d'hébergement comme Yunohost, les mises à jour sont très faciles, n'hésitons pas à en abuser !

 - **N'activons que les services nécessaires à votre serveur** : Inutile d'activer des services dont nous ne nous servons jamais... Comme vous le savez, nous découvrons chaque jour des failles sur de nombreux services ou applications donc plus nous multiplions des services avec failles, plus nous augmentons le risque sur notre serveur et ses utilisateurs. Exemple : si nous n'utilisons pas Telnet, désactivons-le ! Si nous n'utiliserons jamais SSH, désactivons-le.
Il en va de même pour les ports réseau gérés sur ce serveur : via le pare-feu applicatif (firewalld, gufw, etc.), il nous est possible de contrôler finement les ports autorisés et non autorisés. Veillons à être rigoureux sur cet aspect.

**Il s'agit là des 3 règles absolument incontournables.**

Les conséquences seraient bien plus graves que pour un ordinateur personnel. Rappelons-nous que nous ne sommes peut-être pas seul à utiliser ces services que nous hébergeons, et que nous rendrions donc vulnérables les données de toutes ces personnes.

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Esf, Ayo, Nemtech*
<br>