---
title: Partitionner son disque autrement
description: Cet article vous présente une façon de partitionner votre disque adapté à Linux
published: true
date: 2023-11-13T11:24:35.751Z
tags: partitionnement
editor: markdown
dateCreated: 2023-02-13T17:00:12.797Z
---

Installer une distribution GNU/Linux est très simple car le partitionnement de votre disque se fait par défaut de manière automatique.
Cela dit, ce partitionnement peut être optimisé, de plusieurs manières (ce que ne propose pas Windows ;) !).

En effet, il est tout à fait possible de créer plusieurs partitions sur votre disque. Pour ce faire, le répertoire principal système, la racine, c'est à dire le répertoire `/`, pourra être scindé en plusieurs partitions logiques.

Voyons comment nous pouvons procéder sur la majorité des distributions GNU/Linux...

# Séparer son HOME

Premier élément que nous pouvons scinder de la partition système `/`, le répertoire `/home`. C'est la configuration la plus souvent rencontrée sur PC.

Séparer son "home" peut être utile pour plusieurs raisons :
- Dans le cadre d'une [sauvegarde/restauration](https://wikilibriste.fr/debutant/sauvegarde) ou en cas de réinstallation complète d'une distribution (peu importe la raison), dans ce cas, nous pourrons garder telle quelle cette partition `/home` et ne réinstaller que la partition racine `/` du système ; très pratique si l'on souhaite ne pas refaire certains fichiers de configuration.

> Lors de la réinstallation d'une distribution, si vous gardez la partition `/home`, faites attention à donner le même nom d'utilisateur et mot de passe que l'ancienne distribution. Ceci afin d'éviter des manipulations supplémentaires sur votre HOME (pour rappel : `/home/<nom utilisateur>`).
{.is-warning}

- Cela permet aussi d'éviter un **blocage système** dans le cas où notre répertoire `/home` serait plein. En effet, si une seule partition est présente, le système généralement renvoie toutes sortes d'erreurs qui amènent parfois à un blocage intégral du système. En séparant ces 2 partitions, nous pourrons mieux gérer cet aspect et éviter ce blocage.
- Lorsque nous avons plusieurs distributions installées et que nous souhaitons partager cette partition entre les 2 systèmes ; c'est un cas assez rare, mais cette séparation rend moins complexe ce cas d'usage.

En réalité, nous rencontrons très souvent des distributions avec une partition `/home` séparée, notamment sur des serveurs avec de multiples utilisateurs à gérer. Ainsi, nous pouvons gérer clairement la séparation entre ces utilisateurs et leurs données et les fichiers système, ce qui améliore considérablement la sécurité.


Vous pouvez également très bien mettre cette partition `/home` sur un second disque dur, c'est bien sûr tout à fait faisable.

---

Les onglets suivants présentent une séparation lors d'une nouvelle installation d'une distribution :

> Nous prenons pour exemple n°1, un disque dur de 100Go. Vous adapterez les dimensions à votre disque bien entendu.
Généralement, nous conseillons un rapport d'environ 1/3 pour la racine `/` - 2/3 pour votre `/home`, **avec dans tous les cas un _minimum_ de 30 à 40 Go** pour la partition système `/` :
> **Exemple 1 : pour un disque de 100Go ; `/` = 33Go, `/home` = 67Go**
>
>D'autres exemples :
> **Exemple 2 : pour un disque de 256Go ; `/` = 86Go, `/home` = 170Go**
> **Exemple 3 : pour un disque de 512Go ; `/` = 170Go, `/home` = 342Go**

> Dans la suite du tutoriel, nous ne comptons pas l'éventuelle partition SWAP que vous voudriez ajouter. Si vous souhaitez ajouter du SWAP, retranchez-les de la partition HOME !
> Voici sur le [site de ubuntu un abaque](https://help.ubuntu.com/community/SwapFaq#How_much_swap_do_I_need.3F) avec en première colonne la RAM totale installée et la taille swap recommandée (sans ou avec hibernation).
> *Notez qu'il est aussi possible, à la place d'une partition SWAP dédiée, d'[utiliser un fichier `/swapfile`](https://itsfoss.com/create-swap-file-linux/) à la racine de votre partition principale.*
{.is-info}

### Tabs {.tabset}
#### Installateur Ubiquity
Certaines distributions dérivées de Debian et Ubuntu utilisent l'installateur Ubiquity (c'est par exemple le cas d'Ubuntu) :
- Cliquez sur "Autre chose" puis "Suivant" :
![](/images/ubuntu-home-1.png =900x){.align-center}
- Vous obtenez cette fenêtre :
![](/images/ubuntu-home-2.png =900x){.align-center}
- Cliquez sur "Nouvelle table de partition..." puis "Continuer" :
![](/images/ubuntu-home-3.png =900x){.align-center}
![](/images/ubuntu-home-4.png =900x){.align-center}
- Cliquez sur "+", remplissez les champs comme les images suivantes, et cliquez "OK" à chaque étape pour valider chaque partiton :
![](/images/ubuntu-home-5.png =900x){.align-center}
![](/images/ubuntu-home-6.png =900x){.align-center}
![](/images/ubuntu-home-7.png =900x){.align-center}
![](/images/ubuntu-home-8.png =900x){.align-center}
- **Vous devriez obtenir cette répartition :**
![](/images/ubuntu-home-9.png =900x){.align-center}
- Cliquez sur "Continuer"
![](/images/ubuntu-home-10.png =900x){.align-center}

#### Installateur Anaconda
C'est l'installation par défaut de Fedora et ses dérivés :
- Cliquez sur "Personnalisation avancée (Blivet GUI)" :
![](/images/fedora-home-1.png){.align-center}
- Sélectionnez ""Espace disque..." puis cliquez sur le "+" :
![](/images/fedora-home-2.png){.align-center}
- Répétez cette opération en respectant les champs ci-dessous puis "Valider" à chaque étape :
![](/images/fedora-home-3.png){.align-center}
![](/images/fedora-home-4.png){.align-center}
![](/images/fedora-home-5.png){.align-center}
![](/images/fedora-home-6.png){.align-center}
![](/images/fedora-home-7.png){.align-center}
- **Vous devriez obtenir cette répartition**. Cliquez sur le bouton bleu "FAIT" en haut à gauche pour valider et passer à la suite :
![](/images/fedora-home-8.png){.align-center}

#### Installateur Calamares
Souvent utilisé sur des distributions basées sur Arch Linux (Manjaro par exemple, dont nous reprenons l'exemple ci-après) et certaines distributions Debian :
- Cliquez sur "Partitionnement manuel" :
![1](/images/manjaro-home-1.png =900x){.align-center}
- Vous obtenez cette fenêtre... Cliquez sur "Nouvelle table de partitionnement" :
![2](/images/manjaro-home-2.png =900x){.align-center}
- Sélectionnez "Table de partitionnement GUID (GPT)" :
![3](/images/manjaro-home-3.png =900x){.align-center}
- Cliquez sur "Créer" :
![4](/images/manjaro-home-4.png =900x){.align-center}
- Remplissez les champs comme les images suivantes, et cliquez "OK" à chaque étape pour valider chaque partiton :
![5](/images/manjaro-home-5.png =900x){.align-center}
![6](/images/manjaro-home-6.png =900x){.align-center}
![7](/images/manjaro-home-7.png =900x){.align-center}
![8](/images/manjaro-home-8.png =900x){.align-center}
![9](/images/manjaro-home-9.png =900x){.align-center}
![10](/images/manjaro-home-10.png =900x){.align-center}
- **Vous devriez obtenir cette répartition**. Cliquez sur "Suivant" pour valider et passer à la suite :
![11](/images/manjaro-home-11.png =900x){.align-center}

#### Installateur YaST
Utilisé par OpenSuse :
- Cliquez sur "Partitionnement en mode expert", et sélectionnez "Démarrer avec des partitions existantes" :
![](/images/osuse-home-1.png =900x){.align-center}
- Vous obtenez cette fenêtre. Cliquez sur le menu "Périphérique" :
![](/images/osuse-home-2.png =900x){.align-center}
- Puis cliquez sur "Créer une nouvelle table de partitions..." :
![](/images/osuse-home-3.png =900x){.align-center}
- Sélectionnez "GPT" puis cliquez sur "Suivant" :
![](/images/osuse-home-4.png =900x){.align-center}
- Sélectionnez le disque (/dev/sda ou /dev/nvme0 ou ...), puis cliquez sur "Ajouter une partition..." :
![](/images/osuse-home-2.png =900x){.align-center}
- Cette fenêtre se lance... :
![](/images/osuse-home-5.png =900x){.align-center}
- Remplissez les champs comme les images suivantes, et cliquez "Suivant" à chaque étape et pour chaques partitons :
![](/images/osuse-home-6.png =900x){.align-center}
![](/images/osuse-home-7.png =900x){.align-center}
![](/images/osuse-home-8.png =900x){.align-center}
![](/images/osuse-home-9.png =900x){.align-center}
![](/images/osuse-home-10.png =900x){.align-center}
![](/images/osuse-home-11.png =900x){.align-center}
![](/images/osuse-home-12.png =900x){.align-center}
![](/images/osuse-home-13.png =900x){.align-center}
![14](/images/opensuse-home-14.png =900x){.align-center}
![15](/images/opensuse-home-15.png =900x){.align-center}
![16](/images/opensuse-home-16.png =900x){.align-center}
- **Vous devriez obtenir cette répartition**. Vous pouvez maintenant cliquer sur "Accepter" :
![17](/images/opensuse-home-17.png =900x){.align-center}
- Puis ici cliquez sur "Suivant" :
![](/images/opensuse-home-18.png =900x){.align-center}

# Séparer d'autres répertoires

Il est tout à fait envisageable de séparer également d'autres partitions que notre "home". Notamment des partitions avec beaucoup de lectures/écritures disque, comparé aux autres répertoire de la racine `/` qui ne doivent généralement pas être modifiés souvent.

Les 2 répertoires qui enregistrent le plus d'opérations sont :
- le répertoire `/var`
- le répertoire `/tmp`

## Le répertoire VAR

Second élément qui peut potentiellement être scindé de la racine `/`, le répertoire `/var`. 

Ce répertoire contient des fichiers système, des bases de données, toute la journalisation du système, et autres fichiers qui sont amenés à changer fréquemment. Malheureusement si la distribution n'est pas optimisée, il peut parfois remplir le disque et bloquer le système entier.

Il est donc possible de séparer ce répertoire :

_Voici les avantages_ :
1. Améliore les performances : en séparant ce répertoire, cela permet de ne pas bloquer le système entier, et d'éviter un ralentissement du système. Cela permet également d'isoler ce répertoire des autres fichiers système, un bon point pour ne pas affecter les autres parties.
2. Augmente la sécurité : en scindant ce répertoire, cela aide à limiter l'accès aux journaux systèmes à de potentiels attaquants, ne leur permettant pas facilement de les modifier afin de cacher leurs actions.
3. Simplifie la maintenance : en isolant `/var`, nous facilitons (au même titre que la partition `/home`) la sauvegarde et la restauration des fichiers systèmes importants, des bases de données et des configurations importantes.

_Et les inconvénients_ :
1. Requiert de l'espace disque : séparer ce répertoire implique un espace disque suffisant voire additionnel, ce qui ne peut être le cas sur des systèmes avec des disques de petites capacités (256 Go ou 128 Go).
2. Augmente la complexité : bien que nous simplifions la maintenant, cela rend d'un autre côté la gestion du système plus compliquée et difficile à gérer lors d'erreurs à corriger, potentielles mises à jour bancales, etc. Ne convient donc pas forcément aux débutants... 


> Il est donc à noter que nous ne recommandons pas aux débutants de scinder ce répertoire de la racine. Dans ce cas, préférez jouer plutôt sur l'optimisation de la journalisation, évoquée [ici](/tutoriels/distro-protect-hardening#optimisations-journalisation).
{.is-info}

## Le répertoire TMP

Troisième élément qui peut potentiellement être scindé de la racine `/`, le répertoire `/tmp`.

Ce répertoire contient tous les éléments temporaires du système utilisés par les différentes applications, scripts et processus système. Il peut d'agir de tous les fichiers lors d'installation de logiciels, certains fichiers créés lors de "téléchargements en cours", certaines images miniatures, etc., ce que nous nommons généralement des "données volatiles" c'est à dire non nécessaires au fonctionnement intrinsèque du système, et vidés à l'extinction du système.

Il est donc possible de séparer ce répertoire :

_Les avantages_ :
1. Nous améliorons la sécurité : en séparant ce répertoire, nous limitons grandement l'utilisation de fichiers malicieux par des attaquants souhaitant que les utilisateurs accèdent ou exécutent ces fichiers
2. Nous améliorons les performances : en isolant `/tmp`, nous évitons un remplissage générant des lenteurs sur le système.
3. Nous simplifions la maintenance : en isolant `/tmp`, nous facilitons grandement la gestion et surtout le nettoyage des fichiers temporaires, accumulés au fil du temps.

_Mais les inconvénients_ :
1. Espace disque supplémentaire : séparer `/tmp` requiert de l'espace disque, pas simple pour les disques de petites contenances.
2. Peut causer des problèmes de compatibilités : certaines applications ne vont pas aimer accéder à une partition différente, mais préférerons avoir accès à la racine ! Il peut donc subsister des logiciels qui auront des erreurs de compatibilités.


> Sur le même principe que `/var`, nous ne recommandons pas aux débutants d'appliquer une séparation sur `/tmp`. Nous préférerons dans ce cas apporter une optimisation, évoquée [ici](/tutoriels/distro-protect-hardening#optimisations-tmp).
{.is-info}

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo, marmotte*