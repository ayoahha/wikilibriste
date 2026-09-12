---
title: Liste des logiciels libres pour l'ingénieur
description: Cette artiche présente des alternatives de logiciels propriétaires
published: false
date: 2025-05-13T19:43:13.386Z
tags: libre, pro, professionnels, ingénierie, ingénieur
editor: markdown
dateCreated: 2025-05-06T20:35:19.482Z
---

Cet article à pour vocation de présenter les principales alternatives aux logiciels propriétaires disponible dans l'industrie à destination des ingénieurs.
Pour faciliter la recherche d'alternative dans cette page je vous conseille la combinaison de touche "CTRL + F" pour chercher directement le logiciel que vous cherchez à remplacer.
### Dessin industriel
## Plan 2D
L'industrie est malheureusement domminé par des logiciels propriétaire dans ce domaine malheureusemenet,, les logiciels propriétaire à remplacer sont les suivants:
| Logiciel | Problème avec le logiciel |
| --- | --- |
| Autodesk Autocad | Pas disponible sous Linux nativement<br>Politique d'abonnement agressive<br>Prix élevé<br>Dépendance aux technologies Américaines |
| Dassault Systèmes Draftsight | Support Linux maintenant indisponible<br>Politique d'abonnement agressive<br>Cher |
| Aveva E3D | Politique d'abonnement agressive<br>Hors de prix |
| Bentley Microstation | Politique d'abonnement agressive<br>Cher<br>Dépendance aux technologies Américaines |
| Graebert ARES | Propriétaire mais fonctionne sur linux et à des licences à vie<br>Cher |
| Bricscad | Propriétaire mais fonctionne sur Linux et à des licences à vie<br>Cher |

Plusieurs logiciels libres tire leur épingle du jeu et sont disponible sous Linux:
### LibreCAD
LibreCAD est initialement un fork de la version community de Qcad, le logiciel est performant.
Pour l'installer : `flatpak install flathub org.librecad.librecad` et pour le lancer `flatpak run org.librecad.librecad`. La version Flatpak est celle conseillé car bien plus à jour que les paquets systèmes type DEB ou RPM.
Le logiciel vous demandera cependant un temps d'adaptation, l'interface est assez éloigné de ce qui ce fait aujourd'hui en dessin par contre cela plaira bien aux anciens qui ont connu Autocad dans les années 2000. Il existe un [manuel en Anglais](https://docs.librecad.org/en/2.2.0_a/) qui est destiné aux utilisateurs qui n'ont pas connu de logiciel de dessin avant, cependant pour les professionnels qui utilise déjà un logiciel de dessin il y a le [Wiki en anglais](https://dokuwiki.librecad.org/doku.php/start) qui dispose de tutoriels pour voir par des exemples comment faire les choses  qu'ils savent déjà faire sur leur logiciel habituel. Youtube dispose aussi de pas mal de tutoriels vidéos sur le sujet.
LibreCAD dispose de ce que l'on attend de ce type de logiciel 2D, c'est à dire des polylignes, les calques, les cotations et les blocs, il dispose même de quelques bloc par défaut [sur le site](https://wiki.librecad.org/index.php/Part_Libraries). 
Là où LibreCAD est un peu plus limité c'est sur le support du DWG (qui ne mache qu'avec les vieux DWG), sur les blocs paramétriques et sur les types de lignes non standard.
LibreCAD lit très bien les fichiers DXF 2007, il est conseillé de transférer ces librairies par ce format.
Si le logiciel vous plait où si vous n'arrivez pas encore à vous séparer du logiciel propriétaire mais que vous voulez quand même voir l'alternative libre s'améliorer vous  pouvez contribuer financièrement [sur leur site](https://librecad.org/donate.html) et participer sur [le forum](https://forum.librecad.org/).
### Qcad

## Plan 3D
## Schéma P&ID
## Design mécanique
## BIM

Contributeur(s): Justin
