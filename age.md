---
title: Utilisation de l'outil Age
description: Ce tutoriel vous montre simplement l'utilisation de l'outil Age
published: true
date: 2023-05-03T10:49:21.701Z
tags: chiffrement, intermédiaire, intermediaire, initié, initie
editor: markdown
dateCreated: 2023-01-05T12:41:09.432Z
---

Voici un exemple de l'utilisation de l'outil _Age_ : 

# Installation

Age doit être présent sur les machines de l'émetteur et du destinataire.

### Tabs {.tabset}
#### Debian/Ubuntu
Ou autres distributions basées sur Ubuntu ou Debian :
```
sudo apt install age
```

#### Arch Linux
Ou autres distributions basées sur Arch :
```
sudo pacman -S age
```

#### RedHat/Fedora
Ou autres distributions basées sur Redhat :
```
sudo dnf install age
```

#### OpenSuse
```
sudo zypper install age
```


# Utilisation

> Nous partons du principe que vous avez un document à chiffrer dans le répertoire `~/Documents/`, de nom 'mon-fichier.txt' 

Egalement, Age utilise le chiffrement asymétrique (je vous le rappelle encore : on chiffre avec une clé publique et on déchiffre avec une clé privée), nous devons donc respecter ce principe et procéder comme suit :

## ETAPE :one: :
**VOUS :**
```bash
cat ~/Documents/mon-fichier.txt
```
```brainfuck
Ceci est un fichier!
```

**VOTRE INTERLOCUTEUR :**
```bash
# Génération pair de clés
age-keygen | age -p > ~/key.age
```
```brainfuck
Public key: 
age10c5ezzupktxk06xn9zm2evsraspv926uwjzat6frjpj8gpvs3vwsxxrlf2
Enter passphrase (leave empty to autogenerate a secure one): 
Confirm passphrase: 
```

Après que votre interlocuteur ait généré sa paire de clés (dans un fichier key.age, protégé grâce à l'option -p), il doit vous transmettre le hash de sa clé publique, en l'occurence ici `age10c5ezzupktxk06xn9zm2evsraspv926uwjzat6frjpj8gpvs3vwsxxrlf2`.

## ETAPE :two: :
**VOUS :**
```bash
age -o mon-fichier.txt.age -r \
age10c5ezzupktxk06xn9zm2evsraspv926uwjzat6frjpj8gpvs3vwsxxrlf2 \
mon-fichier.txt
```

Vous chiffrez votre fichier avec le hash de la clé publique reçue de votre interlocuteur. Puis vous pouvez transmettre le fichier obtenu, ici mon-fichier.txt.age.

**VOTRE INTERLOCUTEUR :**
```bash
age -d -i ~/key.age mon-fichier.txt.age
```
```brainfuck
Enter passphrase for identity file "/home/interlocuteur/key.age":

Ceci est un fichier!
```

Votre interlocuteur va donc pouvoir déchiffrer avec sa clé privée, en utilisant l'option -i pour indiquer le fichier de clés. 

**Vous voyez que l'on retrouve le bon texte ('Ceci est un fichier!').**


---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo*