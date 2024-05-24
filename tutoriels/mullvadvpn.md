---
title: Créer un compte Mullvad VPN anonyme
description: Tutoriel pour créer un compte Mullvad VPN anonyme et confidentiel
published: false
date: 2024-05-24T13:40:42.960Z
tags: confidentialité, anonymat, vpn, tor, tutoriel, mullvad vpn, coordonnées
editor: markdown
dateCreated: 2024-05-14T10:59:33.252Z
---

Ce tutoriel présente la démarche pour ouvrir un compte Mullvad VPN sans laisser de trace, ni laisser ses coordonnées personnelles, de manière anonyme et confidentielle. Ceci dans le but de ne pas associer votre identité à votre navigation internet.

> Pré-requis : avoir un peu de Bitcoin et connaitre la différence entre Bitcoin on-chain et Bitcoin Lightning.
{.is-success}

Voici les différences entre les transactions Bitcoin sur la chaîne et les transactions Bitcoin Lightning :

1. **Bitcoin on-chain** fait référence aux transactions enregistrées et validées directement sur la blockchain Bitcoin, ce qui garantit la sécurité mais peut prendre plus de temps avec des frais réseau plus cher.
2. **Lightning Network** est un protocole de paiement de couche 2 construit au-dessus de la blockchain Bitcoin, permettant des transactions plus rapides et moins chères en traitant les transactions hors chaîne.
3. Les transactions **on-chain** offrent une sécurité et une finalité accrues car elles sont vérifiées par le réseau Bitcoin distribué, tandis que les transactions **Lightning** reposent sur des canaux de paiement sécurisés mais centralisés.
4. Les transactions **Lightning** conviennent aux micropaiements et aux transactions fréquentes, tandis que les transactions **on-chain** conviennent mieux aux paiements importants ou aux transactions où la sécurité est primordiale ou dans le but d'un investissement long terme.

# Procédure

Ouvrir le navigateur TOR
Entrer l'adresse officielle de Mullvad en .onion :
> http://o54hon2e2vj6c7m3aqqu6uyece65by3vgoxxhlqlsvkmacw6a7m7kiad.onion/fr

> Une URL en .onion correspond à un site hébergé sur le réseau TOR, non surveillable et non censurable, il n'est pas accessible sur le réseau internet normal.
{.is-info}

**1. Créer un compte**
Cliquer sur le bouton "Commencer" en haut à droite ou bien sur "Créer un compte" au milieu de la page.

**2. Générer un numéro de compte**
Ecrire/Copier votre numéro de compte en lieu sûr. Ne partager **JAMAIS** votre identifiant Mullvad VPN en ligne avec d'autres personnes.

**3. Ajouter du crédit à votre compte**
Le site officiel de Mullvad propose le paiement par Monero, Bitcoin et Bitcoin cash. Le paiement par Bitcoin utilise le réseau on-chain, ceci prend du temps et des frais. Une autre solution est de payer par Bitcoin sur le réseau Lightning, rapidement et sans frais. Voici donc la procédure :

**Recharger le VPN Mullvad avec Lightning via le navigateur TOR**

Se rendre sur le site en .onion pour charger votre compte :

> http://soveng42aj6ynynkqeyut2dwnmwou45epfpuwvjy2t45fpxn3dk2ymad.onion/
> De préférence, utiliser le site en .onion, mais au cas où : site web en clair https://vpn.sovereign.engineering/

- Entrer votre numéro de compte et cliquer sur "Login",
- Sélectionner le temps d'utilisation à ajouter à votre compte : 6 ou 12 mois,
- Cliquer sur "Top-up with Lightning".

La facture est générée avec le QR code. Il vous reste à payer avec un portefeuille compatible BTC Lightning.

**4. Installer et utiliser Mullvad VPN**

- Télécharger Mullvad VPN depuis la page de téléchargement :
http://o54hon2e2vj6c7m3aqqu6uyece65by3vgoxxhlqlsvkmacw6a7m7kiad.onion/fr/download/
- L'installer et indiquer votre numéro de compte,
- Vous pouvez surfer de manière anonyme :) .


# Vidéo exemple

Voici pour illustrer une vidéo de 30 secondes :

<iframe class="frame-style" title="Tutoriel pour créer un compte Mullvad VPN anonyme et confidentiel" src="https://peertube.fr/videos/embed/8a04cb41-1ace-4258-9f9b-5e66c0fe44db" frameborder="0" allowfullscreen="1" allow="fullscreen; accelerometer; encrypted-media; gyroscope; picture-in-picture" sandbox="allow-same-origin allow-scripts allow-popups"></iframe>


---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): John*
<br>