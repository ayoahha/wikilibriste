---
title: Utiliser KeepassXC
description: Tutoriel expliquant l'utilisation de KeepassXC sur ordinateur
published: true
date: 2024-08-06T04:04:44.152Z
tags: debutant, débutant, mot de passe, keepass
editor: markdown
dateCreated: 2022-12-02T17:39:35.340Z
---

Bienvenue sur ce tutoriel, qui vous présente comment utiliser **KeePassXC** sur ordinateur fixe et mobile.

Dans ce tutoriel, nous verrons :
1. Comment créer une base de données chiffrée
2. Comment ouvrir cette base
3. Comment ajouter une nouvelle entrée (un nouveau compte)
4. Comment bien paramétrer votre application
5. Comment avoir accès à plusieurs endroits à votre base
6. Comment paramétrer l'application pour une prise en charge des extensions navigateurs

> _Note importante concernant l'usage KeePassXC / Ungoogled Chromium_ : ce navigateur permettant d'assurer une sécurité élevée, il n'est pas évident d'installer des extensions car la fonction est désactivée **par défaut**. De même il faudra configurer correctement l'extension sur votre distribution pour qu'elle reconnaisse l'application KeePassXC, notamment si vous utilisez les versions Flatpak. 
> **En somme, si vous pouvez éviter UC avec KeePassXC, faites-le ;)**
> Pour ceux qui sont à l'aise avec l'outil informatique, vous pourrez tenter l'aventure !
{.is-warning}

# Créer une base

Ouvrez l'application :

![keepass-1.png](/images/keepass-1.png){.align-center}

![keepass-2.png](/images/keepass-2.png){.align-center}

![keepass-3-1.png](/images/keepass-3-1.png){.align-center}

![keepass-3-2.png](/images/keepass-3-2.png){.align-center}

> Pour les algorithmes, veuillez relire l'article sur les [gestionnaires de mots de passe](/debutant/gestionnaire-mots-passe#algorithme).
{.is-info}

![keepass-4-1.png](/images/keepass-4-1.png){.align-center}

![keepass-4-2.png](/images/keepass-4-2.png){.align-center}

![keepass-5.png](/images/keepass-5.png){.align-center}

![keepass-6.png](/images/keepass-6.png){.align-center}

> Voilà, bravo, votre base est créée. 
{.is-success}


- A gauche se trouve une arborescence, car vous pouvez créer des dossiers
- Au milieu haut, vous retrouverez la liste des entrées (données de comptes) créées
- Au milieu bas, vous trouverez les informations de ces entrées, avec les mots de passe obfusqués !

# Ouvrir votre base

Ouvrez l'application :

![keepass-opendb-1.png](/images/keepass-opendb-1.png){.align-center}

> Sélectionnez le répertoire et le fichier de la base préalablement enregistré lors de la création
{.is-info}


![keepass-opendb-2.png](/images/keepass-opendb-2.png){.align-center}

1. Entre votre mot de passe
2. Déverouillez la base

# Ajouter une entrée

Ouvrez l'application et votre base :

![keepass-6-add-1.png](/images/keepass-6-add-1.png){.align-center}

![keepass-6-add-2.png](/images/keepass-6-add-2.png){.align-center}

![keepass-6-add-3-1.png](/images/keepass-6-add-3-1.png){.align-center}

![keepass-6-add-3-2.png](/images/keepass-6-add-3-2.png){.align-center}

![keepass-6-add-3-3.png](/images/keepass-6-add-3-3.png){.align-center}

![keepass-6-add-4.png](/images/keepass-6-add-4.png){.align-center}

![keepass-6-add-5.png](/images/keepass-6-add-5.png){.align-center}

![keepass-6-add-5-1.png](/images/keepass-6-add-5-1.png){.align-center}

![keepass-7.png](/images/keepass-7.png){.align-center}

![keepass-8.png](/images/keepass-8.png){.align-center}

![keepass-9.png](/images/keepass-9.png){.align-center}

# Paramétrages de KeepassXC

Ouvrez l'application et votre base :

![keepass-params-1.png](/images/keepass-params-1.png){.align-center}

> Le presse-papier correspond à la partie de la mémoire qui vous sert à faire des copiers-collés. Si vous utilisez cette fonction pour copier les mots de passe, il est important de nettoyer cette partie de mémoire rapidement afin de ne laisser aucune trace de mot de passe. **Nous positionnons la suppression à 1 min, avec un maximum recommandé de 5 min.**
{.is-warning}

> Egalement, il est important de revérouiller la base après une période d'inactivité sur l'application. Cela évite que lorsque vous quittez votre machine longtemps l'on puisse jeter un coup d'oeil à vos mots de passe. **Nous recommandons : si votre machine est dans un endroit où d'autres personnes sont présentes (travail ? café ?) positionnez le revérouillage à 2 min. Si votre machine est à la maison vous pouvez positionner à 10 min.**
{.is-warning}

> Enfin, activez les options dans le bloc 3.
{.is-warning}

> Il est tout à fait possible si vous téléchargez des miniatures d'internet de plutôt passer par l'index Duckduckgo. C'est optionnel, et nous ne recommandons pas forcément de télécharger des miniatures, cela implique des requêtes sur internet, que vous devriez éviter avec ce genre d'outils.
{.is-info}


# Synchronisation de votre base

Avant d'entrer dans le vif du sujet, il est très important de bien considérer les aspects 'sécurité' autour de cette pratique.

## Les bonnes pratiques

Si vous avez plusieurs machines sur lesquelles vous souhaitez avoir accès à vos mots de passe, vous avez 2 possibilités afin d'accéder à votre base sur plusieurs machines :

1. Vous utilisez une clé USB, sur laquelle vous copiez votre base puis la transférer sur l'autre machine ; opération à répéter à chaque mise à jour de la base (sur une machine ou une autre). Veillez à bien supprimer la base de votre clé une fois l'opération effectuée !

Utiliser une clé USB (de confiance) permet d'éviter que le fichier se transfère sur un réseau, limitant donc son exposition et de facto diminuer la probabilité (même si déjà toute relative !) de compromission.

> Cette solution est en revanche assez contraignante, au quotidien, surtout si vous souhaitez avoir à disposition votre base sur plus de _2 ou 3 machines_...
{.is-info}


> Attention, garder son fichier base sur la clé USB est une fausse bonne idée : non seulement vous pouvez la perdre facilement, mais vous pouvez également perdre les données si la clé USB est corrompue (cela arrive parfois tout comme les cartes SD, ces périphériques ayant une durée de vie moindre que des disques durs mécaniques voire SSD du fait du type de mémoire utilisée).
{.is-warning}


2. Il existe une autre possibilité : synchroniser votre base de données. Certaines applications vous permettent de synchroniser des répertoires par le réseau, que ce soit entre ordinateur fixe/portable ou bien même entre ordinateur et téléphone.

Bien entendu, ici, cela implique certains compromis en terme de sécurité, car vous allez de ce fait augmenter la surface d'attaque sur votre fichier. Afin de garder une relative confiance, vous devrez respecter certaines recommandations :

- Vous allez devoir faire confiance à l'application que vous utiliserez afin de synchroniser le fichier 'base de données' : privilégiez toujours une **application de confiance _open source et/ou libre_**, bien notée par ses utilisateurs, potentiellement avec de bons retours d'experts.

- En termes de bonnes pratiques et d'hygiène cyber, vous devriez uniquement **autoriser la synchronisation sur votre _réseau local_**. Exit donc la synchronisation via 3G/4G/5G ou sur un WiFi autre que le vôtre ! La raison est simple : vous limitez le risque à un échange _purement local, chez vous_, sur votre réseau, et non sur internet, réseau publique.

- Souvenez-vous toujours de **limiter le nombre de sauvegardes** de ce fichier. Moins vous aurez de copies, moins le risque sera important qu'il se retrouve ailleurs ! Nous recommandons de **_limiter à 3_** le nombre de sauvegardes. Attention donc particulièrement si vous activez le *versioning* ou préservation des versions de fichiers.

- *Si possible*, vous devriez **protéger la synchronisation** : une protection par mot de passe pour chiffrer les échanges au minimum et/ou l'utilisation de signatures pour vérifier qu'émetteurs et destinataires sont bien ceux qu'ils prétendent être, etc. Cela reste facultatif (si vous faites pleinement confiance à votre réseau et vos machines !) car certaines applications ont du mal à fonctionner ainsi.


> Cela reste bien sûr des recommandations et vous êtes libres de les adopter ou non, sachant que la base de données elle-même est chiffrée.
{.is-info}


## Mise en place

Voyons maintenant dans la pratique ce que donne la solution 2 :

Dans notre exemple, nous utilisons [Syncthing](https://syncthing.net/), une application de synchronisation réseau très connue de la communauté et très simple d'usage. Egalement, nous utiliserons pour l'exemple un ordinateur et un téléphone, car c'est le cas d'utilisation qui reviendra le plus souvent.

> **Pour ce faire, rendez-vous sur ce [tutoriel](/tutoriels/syncthing) spécifique.**
{.is-success}

*Note : vous pouvez très bien utiliser votre propre application de synchronisation, il n'y aura aucun problème !*

# Intégration aux navigateurs

Il est souvent fastidieux de copier le mot de passe et le coller dans les champs respectifs à chaque fois que l'on désire aller sur un compte en ligne. Il est possible de faire appel à une extension sur votre navigateur qui sera capable de vous pré-remplir les champs lorsque vous tombez sur une page d'identification.

L'extension se nomme 'KeepassXC-Browser extension' et est disponible sur la plupart des navigateurs :
- [Google Chromium, Vivaldi et Brave](https://chrome.google.com/webstore/detail/keepassxc-browser/oboonakemofpalcgghocfoadofidjkkk)
- [Mozilla Firefox et alternatives](https://addons.mozilla.org/en-US/firefox/addon/keepassxc-browser)

> **Dans cet exemple, nous utiliserons Mozilla Firefox sans autre paramétrage**.
> 
> Nous traitons dans la partie [Synchronisation non établie](#synchronisation-non-%C3%A9tablie) les éventuels problèmes de connexion rencontrés avec Ungoogled Chromium et Librewolf.
{.is-info}

Tout d'abord, il va nous falloir configurer KeepassXC. Afin de configurer l'accès à l'extension vers votre base, ouvrez KeePassXC et paramétrez comme suit :
- Allez dans les paramètres, puis "Intégration aux navigateurs",
- Choisissez quel navigateur ira interroger votre base.

![keepass-params.png](/images/keepass-params.png){.align-center}

Ensuite, installez l'extension sur votre navigateur :

![keepass-extension-1.png](/images/keepass-extension-1.png){.align-center}

Ouvrez votre base sur KeePassXC (si ce n'est pas déjà fait !), l'extension vous demandera d'initier la connexion :

- *"KeePassXC-Browser n'est pas configuré. Appuyer sur le bouton Connecter pour se connecter à KeePassXC."*

![keepass-extension-2.png](/images/keepass-extension-2.png){.align-center}

En cliquant sur le bouton "**Se connecter**", une fenêtre s'ouvrira vous demandant de nommer cette connexion. Nous prendrons comme exemple "*connec-test*". Voici ensuite ce que vous devrez obtenir comme message :

- *"KeePassXC-Browser est connecté à KeePassXC et a été configuré avec l’identifiant suivant : connec-test"*

Voilà, vous pouvez maintenant naviguer sur vos sites, _**si vous avez entré les URLs**_, l'extension vous proposera de remplir automatiquement les champs en cliquant sur l'icône KeepassXC.

![keepass-extension-3.png](/images/keepass-extension-3.png){.align-center}

![keepass-extension-4.png](/images/keepass-extension-4.png){.align-center}

## Synchronisation non établie

Il est parfois plus complexe sur certains navigateurs de mettre en place la synchronisation. Cela dépend de certains facteurs :
- Comme le type d'installation de l'application : via Dépôt de la distro, ou via Flatpak ou Snap ou AppImage.
- Comme le navigateur : Firefox est différent de Librewolf par ex.

### Tabs {.tabset}
#### Le cas Ungoogled Chromium
Lorsque vous souhaiterez établir la connexion entre l'extension KeepassXC installée dans UG et l'application KeepassXC, le navigateur vous renverra une erreur du type "L'échange de clés a échoué" ou "Impossible de se connecter à Keepass [...]" !

![](/images/keepass-err-1.png) - ![](/images/keepass-err-2.png)

> Nous allons devoir paramétrer Flatpak afin d'autoriser la communication entre ces 2 applications.
{.is-info}

**Pré-requis** : 
- Nous conseillons _**très vivement**_ de passer par les applications Flatpak de UG et KeepassXC, ceci afin de faciliter la configuration.
- L'extension Keepassxc-browser est installée dans UG.
- Les 2 applications Flatpak sont à jour.

**Procédure pour UG** : Voici la procédure à suivre
1. Ouvrez votre Terminal.
2. Lancez cette commande (elle permet d'autoriser les 2 applications en bac à sable à discuter ensemble) :

```bash
flatpak override --user --filesystem={/var/lib,xdg-data}/flatpak/{app/org.keepassxc.KeePassXC,runtime/org.kde.Platform}:ro --filesystem=xdg-run/app/org.keepassxc.KeePassXC:create com.github.Eloston.UngoogledChromium
```

3. Lancez ensuite ces 2 commandes (telle quelle) :

```bash
cat << 'EOF' > ~/.var/app/com.github.Eloston.UngoogledChromium/config/chromium/Default/keepassxc-proxy-wrapper.sh
#!/bin/bash
APP_REF="org.keepassxc.KeePassXC/x86_64/stable"

for inst in "$HOME/.local/share/flatpak" "/var/lib/flatpak"; do
    if [ -d "$inst/app/$APP_REF" ]; then
        FLATPAK_INST="$inst"
        break
    fi
done
[ -z "$FLATPAK_INST" ] && exit 1

APP_PATH="$FLATPAK_INST/app/$APP_REF/active"

RUNTIME_REF=$(awk -F'=' '$1=="runtime" { print $2 }' < "$APP_PATH/metadata") RUNTIME_PATH="$FLATPAK_INST/runtime/$RUNTIME_REF/active"

exec flatpak-spawn --env=LD_LIBRARY_PATH=/app/lib --app-path="$APP_PATH/files" --usr-path="$RUNTIME_PATH/files" -- keepassxc-proxy "$@"
EOF
```

Puis :

```bash
sudo chmod +x ~/.var/app/com.github.Eloston.UngoogledChromium/config/chromium/Default/keepassxc-proxy-wrapper.sh
```

4. Copiez ensuite le fichier JSON  `org.keepassxc.keepassxc_browser.json` via cette commande :

```bash
cp ~/.config/chromium/NativeMessagingHosts/ ~/.var/app/com.github.Eloston.UngoogledChromium/config/chromium/NativeMessagingHosts/
```

5. Rendez vous dans le répertoire `~/.var/app/com.github.Eloston.UngoogledChromium/config/chromium/NativeMessagingHosts/`

```bash
cd ~/.var/app/com.github.Eloston.UngoogledChromium/config/chromium/NativeMessagingHosts/
```

- Nous allons éditer le fichier JSON `org.keepassxc.keepassxc_browser.json` qui se trouve à l'intérieur, pour pointer vers le proxy. L'original devrait être comme suit  :

```brainfuck
{
    "allowed_origins": [
        "chrome-extension://pdffhmdngciaglkoonimfcmckehcpafo/",
        "chrome-extension://oboonakemofpalcgghocfoadofidjkkk/"
    ],
    "description": "KeePassXC integration with native messaging support",
    "name": "org.keepassxc.keepassxc_browser",
    "path": "/var/lib/flatpak/exports/bin/org.keepassxc.KeePassXC",
    "type": "stdio"
}
```

Nous allons le modifier comme ceci (modification de la ligne 8) :

```brainfuck
{
    "allowed_origins": [
        "chrome-extension://pdffhmdngciaglkoonimfcmckehcpafo/",
        "chrome-extension://oboonakemofpalcgghocfoadofidjkkk/"
    ],
    "description": "KeePassXC integration with native messaging support",
    "name": "org.keepassxc.keepassxc_browser",
    "path": "/home/<VOTRE NOM D'UTILISATEUR>/.var/app/com.github.Eloston.UngoogledChromium/config/chromium/Default/keepassxc-proxy-wrapper.sh",
    "type": "stdio"
}
```

> **Attention 1** : <VOTRE NOM D'UTILISATEUR> doit être remplacé par votre nom d'utilisateur sur votre machine, bien entendu !
> 
> **Attention 2** : Il n'est pas possible d'utiliser le `~/` pour remplacer /home/<VOTRE NOM D'UTILISATEUR>/
{.is-danger}

- Pour ce faire, entrez cette commande (:warning: n'oubliez pas de remplacer <VOTRE NOM D'UTILISATEUR> dans la commande ci-après ! :warning:) :

```bash
sed -i 's!"/var/lib/flatpak/exports/bin/org.keepassxc.KeePassXC"!"/home/<VOTRE NOM D'UTILISATEUR>/.var/app/com.github.Eloston.UngoogledChromium/config/chromium/Default/keepassxc-proxy-wrapper.sh"!g' org.keepassxc.keepassxc_browser.json
```

Vous pouvez vérifier que la ligne 8 a bien été modifiée en exécutant `cat org.keepassxc.keepassxc_browser.json` qui devrait vous afficher le contenu du fichier.

6. Ouvrez ensuite KeepassXC et votre base, puis Ungoogled Chromium.
7. Tentez une nouvelle fois de connecter les 2 applications via l'extension et reprenez la configuration normalement à partir d'[ici](#int%C3%A9gration-aux-navigateurs).

> **Cela devrait fonctionner maintenant !**
{.is-success}

#### Le cas Librewolf
Le même problème que pour UG peut arriver ici encore.

![](/images/keepass-err-1.png) ![](/images/keepass-err-2.png)

Mais le cas Librewolf est encore plus compliqué à configurer.

> Nous allons devoir paramétrer encore plus finement Flatpak ainsi que notre distro afin d'autoriser la communication entre ces 2 applications.
> 
> **Tout le crédit de cette solution est à mettre sur cet utilisateur et [son blog](https://vhs2.org/librewolf-keepassxc-browser-integration) ainsi qu'au développeur ayant publié la solution de [proxy](https://github.com/varjolintu/keepassxc-proxy-rust)**. 
> Nous tentons juste d'apporter quelques corrections mineures et de rendre plus accessible cette solution...
{.is-info}

**Pré-requis** : 
- Ici encore, nous conseillons _**très vivement**_ de passer par les applications Flatpak de Librewolf et KeepassXC, ceci afin de faciliter la mise en oeuvre.
- L'extension Keepassxc-browser est installée dans Librewolf.
- Les 2 applications Flatpak sont à jour.

**Procédure pour Librewolf** : Voici la procédure à suivre
1. Ouvrez votre Terminal.
2. Lancez cette première commande :

```bash
mkdir -p ~/.librewolf/native-messaging-hosts && \
cp ~/.mozilla/native-messaging-hosts/org.keepassxc.keepassxc_browser.json ~/.librewolf/native-messaging-hosts
```

3. Lancez cette commande qui nous permet d'installer Rust sur la machine :

```bash
mkdir -p /tmp/kpxcp && cd /tmp/kpxcp && \
wget https://github.com/varjolintu/keepassxc-proxy-rust/archive/refs/heads/master.zip && unzip master.zip && \
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

**Lors de l'installation de Rust, vous devriez obtenir ce prompt :**

![](/images/keepass-librewolf-1.png){.align-center}

> Ecrivez uniquement le chiffre <kbd>1</kbd> puis <kbd>ENTREE</kbd>.
> 
> **Rust finit de s'installer**.
{.is-success}

3. Fermez le terminal, puis rouvrez-le pour mettre à jour l'environnement, et lancez ensuite cette commande :

```bash
cd /tmp/kpxcp && \
rustup target add x86_64-unknown-linux-musl && cd keepassxc-proxy-rust-master/ && \
RUSTFLAGS='-C link-args=-s' cargo build --release --target x86_64-unknown-linux-musl && \
cp target/x86_64-unknown-linux-musl/release/keepassxc-proxy ~/.librewolf/native-messaging-hosts/ && \
cp target/x86_64-unknown-linux-musl/release/keepassxc-proxy ~/.mozilla/native-messaging-hosts/
```

4.  Rendez vous dans le répertoire `~/.mozilla/native-messaging-hosts/`

```bash
cd ~/.mozilla/native-messaging-hosts
```

- Nous allons éditer le fichier JSON `org.keepassxc.keepassxc_browser.json` qui se trouve à l'intérieur, pour pointer vers le proxy. L'original devrait être comme suit  :

```brainfuck
{
    "allowed_extensions": [
        "keepassxc-browser@keepassxc.org"
    ],
    "description": "KeePassXC integration with native messaging support",
    "name": "org.keepassxc.keepassxc_browser",
    "path": "/var/lib/flatpak/exports/bin/org.keepassxc.KeePassXC",
    "type": "stdio"
}
```

Nous le modifions comme ceci (modification de la ligne 7) :

> **Attention 1** : <VOTRE NOM D'UTILISATEUR> doit être remplacé par votre nom d'utilisateur sur votre machine, bien entendu !
> 
> **Attention 2** : Il n'est pas possible d'utiliser le `~/` pour remplacer /home/<VOTRE NOM D'UTILISATEUR>/
{.is-danger}

```brainfuck
{
    "allowed_extensions": [
        "keepassxc-browser@keepassxc.org"
    ],
    "description": "KeePassXC integration with native messaging support",
    "name": "org.keepassxc.keepassxc_browser",
    "path": "/home/<VOTRE NOM D'UTILISATEUR>/.mozilla/native-messaging-hosts/keepassxc-proxy",
    "type": "stdio"
}
```

- Pour ce faire, entrez cette commande (:warning: n'oubliez pas de remplacer <VOTRE NOM D'UTILISATEUR> dans la commande ci-après ! :warning:) :

```bash
sed -i 's!"/var/lib/flatpak/exports/bin/org.keepassxc.KeePassXC"!"/home/<VOTRE NOM D'UTILISATEUR>/.mozilla/native-messaging-hosts/keepassxc-proxy"!g' org.keepassxc.keepassxc_browser.json
```

Vous pouvez vérifier que la ligne 7 a bien été modifiée en exécutant `cat org.keepassxc.keepassxc_browser.json` qui devrait vous afficher le contenu du fichier.

5.  Rendez vous ensuite dans le répertoire `~/.librewolf/native-messaging-hosts/`

```bash
cd ~/.librewolf/native-messaging-hosts
```

- Nous allons éditer le fichier JSON `org.keepassxc.keepassxc_browser.json` qui se trouve à l'intérieur, pour pointer vers le proxy. L'original devrait être comme suit  :

```brainfuck
{
    "allowed_extensions": [
        "keepassxc-browser@keepassxc.org"
    ],
    "description": "KeePassXC integration with native messaging support",
    "name": "org.keepassxc.keepassxc_browser",
    "path": "/var/lib/flatpak/exports/bin/org.keepassxc.KeePassXC",
    "type": "stdio"
}
```

Nous le modifions comme ceci (modification de la ligne 7) :

> **Attention 1** : <VOTRE NOM D'UTILISATEUR> doit être remplacé par votre nom d'utilisateur sur votre machine, bien entendu !
> 
> **Attention 2** : Il n'est pas possible d'utiliser le `~/` pour remplacer /home/<VOTRE NOM D'UTILISATEUR>/
{.is-danger}


```brainfuck
{
    "allowed_extensions": [
        "keepassxc-browser@keepassxc.org"
    ],
    "description": "KeePassXC integration with native messaging support",
    "name": "org.keepassxc.keepassxc_browser",
    "path": "/home/<VOTRE NOM D'UTILISATEUR>/.librewolf/native-messaging-hosts/keepassxc-proxy",
    "type": "stdio"
}
```

- Pour ce faire, entrez cette commande (:warning: n'oubliez pas de remplacer <VOTRE NOM D'UTILISATEUR> dans la commande ci-après ! :warning:) :

```bash
sed -i 's!"/var/lib/flatpak/exports/bin/org.keepassxc.KeePassXC"!"/home/<VOTRE NOM D'UTILISATEUR>/.librewolf/native-messaging-hosts/keepassxc-proxy"!g' org.keepassxc.keepassxc_browser.json
```

Vous pouvez vérifier que la ligne 7 a bien été modifiée en exécutant `cat org.keepassxc.keepassxc_browser.json` qui devrait vous afficher le contenu du fichier.

6. Installez ensuite (si ce n'est pas déjà fait !) l'application Flatseal :

```bash
flatpak install flathub com.github.tchx84.Flatseal
```

> Validez par <kbd>Y</kbd> puis <kbd>ENTREE</kbd>.
> 
> Cette application va nous permettre de finement configurer les accès système des 2 applications Flatpak.
{.is-info}

7. Ouvrez Flatseal, puis sélectionnez KeepassXC. Descendez ensuite sur la partie "Filesystem" et ajoutez ces 2 accès, comme suit :

![](/images/keepass-librewolf-2-1.png =600x) :arrow_right: ![](/images/keepass-librewolf-2-2.png =600x)

- `~/.mozilla/native-messaging-hosts:ro`
- `~/.librewolf/native-messaging-hosts:ro`

8. Sélectionnez ensuite Librewolf, descendez sur la partie "Filesystem" et ajoutez ces 3 accès, comme suit :

![](/images/keepass-librewolf-3-1.png =600x) :arrow_right: ![](/images/keepass-librewolf-3-2.png =600x)

- `~/.mozilla/native-messaging-hosts:ro`
- `~/.librewolf/native-messaging-hosts:ro`
- `xdg-run/app/org.keepassxc.KeePassXC:ro`

9. Fermez Flatseal
10. Ouvrez l'application KeepassXC, pour configurer correctement l'intégration aux navigateurs :

> Deux messages d'avertissement (cf. ci-après) sont susceptibles d'apparaître lorsque vous lancez KeepassXC. Ignorez-les simplement en cliquant sur OK.
> 
> ![](/images/keepass-librewolf-alert.png)
{.is-warning}

- Tout d'abord dans les "Paramètres", "Général", cochez "Lancez automatiquement KeepassXC au démarrage du système", comme suit :

![](/images/keepass-librewolf-4.png =800x){.align-center}

- Dans "Intégration aux navigateurs", vous devriez obtenir cette configuration pour l'onglet "Général" :

![](/images/keepass-librewolf-5.png =800x){.align-center}

- Dans l'onglet "Avancé", vous devrez cocher "Utiliser un emplacement de navigateur personnalisé :" puis sélectionner Firefox et entrer `~/.librewolf/native-messaging-hosts` dans le champ, comme suit :

![](/images/keepass-librewolf-6.png =800x){.align-center}

> Plusieurs messages d'avertissement peuvent apparaître lorsque vous validez la configuration. Ignorez-	les simplement en cliquant sur OK.
{.is-warning}

11. Retournez sur votre terminal, et entrez cette commande :

```bash
sudo flatpak override --filesystem=xdg-run/kpxc_server:ro io.gitlab.librewolf-community
```

12. Puis entrez ceci :

```bash
mkdir -p ~/.local/share/user-tmpfiles.d && \
echo "
# This file creates a symbolic link for the KeePassXC UNIX socket.
# This makes it possible to access the UNIX socket under it s usual path
# in \$XDG_RUNTIME_DIR by creating a symbolic link pointing inside the
# flatpak-specific dir.
# see https://is.gd/flatpakFirefoxKPXC

# %t = \$XDG_RUNTIME_DIR (if run as user), see \"man tmpfiles.d\"

# type	path		mode	UID 	GID 	Age		Argument
L %t/kpxc_server - - - - %t/app/org.keepassxc.KeePassXC/org.keepassxc.KeePassXC.BrowserServer
" > ~/.local/share/user-tmpfiles.d/kpxc_server.conf
```

13. Redémarrer votre machine.
14. Après le redémarrage, ouvrez tout d'abord KeepassXC.

> Idem ici et **à chaque fois que vous ouvrirez KeepassXC**, les 2 messages d'avertissement (cf. ci-après) apparaîtront. Ignorez-les en cliquant sur OK.
> 
> ![](/images/keepass-librewolf-alert.png)
{.is-warning}

15. Ouvrez votre base.
16. Puis ouvrez ensuite Librewolf.
17. Tentez une nouvelle fois de connecter les 2 applications via l'extension et reprenez la configuration normalement à partir d'[ici](#int%C3%A9gration-aux-navigateurs). 

> **Cela devrait fonctionner maintenant !**
{.is-success}

> **N'oubliez pas, à chaque utilisation** :
> **-- Lancez KeepassXC en premier**,
> **-- Ignorez les 2 messages d'alerte**.
{.is-warning}

## Technique
Pour ceux qui souhaiteraient savoir comment fonctionne cette extension avec l'application KeePass, pour pouvoir peut-être comprendre le fonctionnement intrinsèque, voici en substance ce qui est mis en place pour l'échange des données entre navigateur et KeePassXC :
1. Les communications entre l'extension (dans le navigateur) et l'application s'effectuent via un Proxy _keepassxc-proxy_, disponible et implémenté par l'application KeePassXC. 
2. Les échanges de login et mot de passe se font grâce à _keepassxc-protocol_ qui utilise la cryptographie asymétrique :
    - Chaque partie génère des paires de clés temporaires (re-générées à chaque session) pour chiffrer et signer les échanges.
    - L'identification entre l'extension et l'application se fait grâce à une paire de clés permanente dès lors que vous avez nommé un identifiant de connexion. Cette paire est stockée protégée dans le navigateur.

**Cette solution est plutôt robuste et rend la communication assez sécurisée, surtout pour le mot de passe**. De plus, cela évite d'utiliser le presse-papier sans chiffrer le mot de passe lors d'un classique copier-coller...

Pour plus de détails, vous pouvez consulter la page dédiée sur [le dépôt de l'extension](https://github.com/keepassxreboot/keepassxc-browser/blob/develop/keepassxc-protocol.md).


---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo*