---
title: Whonix
description: Ou comment naviguer sur Internet de manière anonyme avec Whonix
published: true
date: 2023-10-25T13:51:21.325Z
tags: vie privée, anonymat, sécurité
editor: markdown
dateCreated: 2023-05-13T20:03:19.988Z
---

![proxy-image.jpeg](/images/proxy-image.jpeg){.align-center}


[**Whonix**](https://www.whonix.org/) est un système d’exploitation (**OS**) conçu pour renforcer sa vie privée et sa sécurité sur internet, avec un accent prononcé pour l'anonymat. Ce système d’exploitation fait passer votre connexion internet ainsi que tout le trafic réseau par une passerelle **Tor** qui anonymise votre trafic.

**Whonix** peut s'utiliser de deux façons :
- Sur une clé USB, en tant que système indépendant.
- Via des machines virtuelles compatibles tout système d'exploitation (Windows, Linux, MacOS, etc.).

C'est de cette dernière solution dont nous allons parler dans ce tutoriel, car l'utilisation sur clé USB est assez récente et nous lui préférons **Tails OS** dans ce cas précis.

> *Pour plus de détails et explications sur le concept de la virtualisation, nous vous renvoyons vers l'article dédié à la [Virtualisation](/intermediaire/virtualisation).*
{.is-info}

# L'anonymat

## Pourquoi rechercher l'anonymat sur internet ?

> **:warning: A NOTER : LE VRAI ANONYMAT SUR INTERNET N’EXISTE PAS ! MAIS IL EXISTE PLUSIEURS NIVEAU D'ANONYMAT SELON SES BESOINS. :warning:**
> 
> Aucune méthode ne peut prétendre protéger _pleinement_ l’anonymat de l'utilisateur sur le réseau Internet. Le seul fait d’être connecté à un réseau externe mondialement inter-connecté vous expose, peu importe la méthode choisie.
> 
> **La seule façon d'être totalement anonyme sur internet est... de ne pas l'utiliser !** ;-)
{.is-warning}

Avant de voir comment naviguer sur Internet de manière quasi anonyme, posons-nous la question de la raison de rechercher l’anonymat sur Internet, si l’on a rien à se reprocher ?

Les raisons peuvent être multiples :
- Protéger certaines recherches Internet concernant des sujets personnels tels que :
	- Des problèmes de santé
	- Des recherches intimes (orientation sexuelle, etc.)
	- Des croyances religieuses
	- Engagements politiques
	- Espionnage économique
- Protéger certaines sources si vous êtes activiste, journaliste ou avocat

Vous souhaitez bien entendu que personne ne puisse vous relier à ces recherches et que personne ne puisse utiliser ces informations contre vous ?

Ou bien vous vivez peut-être dans une zone dans laquelle la surveillance et la censure Internet ont lieu ? 

Ou plus simplement vous souhaitez protéger vos données personnelles sans avoir le sentiment d’être traqué par les annonceurs et leurs traceurs publicitaires ou par votre fournisseur d’accès Internet ?

**Whonix est une solution à ces problématiques**.

# Présentation de WHONIX

- Il s'agit d'un système d'exploitation (**OS**), à part entière : [**Distributions Linux**](/debutant/linux-distributions) libre et open-source, fonctionnant dans un environnement virtualisé. Cet **OS** se compose en fait de deux machines virtuelles, et le système est basé sur la très reconnue distribution [**Debian**](https://fr.wikipedia.org/wiki/Debian) :
	- L'une sert de station de travail, nommée **Whonix Workstation** alors que, 
	- La seconde, nommée **Whonix Gateway** sert de passerelle réseau pour diriger les connexions internet du navigateur ainsi que le trafic des applications vers [**TOR**](/debutant/vpn-tor#tor)
  {.grid-list}
- **Whonix** permet de dissimuler l’adresse IP attribuée par votre fournisseur d’accès Internet ([FAI](/glossaire#fai)), protégeant ainsi votre trafic du regard de votre FAI ainsi que des sites web que vous visitez. Cela vous permet également de contourner la censure dans l’éventualité ou vous en seriez victime, même si l'utilisation de cet outil peut alerter des autorités malveillantes (il conviendra d'adopter des bonnes pratiques pour se sécuriser).
	- Seules les connections via le réseau **Tor** sont autorisées. Les [**fuites DNS**](https://www.opportunites-digitales.com/protection-fuites-dns) (DNS Leaks) sont dans ce cas très limitées.
	- En utilisant **Whonix**, votre **FAI** peut voir que vous utilisez le réseau **Tor** mais sera incapable de savoir ce que vous y faites.
  {.grid-list}
- Toutes les applications pré-installées sur la distribution sont configurées pour être le plus sûr possible, il n'est donc pas recommandées de modifier la configuration de la distribution.

Techniquement, grâce à la virtualisation :
1. La **Whonix Gateway** ("gateway" pour passerelle) est le première VM à être lancée. Cette VM sert de lien entre la machine hôte et la seconde VM **Whonix Workstation** en créant un réseau virtuel entre les 2 VMs ; son objectif est simple : donner un accès **sécurisé** au réseau à la seconde VM, ce qui sous entend donc l'utilisation de règles pare-feu strictes et d'adressage réseau spécifique (MAC, IP etc.). De plus, scinder la partie réseau dans une VM spécifique renforce le niveau de sécurité des connexions.
2. La **Whonix Workstation** est la seconde VM, et est donc totalement _isolée_ de la machine hôte et du réseau internet de celle-ci, car passant par la **Whonix Gateway**. En effet, elle n'est connectée qu'au réseau virtuel interne et ne peut communiquer directement qu'avec la passerelle, ce qui impose à tout le trafic venant de la station de travail de passer obligatoirement par la passerelle et donc le réseau Tor. Cette VM ne peut « voir » que les adresses **IP** du réseau local virtuel interne. Ainsi, les applications utilisateurs n'ont aucun moyen de connaître la véritable adresse **IP** de l'utilisateur puisque la station de travail elle-même ne la connaît pas. Idem pour l'adresse **MAC**.


# Installation de WHONIX

L'installation de **Whonix** n'a rien de compliqué en soi : il suffit de suivre scrupuleusement les étapes ci-après :

## Pré-requis
> ~~ Avoir un OS **64 bit** et un minimum de **4 Go** de RAM. Pour des performances et un confort d'utilisation confortable, nous conseillons plutôt **8 Go** voire plus. Ces spécifications sont visibles :
	- dans les Paramètres de la distro, partie "A Propos" ou s'en rapprochant
	- ou bien dans un terminal via la commande `uname -m` : si la commande vous renvoi `x86_64`, votre OS est 64 bits, sinon l'OS n'est pas compatible.
>
> ~~ Avoir installé **Virtualbox**, nous renvoyons vers notre tutoriel spécifique concernant [**Virtualbox**](/tutoriels/virtualbox).
{.is-info}

La première étape consiste à télécharger l'image de l'environnement virtualisé (avec l'extension `.ova`, pour "Open Virtual Appliance") sur [le site officiel de **Whonix**](https://www.whonix.org/wiki/VirtualBox). Celle-ci comprend en fait les deux machines virtuelles **Workstation** et **Gateway** déjà pré-configurées pour **Virtualbox**.

![whonix.org.png](/whonix.org.png){.align-center}

La rédaction de ce tutoriel se fait à partir d'une distribution [**Debian**](/tutoriels/debian). L'installateur **Whonix Linux** pour **VirtualBox** n'est pris en charge que pour **Debian** et ses dérivés tels que [**Ubuntu**](/tutoriels/ubuntu), [**Kicksecure**](https://www.kicksecure.com/wiki/Debian), [**Linux Mint**](/tutoriels/mint)...
> Il est à noter que **Whonix** ne pourra s'installer sur **Ubuntu** uniquement à partir de la version 22.04 nom de code **Jammy**.
{.is-warning}

Pour les autres distributions **Linux**, cliquez sur "**Other Linux Distributions**" et suivre les étapes détaillées.
> Vérifiez que l'onglet **GUI** est bien sélectionné, la version **CLI** de **Whonix** est en ligne de commande. 
{.is-warning}

![whonix.org_installation.png](/images/whonix.org_installation.png){.align-center}

- Téléchargement :
```
curl --tlsv1.3 --output whonix-installer-xfce --url https://www.whonix.org/installer-dist
```
- Lancez l'installation :
```
bash ./whonix-installer-xfce
```
- Une question d'acceptation du contrat de licence vous est demandée, avec les flèches de direction de votre clavier. ![touche_fleches.jpg](/images/touche_fleches.jpg){.align-center} Sélectionnez "**Agree**" et validez avec la touche entrée.

![acceptation_license.png](/images/acceptation_license.png){.align-center}

- Patientez jusqu'à la fin de l'installation où il vous sera demandé si vous voulez lancez les **Whonix VM**. Tapez "**y**" (yes) pour accepter 

![question_en_cours_installation.png](/images/question_en_cours_installation.png){.align-center}

- **Virtualbox** va s'ouvrir et vous pouvez constater que les deux **VM** sont présentes, déja configurées, prêtes à être lancées.

![whonix_virtualbox.png](/images/whonix_virtualbox.png){.align-center}

- Sélectionnez une **VM**, en suivant notre tuto sur [**Virtualbox**](/tutoriels/virtualbox) vous pouvez modifier le cas échéant la quantité de mémoire que vous souhaitez allouer à vos **VM**.
- Lancez de préférence **Whonix Gateway** en premier : c'est elle qui configure le réseau **Tor**.

> Même s'il est possible de lancer les deux machines virtuelles en même temps, pour le tout premier démarrage, il est plus confortable de le faire l'une après l'autre. Pour le tutoriel, les deux **VM** sont lancées en même temps.

![affige_deux_machines_virtuelles.png](/images/affige_deux_machines_virtuelles.png){.align-center}

## Premier lancement

- Premier lancement, un message de l'équipe de développement vous informe. Voici la traduction de ce message :

> '*Informations importantes sur ce système d'exploitation (OS) 
Ne continuez pas si vous n'avez pas tout compris !
Il ne s'agit pas du bla-bla habituel, mais de faits. Ce système d'exploitation est un projet de recherche. Ce système d'exploitation est gratuit. Ce système d'exploitation est un dérivé de Debian GNU/Linux. Ce système d'exploitation est produit indépendamment du projet Tor, sans aucune garantie de sa part. Ce système d'exploitation a été créé par des volontaires pendant leur temps libre. Ce système d'exploitation a été créé par des amateurs autodidactes pendant leur temps libre, sans le soutien d'une certification ou d'une formation formelle particulière. Bien que ce système d'exploitation tente d'être aussi utilisable que possible, il échoue à bien des égards. Ce système d'exploitation est en anglais. N'utilisez pas ce système d'exploitation sans une excellente connaissance de la langue anglaise. Les malentendus ont des conséquences. Ce système d'exploitation est basé sur d'autres logiciels, notamment GNU/Linux, Debian et la virtualisation. Ne vous fiez pas à ce système d'exploitation si vous n'avez pas une connaissance pratique de ces technologies.
La documentation disponible sur Whonix.org est un cours accéléré sur l'anonymat, la vie privée et la sécurité sur Internet. Whonix est un moyen technologique d'accéder à l'anonymat, mais rester anonyme n'est pas seulement un problème technologique. Aucun outil n'est suffisant pour assurer votre sécurité. L'anonymat est un problème complexe sans solution facile, et la sécurité est aussi forte que son maillon le plus faible, souvent l'utilisateur. Plus vous en savez, plus vous êtes en sécurité.
Ce système d'exploitation est une compilation de logiciels, chacun étant soumis à son propre copyright et à sa propre licence. Les termes exacts de la licence pour chaque programme sont décrits dans les fichiers individuels dans /usr/share/doc/*/copyright.
La compilation est mise à disposition selon les termes de la licence publique générale GNU publiée par la Free Software Foundation, soit la version 3 de la licence, soit (à votre choix) toute version ultérieure avec des conditions supplémentaires applicables selon la section 7 de la version 3 de la GNU GPL. La licence peut être appelée GPL-3+-with-additional-terms-1 et peut être trouvée dans /usr/share/whonix/WHONIX_BINARY_LICENSE_AGREEMENT ou en ligne ici https://www.whonix.org/wiki/Whonix:Copyrights.*'

- Cliquez sur ***Understood***
- Un autre message s'affiche, cliquez de nouveau sur ***Understood*** et ***Finish*** pour valider les informations
- L'écran suivant est la partie configuration du réseau **Tor**, laissez le choix par défaut **Connect** et cliquez sur **Next**

![configuration_tor.png](/images/configuration_tor.png){.align-center}

- Cliquez sur **Next** une nouvelle fois pour lancer la configuration réseau
- Patientez, un message vous informe que tout est OK, la **Whonix Gateway** est désormais connectée au réseau **Tor**, cliquez sur **Finish**

![succès_connexion_tor_.png](/images/succès_connexion_tor_.png){.align-center}

- Avant de se lancer, **Whonix** vérifie que ses dépôts, **Tor** et la distribution sont à jour. À l'issue du ***System Check***, s'affichent en rouge les mises à jour éventuelles à effectuer. Ici, la distribution **Debian** n'est pas à jour, la commande pour se faire est indiquée dans le message, à savoir :
```
upgrade-nonroot
```
- Pour accéder au terminal, le chemin est également indiqué :
	- Start Menu -> System -> Terminal
- Après le bon déroulement des mises à jour, il faut de nouveau relancer la vérification du système
- Suivez le chemin suivant
	- Start Menu -> System et double cliquez sur **System Check**

![systemcheck.png](/images/systemcheck.png){.align-center}

- Notre **VM** est correctement mise à jour, tout est au vert, **Whonix Gateway** est prête !

![succès_mise_à_jour.png](/images/succès_mise_à_jour.png){.align-center}

> Laissez la VM**Gateway** ouverte, lancez **Whonix Workstation** dans **Virtualbox** et répétez les mêmes opérations.
{.is-warning}

- Les deux **VM** sont désormais à jour, **Whonix** est désormais opérationnel !

![deux_vm_fonctionnelles.png](/images/deux_vm_fonctionnelles.png){.align-center}

> Félicitations, vous avez installé **Whonix** !
{.is-success}

# Premier pas

## Changement disposition clavier
- Après installation, il est nécessaire de changer la disposition du clavier qui est par défaut en **Qwerty**.
- Suivez le chemin suivant : Start Menu -> System -> Keyboard :
1. Cliquez sur **Layout**,
1. Modifiez la langue dans **Keyboard Layout**,
1. Cliquez sur **Add** et choisir **French**,
1. Selectionnez **English (US)** et cliquez sur **Remove** pour supprimer la langue anglaise.

![clavier.png](/images/clavier.png){.align-center}

- **Faites ceci sur les deux VM Whonix** et redémarrez les deux machines virtuelles
> Au moment de la rédaction de cet article, il existe un [bug avec la langue française]( https://www.kicksecure.com/wiki/Keyboard_Layout#Footnotes). Si tel est le cas, recommencez les opérations précédentes et redémarrez plusieurs fois si besoin.
{.is-warning}

## Changement mot de passe par défaut

- Maintenant que votre clavier est en français, il sera plus aisé de changer le mot de passe par défaut.
- Ouvrez le terminal de la **VM** de votre choix, il sera nécessaire de répéter cette opération dans les deux **VM**.
- Tapez la commande suivante et appuyez sur **Entrée** :
```
passwd
```

![changement_mot_de_passe.png](/images/changement_mot_de_passe.png)

- Tapez le mot de passe par défaut qui est "***changeme***".
- Tapez ensuite le nouveau mot de passe et validez.
- Confirmez celui-ci en le tapant une seconde fois et validez.
- Un message vous confirme le succès de l'opération.

![succès_changement_mdp.png](/images/succès_changement_mdp.png){.align-center}

> Vous êtes désormais prêt à utiliser un système sécurisé et vous permettant de renforcer votre anonymat.
{.is-success}

## Bonnes pratiques

> Il est à noter que bien que les fonctions de partage de répertoire et de presse-papier soient très pratiques, cela réduit, de fait, la sécurité des deux systèmes puisque le cloisonnement inhérent aux machines virtuelles n'est plus assuré en totalité. C'est encore plus important sur un système **Whonix**.
> 
> **Il n'est pas donc pas recommandé d'activer ces options**.
{.is-warning}

> Du fait que tout le trafic Internet transite par **Tor**, la navigation peut-être ralentie voire excessivement ralentie ; c'est la contre partie, dû au fonctionnement de **Tor** lui-même.
> 
> **Ceci est à prendre en compte pour les personnes ne bénéficiant pas de connexion Internet à haut débit**.
{.is-warning}

> Afin de garder un niveau de sécurité et d'anonymat optimal il n'est pas recommandé de transférer des fichiers entre ces VM et votre machine hôte.
{.is-warning}

> Egalement, il n'est pas recommandé de vous connecter à des comptes utilisateurs type e-mail, réseau sociaux, au risque bien entendu de vous désanonymiser !
> 
> **Référez-vous à l'article dédié à [Tor](/debutant/vpn-tor#tor)**.
{.is-warning}

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Theudric*
<br>