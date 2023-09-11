---
title: Configurer Librewolf
description: 
published: true
date: 2023-07-02T16:30:35.785Z
tags: librewolf
editor: markdown
dateCreated: 2023-06-30T18:59:51.103Z
---

# Installation

Pour installer le navigateur, la procédure est "ultra" simple :
- Allez sur votre logithèque et installez Librewolf.

> Nous recommandons l'installation via Flatpak pour la majorité des personnes souhaitant utiliser le navigateur.
> Attention toutefois : avec certaines extensions, il conviendra de configurer votre distribution si vous rencontrez quelques problèmes (**extension de [KeePassXC](/tutoriels/keepass) par exemple**).
{.is-success}

## En cas de problème

Il est possible que nous rencontrions des difficultés à rechercher Librewolf sur la logithèque. En effet, Flatpak ne sera parfois pas installé ou sera mal configuré de base.

Nous pouvons traiter ce cas de figure comme suit :
1. Ouvrez votre terminal, puis tentez d'exécuter cette commande : `flatpak list`.

- Si votre terminal vous renvoie une liste d'applications, Flatpak est donc installé !

_Exemple_ de renvoi lorsque Flatpak est installé :
```brainfuck
Name                           Application ID                                 Version             Branch               Installation
LibreWolf                      io.gitlab.librewolf-community                  114.0.2-1           stable               system
Freedesktop Platform           org.freedesktop.Platform                       22.08.12.1          22.08                system
Mesa                           org.freedesktop.Platform.GL.default            23.1.1              22.08                system
Mesa (Extra)                   org.freedesktop.Platform.GL.default            23.1.1              22.08-extra          system
ffmpeg-full                    org.freedesktop.Platform.ffmpeg-full                               22.08                system
openh264                       org.freedesktop.Platform.openh264              2.1.0               2.2.0                system
Yaru Gtk Theme                 org.gtk.Gtk3theme.Yaru                                             3.22                 system
```

> Vous pouvez donc passer directement à l'étape 2.
{.is-info}

- Si votre terminal vous renvoie :
```brainfuck
bash: flatpak : commande introuvable
# Ou en anglais :
bash: flatpak : unknown command
```

Cela signifie que Flatpak n'est pas installé. 

> Procédez donc à son installation, suivant votre distribution : 
> 
> **Vous retrouverez toutes les procédures détaillées [ici](https://flatpak.org/setup/)**.
{.is-info}

2. Une fois Flatpak installé, indiquez-lui vers quel dépôt pointer (si ce n'est pas déjà fait) :

```bash
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

3. Redémarrez votre machine, puis rendez vous dans votre logithèque pour vérifier que Librewolf est disponible.


> Dans certains cas, il peut être nécessaire d'installer le navigateur via cette commande `flatpak install flathub io.gitlab.librewolf-community`.
{.is-warning}

# Configuration

Le navigateur est maintenant installé : nous allons le configurer convenablement afin d'en tirer le meilleur parti. Rendez vous dans les paramètres du navigateur :

![Librewolf-param-1](/images/librewolf-param-1.png){.align-center}
![Librewolf-param-2](/images/librewolf-param-2.png){.align-center}

Nous allons passer en revue les parties de "Paramètres" les plus importantes.

## Vie privée et sécurité

### Pistage

Le premier paramètre "Protection renforcée contre le pistage" propose d'activer le signal "Do Not Track" dans les requêtes que vous transmettez aux sites internet visités. Cela dit, nous ne recommandons pas d'activer cette option ; en effet, cette option est bien, mais rien ne force les sites internet de la respecter, il s'agit uniquement d'une "demande" de votre part ! Nous estimons donc que ce signal n'est pas utile.

- Laissez la configuration par défaut.

![](/images/librewolf-param-3.png){.align-center}

### Cookies

Par défaut, Librewolf supprime tous les cookies lorsque vous fermez le navigateur, ce qui est une bonne chose :

![](/images/librewolf-param-4.png){.align-center}

> Il est à noter qu'à la fermeture du navigateur, toutes vos connexions à des sites internet seront fermées. Il sera donc nécessaire de vous connecter de nouveau lorsque vous souhaiterez y accéder.
{.is-success}

### HTTPs

Il est tout à fait possible, voire recommandé, de forcer l'utilisation du HTTPs lors de toutes nos visites de site internet. Pour ce faire :
- Direction la partie "Mode HTTPS uniquement",
- Activez la première option, comme suit :

![](/images/librewolf-param-5.png){.align-center}

## Recherche

Rentrons dans les Paramètres afin de configurer un moteur de recherche par défaut. Procédez comme suit :

![Librewolf-search-1](/images/librewolf-search-1.png){.align-center}

> Nous vous invitons à choisir votre moteur [ici](/debutant/moteurs-recherche).
{.is-info}

La liste pré-définie par Librewolf comporte déjà certains navigateurs que nous recommandons. Cependant, il est possible que vous choisissiez autre chose. Dans ce cas, ajoutez un autre navigateur sur Librewolf est quelque peu particulier. Voici la procédure à suivre :

- Allez sur l'URL du moteur de recherche que vous souhaitez ajouter ;
- Faites une recherche quelconque, peu importe ;
- Puis cliquez avec le bouton droit sur la barre d'URL du navigateur, vous obtenez le menu suivant :

![Librewolf-search-2](/images/librewolf-search-2_1.png){.align-center}

- Cliquez sur "Ajouter « *MOTEUR_ACTUEL* »", avec "MOTEUR_ACTUEL" le moteur de recherche sur lequel vous êtes. Retournez dans les "Paramètres" :arrow_right: "Recherche" :

![Librewolf-search-2](/images/librewolf-search-2_2.png){.align-center}


## Librewolf - Configuration avancée

La dernière partie des Paramètres vous permet de finement configurer les aspects "vie privée" et "sécurité" du navigateur.

> Par défaut, Librewolf est déjà pré-configuré. Cette configuration est déjà une bonne base pour la majorité des profils : elle permet de neutraliser une bonne partie des pisteurs, d'améliorer son empreinte sur internet, et de renforcer quelque peu la sécurité.
{.is-success}

## Extensions

Le navigateur vient par défaut avec uBlock Origin, pré-configuré. Il est néanmoins possible d'adjoindre des extensions à Librewolf.

- L'accès aux extensions se fait simplement via la page de ["add-ons" Firefox](https://addons.mozilla.org/fr/firefox/).

La procédure pour ajouter une extension est très simple :
1. Faites simplement une recherche de votre extension (ici pour l'exemple, "LocalCDN"):

![](/images/librewolf-ext-1.png){.align-center}

2. Cliquez sur "Ajouter à Firefox" :

![](/images/librewolf-ext-2.png){.align-center}

3. Cliquez en haut à droite sur "Continuer l'installation" afin d'autoriser le téléchargement de l'extension :

![](/images/librewolf-ext-3.png){.align-center}

4. Cliquez ensuite sur "Ajouter" afin de l'ajouter au navigateur :

![](/images/librewolf-ext-4.png){.align-center}

5. Puis "OK" pour terminer l'installation :

![](/images/librewolf-ext-5.png){.align-center}

- L'extension se retrouve ici :

![Librewolf-ext-6](/images/librewolf-ext-6.png){.align-center}

## Facultatif

Si vous souhaitez pointer depuis votre navigateur sur un [serveur DNS](/debutant/dns) tiers, voici comment le configurer sous Librewolf :

![lib-dns-1](/images/lib-dns-1.png){.align-center}
![lib-dns-2](/images/lib-dns-2.png){.align-center}

- Descendez dans cette partie jusqu'à obtenir la section "DNS via HTTPS"

![lib-dns-3](/images/lib-dns-3.png){.align-center}
![lib-dns-4](/images/lib-dns-4.png){.align-center}

- Testons notre configuration pour vérifier que nous pointons bien vers le DNS de la FDN, cf. cette [partie](#auto-audit) :
 
![lib-dns-5](/images/lib-dns-5.png){.align-center}


> Voilà, vous êtes fin prêt pour naviguer sereinement.

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo*