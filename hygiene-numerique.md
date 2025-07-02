---
title: Améliorez votre hygiène numérique
description: Reprenez le contrôle de votre vie numérique et de vos données...
published: true
date: 2025-07-02T16:10:28.134Z
tags: web, internet, privacy, vie privée, pgp, gpg, numérique, informatique, données, anonymat, sécurité, réseau, vpn, tor, proxy, email, courriel, virus, malware, darknet, mot de passe, authentification, clé, cyber
editor: markdown
dateCreated: 2022-11-27T12:39:05.392Z
---

# Les concepts clés

## Les liens hypertextes (URL)

![](/images/phishing_ex.png =600x){.align-center}
***Extrait d'un courriel pour une campagne de hameçonnage***

Ci-dessus un exemple d'un courriel, qui attire notre attention. Ce courriel vous demande d'agir rapidement et vous propose de cliquer sur un lien. Il s'agit en réalité d'un type d'attaque par hameçonnage : au clique sur celui-ci, vous dirigera vers une page internet afin de rentrer des identifiants/mot de passe ou bien des coordonnées bancaires, ou d'autres données personnelles critiques. Bien souvent, ces SPAM sont bien mieux faits que cet exemple (Si vous regardez de plus près, vous vous apercevrez des fautes d'orthographe dans le corps de texte, qui trahissent les emails issus de campagnes de hameçonnage (détaillé ci-après)), mais vous avez l'idée !

**Il est donc PRIMORDIAL de ne jamais cliquer sur des liens (hypertextes) contenus dans les courriels et de toujours vérifier l'information.** Si ce lien vous amène sur un écran où vous devez rentrer vos identifiants, il est préférable de se méfier et de fermer ce site. Puis de vous connecter en allant directement vous-même sur le site en question.

De nos jours, il est très facile de copier une page des sites bien connus (Facebook, Decathlon...) pour récupérer vos données d’authentification ou vos données bancaires (hameçonnage ou "phishing attack").  

*_Exemple_ : vous recevez un courriel (visiblement très professionnel, aucune faute...) de Decathlon vous annonçant que vous pouvez participer à un jeu vous permettant de gagner un bon d'achat exceptionnel pour le dernier vélo électrique à la mode. Vous cliquez sur le lien, qui vous amène sur une page Decathlon tout à fait légitime, puis vous jouez, vous gagnez et enfin on vous demande de rentrer vos coordonnées bancaires, arguant qu’il leur faut faire un retrait de 2 euros afin de faire une empreinte de votre carte pour payer les frais de transports, mais que tout vous sera remboursé par la suite. Le piège s’est refermé, vous renseignez les données. Puis vous voyez un remboursement de 2 euros quelques jours suivants, ce qui vous rassure ; en revanche, les jours qui suivent vous vous apercevez que des retraits de 200 euros, 500 euros ont été effectués. Vous faites opposition mais bien sûr il est trop tard puisque les cybercriminels ont déjà récolté l’argent...*

Cette histoire est tirée d’une réelle campagne de phishing !

> **Ne sous-estimez JAMAIS les cybercriminels, c'est ainsi qu'ils trouvent leur motivation. Ne sur-estimez jamais la façon dont vous pensez pouvoir réagir. Cela peut arriver à n’importe qui, et encore plus à celui qui est trop confiant.**
{.is-warning}


## Les fichiers et leur intégrité

Ceci est un rappel, mais il est important d'éviter de télécharger des **exécutables** directement ou dans des archives, que ce soit pour Linux (via des fichiers ELF ou "Executable Linkable File") ou Windows (via des fichiers à l'extension .exe ou .msi). Dans le cas d'un téléchargement depuis un site internet, plutôt que depuis un centre logiciel, il est recommandé de télécharger depuis le site officiel de l'éditeur logiciel dudit programme.

*_Astuce toute simple_ : depuis son moteur de recherche préféré, taper wikipedia + nom_du_programme_à_télécharger (ou bien demander conseil sur une communauté, comme celle-ci). Depuis l'article Wikipedia, retrouver le lien vers l'[URL](/glossaire#url) de l'éditeur logiciel ; le but étant de télécharger un fichier authentique, en allant directement à la source.*

En prolongement et pour tous types de fichiers (.iso, .img, ...), vérifiez **TOUJOURS**, lorsque disponible, l'intégrité du fichier téléchargé. Cela se fait via une vérification de la "signature" ou de "la somme de contrôle" dudit fichier.

- **Voir l'article dédié à l'[intégrité](/intermediaire/integrite), ainsi que le tutoriel [associé](/tutoriels/verifier-integrite).**



# Définir son modèle de menaces

Tenter de protéger TOUTES ses informations personnelles, TOUT le temps, de TOUT le monde, peut s'avérer être une tâche ardue voire épuisante ! Pas de panique, la sécurité numérique est un long '''voyage '''qui doit s'adapter à votre profil et évoluer selon vos utilisations. La sécurité numérique n'est pas limitée aux seuls outils ou services que vous utilisez, elle commence par l'anticipation et la compréhension des menaces existantes et de la façon de s'en prémunir. Par définition :

> Un modèle de menaces (ou "Threat Model") correspond à l'identification et la compréhension des menaces les plus probables qui peuvent vous impacter. Ainsi, vous serez plus à même de mettre en place les contre-mesures adéquates.

J'en conviens, c'est une définition un peu "barbare", mais tentons d'y voir plus clair sur ce sujet intéressant. En sécurité numérique :
-   une menace se définit par un événement possible et redouté qui saperait vos efforts dans la protection de vos données ;
-   les contre-mesures sont toutes les actions entreprises afin d'écarter ces menaces.

Nous pouvons donc en déduire que grâce à l'identification des menaces que vous rencontrerez potentiellement, il sera possible d'y appliquer des actions récurrentes ou ponctuelles (grâce à des outils ou manuellement) sur votre vie numérique. Mais avant tout cela, tentons de comprendre la finalité...

## Sécurité, vie privée et anonymat

Trois termes extrêmement importants lorsque nous cherchons à comprendre comment nous sommes interconnectés et comment les choses se déroulent dans notre sphère numérique ; trois concepts différents, qui se rejoignent pourtant, et dont voici une définition :
-   La **vie privée**, ou appelée chez nos amis anglo-saxon « Privacy », se rapporte à tout ce qui a trait au contrôle de nos informations personnelles.
-   La **sécurité**, ou « Security », se réfère à la protection de ces informations personnelles, _globalement_ pour se prémunir d'accès non autorisés.
-   L’**anonymat**, ou « Anonymity », représente le fait de cacher l’auteur d’un échange et des informations.
  (*À ne pas confondre avec pseudonymat qui est l'utilisation d'une identité fictive*).

**_Pour illustrer_** :
  - Une méthode pour protéger sa vie privée pourrait être une fonction anti-traceurs dans un navigateur (uBlock), 
  - Une méthode pour assurer un niveau de sécurité pourrait être un mot de passe, 
  - Et enfin l'utilisation de Tor pourrait être un outil afin d'obtenir un *relatif* anonymat.
{.grid-list}

> Souvent, les personnes confondent Vie Privée et Sécurité ; la frontière est mince, mais ces notions renvoient tout de même à des aspects différents de la protection des données : la protection de notre vie privée concerne ce que nous **sommes prêts à donner** comme informations sur nous aux autres personnes, tandis que la sécurité concerne ce que nous allons **entreprendre pour rendre inaccessibles** nos informations ; deux aspects différents, deux objectifs bien distincts...
{.is-info}

Afin d’atteindre un certain degré de sécurité, de vie privée et d’anonymat, il est essentiel aujourd’hui de se pencher véritablement sur nos activités numériques. Voyons ces 3 aspects comme 3 cercles qui se chevauchent, les centres de ces 3 cercles représentant le degré maximal de protection :

```diagram
PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB2ZXJzaW9uPSIxLjEiIHdpZHRoPSI1MDFweCIgaGVpZ2h0PSI0NzZweCIgdmlld0JveD0iLTAuNSAtMC41IDUwMSA0NzYiIGNvbnRlbnQ9IiZsdDtteGZpbGUgaG9zdD0mcXVvdDtlbWJlZC5kaWFncmFtcy5uZXQmcXVvdDsgbW9kaWZpZWQ9JnF1b3Q7MjAyMi0xMi0wMlQxMjozMzowNS43ODRaJnF1b3Q7IGFnZW50PSZxdW90OzUuMCAoWDExOyBMaW51eCB4ODZfNjQpIEFwcGxlV2ViS2l0LzUzNy4zNiAoS0hUTUwsIGxpa2UgR2Vja28pIENocm9tZS8xMDcuMC4wLjAgU2FmYXJpLzUzNy4zNiZxdW90OyBldGFnPSZxdW90O3hmZGlEemVsbFZTOWQxaVlDWkhfJnF1b3Q7IHZlcnNpb249JnF1b3Q7MjAuNi4wJnF1b3Q7IHR5cGU9JnF1b3Q7ZW1iZWQmcXVvdDsmZ3Q7Jmx0O2RpYWdyYW0gaWQ9JnF1b3Q7TVphSFhOamh0d1Z1anpwZXkzMnAmcXVvdDsgbmFtZT0mcXVvdDtQYWdlLTEmcXVvdDsmZ3Q7N1poYmI1c3dGTWMvRFkrVHdGeENIbk5oWGFUMW9xYnJ0RWNERGxnMW1EbE9rKzdUN3hoTXVGYWQxTFNacWo1aC84K3hzYy8vWjZQRXNCZlo0VUxnSXIza01XRUdNdU9EWVM4TmhDeGsrdkJReWxPbFRDeXpFaEpCWTUzVUNHdjZoMml4VHR2Um1HdzdpWkp6Sm1uUkZTT2U1eVNTSFEwTHdmZmR0QTFuM2JjV09DRURZUjFoTmxSLzBsaW1sZXFqU2FOL0l6Uko2emRiM3JTS1pMaE8xanZacGpqbSs1WmtCNGE5RUp6THFwVWRGb1NwNHRWMXFjWjlmU1o2WEpnZ3VmeVhBYWdhOElqWlR1L05RQjZEb2ZNTmh4bGdnZkpKNzlyN3ZlTjE0TXUyOUdRR0NjZ3B3TmQ1RTRkV29wL2xSR0V0cklQRmo5dlZYVkFIWUZWaFB4bTA2c1cxakRwclFMQjZNQms2ODMxS0pWa1hPRktSUFhBR1dpb3pCajBMbW5oYlZNNXY2SUhFYXRtVXNRVm5YSlFUMmJGTC9OZ0JmU3NGZnlDdGlJOUMyL01nd21GeUtoV2lFMVBOeUdpU1F5ZUMwaExJblQ4U0lTbEFNZE9Ca0V2Sk16V2xHcGduYzkxZk9tWWpmaWNidFNyenVMbTJWOW8rTlRFNXRDVHQzUVhoR1pIaUNWTHFxS2M1MGdjSitXN1YzemRZMnFiT1NWdElIa1dzajBKeW5MdWhCUm9hbUhGNDdHZmhHZmo2YXBydVY4Q05lWE83dWcrQ1oyRVo0K3F0QUNJV0lEUVpBMmpxVFd3OEFsQ2ZGOG1MaG9zNzFhbElPUUVYeU8xeVlkVTM1N3R3NGJ3akY3T3I2NnRmbDdPNy80S0pqUitSS0Jwakl2UmR4elU3VEhnbnVGUk9nSXA5MWl2RUhVR2w1dzU4SWd2VjVDSTQrbFFRUWVGZHFtSkw3ZDVOSTcxa1k0aWpoMFR3WFI1Zjd5U2pPZEg2S2FwcGRxdnBvR0UxMFVneDBRbHE2UTFxYWFuVnVJT0t3bDVrdHlLQ3dGSERZWmxRWXJtVHZEcDhGZmN2VVpyUk9HYWxNWnptc3R5RE96ZmNaZStJNUZ6VnVuYzZ0Rmo2b1E3VnFiNk5xQWUyTTNJSHVxTmN2OTZLeVFmRDJqMGoxdjRuMW0wcm5ETmlQZjFnV052VDNyZlBIZGJ5cmJDdWJmdmtXbnZoVEx0ZTJHL0dOWFNiWDlobHJQVS9oUjM4QlE9PSZsdDsvZGlhZ3JhbSZndDsmbHQ7L214ZmlsZSZndDsiPjxkZWZzLz48Zz48ZWxsaXBzZSBjeD0iMTUwIiBjeT0iMzI1IiByeD0iMTUwIiByeT0iMTUwIiBmaWxsLW9wYWNpdHk9IjAuNyIgZmlsbD0iI2Q1ZThkNCIgc3Ryb2tlPSIjODJiMzY2IiBzdHJva2Utb3BhY2l0eT0iMC43IiBwb2ludGVyLWV2ZW50cz0iYWxsIi8+PGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTAuNSAtMC41KSI+PHN3aXRjaD48Zm9yZWlnbk9iamVjdCBwb2ludGVyLWV2ZW50cz0ibm9uZSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5IiBzdHlsZT0ib3ZlcmZsb3c6IHZpc2libGU7IHRleHQtYWxpZ246IGxlZnQ7Ij48ZGl2IHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzdHlsZT0iZGlzcGxheTogZmxleDsgYWxpZ24taXRlbXM6IHVuc2FmZSBmbGV4LWVuZDsganVzdGlmeS1jb250ZW50OiB1bnNhZmUgY2VudGVyOyB3aWR0aDogMjk4cHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogNDMycHg7IG1hcmdpbi1sZWZ0OiAxcHg7Ij48ZGl2IGRhdGEtZHJhd2lvLWNvbG9ycz0iY29sb3I6IHJnYigwLCAwLCAwKTsgIiBzdHlsZT0iYm94LXNpemluZzogYm9yZGVyLWJveDsgZm9udC1zaXplOiAwcHg7IHRleHQtYWxpZ246IGNlbnRlcjsiPjxkaXYgc3R5bGU9ImRpc3BsYXk6IGlubGluZS1ibG9jazsgZm9udC1zaXplOiAxMnB4OyBmb250LWZhbWlseTogSGVsdmV0aWNhOyBjb2xvcjogcmdiKDAsIDAsIDApOyBsaW5lLWhlaWdodDogMS4yOyBwb2ludGVyLWV2ZW50czogYWxsOyB3aGl0ZS1zcGFjZTogbm9ybWFsOyBvdmVyZmxvdy13cmFwOiBub3JtYWw7Ij48Zm9udCBzdHlsZT0iZm9udC1zaXplOiAyNHB4OyI+PGI+U0VDVVJJVEU8L2I+PC9mb250PjwvZGl2PjwvZGl2PjwvZGl2PjwvZm9yZWlnbk9iamVjdD48dGV4dCB4PSIxNTAiIHk9IjQzMiIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPlNFQ1VSSVRFPC90ZXh0Pjwvc3dpdGNoPjwvZz48ZWxsaXBzZSBjeD0iMjQwIiBjeT0iMTUwIiByeD0iMTUwIiByeT0iMTUwIiBmaWxsLW9wYWNpdHk9IjAuNyIgZmlsbD0iI2UxZDVlNyIgc3Ryb2tlPSIjOTY3M2E2IiBzdHJva2Utb3BhY2l0eT0iMC43IiBwb2ludGVyLWV2ZW50cz0iYWxsIi8+PGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTAuNSAtMC41KSI+PHN3aXRjaD48Zm9yZWlnbk9iamVjdCBwb2ludGVyLWV2ZW50cz0ibm9uZSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5IiBzdHlsZT0ib3ZlcmZsb3c6IHZpc2libGU7IHRleHQtYWxpZ246IGxlZnQ7Ij48ZGl2IHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzdHlsZT0iZGlzcGxheTogZmxleDsgYWxpZ24taXRlbXM6IHVuc2FmZSBmbGV4LXN0YXJ0OyBqdXN0aWZ5LWNvbnRlbnQ6IHVuc2FmZSBjZW50ZXI7IHdpZHRoOiAyOThweDsgaGVpZ2h0OiAxcHg7IHBhZGRpbmctdG9wOiA0N3B4OyBtYXJnaW4tbGVmdDogOTFweDsiPjxkaXYgZGF0YS1kcmF3aW8tY29sb3JzPSJjb2xvcjogcmdiKDAsIDAsIDApOyAiIHN0eWxlPSJib3gtc2l6aW5nOiBib3JkZXItYm94OyBmb250LXNpemU6IDBweDsgdGV4dC1hbGlnbjogY2VudGVyOyI+PGRpdiBzdHlsZT0iZGlzcGxheTogaW5saW5lLWJsb2NrOyBmb250LXNpemU6IDEycHg7IGZvbnQtZmFtaWx5OiBIZWx2ZXRpY2E7IGNvbG9yOiByZ2IoMCwgMCwgMCk7IGxpbmUtaGVpZ2h0OiAxLjI7IHBvaW50ZXItZXZlbnRzOiBhbGw7IHdoaXRlLXNwYWNlOiBub3JtYWw7IG92ZXJmbG93LXdyYXA6IG5vcm1hbDsiPjxiPjxmb250IHN0eWxlPSJmb250LXNpemU6IDI0cHg7Ij5WSUUgUFJJVkVFPC9mb250PjwvYj48L2Rpdj48L2Rpdj48L2Rpdj48L2ZvcmVpZ25PYmplY3Q+PHRleHQgeD0iMjQwIiB5PSI1OSIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPlZJRSBQUklWRUU8L3RleHQ+PC9zd2l0Y2g+PC9nPjxlbGxpcHNlIGN4PSIzNTAiIGN5PSIzMjUiIHJ4PSIxNTAiIHJ5PSIxNTAiIGZpbGwtb3BhY2l0eT0iMC42IiBmaWxsPSIjZjhjZWNjIiBzdHJva2U9IiNiODU0NTAiIHN0cm9rZS1vcGFjaXR5PSIwLjYiIHBvaW50ZXItZXZlbnRzPSJhbGwiLz48ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMC41IC0wLjUpIj48c3dpdGNoPjxmb3JlaWduT2JqZWN0IHBvaW50ZXItZXZlbnRzPSJub25lIiB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiByZXF1aXJlZEZlYXR1cmVzPSJodHRwOi8vd3d3LnczLm9yZy9UUi9TVkcxMS9mZWF0dXJlI0V4dGVuc2liaWxpdHkiIHN0eWxlPSJvdmVyZmxvdzogdmlzaWJsZTsgdGV4dC1hbGlnbjogbGVmdDsiPjxkaXYgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGh0bWwiIHN0eWxlPSJkaXNwbGF5OiBmbGV4OyBhbGlnbi1pdGVtczogdW5zYWZlIGZsZXgtZW5kOyBqdXN0aWZ5LWNvbnRlbnQ6IHVuc2FmZSBjZW50ZXI7IHdpZHRoOiAyOThweDsgaGVpZ2h0OiAxcHg7IHBhZGRpbmctdG9wOiA0MzJweDsgbWFyZ2luLWxlZnQ6IDIwMXB4OyI+PGRpdiBkYXRhLWRyYXdpby1jb2xvcnM9ImNvbG9yOiByZ2IoMCwgMCwgMCk7ICIgc3R5bGU9ImJveC1zaXppbmc6IGJvcmRlci1ib3g7IGZvbnQtc2l6ZTogMHB4OyB0ZXh0LWFsaWduOiBjZW50ZXI7Ij48ZGl2IHN0eWxlPSJkaXNwbGF5OiBpbmxpbmUtYmxvY2s7IGZvbnQtc2l6ZTogMTJweDsgZm9udC1mYW1pbHk6IEhlbHZldGljYTsgY29sb3I6IHJnYigwLCAwLCAwKTsgbGluZS1oZWlnaHQ6IDEuMjsgcG9pbnRlci1ldmVudHM6IGFsbDsgd2hpdGUtc3BhY2U6IG5vcm1hbDsgb3ZlcmZsb3ctd3JhcDogbm9ybWFsOyI+PGI+PGZvbnQgc3R5bGU9ImZvbnQtc2l6ZTogMjRweDsiPkFOT05ZTUFUPC9mb250PjwvYj48L2Rpdj48L2Rpdj48L2Rpdj48L2ZvcmVpZ25PYmplY3Q+PHRleHQgeD0iMzUwIiB5PSI0MzIiIGZpbGw9InJnYigwLCAwLCAwKSIgZm9udC1mYW1pbHk9IkhlbHZldGljYSIgZm9udC1zaXplPSIxMnB4IiB0ZXh0LWFuY2hvcj0ibWlkZGxlIj5BTk9OWU1BVDwvdGV4dD48L3N3aXRjaD48L2c+PGVsbGlwc2UgY3g9IjE1MCIgY3k9IjMyNSIgcng9IjEwIiByeT0iMTAiIGZpbGw9InJnYigyNTUsIDI1NSwgMjU1KSIgc3Ryb2tlPSJyZ2IoMCwgMCwgMCkiIHBvaW50ZXItZXZlbnRzPSJhbGwiLz48cGF0aCBkPSJNIDE0MCAzMjUgTCAxNjAgMzI1IiBmaWxsPSJub25lIiBzdHJva2U9InJnYigwLCAwLCAwKSIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiBwb2ludGVyLWV2ZW50cz0iYWxsIi8+PHBhdGggZD0iTSAxNTAgMzE1IEwgMTUwIDMzNSIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJyZ2IoMCwgMCwgMCkiIHN0cm9rZS1taXRlcmxpbWl0PSIxMCIgcG9pbnRlci1ldmVudHM9ImFsbCIvPjxyZWN0IHg9IjEwMCIgeT0iMzAwIiB3aWR0aD0iNTAiIGhlaWdodD0iMzAiIGZpbGw9Im5vbmUiIHN0cm9rZT0ibm9uZSIgcG9pbnRlci1ldmVudHM9ImFsbCIvPjxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKC0wLjUgLTAuNSkiPjxzd2l0Y2g+PGZvcmVpZ25PYmplY3QgcG9pbnRlci1ldmVudHM9Im5vbmUiIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIHJlcXVpcmVkRmVhdHVyZXM9Imh0dHA6Ly93d3cudzMub3JnL1RSL1NWRzExL2ZlYXR1cmUjRXh0ZW5zaWJpbGl0eSIgc3R5bGU9Im92ZXJmbG93OiB2aXNpYmxlOyB0ZXh0LWFsaWduOiBsZWZ0OyI+PGRpdiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94aHRtbCIgc3R5bGU9ImRpc3BsYXk6IGZsZXg7IGFsaWduLWl0ZW1zOiB1bnNhZmUgY2VudGVyOyBqdXN0aWZ5LWNvbnRlbnQ6IHVuc2FmZSBjZW50ZXI7IHdpZHRoOiAxcHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogMzE1cHg7IG1hcmdpbi1sZWZ0OiAxMjVweDsiPjxkaXYgZGF0YS1kcmF3aW8tY29sb3JzPSJjb2xvcjogcmdiKDAsIDAsIDApOyAiIHN0eWxlPSJib3gtc2l6aW5nOiBib3JkZXItYm94OyBmb250LXNpemU6IDBweDsgdGV4dC1hbGlnbjogY2VudGVyOyI+PGRpdiBzdHlsZT0iZGlzcGxheTogaW5saW5lLWJsb2NrOyBmb250LXNpemU6IDEycHg7IGZvbnQtZmFtaWx5OiBIZWx2ZXRpY2E7IGNvbG9yOiByZ2IoMCwgMCwgMCk7IGxpbmUtaGVpZ2h0OiAxLjI7IHBvaW50ZXItZXZlbnRzOiBhbGw7IHdoaXRlLXNwYWNlOiBub3dyYXA7Ij4xMDAlPC9kaXY+PC9kaXY+PC9kaXY+PC9mb3JlaWduT2JqZWN0Pjx0ZXh0IHg9IjEyNSIgeT0iMzE5IiBmaWxsPSJyZ2IoMCwgMCwgMCkiIGZvbnQtZmFtaWx5PSJIZWx2ZXRpY2EiIGZvbnQtc2l6ZT0iMTJweCIgdGV4dC1hbmNob3I9Im1pZGRsZSI+MTAwJTwvdGV4dD48L3N3aXRjaD48L2c+PGVsbGlwc2UgY3g9IjM1MCIgY3k9IjMyNSIgcng9IjEwIiByeT0iMTAiIGZpbGw9InJnYigyNTUsIDI1NSwgMjU1KSIgc3Ryb2tlPSJyZ2IoMCwgMCwgMCkiIHBvaW50ZXItZXZlbnRzPSJhbGwiLz48cGF0aCBkPSJNIDM0MCAzMjUgTCAzNjAgMzI1IiBmaWxsPSJub25lIiBzdHJva2U9InJnYigwLCAwLCAwKSIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiBwb2ludGVyLWV2ZW50cz0iYWxsIi8+PHBhdGggZD0iTSAzNTAgMzE1IEwgMzUwIDMzNSIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJyZ2IoMCwgMCwgMCkiIHN0cm9rZS1taXRlcmxpbWl0PSIxMCIgcG9pbnRlci1ldmVudHM9ImFsbCIvPjxyZWN0IHg9IjMwMCIgeT0iMzAwIiB3aWR0aD0iNTAiIGhlaWdodD0iMzAiIGZpbGw9Im5vbmUiIHN0cm9rZT0ibm9uZSIgcG9pbnRlci1ldmVudHM9ImFsbCIvPjxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKC0wLjUgLTAuNSkiPjxzd2l0Y2g+PGZvcmVpZ25PYmplY3QgcG9pbnRlci1ldmVudHM9Im5vbmUiIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIHJlcXVpcmVkRmVhdHVyZXM9Imh0dHA6Ly93d3cudzMub3JnL1RSL1NWRzExL2ZlYXR1cmUjRXh0ZW5zaWJpbGl0eSIgc3R5bGU9Im92ZXJmbG93OiB2aXNpYmxlOyB0ZXh0LWFsaWduOiBsZWZ0OyI+PGRpdiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94aHRtbCIgc3R5bGU9ImRpc3BsYXk6IGZsZXg7IGFsaWduLWl0ZW1zOiB1bnNhZmUgY2VudGVyOyBqdXN0aWZ5LWNvbnRlbnQ6IHVuc2FmZSBjZW50ZXI7IHdpZHRoOiAxcHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogMzE1cHg7IG1hcmdpbi1sZWZ0OiAzMjVweDsiPjxkaXYgZGF0YS1kcmF3aW8tY29sb3JzPSJjb2xvcjogcmdiKDAsIDAsIDApOyAiIHN0eWxlPSJib3gtc2l6aW5nOiBib3JkZXItYm94OyBmb250LXNpemU6IDBweDsgdGV4dC1hbGlnbjogY2VudGVyOyI+PGRpdiBzdHlsZT0iZGlzcGxheTogaW5saW5lLWJsb2NrOyBmb250LXNpemU6IDEycHg7IGZvbnQtZmFtaWx5OiBIZWx2ZXRpY2E7IGNvbG9yOiByZ2IoMCwgMCwgMCk7IGxpbmUtaGVpZ2h0OiAxLjI7IHBvaW50ZXItZXZlbnRzOiBhbGw7IHdoaXRlLXNwYWNlOiBub3dyYXA7Ij4xMDAlPC9kaXY+PC9kaXY+PC9kaXY+PC9mb3JlaWduT2JqZWN0Pjx0ZXh0IHg9IjMyNSIgeT0iMzE5IiBmaWxsPSJyZ2IoMCwgMCwgMCkiIGZvbnQtZmFtaWx5PSJIZWx2ZXRpY2EiIGZvbnQtc2l6ZT0iMTJweCIgdGV4dC1hbmNob3I9Im1pZGRsZSI+MTAwJTwvdGV4dD48L3N3aXRjaD48L2c+PGVsbGlwc2UgY3g9IjI0MCIgY3k9IjE1MCIgcng9IjEwIiByeT0iMTAiIGZpbGw9InJnYigyNTUsIDI1NSwgMjU1KSIgc3Ryb2tlPSJyZ2IoMCwgMCwgMCkiIHBvaW50ZXItZXZlbnRzPSJhbGwiLz48cGF0aCBkPSJNIDIzMCAxNTAgTCAyNTAgMTUwIiBmaWxsPSJub25lIiBzdHJva2U9InJnYigwLCAwLCAwKSIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiBwb2ludGVyLWV2ZW50cz0iYWxsIi8+PHBhdGggZD0iTSAyNDAgMTQwIEwgMjQwIDE2MCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJyZ2IoMCwgMCwgMCkiIHN0cm9rZS1taXRlcmxpbWl0PSIxMCIgcG9pbnRlci1ldmVudHM9ImFsbCIvPjxyZWN0IHg9IjE4OSIgeT0iMTIwIiB3aWR0aD0iNTAiIGhlaWdodD0iMzAiIGZpbGw9Im5vbmUiIHN0cm9rZT0ibm9uZSIgcG9pbnRlci1ldmVudHM9ImFsbCIvPjxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKC0wLjUgLTAuNSkiPjxzd2l0Y2g+PGZvcmVpZ25PYmplY3QgcG9pbnRlci1ldmVudHM9Im5vbmUiIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIHJlcXVpcmVkRmVhdHVyZXM9Imh0dHA6Ly93d3cudzMub3JnL1RSL1NWRzExL2ZlYXR1cmUjRXh0ZW5zaWJpbGl0eSIgc3R5bGU9Im92ZXJmbG93OiB2aXNpYmxlOyB0ZXh0LWFsaWduOiBsZWZ0OyI+PGRpdiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94aHRtbCIgc3R5bGU9ImRpc3BsYXk6IGZsZXg7IGFsaWduLWl0ZW1zOiB1bnNhZmUgY2VudGVyOyBqdXN0aWZ5LWNvbnRlbnQ6IHVuc2FmZSBjZW50ZXI7IHdpZHRoOiAxcHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogMTM1cHg7IG1hcmdpbi1sZWZ0OiAyMTRweDsiPjxkaXYgZGF0YS1kcmF3aW8tY29sb3JzPSJjb2xvcjogcmdiKDAsIDAsIDApOyAiIHN0eWxlPSJib3gtc2l6aW5nOiBib3JkZXItYm94OyBmb250LXNpemU6IDBweDsgdGV4dC1hbGlnbjogY2VudGVyOyI+PGRpdiBzdHlsZT0iZGlzcGxheTogaW5saW5lLWJsb2NrOyBmb250LXNpemU6IDEycHg7IGZvbnQtZmFtaWx5OiBIZWx2ZXRpY2E7IGNvbG9yOiByZ2IoMCwgMCwgMCk7IGxpbmUtaGVpZ2h0OiAxLjI7IHBvaW50ZXItZXZlbnRzOiBhbGw7IHdoaXRlLXNwYWNlOiBub3dyYXA7Ij4xMDAlPC9kaXY+PC9kaXY+PC9kaXY+PC9mb3JlaWduT2JqZWN0Pjx0ZXh0IHg9IjIxNCIgeT0iMTM5IiBmaWxsPSJyZ2IoMCwgMCwgMCkiIGZvbnQtZmFtaWx5PSJIZWx2ZXRpY2EiIGZvbnQtc2l6ZT0iMTJweCIgdGV4dC1hbmNob3I9Im1pZGRsZSI+MTAwJTwvdGV4dD48L3N3aXRjaD48L2c+PC9nPjxzd2l0Y2g+PGcgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5Ii8+PGEgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMCwtNSkiIHhsaW5rOmhyZWY9Imh0dHBzOi8vd3d3LmRpYWdyYW1zLm5ldC9kb2MvZmFxL3N2Zy1leHBvcnQtdGV4dC1wcm9ibGVtcyIgdGFyZ2V0PSJfYmxhbmsiPjx0ZXh0IHRleHQtYW5jaG9yPSJtaWRkbGUiIGZvbnQtc2l6ZT0iMTBweCIgeD0iNTAlIiB5PSIxMDAlIj5UZXh0IGlzIG5vdCBTVkcgLSBjYW5ub3QgZGlzcGxheTwvdGV4dD48L2E+PC9zd2l0Y2g+PC9zdmc+
```

**Oui, alors on ne se moque pas : je ne suis pas webdesigner :D !**

---
Schématiquement, nous pouvons nous apercevoir qu'il est **extrêmement difficile**, si ce n'est **impossible**, de se placer à l'interjection des 3 cercles de protection en espérant le 100% sur chaque pan de protection.

De fait, multiplier les mécanismes pro-vie-privée, multiplier les équipements ou applications de sécurité (pare-feu, IDS/IPS, honeypot, anti-malware, proxy, host IDS, etc.) et autres procédés d’anonymat ne signifie pas automatiquement une plus grande protection des données, de vie privée et une amélioration de l'anonymat. Au contraire, parfois, complexifier votre approche est le meilleur moyen pour faire grossir la liste des potentielles failles de sécurité ou vulnérabilités. On appelle cela **augmenter sa surface d'attaque** : plus vous avez d'équipements, de services ou de logiciels, plus le nombre de vulnérabilités augmente, donc plus la probabilité d'avoir une faille exploitable augmente également.

Souvent vous souhaitez utiliser l'outil le plus sécurisé et à la mode, néanmoins vous n'êtes pas prêt à accepter le côté austère et compliqué de l'outil, ni les conditions d'utilisation drastiques ! En d'autres termes, si votre objectif est d'utiliser les outils les plus sécurisés du moment, vous devrez sacrifier énormément sur le côté simplicité et facilité d'utilisation au quotidien. Et quand bien même, rien ne sera totalement sécurisé...

> L'objectif d'atteindre le 100% du triptique est impossible, l'idée est donc d'établir des **compromis** entre sécurité, vie privée, anonymat, et facilité d'utilisation. Voilà pourquoi établir son modèle de menaces peut nous aider à identifier les outils et les procédés les plus adéquats pour notre profil de sécurité.
{.is-success}


Vous allez donc devoir porter votre attention sur les menaces les plus probables que vous pourriez rencontrer dans votre vie numérique de tous les jours et celles qui vous semblent les plus importantes à vos yeux (attention ici à ne pas non plus entrer dans une paranoïa excessive !).

## Établir son modèle de menaces

Établir son modèle de menaces n’est pas aisé, mais nous allons tenter de simplifier ensemble cette procédure afin de vous y aider...

### Contre qui ?

La première question à se poser sera : contre qui je souhaite me protéger ?

Évidemment ici, il est assez compliqué pour celui qui ne se tient pas informé du monde numérique de connaître et encore moins de comprendre les potentiels adversaires auxquels nous pourrions faire face. À tout le moins, nous pouvons nous dire qu'il existe des *hackers malveillants* qui peuvent en avoir après nos données, mais pour la suite, cela reste flou... Voici pourquoi nous vous avons fait une liste des adversaires auxquels nous pourrions faire face dans la vie de tous les jours :
1. Votre patron ou vos collègues
2. Votre ex ( :) ) ou votre famille
3. Des entreprises (type petite ou moyenne entreprise, moyens limités)
4. Des multinationales (type GAFAM, BATX, à fort pouvoir de collusion)
5. Des gouvernements (par le biais d'agences gouvernementales)
6. Des cybercriminels (que ce soient des [script-kiddies](https://fr.wikipedia.org/wiki/Script_kiddie), hackers malveillants seuls ou en groupe)

### Quelles données ?

Ensuite vient la question des éléments, que nous qualifions à suivre d' "items", que vous allez devoir protéger des yeux curieux et/ou malveillants. Faites une liste exhaustive des données qui, perdues ou volées, constitueraient un problème. Voici une liste d'éléments :
1. vos courriels
2. votre liste de contact
3. vos messageries instantanées
4. votre position géographique
5. vos fichiers (ou certains d'entre eux)
6. votre réseau local (wifi, routeurs, NAS, etc.)
7. vos métadonnées
8. vos stockages de données en ligne ("clouds")
9. votre ordinateur (ou vos partitions...)
10. vos photos/vidéos

### Analyse des risques

> Un "risque" se définit comme la probabilité qu'une **menace spécifique** ait un **impact** sur l'un de vos items.

Ouch, c'est un peu barbare encore une fois ! Voici la traduction par un exemple : votre opérateur téléphonique a la capacité d'accéder à des données vous concernant, mais cela dit le risque qu'ils viennent les dévoiler publiquement sur un réseau social afin de détruire votre réputation en ligne est plutôt faible, vous en conviendrez. Vous l'aurez sûrement compris, après avoir répondu aux deux premières questions, il est important de distinguer entre :
-  ce qui pourrait arriver 
-  et la probabilité que cela arrive réellement

> _Exemple_ : il existe la menace que votre immeuble puisse s'effondrer, mais le risque que cela arrive est plus important au Japon, car plus sujets aux tremblements de terre qu'en France !
{.is-info}

Évaluer le risque est également quelque chose de personnel et subjectif ; certains vont trouver des menaces inacceptables peu importe la probabilité d’occurrence, d'autres vont choisir d'ignorer les risques de type faible, car ils estimeront que la menace n'est pas un problème pour eux. L'idée est donc de lister quelles sont pour vous les menaces les plus importantes, celles que vous allez prendre en compte sérieusement, et celles au contraire trop rares ou trop compliquées à combattre pour s'inquiéter.

**C'est ici la question la plus complexe, elle doit coller au maximum à votre profil (vos menaces, vos usages...).**

Un très bon guide est déjà en ligne, sur [guide.boum.fr/choisir les réponses adaptées](https://guide.boum.org/hors-connexions-choisir-des-reponses-adaptees-introduction.html). Inutile de paraphraser donc ce guide qui est très complet du point de vue d'un utilisateur lambda. Ce guide doit être lu **avec recul** sans forcément parler d'outils pour le moment. L'idée est ici de comprendre la logique globale de la réflexion à avoir afin d'établir une stratégie : évaluer les menaces sera donc une analyse concernant les données à protéger, ainsi que sur le type d'acteurs qui pourraient concrètement en avoir après nos données. À partir de là, nous pouvons établir les moyens potentiels de nos adversaires, et donc créer notre propre stratégie de protection.

> **Les sections suivantes pourront justement vous donner un aperçu des possibilités et outils afin de mettre en place cette stratégie...**
{.is-success}


# Aller plus loin

Cette partie est dédiée à toute personne souhaitant aller plus loin dans la sécurisation de ses données, de ses communications, et son anonymat. Elle représente un aperçu des possibilités associées aux « bonnes pratiques ».

> Nous faisons ici état d’outils qui sont actuellement parfois en phase de recherche ou de tests. Il convient en priorité d’être à l’aise avec l’outil informatique en général, sur les aspects réseau, intrusion, vulnérabilités. Encore une fois, utiliser des outils que l’on ne maîtrise pas engendre une augmentation de sa surface d'attaque et donc potentiellement une diminution dans son niveau de sécurité ! Lisez les documentations...
{.is-danger}

## Stockage de données et "clouds" sécurisés

-   Sur un VPS (Virtual Private Server). Fournisseurs de confiance recommandables, en tout cas traitant a priori vos données avec respect :
        -   [Njal.la](https://njal.la/servers/)
        -   [1984.is](https://1984.hosting/product/vps/)
        -   [Privex.io](https://www.privex.io/)

## DVPN - Decentralized VPN

Pour ceux qui souhaitent utiliser pleinement les capacités du web 3.0 (nous ne rentrons pas dans les détails du web3 dans cet article), l’utilisation d’un « decentralized VPN » (VPN décentralisé ou dVPN) peut être envisagé. En somme, il s’agit d’utiliser la [blockchain](/glossaire#blockchain) afin de fournir un service VPN, dans lequel vous êtes partie prenante ; en effet, l'accès aux réseaux décentralisés de ces outils nécessitera une contrepartie :
- soit moyennant des micro-paiements en cryptomonnaie, 
- soit en hébergeant des serveurs.

**<span class="red-text">Néanmoins, ce mécanisme en est encore à ses balbutiements et nous n’avons pas assez de recul. Qui plus est, vous devrez comprendre le fonctionnement des cryptomonnaies et les risques inhérents.</span>**

Si vous êtes tout de même intéressé(e), voici quelques réseaux dont les communautés sont actives :
-   Sentinel : réseau de DVPN et son client Velocity VPN. Basé sur le [token](/glossaire#token) COSMOS.
-   Nym : Nym est une application basée sur un mixnet. Basé sur le token NYM.
-   Mysterium : et son client Mysterium VPN, le plus connu. Basé sur le token MYST, même s'ils acceptent d'autres tokens comme BTC, ETH, LTC.
-   Deeper DPN : Solutions hardware proposées à la vente pour la participation au réseau (attention plutôt onéreuses !) et afin d'accéder à leur réseau. Basé sur le token DPR.
-   Orchid : réseau de routage en oignon, et client VPN multi bonds. Basé sur le token OXT.

## I2P - L'autre Tor

Afin de bien comprendre en quoi I2P peut nous être utile, intéressons-nous tout d'abord aux applications d'internet et donc principalement aux _WEBs_.

Oui vous avez bien lu, j'ai ajouté un "s" à Web (nous vous renvoyons ici au [glossaire](/glossaire#web) pour la terminologie).

Pour rappel la différence entre internet et le Web :
-   Comme nous l'avons déjà défini, internet est un réseau (de réseaux)
-   Le Web, quant à lui, est l'outil d'inter-connexion des sites internet

Concernant le Web, il en existe donc plusieurs :
- Web visible (aussi appelé Web surfacique) : correspond à tout ce qui est indexé par les moteurs de recherche, et donc *_recherchable_* et accessible sur n'importe quel moteur de recherche. Par exemple : wikipedia.com ou encore orange.fr etc.
- Web invisible : représente toute la part des sites et pages internet qui ne sera jamais indexée par les moteurs de recherche et donc inaccessible publiquement.

Voici comment nous représentons généralement le Web :

![Le web profond](/images/deepweb.png =600x){.align-center}

Vous vous apercevez ici que le "Web visible" que vous connaissez bien ne représente qu'une petite partie du réseau mondial, c'est-à-dire entre 4 et 5% : "c'est le côté visible de l'iceberg" !

Nous y venons donc, le "Web invisible" est, quant à lui, également découpé en plusieurs parties. Il est communément admis de représenter ces parties ainsi :
- Le Web profond (Deep Web en anglais) : est une partie du Web invisible, pour ne pas dire une très grande partie (90%) qui gère tous les contenus non indexables de tous les sites internet : il peut s'agir par exemple de votre page d'accès à votre mandataire de courriel comme Gmail ou ProtonMail (imaginez que l'on puisse tous accéder à cette page et voir vos courriels !), ou bien des pages spécifiques liées à votre banque en ligne. Ou bien des contenus éducatifs d'universités qu'il ne faut pas rendre public forcément... Toutes ces pages ou sites ne seront jamais indexés et donc non *recherchables et non accessibles*. Ce qui se comprend...
- Les dark Webs (pas forcément de traduction française !) : ils contiennent toute la part cachée d'internet (environ 5-6%), également bien entendu non indexée par des moteurs de recherche habituels ; il y a du bon et du moins bon. 
  Le bon côté de ces dark Webs est le fait que certaines personnes puissent avoir la capacité de contourner les censures mises en place dans des pays autoritaires et donner un peu de liberté, et surtout d'anonymat. 
  De l'autre côté, le plus sombre, certaines zones des dark Webs sont en effet liées à la cyber-criminalité, où l'on peut retrouver des sites marchands illégaux et d'autres choses peu reluisantes.
  >"Tirer sur l'ambulance", en ne mettant en avant que l'aspect sombre du darkweb serait néanmoins contre-productif : ce serait omettre le rôle essentiel que les outils qui y sont liés (les "darknets", détaillés plus bas) jouent dans la société, étant donné que de nombreux journalistes et lanceurs d'alerte utilisent par exemple Tor. Notamment via l'outil Tails (voir : Devenez difficile à tracer/Parlons Technique/Anonymat avancé plus haut), ou via les messageries chiffrées. 
  Mettre un terme à ce genre de réseau signifierait un nouveau coup contre la liberté d'expression (ce serait par ailleurs difficile à réaliser, de par son aspect décentralisé). La décentralisation est l'amie des libertés publiques ; il faut donc savoir raison garder et ne pas réagir sur le coup de l'émotion. Par ailleurs, on n'est pas en mesure de savoir quelle part des "dark-markets" est réelle, et quelle part propose des services qui sont des arnaques plutôt que de véritables services criminels...
  Faire des dons, ou militer pour l'usage de Tor - ou tout autre darknet - reste un enjeu démocratique.
  
*Note : la terminologie dark Web peut varier de temps en temps, et il est parfois admis qu'il existe encore plus profond que le Dark Web !*

Mais quelle est la raison de tout ce blabla ?

Car afin d'accéder à ces dark Webs, il faut obligatoirement utiliser des services spécifiques, via des domaines de premiers niveaux spécifiques (allez relire la partie sur les DNS !) - non accessibles sur l'internet "classique" (la résolution DNS ne fonctionnera pas ici) - sur des réseaux spécifiques (vous vous souvenez, internet, réseau de réseaux...) appelés **DARKNETs**. Voici donc les services et réseaux les plus connus :
-   **Tor** : Eh oui, le plus connu de ces réseaux bien entendu, afin de surfer anonymement sur le web classique. Mais également accéder au darknet confidentiel Tor, avec des URL qui terminent en .onion (ce que l'on appelle des Top Level Domain - TLD)
-   **I2P** : tiens donc, le voilà ! Tout comme Tor, il permet de naviguer sur le web classique de façon anonyme. Mais il fournit également des services plus confidentiels de forum, courriel, etc sur le darknet I2P avec ses TLD en .i2p

> Bien entendu, ces deux darknets ont chacun leurs avantages et leurs inconvénients.
{.is-info}

D'autres darknets existent bien sûr. Ils ne sont pas forcément utilisés pour rendre la navigation anonyme sur l'internet classique, mais plus pour avoir accès à leur réseau, en dehors de l'espace surfacique du net. Parmi les plus connus, citons :
-   **Freenet**, l'un des plus robustes et plus recommandés des darknets.
-   **Lokinet, maintenant devenu Oxen** (sur lequel la messagerie décentralisée Session se base !)
-   **GNUnet**
-   **AnonNet**
-   **Riffle**

Et bien d'autres...

# The end... ?

Nous arrivons enfin à la fin de cet article, très dense... 
En espérant que vous n'avez pas trop mal à la tête !

### Ce qu'il faut retenir

La complexité des mécanismes en jeu, dans la protection de ses données, poussent la plupart des personnes à abandonner leur protection ou à donner mandat à un/des tiers afin d’assurer cette protection. 

***Ceci doit être aujourd'hui reconsidéré...***

S'il ne devait y rester qu'un leitmotiv à se remémorer tous les matins en se brossant les dents :

-   Chiffrement de bout en bout (E2EE) partout,
-   Aucune confiance à aucun service extérieur,
-   Pseudonymat au maximum,
-   Contrôle perpétuel de ses données,
-   Mise à jour régulière de votre modèle de menaces.
  
En tout cas, bravo ! Nous avons passé le plus dur, en faisant un tour d'horizon qui se veut le plus exhaustif, tout en étant le plus vulgarisé possible. Nous sommes conscients que cette débauche d'informations nouvelles ne peut pas être retenue et assimilée en une seule fois. C'est pourquoi, nous vous invitons à passer du _pourquoi_ au _comment_ en vous rendant sur toutes les autres pages du wiki... Vous allez le voir, en faisant les choses, on passe rapidement d'un aspect théorique qui peut paraître complexe, à des nouvelles habitudes qui deviennent des automatismes, ancrées dans notre quotidien.

> **Il est essentiel aujourd'hui de reprendre la main sur son espace numérique et sur la manière dont nous utilisons les outils numériques mis à notre disposition.**
{.is-warning}

A ce titre, il est important de garder en tête qu'aucun mécanisme ni aucune technologie ne nous assurera une sécurité optimale de l'information, tout en assurant une vie privée et un anonymat à 100%. Ces aspects dépendent aussi, avant tout, de nous-mêmes et de l'hygiène numérique que nous adoptons.

Pour conclure, nous avons en début d'article mentionné que la protection de notre sphère numérique était un voyage et non une destination ; si tout ce que vous avez fait jusqu'alors ne correspond pas aux précédentes sections, ne vous blâmez pas ! L'important est d'y aller par étapes successives, et de choisir les outils et mécanismes qui correspondent le plus à vos besoins. Vous ferrez des erreurs, tant mieux, mais vous apprendrez surtout à maîtriser votre espace numérique, tout comme maîtriser sa voiture ou son vélo est essentiel afin d'utiliser le réseau routier (et ne s'apprend pas du jour au lendemain) !

Enfin, nous terminerons par la fameuse maxime à ne jamais oublier :

> **"Si c'est gratuit (en tout cas pour les logiciels propriétaires), il y a de fortes chances que vous soyez le produit !"** (Citation bien connue)

