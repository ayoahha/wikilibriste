---
title: Utilisation du Terminal
description: Article générique sur l'utilisation d'un terminal sous GNU/Linux et des principales commandes...
published: true
date: 2023-06-30T20:50:39.094Z
tags: terminal, commandes, shell, debutant, débutant
editor: markdown
dateCreated: 2022-11-25T18:21:33.942Z
---

> Ce chapitre s'adresse avant tout à ceux qui souhaitent creuser les fonctionnalités de lignes de commande inhérentes à une distributions GNU/Linux afin de découvrir cet environnement ou de se débloquer suite à un quelconque blocage...
>
> **Cela dit dans 98% des cas, il est tout à fait possible de se passer du terminal et des lignes de commandes** ;)
{.is-info}

Bête noire et assez peu amicale au premier abord, cet outil est un redoutable monstre de **puissance**, de **rapidité** et de **simplicité** dans son utilisation. Il a finalement toutes les qualités, sauf d'être conviviale...

Chaque distribution GNU/Linux en dispose. Elle est l'essence même de ce qui se passe au cœur de votre ordinateur. Oui, oui ! Vous utilisez sûrement une distribution avec une interface graphique qui vous plaît bien, mais tout ce qui se passe derrière, ça se passe en ligne de commande.

D'ailleurs, on parle de GUI (Graphical User Interface : Interface Graphique Utilisateur) pour parler de ce qui se passe graphiquement à votre écran, et de CLI (Command Line Interface) pour ce qui se passe dans le terminal. Certaines distributions n'ont même pas d'interface graphique par défaut ! Juste un terminal. C'est à vous d'installer l'interface (ou pas).

C'est le cas, par exemple, du serveur qui héberge ce site.

![utilisation_du_terminal.jpg](/images/utilisation_du_terminal.jpg =500x){.align-center}


## Qu'est ce que le terminal ?

Avant de vous présenter les lignes de commande, commençons par faire un tour général de comment s'organise l'usage d'un terminal.

Il est au début très déroutant de se dire que l'on peut exécuter des logiciels sans ne rien voir d'autre que des lignes de texte qui s'affiche dans le terminal. Pourtant, c'est bien cela qui se passe. Quand vous tapez une commande, vous allez donner au préalable l'ensemble des paramètres qui vont dire au logiciel quelle est l'action à exécuter : là où, pour un logiciel graphique, vous allez utiliser des boutons et des éléments graphiques qui vont interagir avec le logiciel qui va ainsi adapter son comportement pour atteindre l'objectif que vous souhaitez.

Ceci étant dit, commençons par le plus nécessaire : ouvrir un terminal.
Pour cela, vous allez dans la liste de vos logiciels, et vous cherchez "Terminal". Il est également possible de l'ouvrir avec le raccourci <kbd>CTRL</kbd> + <kbd>ALT</kbd> + <kbd>T</kbd> sur la majorité des distributions Linux.

Vous obtiendrez une fenêtre semblable à celle-ci :
![terminal_ouverture](/images/terminal_ouverture.webp =600x){.align-center}


### Présentation

Dans cette fenêtre (dont les couleurs changent en fonction de votre configuration), vous ne pouvez faire qu'une chose : taper du texte et lire du texte.

Tout commence avec cette première ligne : `user@computer:~$` ou `[user@computer ~]$`. Elle est nommée **invite de commande**, ou **prompt** pour les intimes...

Cette première ligne contient beaucoup d'informations, et non, rien n'est dû au hasard :

 - `user` désigne l’utilisateur connecté.
 - `@` est juste un séparateur qui signifie “at” ou “chez”, dans la langue de Molière.
 - `computer`, c’est le nom de l’ordinateur sur lequel `user` est connecté.
 - `~` ou la tilde signifie que vous travaillez actuellement dans le dossier utilisateur de `user`.*
 - `$` c’est pour dire que vous êtes connectés en tant qu’utilisateur normal. Vous verriez apparaître un `#` si vous étiez connecté en root.

* Il est à noter que toute commande, et plus largement, tout logiciel est exécuté dans un répertoire. Dans le terminal, par défaut, vous arrivez dans le répertoire de l'utilisateur connecté. Dans notre cas, nous nous trouvons dans `/home/user` qui est aussi abrégé `~`.

_Récapitulons_ : en ouvrant le terminal, nous voyons que nous sommes connectés en tant qu’utilisateur normal *user*, dans le dossier utilisateur de ce même utilisateur, sur l’ordinateur *computer*.


### Un peu de théorie avant la pratique

Il est déjà important d'avoir conscience que chaque commande est exécutée dans un répertoire.

Pour taper une commande, il suffit de l'appeler en tapant son nom. Elle pourra être suivie de "paramètres" si nécessaire.
:warning: *Chaque paramètre doit impérativement être séparé d'un espace. Si vous collez un paramètre au nom de la commande, le système croira que le tout est le nom de la commande.*

Ensuite, pour exécuter la commande, il suffit de taper sur la touche <kbd>ENTREE</kbd>.

C'est tout. Ne fuyez pas tout de suite ! Vous allez très vite comprendre en tapant votre première commande en dessous ;)

> Note : Lorsque, dans un encadré contenant des lignes de commande, une des lignes commence par le caractère "#", cela veut dire que c'est un commentaire. Vous pouvez vous amuser à le copier/coller dans votre terminal et à l'exécuter, il ne se passera rien. Si la ligne commence par un "#", la ligne sera purement et simplement ignorée.
> -- L'utilité du "#" est simplement de pouvoir commenter.
{.is-info}

### Quelques astuces

#### Flèche haut

Pour retaper une commande que vous avez tapé précédemment, il suffit d’appuyer sur <kbd>Flèche Haut</kbd> autant de fois que nécessaire.

#### L'auto-complétion

Le Terminal gère l'auto-complétion. En d'autres termes, si vous commencez à taper le début d'une commande, vous pourrez auto-compléter ce nom avec la touche <kbd>TAB</kbd>.

Commencez à taper `/home/u`, puis appuyez sur la touche <kbd>TAB</kbd> permet de compléter la saisie et indiquera alors `/home/user`.

Si plusieurs solutions ont été trouvées, alors il complétera jusqu'à l'endroit où les solutions diverges. En reprenant l'exemple précédent, mais en imaginant qu'il y ait un dossier `usat` dans /home. Commencez à taper `/home/u`, auto-complétez avec <kbd>TAB</kbd>, et la saisie vous indiquera `/home/us`. Vous pouvez alors rajouter un "e" ou un "a" puis auto-compléter. Vous obtiendrez respectivement `/home/user` ou `/home/usat`.

#### Couper l'exécution d'un programme

Si vous lancez une commande, qu'elle met un peu de temps à s'exécuter, et que vous vous rendez compte qu'il y a une erreur, ou que vous voulez quitter le programme avant la fin, il y a une solution.

Pour arrêter en plein vol une commande, il faut utiliser le raccourci : <kbd>CTRL</kbd> + <kbd>C</kbd>.

#### Le bang-bang

Non non, ce n'est pas une blague... Le "bang", en argot anglais, désigne le point d'exclamation. Donc "bang-bang" signifie... vous avez compris !

Si, par exemple, au lieu de taper `cd /home/user/Documents`, vous tapez `/home/user/Documents` puis vous validez avant de vous rendre compte de votre bêtise, alors, pas besoin de retaper toute la ligne.

Le "bang-bang" signifie : "la commande précédente". Vous n'aurez donc qu'à taper `cd !!`. Le terminal comprendra alors ce que vous vouliez dire : il remplacera "!!" par le contenu de la commande précédente.


## Naviguer depuis le terminal

> Crucial pour la suite...
> Vous utiliserez ces quelques commandes plus que toutes les autres.
{.is-info}

### Se retrouver

Pour savoir où l'on va, il faut savoir où nous sommes… C’est l’occasion de voir notre première commande.

Pour connaître le répertoire où nous sommes placé, et donc où nous allons exécuter nos commandes, nous utilisons :

```bash
pwd
```

Une fois la commande tapée, vous pouvez la relire, avant de l'exécuter en tapant sur <kbd>ENTREE</kbd>.

![terminal, première commande tapée](/images/terminal_commande_pwd.webp =500x){.align-center}

Vous devriez alors voir apparaître une nouvelle ligne dans votre terminal, semblable à : `/home/user`. En dessous, un nouveau "prompt" s'affiche, ce qui indique que vous pouvez taper une nouvelle commande.

`pwd` n'a rien à voir avec une contraction du mot "password", cela signifie **print working directory** (*imprimer le dossier de travail*, dans une langue moins barbare…).


### Trouver les autres

Maintenant que nous savons où nous sommes, regardons ce qui est disponible dans notre dossier de travail.

Pour cela, tapez la commande :

```bash
ls
```

Comme **list**. Pour lister ce qui se trouve dans le dossier courant (votre dossier de travail actuel). À partir de maintenant, je ne vous dirai plus de taper sur <kbd>ENTREE</kbd> après chaque commande.

Vous devriez voir la liste de vos dossiers personnels :

![terminal, liste des dossiers](/images/terminal_commande_ls.webp =500x){.align-center}

Si c’est pas exactement ça, ça y ressemble !

**Ajouter un paramètre (ou option) à une commande**
Peu après le début, je vous ai parlé de paramètre possible pour les commandes. La commande `ls` permet d'en ajouter. Créons donc notre première commande avec paramètre !
`ls` n'affiche en réalité pas tous les fichiers et répertoires. Mais seulement les fichiers et répertoires visibles (car certains sont cachés).
Le paramètre `-a` ("a", comme "all", "tout" en français) va dire à `ls` d'afficher **tout** ce qui est contenu dans notre répertoire courant.

La commande sera alors :

```bash
ls -a
```

*2 remarques face au résultat de la commande :*
 - *Vous remarquerez qu'un dossier ou un fichier qui commence par un point est un dossier ou un fichier caché sur GNU/Linux.*
 - *Il y a un dossier `..` (c'est bien un dossier, réel). Il correspond au dossier parent, c’est-à-dire le dossier qui contient celui dans lequel vous vous trouvez. Dans notre exemple, vous vous trouvez dans le dossier `/home/user`. Le dossier parent est donc `/home`.

Le résultat chez moi :

![terminal, liste des fichiers et dossier y compris caché](/images/terminal_commande_ls-a.webp =500x){.align-center}

**Il est également possible d'ajouter d'autres paramètres**
On peut par exemple demander à `ls` de nous afficher **tous** les fichiers/répertoires contenus dans notre dossier *Documents*.

Pour cela :

```bash
ls -a Documents/
```

On obtiendra le même résultat en tapant :

```bash
ls -a /home/user/Documents/
```

*si vous avez bien suivi, vous verrez qu'il est nécessaire d'adapter `user` avec votre nom d'utilisateur.


### Se déplacer

Pour se déplacer dans un autre dossier, c'est-à-dire, changer de répertoire de travail, il faut utiliser la commande `cd`, pour "change directory" ("changer de répertoire"). *Vous remarquerez que les commandes sont souvent des contractions de mots anglais.*

Mais, pour que `cd` sache dans quel répertoire vous souhaitez vous déplacer, il faut le lui indiquer en paramètre.

Ainsi, la commande devient :

```bash
cd Documents
```

ou encore :

```bash
cd /home/user/Documents
```

*(À partir de maintenant, nous ne détaillerons plus les deux manières d'indiquer un chemin. Sachez que la première utilise un "chemin relatif", car relatif à l'emplacement où vous êtes actuellement. La seconde utilise un "chemin absolu", car il indique le chemin depuis le point de départ de votre disque dur).*

Maintenant cette commande `cd` tapée, vous pouvez vérifier que votre répertoire de travail a changé :
 - Avec la commande `pwd`, qui vous retournera maintenant `/home/user/Documents`.
 - Dans les informations du prompt : `~` est devenu `~/Documents`.

Pour revenir au dossier parent, nous utilisons ce que nous avons précédemment appris avec la commande `ls` en tapant :

```bash
cd ..
```

Mais si, plutôt que de revenir au dossier parent, nous souhaitons aller dans le dossier "Images", nous pouvons aussi le faire en tapant directement :

```bash
cd ../Images
```

*Notez bien l'espace qui sépare `cd` de `..`.*


## Manipuler les fichiers et les dossiers

> Maintenant que vous êtes super calé pour naviguer avec le terminal, on va apprendre à manipuler les fichiers et les dossiers.
{.is-info}


### Créer un dossier

Vous remarquerez que toutes les commandes ont des noms anglais...
Pour créer un dossier, en anglais *make directory*, ça a donné la commande `mkdir`.

Nous allons donc créer un dossier nommé *Photos*.

```bash
mkdir Photos
```

Et en faisant un petit `ls`, vous verrez votre nouveau dossier nommé *Photos*. Et si vous ouvrez votre navigateur de fichier graphique dans le même dossier de travail que là où vous êtes dans le terminal (commande `pwd` si vous avez un doute ;), vous verrez également ce dossier "Photos".

Il est possible d'en créer plusieurs simultanément :

```bash
mkdir Photos1 Photos2 Photos3
```

Il suffit de séparer les différents dossiers par un espace. Faites un test et vérifiez avec `ls`, vous verrez !

Cependant, attention ! Si par exemple vous voulez créer un dossier qui s'appelle "*Photos de vacances 2022*", et que vous faites `mkdir Photos de vacances 2022`, alors vous n'aurez pas un mais quatre dossiers ! Le premier sera nommé *Photos*, le second sera nommé *de*, le 3ème sera nommé *vacances* et le dernier, *2022*.
En effet, le programme "mkdir" croit que vous voulez créer 4 dossiers dont les noms sont séparés par des espaces (comme la commande précédente).

Pour dire au programme que non, ce n'est qu'un seul nom, il faut utiliser des guillemets qui "encadreront" le nom de votre dossier.

```bash
mkdir "Photos de vacances 2022"
```

*NB : Il existe un autre moyen de créer un fichier dont le nom comporte des espaces, mais on verra ça plus tard !*

Notez que ce problème d'espace est vrai pour toutes les commandes que vous taperez. Un autre exemple, si vous voulez vous déplacer dans le dossier "Images/Photos de vacances 2022", il faudra aussi mettre des guillemets, sinon la commande vous retournera une erreur :

```bash
cd "Images/Photos de vacances 2022"
```

Si vous voulez prendre une bonne habitude : mettez **toujours** des guillemets autour de vos noms/chemins de fichiers ;)

### Créer un fichier

Bon, j'ai envie de dire "*Ne me demandez pas pourquoi*", mais la commande pour créer un fichier, c'est `touch`...

Bien sûr, vous allez me demander "*pourquoi ?*" alors, à cette question, je vais répondre plus tard mais sachez que c'est exactement la même procédure que pour les dossiers.

Pour créer un fichier :

```bash
touch mon_fichier.txt
```

*NB : remarquez que pour éviter l'espace, nous le changeons en "_".*

Pour créer un fichier avec des espaces dans le nom :

```bash
touch "Mon super fichier avec des espaces dans le nom.txt"
```

Pour créer plusieurs fichiers :

```bash
touch fichier1 fichier2 fichier3
```

> Remarque : Sur Linux, les extensions (.txt, .mp4, .odt, .conf, etc...) n'ont pas d'impact sur le fichier lui-même. Cela va juste permettre d'indiquer le logiciel qui servira à ouvrir le fichier. Mais si vous souhaitez vous amuser, vous pouvez créer votre propre extension. De fait, nous recommandons de suivre les conventions qui permettront de garder de l'ordre dans vos fichiers.
{.is-info}


### Supprimer un fichier

"*Supprimer*" ou "*to remove*", de l'autre côté de la Manche (et de l'Atlantique aussi, d'ailleurs).
Dans notre terminal, nous allons utiliser `rm`.

Supprimer un fichier :

```bash
rm mon_fichier.txt
```

Supprimer plusieurs fichiers :

```bash
rm fichier1 fichier2 fichier3
```

Supprimer un fichier dont le nom contient des espaces :

```bash
rm "Mon super fichier avec des espaces dans le nom.txt"
```

Et hop, les fichiers ont été supprimés !


Il existe un petit caractère magique dans les commandes : `*` - l'étoile. Et là on commence à toucher un début de puissance de la ligne de commande. Ce caractère remplace n'importe quel caractère ou n'importe quelle chaîne de caractères.

Exemple : pour supprimer nos trois fichiers (fichier1, fichier2, fichier3) on peut faire simplement :

```bash
rm fichier*
```

2 remarques s'imposent :
 - Vérifiez que vous n'avez pas un fichier qui s'appellerait "*fichier de travail.odt*" par exemple, car il serait supprimé. Tout ce qui commence par "*fichier*", peu importe la suite du nom, sera supprimé.
 - Vous ne pouvez pas mettre le `*` entre guillemets. Sinon, la commande cherchera un seul fichier dont le nom sera "fichier*". Pour combiner ce caractère avec une recherche de fichier avec espace : `"fichier avec blanc"*`

Quelques exemples :

```bash
#supprimer tous les fichiers qui commencent par "fich"
rm fich*
#suprimmer toutes vos photos qui finissent par ".jpg"
rm *.jpg
```

> Attention : s'il y a des millions de fichiers dans votre dossier qui correspond à votre recherche, `rm *` supprimera l'ensemble sans rien vous demander. Vous lui demandez de faire, il fait, donc faites attention à ce que vous lui demandez. Soyez donc prudents dans son utilisation.
{.is-warning}


###  Supprimer un dossier

Supprimer ("remove" chez nos voisins) : `rm`... La même commande que pour supprimer un fichier.

Mais si vous essayez de supprimer un dossier avec la commande `rm`, celle-ci va vous retourner une erreur en disant qu'elle ne peut pas supprimer, parce que c'est un dossier.

Il va falloir dire à la commande : attention, c'est un dossier, et je veux le supprimer. Pour cela, il faudra ajouter à `rm` l'option `-r` pour dire qu'il faut supprimer les dossiers et fichiers de façon récursive.

Cela donnera donc :

```bash
#supprimer un dossier
rm -r dossier
#supprimer plusieurs dossiers
rm -r dossier1 dossier2
#supprimer plusieurs dossiers : attention à vous ;)
rm -r dossier*
```


## Quelques commandes de tous les jours

Bon, on est bien gentil, on vous surcharge d'informations... Mais se déplacer dans vos dossiers, créer des dossiers, des fichiers, les supprimer, vous le faites depuis longtemps avec votre souris et ça marche aussi. Vous voulez nous dire : *faites nous voir quelque chose d'utile !*

On vous entend, mais ces quelques commandes étaient nécessaires pour comprendre un minimum ce que vous faites avant d'aborder des commandes très pratiques.

> Maintenant, voyons des exemples qui vont mettre en œuvre tout ce que nous avons vu précédemment. Si vous n'avez pas lu les sections précédentes, nous vous conseillons vivement de les suivre avant de passer à celles-ci.
{.is-info}

### Editer le contenu d'un fichier

Vous allez sans doute parfois vouloir éditer un fichier. Bien que vous pouvez utiliser les outils graphiques (tels que gEdit, Kate ou Mousepad, etc.), il est tout à fait possible de modifier du texte dans un fichier grâce au terminal, c'est parfois même plus rapide ! Voyons ce que cela donne :

#### Nano

GNU Nano est un outil d'éditeur de texte en ligne de commande, utilisable sur beaucoup de distro nativement.

- **Dans le cas contraire, installez simplement le paquet nommé 'nano'**

Nano est extrêmement simple dans son utilisation : vous ouvrez l'outil, et éditez directement le texte, puis une combinaison de touches vous permet d'effectuer les actions nécessaires (enregistrement, quitter, etc.).

Prenons le cas d'un fichier texte `monfichier.txt` se trouvant dans ce répertoire `~/Documents`. Nous souhaitons modifier son contenu.

Pour commencer, lançons l'outil dans le répertoire (`~/Documents`, cf. [ici](/debutant/terminal#se-d%C3%A9placer) si vous avez un doute) en question en lui indiquant le fichier que nous souhaitons éditer :

```bash
nano monfichier.txt
```

Voici ce que nous obtenons :

![GNU Nano](/images/nano.png =600x){.align-center}

Nous pouvons voir ici que :
- Le **curseur** est représenté par un "rectangle blanc", qui clignote, en tout début de fichier.
- Nous pouvons nous déplacer dans tout le contenu avec les touches directionnelles <kbd>Flèche Haut</kbd>, <kbd>Flèche Bas</kbd>, <kbd>Flèche Gauche</kbd>, <kbd>Flèche Droite</kbd>.
- Nous pouvons également supprimer ou ajouter du contenu, **au curseur**.
- Des indications sont présentes en bas de l'outil :

![GNU Nano - Barre d'information](/images/nano-infos.png =600x){.align-center}

> Il s'agit des combinaisons de touches à effectuer afin d'obtenir les actions citées.
> _Note_ : Le caractère "**^**" représente la touche <kbd>CTRL</kbd>.
>
> _Par exemple_ : Pour quitter l'outil, il nous suffit simplement d'appuyer simultanément sur <kbd>CTRL</kbd> + <kbd>X</kbd>.
{.is-info}

Tentons de modifier le fichier, d'enregistrer le contenu puis de quitter l'outil :
1. Nous ajoutons du texte (peu importe) à la fin du fichier :

![GNU Nano - Edition](/images/nano-1.png =600x){.align-center}

2. Nous appuyons simultanément sur <kbd>CTRL</kbd> + <kbd>X</kbd>, puis nous obtenons :

![GNU Nano - Edition](/images/nano-2.png =600x){.align-center}

- L'outil a ici détecté une modification du fichier, et nous propose donc de sauvegarder ces modifications. Nous avons le choix :
	- Y (ou O en français) pour accepter les modifications,
	- N (ou N en français) pour refuser les modifications.

3. Acceptons les modifications en entrant <kbd>Y</kbd> (ou <kbd>O</kbd>), l'outil nous propose de confirmer le nom du fichier (nous pouvons très bien entrer un nom différent, ce qui aura pour but de modifier le nom du fichier !) :

![GNU Nano - Edition](/images/nano-3.png =600x){.align-center}

4. Tapons <kbd>ENTREE</kbd> pour valider le nom de fichier puisque nous souhaitons garder ce nom. L'outil se ferme et le terminal est de nouveau affiché.

Voilà, le fichier est bien modifié. Nous pouvons vérifier par cette commande :
```bash
cat monfichier.txt
```

![GNU Nano - Edition](/images/nano-4.png =600x){.align-center}

> Il existe bien entendu d'autres combinaisons de touches (<kbd>CTRL</kbd> + <kbd>K</kbd>, <kbd>CTRL</kbd> + <kbd>U</kbd>, <kbd>CTRL</kbd> + <kbd>G</kbd>, etc.). Nous vous recommandons de lire le manuel pour obtenir des informations sur ces combinaisons.
{.is-info}

#### Vim

Vim est le successeur du très ancien et très connu Vi, outil très puissant d'édition en ligne de commande ; d'ailleurs, son nom le montre bien 'VIM' pour 'VI iMproved' ! Vim est pré-installé sur une grande partie des distros.

- **Dans le cas contraire, installez simplement le paquet nommé 'vim'** (et non neovim, nvim, etc.)

Vim est un peu plus complexe que d'autres outils d'édition de texte en ligne de commande : par défaut, l'écriture n'est pas active, il faudra utiliser certaines touches ou suites de touches du clavier pour activer certaines fonctions.

Voyons cela !

Prenons le cas d'un fichier texte `monfichier.txt` se trouvant dans ce répertoire `~/Documents`. Nous souhaitons modifier son contenu.

Pour commencer, lançons l'outil dans le répertoire (`~/Documents`, cf. [ici](/debutant/terminal#se-d%C3%A9placer) si vous avez un doute) en question en lui indiquant le fichier que nous souhaitons éditer :

```bash
vim monfichier.txt
```

Voici ce que nous obtenons :

![Vim](/images/vim.png =600x){.align-center}

Nous pouvons voir ici que :
- Le **curseur** est représenté par un "rectangle blanc", qui clignote, en tout début de fichier.
- Nous pouvons nous déplacer dans tout le contenu avec les touches directionnelles <kbd>Flèche Haut</kbd>, <kbd>Flèche Bas</kbd>, <kbd>Flèche Gauche</kbd>, <kbd>Flèche Droite</kbd>.
- Des indications sont présentes en bas de l'outil :

![Vim - Barre d'information](/images/vim-infos.png =600x){.align-center}

> Il s'agit d'informations utiles sur le contenu du fichier.
> 
> **Cette zone sera néanmoins très utile par la suite car les combinaisons de touches apparaîtront ici !**
{.is-info}


Tentons de modifier le fichier, d'enregistrer le contenu puis de quitter l'outil :
1. Nous souhaitons ajouter du texte (peu importe) à la fin du fichier. Pour ce faire, l'outil est différent des autres, nous allons devoir placer le curseur là où nous souhaitons ajouter du texte, puis appuyer sur la touche <kbd>i</kbd> afin d'autoriser l'édition :

![Vim - Edition](/images/vim-1.png =600x){.align-center}

Vous pouvez vous apercevoir ici qu'en bas à droite de l'outil, la mention "-- INSERT --" est présente, ceci vous indique que le mode "Edition" est activé.

2. A la fin de la modification, nous allons sortir de ce mode "Edition", en appuyant simplement sur <kbd>ECHAP</kbd>. Nous revenons dans le mode initial.
3. Pour pouvoir sauvegarder les modifications, nous allons appuyer sur les touches suivantes dans cet ordre : <kbd>:</kbd> et <kbd>w</kbd>. Observez bien la barre d'information en bas :

![Vim - Edition](/images/vim-2.png =600x){.align-center}

- La touche <kbd>:</kbd> indique à l'outil que nous souhaitons ouvrir un prompt d'actions.
- La touche <kbd>w</kbd> est la touche utilisée pour sauvegarder.

4. Appuyez sur <kbd>ENTREE</kbd> :

![Vim - Edition](/images/vim-3.png =600x){.align-center}

5. Pour quitter l'outil, nous entrerons simplement, dans l'ordre : <kbd>:</kbd> et <kbd>q</kbd>

![Vim - Edition](/images/vim-4.png =600x){.align-center}

- La touche <kbd>:</kbd> indique à l'outil que nous souhaitons ouvrir un prompt d'actions.
- La touche <kbd>q</kbd> est la touche utilisée pour quitter.

6. Puis <kbd>ENTREE</kbd>. L'outil se ferme et le terminal est de nouveau affiché.

Voilà, le fichier est bien modifié. Nous pouvons vérifier par cette commande :
```bash
cat monfichier.txt
```

![Vim - Edition](/images/vim-6.png =600x){.align-center}

> Afin de combiner sauvegarde et sortie de l'outil, nous pouvons entrer à la suite : <kbd>:</kbd>, <kbd>w</kbd> puis <kbd>q</kbd> !
> 
> ![Vim - Edition](/images/vim-5.png =600x)
{.is-info}

> Il existe bien entendu d'autres actions, à activer avec certaines touches du clavier. Nous vous laissons lire la documentation pour en apprendre davantage.
{.is-info}

### Déplacer toutes les images JPG dans un dossier

Voici un exemple concret et utile. Si vous avez des milliers d'images en ".jpg" mélangées à des images ".png" et ".webp", et que vous voulez déplacer ces images *jpg* dans un dossier "photos", les logiciels graphiques ne vous seront pas d'une grande utilité. Vous allez mettre longtemps à sélectionner toutes vos images, qui plus est sans vous tromper... La ligne de commande va vous sauver.

La commande à appeler est `mv` ("move", *déplacer* en anglais). En combinant cette commande avec le caractère `*` on obtient :

```bash
#si votre dossier n'existe pas :
mkdir photos
#déplacer toutes les photos qui finissent par .jpg dans le dossier "photos"
mv *.jpg photos/
```

### Convertir une image dans un autre format

Les logiciels pour convertir une image dans un autre format existent bel et bien. Mais, faisons un concours de rapidité : terminal vs graphique...

Pour le terminal, il faudra préalablement installer le logiciel *imagemagick* (`sudo apt install imagemagick`, détail en dessous).

Ensuite, supposons que nous voulons convertir notre image "capture_firefox_2023-01-24.png" dans le format webp.

Pour cela, *imagemagick* offre une commande `convert` qui s'utilise ainsi : `convert <image_source> <image_cible>`.

Ce qui nous donnera :

```bash
convert capture_firefox_2023-01-24.png capture_firefox_2023-01-24.webp
```

Mais souvenez-vous : on peut aller extrêmement vite pour taper les noms grâce à l'auto-complétion. En ne tapant que le début de la commande, puis le début des noms, et en auto-complétant à chaque fois, taper cette longue commande m'a pris moins de 5 secondes... En le faisant 2-3 fois, vous serez convaincu de gagner du temps à convertir une image via le terminal ;)

Finalement, en littéralement moins de 10 secondes, la conversion peut être faite. Pas sûr de pouvoir en dire autant d'un logiciel graphique.


### Télécharger une vidéo

Question récurrente sur beaucoup de forum : comment télécharger les vidéos de tel ou tel site ?

En ligne de commande, rien de plus simple avec le logiciel [yt-dlp](https://github.com/yt-dlp/yt-dlp/) qu'il faudra avant installer.

Supposons que nous voulons **télécharger une vidéo depuis Youtube** :

```bash
#On se déplace dans nos téléchargements
cd "Téléchargements"
#On télécharge la vidéo
yt-dlp "https://youtu.be/g90FZJhl82k"
```

*Note : pour ne pas avoir à vous déplacer dans le dossier "Téléchargements" en ligne de commande, vous pouvez ouvrir directement le terminal dans ce dossier en utilisant votre gestionnaire de fichiers, en allant dans vos téléchargements, puis en faisant : clic-droit > Ouvrir dans un terminal*

Oui mais c'est une musique, la vidéo n'est pas très intéressante...
`yt-dlp` permet de **ne télécharger que l'audio** si vous souhaitez grâce à l'option `-x`, ce qui donne :

```bash
yt-dlp -x "https://youtu.be/g90FZJhl82k"
```

> Bonne nouvelle : yt-dlp ne télécharge pas que des vidéos provenant de Youtube. Mais il est capable de télécharger des vidéos de plusieurs centaines de sites différents. Vous lui donnez n'importe quelle URL, et il s'occupe de détecter la provenance de la vidéo, et de la télécharger (par défaut, la meilleure qualité disponible).
{.is-info}


### Partager un fichier sur le réseau

Si vous êtes chez vous et que vous voulez transférer un fichier sur un autre ordinateur connecté au même réseau (même box), la ligne de commande peut encore vous sauver. *(nous n'entrerons pas dans le détail technique)*

Sur l'ordinateur dont vous voulez partager le fichier, nous avons besoin de connaître son adresse IP :

```bash
hostname -I
```

Puis nous partageons le dossier où se trouve notre fichier : dans notre cas, le fichier se trouve dans nos *Documents*.

```bash
#on se déplace dans nos documents
cd Documents/
#on partage le fichier
python3 -m http.server
```

Pour arrêter le partage, nous utiliserons le raccourci : <kbd>CTRL</kbd> + <kbd>C</kbd>.

Sur l'ordinateur cible, il suffira d'ouvrir le navigateur (firefox par exemple). Dans la barre d'URL, vous entrerez l'adresse IP trouvée en première étape, suivie de ":8000". Vous n'aurez alors plus qu'à cliquer sur votre fichier.


## Quelques commandes *root* (administrateur)

**Sur Linux les droits sont extrêmement encadrés.** Un utilisateur ne peut toucher qu'à ces propres fichiers (tout ce qui se trouve dans `/home/user`).
Mais si vous voulez par exemple installer un logiciel, le logiciel sera installé dans des répertoires tel que `/usr` ou `/bin`. Donc, **en tant qu'utilisateur, vous n'avez pas le droit d'installer les logiciels. Pour obtenir ces droits, il faut être ce qu'on appelle "*root*".**

> Attention : `sudo` confère de grande responsabilité. Avec les droits administrateur, vous obtenez les droits de faire ce que vous voulez sur tout l'ordinateur. **Ce qui veut également dire que vous pouvez détruire des fichiers nécessaires au fonctionnement de votre ordinateur**. Ne tapez donc pas de commande dont vous n'êtes pas sûr, et si vous avez des doutes, n'hésitez pas à vous renseigner avant, ou à demander de l'aide à un ami ou sur un forum !
{.is-warning}

Pour donner ces droits administrateur à une commande, il suffit d'utiliser la commande `sudo` (pour *superuser do*), suivie de la commande que vous voulez exécuter.

Si vous voulez donner les droits administrateur à toutes les commandes que vous taperez par la suite (déconseillé), tapez la commande `sudo -i`. Cela modifiera votre prompt qui finira à présent par un `#`, ce qui indiquera que vos commandes sont tapées en tant que *root*.

**Quoi qu'il arrive, quand vous appelez sudo, votre mot de passe sera demandé, vous n'aurez qu'à le taper, et à le valider par <kbd>ENTREE</kbd>.**

### Chercher/Installer/Supprimer des logiciels

Je sais, on peut le faire en graphique sur la majorité des distributions Linux. De fait, si une erreur survient, la ligne de commande vous donnera des détails de l'erreur, pas l'interface graphique (1er avantage). 2ème avantage : c'est beaucoup plus rapide.

Pour toutes ces tâches, nous utiliserons la commande `apt`.

Pour chercher un logiciel : on cherche (en anglais) un outil pour télécharger des vidéos youtube :

```bash
#"apt search" suivi des mots de recherche
apt search youtube downloader
```

Pour installer un logiciel : installation de yt-dlp :

```bash
#"apt install" suivi du nom du paquet à installer
sudo apt install yt-dlp
```

Pour désinstaller un logiciel :

```bash
#"apt remove" suivi du nom du paquet à désinstaller
sudo apt remove yt-dlp
```

Bonus, **pour mettre à jour votre ordinateur** :

```bash
sudo apt update
sudo apt upgrade
```

Ces deux commandes sont à mettre dans cet ordre car :
- `Update` sert à mettre à jour les dépôts.
- `Upgrade` sert à mettre à jour les paquets issus des dépôts... nouvellement mis à jour.


## Astuces

Lorsque vous débutez, il est préférable de saisir une commande à la fois.
En revanche, si vous maîtrisez les lignes de commande ou si vous avez beaucoup de commandes à taper, vous pouvez utiliser : 

- Le `&&` (double "et" commercial) qui sert à enchaîner la commande qui suit, si et seulement si la précédente se termine avec succès.
- Le `;` (point virgule) qui enchaîne les commandes qu'elles réussissent ou non.

Donc au lieu de faire...
```bash
sudo apt update
``` 
Appuyez sur la touche <kbd>Entrée</kbd> pour valider la commande.
```bash
sudo apt upgrade
```
Appuyez sur la touche <kbd>Entrée</kbd> pour valider la commande.
... vous pouvez faire :
```bash
sudo apt update && sudo apt upgrade
```
Appuyez sur la touche <kbd>Entrée</kbd> pour valider la commande.
ou 
```bash
sudo apt update ; sudo apt upgrade
```
Appuyez sur la touche <kbd>Entrée</kbd> pour valider la commande.

## Quitter le terminal

Et oui, tout a une fin ;(
Aussi, pour sortir du mode root pour revenir au mode user classique, utilisez l'une ou l'autre de ces commandes : 
```bash
sudo -k
```
ou
```bash
exit
```

Enfin, pour quitter et sortir du Terminal sans passer par le menu Fichier - Fermer la fenêtre, vous pouvez aussi utiliser :
```bash
exit
```

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo, marmotte et Theudric*