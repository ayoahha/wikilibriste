---
title: Améliorer la compatibilité des applications bancaires sur les systèmes basés sur Lineage
description: Cet article présente différentes manières et configuration  pour améliorer la compatibilité des applications bancaires sur /e/OS, LineageOS, CalyxOS et tout autre système complètement dégoogleisé utilisant une base LineageOS et microG 
published: true
date: 2025-05-15T20:41:45.861Z
tags: 
editor: markdown
dateCreated: 2025-05-13T20:48:04.308Z
---

# Introduction
Grace aux alternatives open sources disponible sur [F-droid](https://f-droid.org/fr/) ou encore sur [Droid-ify qui inclue le dépot IzzyOnDroid](https://f-droid.org/fr/packages/com.looker.droidify/), il ne reste quasi plus aucune application qui n'est pas une alternative Open Source capable de faire le travail. Et avec des [ROM](/glossaire) comme [/e/OS](https://e.foundation/e-os/) qui propose tout les remplacements à Google préinstallé il n'y a plus aucune raison de ne pas enlever au maximum Google de sa vie, cependant un type d'application necessaire mais parfois compliquer à faire tourner revient régulièrement, les applications bancaires.
Dans ce tutoriel on va donc voir comment améliorer la compatibilité de celles-ci.

# Les banques à problèmes
Certaines banques sont des plaies pour le monde de l'open source, voici quelques exemples :
- Revolut : A éviter absolument, c'est une banque qui lutte activement contre les ROM alternatives sous couvert d'amélioration de la sécurité alors m^eme qu'elle est installable sur des versions d'android qui ne sont plus mis a jour depuis plusieurs années. Ils utilisent les technologies de DexProtector pour bien maximiser les chances de ne pas fonctionner sur une ROM alternative.
- Boursobank, anciennement Boursorama, qui utilise des technologies plus simple pour bloquer les app soit disant ne venant pas du Playstore comme pour un soutien à la pratique anticoncurrentielle de Google sur le marché.

Pour Revolut, il faut utiliser des solutions de contournement spécifiques à chaque protection mise en place, ce qui n'est pas encore très implémenté dans les ROM basé sur LineageOS car cela revient à adapter spécialement le système d'exploitation pour faire fonctionner une seule application.
Pour Boursorama, l'utilisation de microG bien configuré perment de grandement améliorer la compatibilité de l'app et permet pour le moment de réussir à ce connecter une fois l'application connecté.

/e/OS maintiennent sur leur forum une [liste de la compatibilité](https://community.e.foundation/t/list-banking-apps-on-e-os/33091) des app bancaires avec /e/OS.

# Les outils des banques
Les développeurs des banques utilisent les moyens mis à disposition dans les librairies de Google pour contrôler si le système d'exploitation est sécuritaire ou pas, le principal moyen c'est le [Google Play Integrity](https://developer.android.com/google/play/integrity?hl=fr) (GPI). Vous pouvez vérifier votre niveau de compatibilité avec le GPI en utilisant une application checker comme [SPIC Simple Play Integrity Checker](https://github.com/herzhenr/spic-android) aussi dispo sur [ApkLounge ou Aurora Store](https://play.google.com/store/apps/details?id=com.henrikherzig.playintegritychecker). 

Il existe 4 niveaux de conformité au GPI :
1. NO_INTEGRITY ce qui veut dire que le téléphone a été rooté de facon visible ou que l'application fonctionne sur un émulateur Android comme Waydroid par exemple.
2. MEETS_BASIC_INTEGRITY ce qui veut dire que le système d'exploitation n'a pas été certifié par un fabricant reconnu par Google et d'ont l'installation du Playstore n'a pas été reconnu par Google. C'est aujourd'hui le niveau que microG permet d'atteindre en simulant les services Google sur le téléphone et c'est aussi le niveau que doivent atteindre les téléphones chinois qui n'ont plus le droit d'installer les services de Google. C'est le niveau maximum demandé par la plupart des application bancaires d'après les retours utilisateurs.
3. MEETS_DEVICE_INTEGRITY ce qui veut dire que le téléphone dispose des services play officiel de Google ou en tout cas que ceux si sont suffisament bien simulé pour que GPI le detecte comme tel.
4. MEETS_STRONG_INTEGRITY ce qui veut dire que en plus d'^etre apprové par Google, il n'y a pas eu de modification du chargeur de démarrage et celui ci est bien sécurisé par des sécurisations approuvées par Google.

Il existe un dernier niveau, le MEETs_VIRTUAL_INTEGRITY mais celui ci est pour les machines virtuelles avec le Playstore installé.

> Avant que Google Play Integrity soit implémenté, [SafetyNet Attestation](https://developer.android.com/privacy-and-security/safetynet/deprecation-timeline?hl=fr) était utilisé et l'est encore par de nombreuses applications mais l'API n'est plus fonctionnelle depuis Janvier 2025 (ce qui colle aussi à quelques mois avec la période de début de problème de compatibilité des applications du playstore. Entre temps microG c'est adapté et permet d'obtenir le premier niveau tout en ce protégeant de Google.
{.is-info}

> Sur la même thématique il existe aussi une application qui permet de tester les méthodes de détection de possible root du téléphone utilisé par les app propriétaires pour justifier un non fonctionnement sur l'appareil, l'application s'appelle [Rootbeer](https://github.com/scottyab/rootbeer), elle était auparavant disponible sur AppLounge et AuroraStore cependant elle ne l'est plus et est uniquement accessible en compilant les sources.
{.is-info}

# Les solutions libres pour faire fonctionner les applications open sources sur les roms avec microG

Comme vous avez pus le comprendre en lisant les chapitres précédents, [microG](https://microg.org/) est une grosse partie de la solution qui permet de contourner les protections mises en place par les applications bancaires à question de le configurer correctement. Une autre solution, qui demande cependant d'avoir rooté le téléphone et masqué le root avec un module XPosed c'est [FakeGApps](https://github.com/whew-inc/FakeGApps/) cependant du fait de la relative complexité qu'il faut, je vous conseille de partir sur un système déjà préconfiguré et qui à déjà un système intégré pour falsifier la signature des Google App et qui a déjà microG d'intégré. La liste non exhaustive de ces ROMs est la suivante :
- [/e/OS](https://doc.e.foundation/devices) qui est Français,
- [CalyxOS](https://calyxos.org/install/) qui est des USA,
- [LineageOS for microG](https://lineage.microg.org/),
- [iodé](https://iode.tech/fr/appareils-pris-en-charge-officiellement-par-iodeos/) qui est Francais,

## Bien configurer microG pour maximiser le nombre d'application bancaire pouvant fonctionner
