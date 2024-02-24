---
title: Jouer sur Linux
description: Cet article tente de répondre à la question : peut-on jouer à des jeux vidéos sur GNU/Linux ?
published: false
date: 2024-02-24T23:52:59.029Z
tags: jeux, jeux vidéo, jeux video, jeu video, jeu vidéo, jouer, gaming
editor: markdown
dateCreated: 2022-12-04T14:31:15.648Z
---

---
title: Jouer sur Linux
description: Cet article tente de répondre à la question : peut-on jouer à des jeux vidéos sur GNU/Linux ?
published: true
date: 2023-03-25T07:12:43.500Z
tags: jeux, jeux vidéo, jeux video, jeu video, jeu vidéo, jouer, gaming
editor: markdown
dateCreated: 2022-12-04T14:31:15.648Z
---

Une question revient souvent chez les débutants prêts à passer à Linux : peut-on jouer à des jeux vidéos ?

Il est clair que pendant longtemps Windows et MacOS étaient les plateformes privilégiées pour jouer. C'était possible avec Wine mais ça freinait quand même certaines personnes pour passer au libre. Maintenant, les choses sont devenues beaucoup plus simples et la réponse est oui, avec cependant quelques efforts...

# Wine & Consorts

Comment faire fonctionner un programme Windows (dont il n'existe pas de version Linux) sur GNU/Linux ?

Pour pouvoir faire fonctionner un programme Windows (dont il n'existe pas de version Linux) sur GNU/Linux, vous allez devoir **simuler** un environnement Windows, ou autrement dit implémenter une interface technique de type *windows*.

[Wine](https://www.winehq.org/) est crée en 1983 et c'est un acronyme : Wine Is Not a Emulator. C'est un logiciel qui reprend l'implémentation de Windows pour lancer des jeux vidéos sur GNU/Linux. En résumé, vous avez Linux mais vous avez une interface Windows qui vous permet de jouer à des jeux disponibles seulement sur Windows. 

Il est tout à fait possible d'utiliser Wine seul, sans autre programme pour vous aider. C'est très bien pour des utilisateurs confirmés, mais pour les débutants ou utilisateurs standards, nous allons préférer une "surcouche" avec une interface graphique claire et des fonctionnalités construites pour vous. 

Plusieurs programmes permettent de faire cela. Tous ceux cités dans cette liste utilisent en fait comme socle **Wine**, devenu le *saint-graal* ( :) ) pour tous ceux qui cherchent à utiliser des programmes Windows sur GNU/Linux :

- [Bottles](https://usebottles.com/) : Vous permet très facilement de faire fonctionner un programme Windows sur GNU/Linux avec une interface simple et efficace. Configurable selon vos besoins. Chaque application est confinée dans une "bouteille".

- [Lutris](https://lutris.net/) : Lutris permet à la base de faire fonctionner des jeux, mais peut être utilisé pour d'autres programmes. L'interface graphique est claire et épurée, quelques fonctionnalités de bases facilement repérables, et bonnes possibilités de configuration. Si vous jouez, il vous sera très facile d'installer des milliers de jeu en quelques clics sans connaissance technique.

- [PlayOnLinux](https://www.playonlinux.com/fr/) : PlayOnLinux est un logiciel libre basé sur Wine. C'est le même principe que Lutris, son ancêtre en quelque sorte. Efficace et relativement simple (moins que Lutris) et interface graphique potable.

- [CrossOver](https://www.codeweavers.com/) : Version professionnelle et payante de Wine. Utile si vous souhaitez faire tourner un programme et que vous rencontrez quelques difficultés. 30 jours d'essai gratuit, après c'est payant. Toutes les modifications de Wine apportées par CodeWeavers sont en retour utilisables par la communauté, conformément à la licence LGPL. CodeWeavers emploie la grande majorité des développeurs de Wine.

- [Proton](https://www.protondb.com/) : C'est un fork de Wine utilisé par Steam pour faire tourner une grande partie de ses jeux. Vous ne pouvez l'utiliser que pour Steam et ses jeux. Il fonctionne très bien, et est de plus en plus performant, et ça ne risque pas de s’arrêter avec la sortie de la Steam Deck. Pour voir les milliers de jeux compatibles, c'est ici :

- [Playnite](https://playnite.link/) est une bibliothèque de jeux unifiée avec une interface simple et esthétique.

# Steam

Lorsqu'on parle de jeux vidéo, on pense rapidement à **Steam**. 

[Steam](https://store.steampowered.com/?l=french) est une plateforme de jeux. Elle dispose aussi d'un magasin recensant environ 15 000 jeux. Cette plateforme a été créée en 2003 par Valve Corporation (dirigée par Gabe Newell) et l'entreprise est connue pour ses jeux phares tels que *Half Life*, *Team Fortress* et *Counter-Strike* pour les connaisseurs.

En 2013, Steam a été adapté pour les systèmes GNU/Linux. Les utilisateurs pouvaient jouer à quelques jeux comme *Left 4 Dead*.

_Quelques articles complémentaires :_
- [Wine](https://fr.wikipedia.org/wiki/Wine)
- [Steam](https://fr.wikipedia.org/wiki/Steam)
- [Installer Steam](https://fr.wikihow.com/installer-Steam)
- [Article Jouer sur Linux](https://www.clubic.com/jeu-video/steam-machine/actualite-5038-jouer-sur-linux-c-est-possible-on-a-essaye-et-on-a-adore-.html)


# Distributions Gaming

## Les distros classiques

| Nom distro | Environnements<br>de Bureau | Base | CPU | URL | Gestionnaires<br>de paquets |  Commentaires |
|----------|----------|----------|----------|----------|----------|----------|
| Linux Mint | **Cinnamon**<br>Mate<br>Xfce | Ubuntu LTS | 64 bits | [Site de Linux Mint](https://linuxmint.com/download.php) | dpkg (.deb)<br>apt<br>MintInstall<br>Flatpak | Cette distribution est tellement stable que vous pourrez très bien partir sur une base Mint, puis installer les outils de gaming, Steam, Lutris, etc. et la plupart des jeux tourneront ! <br>**Néanmoins sur des configurations récentes, cette distribution n'exploitera pas tout le potentiel des composants CPU et graphique, un compromis à faire !** |
| Zorin OS | **Gnome Zorin** | Ubuntu LTS | 64 bits | [Site de Zorin OS](https://zorin.com/os/download/) | dpkg (.deb)<br>apt<br>Zorin SoftwareStore<br>Snap Store<br>Flatpak | Idem ici, distribution extrêmement stable, ce qui lui permet d'obtenir des performances honorables<br>**Les équipes de Zorin ont même plancher sur une compatibilité accrue des programmes Windows. Mais tout comme Linux Mint, pour des configurations très récentes, les performances peuvent être inférieures des distros optimisées.** |
| Ubuntu Desktop | **Gnome Ubuntu**<br>KDE Plasma | Debian Testing + Ajouts Canonical | 64 bits | [Site de Ubuntu-FR](https://www.ubuntu-fr.org/download/) | dpkg (.deb)<br>apt<br>Snap Store<br>Flatpak | N'oublions pas non plus Ubuntu, qui avec les DE GNOME ou KDE (uniquement), d'après certains tests permettent d'obtenir de bonnes performances en gaming. |
| KDE Neon | **KDE Plasma** | Ubuntu LTS | 64 bits | [Site de KDE Neon](https://neon.kde.org/) | dpkg (.deb)<br>apt<br>Snap Store<br>Flatpak | C'est une belle surprise car, dans quelques tests d'utilisateurs, elle arrive à concurrencer les distributions optimisées. |
{.dense}

## Les distros optimisées

| Nom distro | Environnements<br>de Bureau | Base | CPU | URL | Gestionnaires<br>de paquets |  Commentaires |
|----------|----------|----------|----------|----------|----------|----------|
| Nobara | **Gnome**<br>KDE Plasma<br> | Fedora | 64 bits | [Site de Nobara](https://nobaraproject.org/download-nobara/) | dnf | Nobara est l'une des distributions les plus prometteuses pour le gaming, le streaming et la création de contenus. Elle est cependant assez jeune mais évolue vite et possède déjà un bon socle d'utilisateurs. Basé sur le `kernel-zen` modifié et optimisé.<br>**Vous trouverez cependant certains jeux qui ne tourneront pas sans configuration préalable. Pour ce faire, il conviendra de s'appuyer sur le site [ProtonDB](https://www.protondb.com/).** |
| Garuda | **KDE Plasma**<br>Gnome<br>Xfce | Arch Linux | 64 bits | [Site de Garuda](https://garudalinux.org/downloads.html) | pacman | Distribution qui se veut tournée vers le gaming sur Linux. Basé sur le `kernel-zen` ou le `kernel-amd` (pour les possesseurs de matériels AMD).<br>**Vous trouverez également ici certains jeux qui devront être configurés grâce à [ProtonDB](https://www.protondb.com/).** |
| Kernel XanMod | KDE Plasma<br>Gnome<br>Xfce | Ubuntu | 64 bits | [Site de XanMod](https://xanmod.org/) | apt | Nous fournissons ici une solution différente : l'idée ici est d'installer une distribution standard basée sur Ubuntu (Ubuntu, Mint, Zorin ou autre), avec l'installation du kernel XanMod, dédié au gaming et l'optimisation du système.<br>**Réservé à ceux qui ont un bagage Linux important !** |
{.dense}


*Par LPGEL*
