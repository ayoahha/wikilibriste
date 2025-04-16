---
title: Sauvegarde des données par synchronisation
description: Gestion des copies de sauvegarde
published: false
date: 2025-04-16T20:07:44.024Z
tags: sauvegarde, copies synchronisées, restauration données
editor: markdown
dateCreated: 2025-04-15T13:35:26.629Z
---

# FreeFileSync

https://freefilesync.org/ 
FreeFileSync est un logiciel de comparaison et de synchronisation de dossiers qui vous permet d'éviter les multiples sauvegardes et les doublons qui en découlent. Un dossier source "maître" est comparé à un dossier "cible" à mettre à jour. C'est aussi simple que cela.
>Une condition impérative : un paramétrage rigoureux **à vérifier à chaque session par sécurité** 
{.is-warning}

L'interface de FreeFileSync, très intuitive par ses libellés et ses titres, permet de rapidement s'approprier les fonctions de ce logiciel très "salvateur" pour nos précieuses données :heartpulse: :heartpulse:

## Outils de paramétrages

### Colonne de gauche : 
- Barre de menus standard
![ffs-menu-standard.png](/images/ffs-menu-standard.png)
- Icônes de fonctions rapides
![ffs-icones-fonctions-rapides.png](/images/ffs-icones-fonctions-rapides.png)
- Sauvegardes personnalisées enregistrées
![ffs-sauvegardes-enregistrées.png](/images/ffs-sauvegardes-enregistrées.png)
- Aperçu des modifications à venir avant validation  de la synchronisation
![ffs-apercu-modifications-proposees.png](/images/ffs-apercu-modifications-proposees.png)
### Colonne centrale de configuration
Elle se présente sous une forme de tableau dans lequel nous allons préparer et personnaliser une synchronisation grâce à la roue crantée verte.
![roue-ffs-crantee.png](/images/roue-ffs-crantee.png)

![source-et-cible-num-2.png](/images/source-et-cible-num-2.png)

### Passons à notre première synchronisation :heart:
Une sauvegarde ne se fait **JAMAIS** sur le même support (ou périphérique) que le dossier "Source".
- Choix de la "**source**" : **parcourir** le gestionnaire de fichiers et sélectionner le dossier désiré.
- Choix de la "**cible**" : **parcourir** et choisir le support de sauvegarde. Il y est fortement conseillé de **nommer clairement et dater** votre dossier de sauvegarde.

Notre meilleur outil : **la roue verte crantée** ![roue-ffs-crantee.png](/images/roue-ffs-crantee.png)

**4 modes de sauvegardes sont proposées**. Chacune d'entre elles a ses particularités ; le logiciel vous indique tant graphiquement (type et couleur d'icône) qu'avec le pointeur de la souris affichant des "infos-bulles", leurs fonctions .

**Nous nous limiterons ici à une synchronisation en "miroir" : la cible sera identique à la source.**
> :point_down::exclamation::point_down::exclamation::point_down:
*Ce paramétrage permet d'envoyer les fichiers supprimés dans la corbeille ; ils seront ainsi récupérables en cas d'erreurs.*  :satisfied:{.is-warning}

![ffs-fenetre-parametrages-miroir-2.png](/images/ffs-fenetre-parametrages-miroir-2.png)

> :point_down::exclamation::point_down::exclamation::point_down:
*Ce paramétrage, mode permanent, permet de supprimer définitivement les fichiers ; ils seront donc irrécupérables en cas d'erreurs.*  :sob:{.is-warning}

![ffs-corbeille-permanente.png](/images/ffs-corbeille-permanente.png)
