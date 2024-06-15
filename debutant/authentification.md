---
title: Utiliser le 2FA pour l'authentification
description: Découvrez quelques applications d'authentification double-facteurs
published: true
date: 2024-06-15T17:10:45.127Z
tags: 2fa, double authentification, multi-facteurs, google authenticator, lastpass authenticator, authy, otp, aegis, keysmith
editor: markdown
dateCreated: 2024-05-15T13:09:24.980Z
---

:arrow_right: Vous souhaitez utiliser des jetons de connexion (cf. [TOTP](https://wikilibriste.fr/fr/glossaire#totp), et [ici](https://wikilibriste.fr/hygiene-numerique#acc%C3%A8s-aux-informations-ou-authentification) et [ici](https://wikilibriste.fr/hygiene-numerique#authentification)) à vos logiciels et souhaiteriez trouver des alternatives open-source, voire libres ?

Alors, vous êtes au bon endroit ! :)

# Les outils 2FA à proscrire

Pour générer des jetons pour vos connexions avec authentification à deux facteurs (2FA), nous vous recommandons d’éviter ces 4 applications, car elles ne sont pas open-source et vos données sont conservées dans leurs clouds, qui peuvent à tout moment subir une fuite de bases de données.
- 🛑 Google Authenticator
- 🛑 Microsoft Authenticator
- 🛑 Lastpass Authenticator
- 🛑 Authy
- 🛑 ... D’une façon générale, toute application à sources fermées
{.grid-list}

# Les outils 2FA "libres"

En utilisant un des outils suivants, vos identifiants sont conservés localement et vous pouvez exporter/importer votre liste de jetons pour en faire des sauvegardes sur lesquelles vous gardez le contrôle.

## Sur PC Linux 🐧

- [Keysmith (KDE app) *Keysmith génère des jetons pour vos connexions avec authentification à deux facteurs (2FA)* ](https://apps.kde.org/fr/keysmith/)
{.links-list}

### Sur PC avec extensions navigateurs

- [Authenticator *Génère des codes de vérification en deux étapes dans votre navigateur. Pour bases Firefox et Chrome* ](https://authenticator.cc)
- [Bitwarden OTP *Authentificateur Bitwarden TOTP* ](https://bitwarden.com/fr-fr/help/integrated-authenticator/)
{.links-list}

## Sur Android <span class="mdi mdi-android"></span>

- [Aegis Authenticator *Aegis Authenticator est une application gratuite, sécurisée et open-source pour Android qui permet de gérer vos jetons de vérification en 2 étapes pour vos services en ligne* ](https://getaegis.app)
- [Authenticator Pro *est une application d’authentification à deux facteurs gratuite et open-source pour Android. Elle propose des sauvegardes chiffrées, des icônes, des catégories, un haut niveau de personnalisation et même une application Wear OS* ](https://authenticatorpro.jmh.me)
{.links-list}

## Sur iOS 📱

- [Tofu *Une application d’authentification à deux facteurs, facile à utiliser et open-source, conçue spécifiquement pour iOS* ](https://tofuauth.com)
{.links-list}

> Noter que la majorité des gestionnaires de mot de passe sont également capables de générer des jetons, au même titre que Bitwarden, Cf. [article sur ces outils](/debutant/gestionnaire-mots-passe).
{.is-info}

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): John*
<br>