---
title: Utilisation standard de Kryptor
description: Ce tutoriel vous montre comment utiliser l'outil Kryptor
published: true
date: 2023-05-03T10:47:59.300Z
tags: signature, chiffrement, intermédiaire, intermediaire, initié, tutoriel, initie
editor: markdown
dateCreated: 2023-01-05T12:39:08.096Z
---

Voici des exemples de l'utilisation de l'outil _Kryptor_ :

# Installation

Voici les commandes à utiliser afin de télécharger et installer l'outil :

```bash
wget https://github.com/samuel-lucas6/Kryptor/releases/latest/download/kryptor-linux-x64.zip
```
```brainfuck
[...]
kryptor-linux-x64.zip                              100%[===============================================================================================================>]  13,95M  10,8MB/s    ds 1,3s

2022-11-21 14:12:32 (10,8 MB/s) - ‘kryptor-linux-x64.zip’ enregistré [14630982/14630982]
```
```bash
wget https://github.com/samuel-lucas6/Kryptor/releases/latest/download/kryptor-linux-x64.zip.digest
```
```brainfuck
[...]
kryptor-linux-x64.zip.digest                     100%[===============================================================================================================>]      89  --.-KB/s    ds 0s

2022-11-21 14:13:33 (3,24 MB/s) - ‘kryptor-linux-x64.zip.digest’ enregistré [89/89]
```
```bash
sha256sum -c kryptor-linux-x64.zip.digest kryptor-linux-x64.zip
```
```brainfuck
kryptor-linux-x64.zip: Réussi
```
```bash
unzip kryptor-linux-x64.zip 
```
```brainfuck
Archive:  kryptor-linux-x64.zip
      inflating: kryptor
      inflating: LICENSE.txt
       creating: Licenses/
      inflating: Licenses/ChaCha20-BLAKE2b LICENSE.txt
      inflating: Licenses/CommandLineUtils LICENSE.txt
      inflating: Licenses/Geralt LICENSE.txt
      inflating: Licenses/kcChaCha20-Poly1305 LICENSE.txt
      inflating: Licenses/libsodium LICENSE.txt
      inflating: Licenses/libsodium-core LICENSE.txt
      inflating: Licenses/Monocypher.NET LICENSE.txt
```
```bash
chmod +x kryptor
```


# Chiffrement symétrique

> Nous partons du principe que vous avez un document à chiffrer dans `~/Documents` de nom mon-fichier.txt. 

Ce premier point utilise le chiffrement symétrique :

```bash
./kryptor -u
./kryptor -e -k " " ~/Documents/mon-fichier.txt
```
```brainfuck
Randomly generated key: PSK/+p7+gfFvwEi4jcN4/28+GT+TKqslk+okMGl58I0pTtE=

Encrypting "mon-fichier.txt" => "mon-fichier.txt.bin"...

Successfully encrypted: 1/1
```

Nous utilisons une clé symétrique générée aléatoirement par l'outil grâce à l'option `-k " "`. Si cela dit vous avez déjà une clé symétrique et que vous souhaitez l'utiliser, vous pouvez la spécifier avec cette option.

> Vous obtenez un fichier de sortie avec l'extension .bin, c'est ce fichier qui est chiffré.
{.is-success}

# Chiffrement asymétrique

> Nous partons du principe que vous avez un document à chiffrer dans `~/Documents` de nom mon-fichier.txt. 

Ce second point utilise maintenant le chiffrement asymétrique. La bi-clé sera générée ici : `~/.kryptor/`. 
Mais attention ici, l'utilisation du chiffrement asymétrique impose quelques conditions. Relisez bien le préambule sur l'[utilisation de PGP](/intermediaire/chiffrement#pgp-gpg) notamment le paragraphe sur le chiffrement asymétrique : ce type de cryptographie impose de chiffrer avec une clé publique et déchiffrer avec une clé privée. Comme une clé privée ne se transmet JAMAIS, il va nous falloir respecter ce principe. 2 cas de figures ici : soit vous chiffrez pour vous-même et dans ce cas il est inutile de vous embêtez avec l'utilisation puisque vous êtes propriétaire de la clé publique ET privée. En revanche, si vous souhaitez chiffrer pour transmettre à une tierce personne, vous allez devoir respecter ce principe : chiffrer avec la clé publique du destinataire, de sorte que celui-ci puisse déchiffrer avec sa clé privée.

## CAS 1 : Vous chiffrez pour vous-même

```bash
./kryptor -g
```
```brainfuck
Please select a key pair type (type 1 or 2):
1) Encryption
2) Signing
1

Enter a password (leave empty for a random passphrase):

Retype password:

Deriving encryption key from password...

Public key: Cu//VyfaURgSwNYxWLuYXCZ0r9ZEP7HpwqsVaUpfPVN36wY=
Public key file: "/home/user/.kryptor/encryption.public"

Private key file: "/home/user/.kryptor/encryption.private" - Keep this secret!

IMPORTANT: Please back up these files to external storage (e.g. memory sticks).
```
```bash
[user@ordinateur:~ $] ./kryptor -e ~/Documents/mon-fichier.txt
```
```brainfuck
Enter your private key password:

Decrypting private key...

Encrypting "mon-fichier.txt" => "mon-fichier.txt.bin"...

Successfully encrypted: 1/1
```

Nous avons généré notre bi-clé de chiffrement, comme ce que nous demande PGP (bien que la génération soit un peu plus simple). Cependant, tout comme PGP et comme l'outil le stipule bien, veillez à bien garder votre *clé privée* au chaud, le mieux bien entendu est de la stocker de la même manière que pour PGP (hors ligne, clé USB chiffrée) ! Clé USB à resortir à chaque fois que vous souhaiterez chiffrer un fichier ou un répertoire.

Notez bien que lors de la commande `kryptor -e`, vous devrez entrer le mot de passe donné lors de la génération de la clé de chiffrement.

## CAS 2 : Vous chiffrez pour transmettre une information

*Nous partirons du principe que votre interlocuteur a également généré sa bi-clé de chiffrement via Kryptor puis vous a transmis sa clé publique, que vous avez stockée ici : ~/.kryptor/cle\_interlocuteur.public*. 

Puis la commande `cd ~/.kryptor/ && cat cle_interlocuteur.public` vous a permis de pouvoir retenir le hash de cette clé, dans notre exemple : Cu//2SQwPkpAzHDVDDlCmfx3C681I++EZS9/JjsCcPgA60w=
*Ensuite, vous avez également de votre côté transmis votre clé publique.*

```bash
./kryptor -e -y Cu//2SQwPkpAzHDVDDlCmfx3C681I++EZS9/JjsCcPgA60w= ~/Documents/text.txt
```
```brainfuck
Enter your private key password:

Decrypting private key...

Encrypting "text.txt" => "text.txt.bin"...
```

La petite particularité ici avec Kryptor est que vous aurez besoin de votre clé privée (oui je parle bien de la vôtre !) afin d'appliquer ce chiffrement. Il vous sera demandé le mot de passe de votre clé privée, sûrement que les développeurs ont pensé que l'opération étant critique la seule manière de confirmer que c'est vous qui chiffrez est d'utiliser votre clé privée afin d'activer le chiffrement...

Pour déchiffrer, votre interlocuteur devra utiliser le hash de votre clé publique (ici Cu//VyfaURgSwNYxWLuYXCZ0r9ZEP7HpwqsVaUpfPVN36wY=) et faire comme suit :

```bash
./kryptor -d -y Cu//VyfaURgSwNYxWLuYXCZ0r9ZEP7HpwqsVaUpfPVN36wY= text.txt.bin
```
```brainfuck
Enter your private key password:

Decrypting private key...

Decrypting "text.txt.bin" => "text.txt"...

Successfully decrypted: 1/1
```

## CAS 3 : Vous souhaitez signer votre message

Nous sommes dans un article lié au chiffrement, mais exceptionnellement nous parlerons de signature : Krypto vous permet sur le même principe que le chiffrement de pouvoir générer une clé spécifique pour les signatures. Généralement nous signons lorsque nous devons envoyer des données principalement lié aux courriels, mais il est tout à fait possible de signer vos fichiers ou répertoires afin d'authentifier, ou bien vous êtes développeur et vous souhaiterez signer vos commits par exemple... Voici la procédure :

```bash
./kryptor -g
```
```brainfuck
Please select a key pair type (type 1 or 2):
1) Encryption
2) Signing
2

Enter a password (leave empty for a random passphrase):

Retype password:

Deriving encryption key from password...

Public key: Ed//ygDw0INhNEruvwjrJpd9yVEhn/BCRYoI+Uu1GGk1XKA=
Public key file: "/home/user/.kryptor/signing.public"

Private key file: "/home/user/.kryptor/signing.private" - Keep this secret!

IMPORTANT: Please back up these files to external storage (e.g. memory sticks).
```
```bash
[user@ordinateur:~ $] ./kryptor -s mon-fichier.txt
```
```brainfuck
Enter your private key password:

Decrypting private key...

Signing "texte.txt" => "texte.txt.signature"...

Successfully signed: 1/1
```

Bien entendu encore ici, stockez votre clé privée en sécurité !

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo*