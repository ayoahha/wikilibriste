---
title: Les distributions GNU/Linux
description: Article relatif aux distributions GNU/Linux que le collectif recommande...
published: true
date: 2024-01-16T12:17:18.164Z
tags: linux, debutant, intermédiaire, débutant, intermediaire, initié, expert
editor: markdown
dateCreated: 2022-11-24T21:02:27.494Z
---

![Tux](/images/tux.svg =100x){.align-center}

Il existe littéralement **une centaine de distributions GNU/Linux** ! L'avantage d'un système ouvert est qu'il est possible de finement adapter le matériel à ses besoins... En contrepartie, il est très compliqué pour le néophyte de s'y retrouver. Vous ne trouverez donc ici que les distros que nous avons sélectionnées, orientées **respect de la vie privée, pour ordinateur obsolète ou bien adaptées pour les débutants**.

Soit dit en passant :
-   Vous pouvez retrouver sur le site [DistroWatch](https://distrowatch.com) toutes les distributions GNU/Linux.
-   L'outil d'aide à la décision d'une distro Linux [DistroChooser](https://distrochooser.de/fr_DistroChooser) peut vous aider à choisir la plus adaptée à vos besoins.
{.grid-list}

> On ne le répétera jamais assez : pensez à faire une sauvegarde avant d'installer une distribution Linux et suivez les recommandations de base de la page [Avertissement](/avertissement).
>
> **Notre équipe ne pourra être tenue responsable de la perte de vos données.**
{.is-warning}

# Général
Les listes ci-après indiquent différentes distributions GNU/Linux, que nous nommons "_distros_" pour rappel, sélectionnées par nos soins, avec prise en compte du niveau de l'utilisateur, grâce aux 3 onglets. 

_Note_ : certaines distros seront spécifiques car orientées 'full-FOSS' (Free and Open Source Software), sécurité, vieille machine ou serveurs.


# Clef USB bootable
Nous recommandons principalement 3 outils, open-source et libres, qui possèdent la plus haute probabilité de succès afin de créer une clé USB bootable avec une ou plusieurs image(s) du système d'exploitation que vous souhaitez installer :
- [BalenaEtcher](https://www.balena.io/etcher/) : marche dans 85 à 90% des cas. Attention à bien utiliser une clé USB saine. Si vous rencontrez des problèmes, vous pouvez essayer le second outil.
- [Ventoy](https://www.ventoy.net/en/index.html) : Ventoy est spécifique, il vous permet de stocker plusieurs images en même temps de sorte à pouvoir sélectionner l'OS dans la liste et booter dessus. Outil très utilisé et apprécié de la communauté.
{.grid-list}
> **Nous avons rédigé un [tutoriel](/tutoriels/usb-bootable) pour vous montrer comment procéder avec ces 2 outils.**
{.is-info}


- [UNetBootIn](https://unetbootin.github.io/) : un peu plus complexe à utiliser, et parfois capricieux.
{.grid-list}

# Choisissez votre distro
N'oubliez pas de modifier votre BIOS afin de permettre un boot sur une clef USB.


> **Nous avons rédigé un [tutoriel](/tutoriels/bios-boot) spécifique pour le paramétrage d'un BIOS**.
{.is-info}

Sur le principe, nous avons tendance à grossièrement schématiser cette répartition :
```diagram
PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB2ZXJzaW9uPSIxLjEiIHdpZHRoPSI4MTRweCIgaGVpZ2h0PSI0NzFweCIgdmlld0JveD0iLTAuNSAtMC41IDgxNCA0NzEiIGNvbnRlbnQ9IiZsdDtteGZpbGUgaG9zdD0mcXVvdDtlbWJlZC5kaWFncmFtcy5uZXQmcXVvdDsgbW9kaWZpZWQ9JnF1b3Q7MjAyMy0wNS0xMFQxMzoxMzoyMS45OTZaJnF1b3Q7IGFnZW50PSZxdW90O01vemlsbGEvNS4wIChYMTE7IExpbnV4IHg4Nl82NCkgQXBwbGVXZWJLaXQvNTM3LjM2IChLSFRNTCwgbGlrZSBHZWNrbykgQ2hyb21lLzExMy4wLjAuMCBTYWZhcmkvNTM3LjM2JnF1b3Q7IGV0YWc9JnF1b3Q7T2d6a3lUa20wQk9lU0cwdXdNT2kmcXVvdDsgdmVyc2lvbj0mcXVvdDsyMS4yLjkmcXVvdDsgdHlwZT0mcXVvdDtlbWJlZCZxdW90OyZndDsmbHQ7ZGlhZ3JhbSBpZD0mcXVvdDtJUXBXNFNNTGxwNFNmdDhWeVRrTSZxdW90OyBuYW1lPSZxdW90O1BhZ2UtMSZxdW90OyZndDs3VnBiYjlzMkZQNDFCcnFIRWlRUHI0K3AwM1lGVm14WU1BelltMnd4dGpCWjlDUzZjZmZyZDZpTGJWbDJrNlYySFFTT0hpSWRIbEhrK2I1eklla1JqQmZyajJXeW5ILzJxY3RIbktickVkeU9PR2NDQlA2TGtxK054RkRlQ0dabGxyWktXOEZkOXE5cmhiU1ZyckxVVlQzRjRIMGVzbVZmT1BWRjRhYWhKMHZLMGovMDFlNTkzdi9xTXBtNWdlQnVtdVJENlo5Wkd1YXRsQ203YmZqWlpiTjUrMm5EZGRPd1NEcmxkaWJWUEVuOXc0NEkzbzlnWEhvZm1ydkZldXp5YUx6T0xzMTdINDYwYmdaV3VpSTg1UVhlSXZFbHlWZnQ1TnFCaGEvZGJHZWxYeTFiTlZjR3R6NWs0MlRTcWRQaEdOaG1aa2dKNXhjdWxGOVJaZDFIZFVNR290dEJQR3lOYXpxdCtZNWRoYktFbXhiWEZ0UFpwdi90dFBHbW5ma1JLL0RIcllCdklMM3c0ZDNEUEF2dWJwbE1ZOHNETWh4bDg3REF6bThaM3Q1bmVUNzJ1Uy9yOStEZTNtdUgzM21YSnRVODN0Uks4ZUczSkFSWEZpakJLVkNEMGlxVS91OE5wZmhHc3RNZEtMQVF1eXQ5U0VMbTQrdHZnYUpnYVBZTnVQdW9IWVZDTUVPVU1ZcFpaYWcySUZRZkdrNjRGTkZkTmRXY01qR0FDVFFsVmpCUVZsZ09wbk9JWGRDWUVRUTdvVXBTVUVMclUrQkh6NGZmSkptYUZFNkdId2NoWkhvaXVMamd4Q0FmTEpwY0dDbEE5K0RpbWhPdGxkR1NXUjU1SXdkNFlRT1JWbWtFUXdKVHRPdGhGekJqQ2NKdGhVRW5WQmpseEFrQWV4d3ZqSXpMZUlzV0NsbVMveDVqVERITG53RGd4SWZnRi9nUXZhSnM1MEgza0MxODRmYThpSm1vbEdZbGZxb1JWWDRWRFhVYXJDd0JhamdGUUVna29zVjdXRWxMbUZFeVprZk1JMVR3b1c5cFFEaXBwRVlJOURETmhrZ0J1cFpRQ0xWRTcxTUtmZXo3b1dMbWpMRlJ4dXU1dm5Ydmk3QWJHZXUvUXo2bjZyOFQ0UWdhSXlTeldtck5NQXp1d1FpMVJ3ckpxRVYzNDJLSTRqR2ZQYlBISGNyektnL1JYZkJtRm1yck5JSm8xeDYrNnArVjd4cmVWblUxZG9NS0hKYnI1clcydmV0bzdCZkwzSzJ6TUJyRDZNYkdnaTMzazFnOWNmb21LNnFRNUhuamRaeTYrS2xWeVBLc3FrVS9kYVBBQ1RVRDZROE94VHNEM3VNaFFoajZoT3R6b1hYNkEzRWd5Yk5aWk5zVW1lRlEvaTRTSXNPSzc2WnRXR1JwZWpUNFlJRlVwRFYvVDVXSWo4WGxsbVpDQUZIQ01xa1ZnTUhvTWFBWk1wQVlTbU1zWVZSS1pPdVFabHdTaFRGSlJBOWhXZ3Y5L1RTVFA1Qm1uNG92cmdwWlZibUZxN3Q2NHlLamdsc3NxMWRBbzkzVVpQY3prMHVxY0NLcXZXVUF4Qm9LMG5DcmphUjdSUVRqeE9vdDB3NXdqVnNndTZudFVFZzdBOWZzVWE2MTFKcHVVc0NXT2pDWlVPWG9ydWdKRktSSEtEZ2c5eCtUVlJGV2gxbDJoSkF2a253bmlXRmFFb09GQ05wUFNjc3RoYjFVYVluQ2RRSkZKQm5UVEt0aGRVb3BpWlVTbHJDWTM4MW1tK0RNeEdLSGxoT1BNeXRsR0szUHdLd0R2UXoxZjhtSzFScDFQMmMxdDY3MDQ1S1M3cVdPY1poVXdRNVp4ckRjVWtlWWRRSTJzV2V4U1FndHAvSmNjZXFEUzMyWlhJblM0TXdJWjRBaHlHQWMwWlQyV1JPcmNhTUVveUJBWWRtdlhrNmNPclNNL3AvRjFhbml6MDA1bmFOcUc0YXV0RUs4UVJJYk43dUJXWVpaenZSWXhSVEROWjQxRmd0MGFYU1hHMThBcWVCWjRVcGJPcVhUQ3lXL1d6ZkprdUpLdXpySlVVYUVsSVlpSVNoVFlxK2NCeWFKc0hpaEJ0YnRraDNZRTd3UThZNXZVWHd6VHlZVHZDNUV2TDk4bVJXLzNsMlpWNi9IT0dHTUNhc0ExNUZJbmY3WkFlQnFBQ2psUWlpcHNmYm5MNFozeC9jc3ZzVTdLcFdLeDNvWDRkMnZTMWZjclNwM0pWNjlHeWFSZVFZd25YSXB1VkNzWDc4SlRaaFFGTGpoQ2h2Tnk2bmYxUE1pM3BSU2F5L0V2SStJay9kWDNzVldKWUV3S1pCeEdnMjhPUkh2RGtzRk1VeURFcEpxd1Byb3hiQk9QNHQxYWhLdlMrMXVmTGptMkxwVlUwbW9aZ3BrNUIzWS9wYmFFdzRScFlybjgxRkhLNG02UXY0WTBnMDNhMitiMDZISktpUVJ1dGNMR2RZOUNxeU1rVUxHYllTOWVqeHVQaWt0dVVFbDFkbDZGN0c0ajhWVjNIMWdjYnYwd0xudkdRRGp3MTJyVDlHZWl3YTFORXV5MHIxaTFLSXZvWDlZSVdJWU0zTHZVT1R4bXVKQ3NBMVg3Mk5mM0djZGJxOFlNYUVNc2NEUXgyTGdRM1AyRUdPNExMWlVTSXYreUlSVXcrWEhEd0VNSDdjLzdxdmJkbjRpQ2UvL0F3PT0mbHQ7L2RpYWdyYW0mZ3Q7Jmx0Oy9teGZpbGUmZ3Q7Ij48ZGVmcy8+PGc+PGVsbGlwc2UgY3g9IjYwNS4xNiIgY3k9IjE3NC4yNSIgcng9IjE4NS40NzA2ODQ3NDYxOTM0NiIgcnk9IjkyLjI3MTAzMjUxODIzODkiIGZpbGw9IiNmOWY3ZWQiIHN0cm9rZT0iIzM2MzkzZCIgc3Ryb2tlLXdpZHRoPSIyIiBzdHJva2UtZGFzaGFycmF5PSIxNiAxNiIgdHJhbnNmb3JtPSJyb3RhdGUoLTMwLDYwNS4xNiwxNzQuMjUpIiBwb2ludGVyLWV2ZW50cz0ibm9uZSIvPjxlbGxpcHNlIGN4PSIzNDAuMTQiIGN5PSIzMTcuMzUiIHJ4PSI5Ni4yOTgzODI1MjY1ODAxOCIgcnk9IjQ0Ljg1Mzk3NDE0MDgxMDU3IiBmaWxsPSIjYmFjOGQzIiBzdHJva2U9IiMyMzQ0NWQiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWRhc2hhcnJheT0iMTYgMTYiIHBvaW50ZXItZXZlbnRzPSJub25lIi8+PHBhdGggZD0iTSAyMDQuNDMgLTExNS4yMSBMIDU4OC44OSAtMTE1LjIxIE0gNTg4Ljg5IDYxNy40OSBNIDIwNC40MyA2MTcuNDkgTCAyMDQuNDMgLTExNS4yMSIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJyZ2IoMCwgMCwgMCkiIHN0cm9rZS1saW5lY2FwPSJzcXVhcmUiIHN0cm9rZS1taXRlcmxpbWl0PSIxMCIgdHJhbnNmb3JtPSJyb3RhdGUoLTkwLDM5Ni42NiwyNTEuMTQpIiBwb2ludGVyLWV2ZW50cz0ibm9uZSIvPjxlbGxpcHNlIGN4PSIxNjAuMSIgY3k9IjM4Ny40MSIgcng9IjEyMS40MTk2OTk3MDc0MjcxOCIgcnk9IjQ0Ljg1Mzk3NDE0MDgxMDU3IiBmaWxsPSIjZjVmNWY1IiBzdHJva2U9IiM2NjY2NjYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWRhc2hhcnJheT0iMTYgMTYiIHBvaW50ZXItZXZlbnRzPSJub25lIi8+PGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTAuNSAtMC41KSI+PHN3aXRjaD48Zm9yZWlnbk9iamVjdCBwb2ludGVyLWV2ZW50cz0ibm9uZSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5IiBzdHlsZT0ib3ZlcmZsb3c6IHZpc2libGU7IHRleHQtYWxpZ246IGxlZnQ7Ij48ZGl2IHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzdHlsZT0iZGlzcGxheTogZmxleDsgYWxpZ24taXRlbXM6IHVuc2FmZSBjZW50ZXI7IGp1c3RpZnktY29udGVudDogdW5zYWZlIGNlbnRlcjsgd2lkdGg6IDUwOXB4OyBoZWlnaHQ6IDFweDsgcGFkZGluZy10b3A6IDQ1NnB4OyBtYXJnaW4tbGVmdDogMTk1cHg7Ij48ZGl2IGRhdGEtZHJhd2lvLWNvbG9ycz0iY29sb3I6IHJnYigwLCAwLCAwKTsgIiBzdHlsZT0iYm94LXNpemluZzogYm9yZGVyLWJveDsgZm9udC1zaXplOiAwcHg7IHRleHQtYWxpZ246IGNlbnRlcjsiPjxkaXYgc3R5bGU9ImRpc3BsYXk6IGlubGluZS1ibG9jazsgZm9udC1zaXplOiAxMnB4OyBmb250LWZhbWlseTogSGVsdmV0aWNhOyBjb2xvcjogcmdiKDAsIDAsIDApOyBsaW5lLWhlaWdodDogMS4yOyBwb2ludGVyLWV2ZW50czogbm9uZTsgd2hpdGUtc3BhY2U6IG5vcm1hbDsgb3ZlcmZsb3ctd3JhcDogbm9ybWFsOyI+PGI+PGZvbnQgc3R5bGU9ImZvbnQtc2l6ZTogMjNweDsiPkNvbXBsZXhpdMOpIGdsb2JhbGUgKGluc3RhbGxhdGlvbiBldCB1dGlsaXNhdGlvbik8L2ZvbnQ+PC9iPjwvZGl2PjwvZGl2PjwvZGl2PjwvZm9yZWlnbk9iamVjdD48dGV4dCB4PSI0NDkiIHk9IjQ2MCIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPkNvbXBsZXhpdMOpIGdsb2JhbGUgKGluc3RhbGxhdGlvbiBldCB1dGlsaXNhdGlvbik8L3RleHQ+PC9zd2l0Y2g+PC9nPjxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKC0wLjUgLTAuNSlyb3RhdGUoLTkwIDEzLjU2MDY1ODU5MDQyMzYgMjI1LjUwNjk5NzUyMTMxNDEzKSI+PHN3aXRjaD48Zm9yZWlnbk9iamVjdCBwb2ludGVyLWV2ZW50cz0ibm9uZSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5IiBzdHlsZT0ib3ZlcmZsb3c6IHZpc2libGU7IHRleHQtYWxpZ246IGxlZnQ7Ij48ZGl2IHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzdHlsZT0iZGlzcGxheTogZmxleDsgYWxpZ24taXRlbXM6IHVuc2FmZSBjZW50ZXI7IGp1c3RpZnktY29udGVudDogdW5zYWZlIGNlbnRlcjsgd2lkdGg6IDI5MXB4OyBoZWlnaHQ6IDFweDsgcGFkZGluZy10b3A6IDIyNnB4OyBtYXJnaW4tbGVmdDogLTEzMnB4OyI+PGRpdiBkYXRhLWRyYXdpby1jb2xvcnM9ImNvbG9yOiByZ2IoMCwgMCwgMCk7ICIgc3R5bGU9ImJveC1zaXppbmc6IGJvcmRlci1ib3g7IGZvbnQtc2l6ZTogMHB4OyB0ZXh0LWFsaWduOiBjZW50ZXI7Ij48ZGl2IHN0eWxlPSJkaXNwbGF5OiBpbmxpbmUtYmxvY2s7IGZvbnQtc2l6ZTogMTJweDsgZm9udC1mYW1pbHk6IEhlbHZldGljYTsgY29sb3I6IHJnYigwLCAwLCAwKTsgbGluZS1oZWlnaHQ6IDEuMjsgcG9pbnRlci1ldmVudHM6IG5vbmU7IHdoaXRlLXNwYWNlOiBub3JtYWw7IG92ZXJmbG93LXdyYXA6IG5vcm1hbDsiPjxiPjxmb250IHN0eWxlPSJmb250LXNpemU6IDIzcHg7Ij5JbnZlc3Rpc3NlbWVudCAoZW4gdGVtcHMpPC9mb250PjwvYj48L2Rpdj48L2Rpdj48L2Rpdj48L2ZvcmVpZ25PYmplY3Q+PHRleHQgeD0iMTQiIHk9IjIyOSIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPkludmVzdGlzc2VtZW50IChlbiB0ZW1wcyk8L3RleHQ+PC9zd2l0Y2g+PC9nPjxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKC0wLjUgLTAuNSkiPjxzd2l0Y2g+PGZvcmVpZ25PYmplY3QgcG9pbnRlci1ldmVudHM9Im5vbmUiIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIHJlcXVpcmVkRmVhdHVyZXM9Imh0dHA6Ly93d3cudzMub3JnL1RSL1NWRzExL2ZlYXR1cmUjRXh0ZW5zaWJpbGl0eSIgc3R5bGU9Im92ZXJmbG93OiB2aXNpYmxlOyB0ZXh0LWFsaWduOiBsZWZ0OyI+PGRpdiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94aHRtbCIgc3R5bGU9ImRpc3BsYXk6IGZsZXg7IGFsaWduLWl0ZW1zOiB1bnNhZmUgY2VudGVyOyBqdXN0aWZ5LWNvbnRlbnQ6IHVuc2FmZSBjZW50ZXI7IHdpZHRoOiA5OHB4OyBoZWlnaHQ6IDFweDsgcGFkZGluZy10b3A6IDM2MnB4OyBtYXJnaW4tbGVmdDogMTc4cHg7Ij48ZGl2IGRhdGEtZHJhd2lvLWNvbG9ycz0iY29sb3I6IHJnYigwLCAwLCAwKTsgIiBzdHlsZT0iYm94LXNpemluZzogYm9yZGVyLWJveDsgZm9udC1zaXplOiAwcHg7IHRleHQtYWxpZ246IGNlbnRlcjsiPjxkaXYgc3R5bGU9ImRpc3BsYXk6IGlubGluZS1ibG9jazsgZm9udC1zaXplOiAxMnB4OyBmb250LWZhbWlseTogSGVsdmV0aWNhOyBjb2xvcjogcmdiKDAsIDAsIDApOyBsaW5lLWhlaWdodDogMS4yOyBwb2ludGVyLWV2ZW50czogbm9uZTsgd2hpdGUtc3BhY2U6IG5vcm1hbDsgb3ZlcmZsb3ctd3JhcDogbm9ybWFsOyI+PGZvbnQgc3R5bGU9ImZvbnQtc2l6ZTogMjBweDsiIGNvbG9yPSIjYmIwNmUwIj48Yj5VYnVudHU8L2I+PC9mb250PjwvZGl2PjwvZGl2PjwvZGl2PjwvZm9yZWlnbk9iamVjdD48dGV4dCB4PSIyMjciIHk9IjM2NiIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPlVidW50dTwvdGV4dD48L3N3aXRjaD48L2c+PGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTAuNSAtMC41KSI+PHN3aXRjaD48Zm9yZWlnbk9iamVjdCBwb2ludGVyLWV2ZW50cz0ibm9uZSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5IiBzdHlsZT0ib3ZlcmZsb3c6IHZpc2libGU7IHRleHQtYWxpZ246IGxlZnQ7Ij48ZGl2IHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzdHlsZT0iZGlzcGxheTogZmxleDsgYWxpZ24taXRlbXM6IHVuc2FmZSBjZW50ZXI7IGp1c3RpZnktY29udGVudDogdW5zYWZlIGNlbnRlcjsgd2lkdGg6IDExOHB4OyBoZWlnaHQ6IDFweDsgcGFkZGluZy10b3A6IDQwNXB4OyBtYXJnaW4tbGVmdDogNTJweDsiPjxkaXYgZGF0YS1kcmF3aW8tY29sb3JzPSJjb2xvcjogcmdiKDAsIDAsIDApOyAiIHN0eWxlPSJib3gtc2l6aW5nOiBib3JkZXItYm94OyBmb250LXNpemU6IDBweDsgdGV4dC1hbGlnbjogY2VudGVyOyI+PGRpdiBzdHlsZT0iZGlzcGxheTogaW5saW5lLWJsb2NrOyBmb250LXNpemU6IDEycHg7IGZvbnQtZmFtaWx5OiBIZWx2ZXRpY2E7IGNvbG9yOiByZ2IoMCwgMCwgMCk7IGxpbmUtaGVpZ2h0OiAxLjI7IHBvaW50ZXItZXZlbnRzOiBub25lOyB3aGl0ZS1zcGFjZTogbm9ybWFsOyBvdmVyZmxvdy13cmFwOiBub3JtYWw7Ij48Zm9udCBzdHlsZT0iZm9udC1zaXplOiAyMHB4OyIgY29sb3I9IiNkMTY1MDAiPjxiIHN0eWxlPSIiPkxpbnV4IE1pbnQ8L2I+PC9mb250PjwvZGl2PjwvZGl2PjwvZGl2PjwvZm9yZWlnbk9iamVjdD48dGV4dCB4PSIxMTEiIHk9IjQwOSIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPkxpbnV4IE1pbnQ8L3RleHQ+PC9zd2l0Y2g+PC9nPjxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKC0wLjUgLTAuNSkiPjxzd2l0Y2g+PGZvcmVpZ25PYmplY3QgcG9pbnRlci1ldmVudHM9Im5vbmUiIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIHJlcXVpcmVkRmVhdHVyZXM9Imh0dHA6Ly93d3cudzMub3JnL1RSL1NWRzExL2ZlYXR1cmUjRXh0ZW5zaWJpbGl0eSIgc3R5bGU9Im92ZXJmbG93OiB2aXNpYmxlOyB0ZXh0LWFsaWduOiBsZWZ0OyI+PGRpdiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94aHRtbCIgc3R5bGU9ImRpc3BsYXk6IGZsZXg7IGFsaWduLWl0ZW1zOiB1bnNhZmUgY2VudGVyOyBqdXN0aWZ5LWNvbnRlbnQ6IHVuc2FmZSBjZW50ZXI7IHdpZHRoOiA5OHB4OyBoZWlnaHQ6IDFweDsgcGFkZGluZy10b3A6IDMwMnB4OyBtYXJnaW4tbGVmdDogMjUzcHg7Ij48ZGl2IGRhdGEtZHJhd2lvLWNvbG9ycz0iY29sb3I6IHJnYigwLCAwLCAwKTsgIiBzdHlsZT0iYm94LXNpemluZzogYm9yZGVyLWJveDsgZm9udC1zaXplOiAwcHg7IHRleHQtYWxpZ246IGNlbnRlcjsiPjxkaXYgc3R5bGU9ImRpc3BsYXk6IGlubGluZS1ibG9jazsgZm9udC1zaXplOiAxMnB4OyBmb250LWZhbWlseTogSGVsdmV0aWNhOyBjb2xvcjogcmdiKDAsIDAsIDApOyBsaW5lLWhlaWdodDogMS4yOyBwb2ludGVyLWV2ZW50czogbm9uZTsgd2hpdGUtc3BhY2U6IG5vcm1hbDsgb3ZlcmZsb3ctd3JhcDogbm9ybWFsOyI+PGZvbnQgc3R5bGU9ImZvbnQtc2l6ZTogMjBweDsiIGNvbG9yPSIjNDQ3NWM1Ij48Yj5GZWRvcmE8L2I+PC9mb250PjwvZGl2PjwvZGl2PjwvZGl2PjwvZm9yZWlnbk9iamVjdD48dGV4dCB4PSIzMDIiIHk9IjMwNiIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPkZlZG9yYTwvdGV4dD48L3N3aXRjaD48L2c+PGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTAuNSAtMC41KSI+PHN3aXRjaD48Zm9yZWlnbk9iamVjdCBwb2ludGVyLWV2ZW50cz0ibm9uZSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5IiBzdHlsZT0ib3ZlcmZsb3c6IHZpc2libGU7IHRleHQtYWxpZ246IGxlZnQ7Ij48ZGl2IHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzdHlsZT0iZGlzcGxheTogZmxleDsgYWxpZ24taXRlbXM6IHVuc2FmZSBjZW50ZXI7IGp1c3RpZnktY29udGVudDogdW5zYWZlIGNlbnRlcjsgd2lkdGg6IDk4cHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogMTc0cHg7IG1hcmdpbi1sZWZ0OiA1MzhweDsiPjxkaXYgZGF0YS1kcmF3aW8tY29sb3JzPSJjb2xvcjogcmdiKDAsIDAsIDApOyAiIHN0eWxlPSJib3gtc2l6aW5nOiBib3JkZXItYm94OyBmb250LXNpemU6IDBweDsgdGV4dC1hbGlnbjogY2VudGVyOyI+PGRpdiBzdHlsZT0iZGlzcGxheTogaW5saW5lLWJsb2NrOyBmb250LXNpemU6IDEycHg7IGZvbnQtZmFtaWx5OiBIZWx2ZXRpY2E7IGNvbG9yOiByZ2IoMCwgMCwgMCk7IGxpbmUtaGVpZ2h0OiAxLjI7IHBvaW50ZXItZXZlbnRzOiBub25lOyB3aGl0ZS1zcGFjZTogbm9ybWFsOyBvdmVyZmxvdy13cmFwOiBub3JtYWw7Ij48Zm9udCBzdHlsZT0iZm9udC1zaXplOiAyMHB4OyI+PGIgc3R5bGU9IiI+QXJjaCBMaW51eDwvYj48L2ZvbnQ+PC9kaXY+PC9kaXY+PC9kaXY+PC9mb3JlaWduT2JqZWN0Pjx0ZXh0IHg9IjU4NyIgeT0iMTc4IiBmaWxsPSJyZ2IoMCwgMCwgMCkiIGZvbnQtZmFtaWx5PSJIZWx2ZXRpY2EiIGZvbnQtc2l6ZT0iMTJweCIgdGV4dC1hbmNob3I9Im1pZGRsZSI+QXJjaCBMaW51eDwvdGV4dD48L3N3aXRjaD48L2c+PGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTAuNSAtMC41KSI+PHN3aXRjaD48Zm9yZWlnbk9iamVjdCBwb2ludGVyLWV2ZW50cz0ibm9uZSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5IiBzdHlsZT0ib3ZlcmZsb3c6IHZpc2libGU7IHRleHQtYWxpZ246IGxlZnQ7Ij48ZGl2IHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzdHlsZT0iZGlzcGxheTogZmxleDsgYWxpZ24taXRlbXM6IHVuc2FmZSBjZW50ZXI7IGp1c3RpZnktY29udGVudDogdW5zYWZlIGNlbnRlcjsgd2lkdGg6IDk4cHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogMzI4cHg7IG1hcmdpbi1sZWZ0OiAzMDNweDsiPjxkaXYgZGF0YS1kcmF3aW8tY29sb3JzPSJjb2xvcjogcmdiKDAsIDAsIDApOyAiIHN0eWxlPSJib3gtc2l6aW5nOiBib3JkZXItYm94OyBmb250LXNpemU6IDBweDsgdGV4dC1hbGlnbjogY2VudGVyOyI+PGRpdiBzdHlsZT0iZGlzcGxheTogaW5saW5lLWJsb2NrOyBmb250LXNpemU6IDEycHg7IGZvbnQtZmFtaWx5OiBIZWx2ZXRpY2E7IGNvbG9yOiByZ2IoMCwgMCwgMCk7IGxpbmUtaGVpZ2h0OiAxLjI7IHBvaW50ZXItZXZlbnRzOiBub25lOyB3aGl0ZS1zcGFjZTogbm9ybWFsOyBvdmVyZmxvdy13cmFwOiBub3JtYWw7Ij48Zm9udCBzdHlsZT0iZm9udC1zaXplOiAyMHB4OyIgY29sb3I9IiM3OTBjMGMiPjxiIHN0eWxlPSIiPkRlYmlhbjwvYj48L2ZvbnQ+PC9kaXY+PC9kaXY+PC9kaXY+PC9mb3JlaWduT2JqZWN0Pjx0ZXh0IHg9IjM1MyIgeT0iMzMyIiBmaWxsPSJyZ2IoMCwgMCwgMCkiIGZvbnQtZmFtaWx5PSJIZWx2ZXRpY2EiIGZvbnQtc2l6ZT0iMTJweCIgdGV4dC1hbmNob3I9Im1pZGRsZSI+RGViaWFuPC90ZXh0Pjwvc3dpdGNoPjwvZz48ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMC41IC0wLjUpIj48c3dpdGNoPjxmb3JlaWduT2JqZWN0IHBvaW50ZXItZXZlbnRzPSJub25lIiB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiByZXF1aXJlZEZlYXR1cmVzPSJodHRwOi8vd3d3LnczLm9yZy9UUi9TVkcxMS9mZWF0dXJlI0V4dGVuc2liaWxpdHkiIHN0eWxlPSJvdmVyZmxvdzogdmlzaWJsZTsgdGV4dC1hbGlnbjogbGVmdDsiPjxkaXYgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGh0bWwiIHN0eWxlPSJkaXNwbGF5OiBmbGV4OyBhbGlnbi1pdGVtczogdW5zYWZlIGNlbnRlcjsganVzdGlmeS1jb250ZW50OiB1bnNhZmUgY2VudGVyOyB3aWR0aDogOThweDsgaGVpZ2h0OiAxcHg7IHBhZGRpbmctdG9wOiAzODhweDsgbWFyZ2luLWxlZnQ6IDk0cHg7Ij48ZGl2IGRhdGEtZHJhd2lvLWNvbG9ycz0iY29sb3I6IHJnYigwLCAwLCAwKTsgIiBzdHlsZT0iYm94LXNpemluZzogYm9yZGVyLWJveDsgZm9udC1zaXplOiAwcHg7IHRleHQtYWxpZ246IGNlbnRlcjsiPjxkaXYgc3R5bGU9ImRpc3BsYXk6IGlubGluZS1ibG9jazsgZm9udC1zaXplOiAxMnB4OyBmb250LWZhbWlseTogSGVsdmV0aWNhOyBjb2xvcjogcmdiKDAsIDAsIDApOyBsaW5lLWhlaWdodDogMS4yOyBwb2ludGVyLWV2ZW50czogbm9uZTsgd2hpdGUtc3BhY2U6IG5vcm1hbDsgb3ZlcmZsb3ctd3JhcDogbm9ybWFsOyI+PGZvbnQgc3R5bGU9ImZvbnQtc2l6ZTogMjBweDsiIGNvbG9yPSIjNGFiYWJhIj48YiBzdHlsZT0iIj5ab3Jpbk9TPC9iPjwvZm9udD48L2Rpdj48L2Rpdj48L2Rpdj48L2ZvcmVpZ25PYmplY3Q+PHRleHQgeD0iMTQzIiB5PSIzOTEiIGZpbGw9InJnYigwLCAwLCAwKSIgZm9udC1mYW1pbHk9IkhlbHZldGljYSIgZm9udC1zaXplPSIxMnB4IiB0ZXh0LWFuY2hvcj0ibWlkZGxlIj5ab3Jpbk9TPC90ZXh0Pjwvc3dpdGNoPjwvZz48ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMC41IC0wLjUpIj48c3dpdGNoPjxmb3JlaWduT2JqZWN0IHBvaW50ZXItZXZlbnRzPSJub25lIiB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiByZXF1aXJlZEZlYXR1cmVzPSJodHRwOi8vd3d3LnczLm9yZy9UUi9TVkcxMS9mZWF0dXJlI0V4dGVuc2liaWxpdHkiIHN0eWxlPSJvdmVyZmxvdzogdmlzaWJsZTsgdGV4dC1hbGlnbjogbGVmdDsiPjxkaXYgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGh0bWwiIHN0eWxlPSJkaXNwbGF5OiBmbGV4OyBhbGlnbi1pdGVtczogdW5zYWZlIGNlbnRlcjsganVzdGlmeS1jb250ZW50OiB1bnNhZmUgY2VudGVyOyB3aWR0aDogOThweDsgaGVpZ2h0OiAxcHg7IHBhZGRpbmctdG9wOiAyNjBweDsgbWFyZ2luLWxlZnQ6IDQ1NHB4OyI+PGRpdiBkYXRhLWRyYXdpby1jb2xvcnM9ImNvbG9yOiByZ2IoMCwgMCwgMCk7ICIgc3R5bGU9ImJveC1zaXppbmc6IGJvcmRlci1ib3g7IGZvbnQtc2l6ZTogMHB4OyB0ZXh0LWFsaWduOiBjZW50ZXI7Ij48ZGl2IHN0eWxlPSJkaXNwbGF5OiBpbmxpbmUtYmxvY2s7IGZvbnQtc2l6ZTogMTJweDsgZm9udC1mYW1pbHk6IEhlbHZldGljYTsgY29sb3I6IHJnYigwLCAwLCAwKTsgbGluZS1oZWlnaHQ6IDEuMjsgcG9pbnRlci1ldmVudHM6IG5vbmU7IHdoaXRlLXNwYWNlOiBub3JtYWw7IG92ZXJmbG93LXdyYXA6IG5vcm1hbDsiPjxmb250IHN0eWxlPSJmb250LXNpemU6IDIwcHg7IiBjb2xvcj0iIzA1NjYyNyI+PGIgc3R5bGU9IiI+T3BlblN1c2U8L2I+PC9mb250PjwvZGl2PjwvZGl2PjwvZGl2PjwvZm9yZWlnbk9iamVjdD48dGV4dCB4PSI1MDMiIHk9IjI2MyIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPk9wZW5TdXNlPC90ZXh0Pjwvc3dpdGNoPjwvZz48ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMC41IC0wLjUpIj48c3dpdGNoPjxmb3JlaWduT2JqZWN0IHBvaW50ZXItZXZlbnRzPSJub25lIiB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiByZXF1aXJlZEZlYXR1cmVzPSJodHRwOi8vd3d3LnczLm9yZy9UUi9TVkcxMS9mZWF0dXJlI0V4dGVuc2liaWxpdHkiIHN0eWxlPSJvdmVyZmxvdzogdmlzaWJsZTsgdGV4dC1hbGlnbjogbGVmdDsiPjxkaXYgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGh0bWwiIHN0eWxlPSJkaXNwbGF5OiBmbGV4OyBhbGlnbi1pdGVtczogdW5zYWZlIGNlbnRlcjsganVzdGlmeS1jb250ZW50OiB1bnNhZmUgY2VudGVyOyB3aWR0aDogOThweDsgaGVpZ2h0OiAxcHg7IHBhZGRpbmctdG9wOiA5N3B4OyBtYXJnaW4tbGVmdDogNjU1cHg7Ij48ZGl2IGRhdGEtZHJhd2lvLWNvbG9ycz0iY29sb3I6IHJnYigwLCAwLCAwKTsgIiBzdHlsZT0iYm94LXNpemluZzogYm9yZGVyLWJveDsgZm9udC1zaXplOiAwcHg7IHRleHQtYWxpZ246IGNlbnRlcjsiPjxkaXYgc3R5bGU9ImRpc3BsYXk6IGlubGluZS1ibG9jazsgZm9udC1zaXplOiAxMnB4OyBmb250LWZhbWlseTogSGVsdmV0aWNhOyBjb2xvcjogcmdiKDAsIDAsIDApOyBsaW5lLWhlaWdodDogMS4yOyBwb2ludGVyLWV2ZW50czogbm9uZTsgd2hpdGUtc3BhY2U6IG5vcm1hbDsgb3ZlcmZsb3ctd3JhcDogbm9ybWFsOyI+PGZvbnQgc3R5bGU9ImZvbnQtc2l6ZTogMjBweDsiIGNvbG9yPSIjNGMwMDk5Ij48YiBzdHlsZT0iIj5HZW50b288L2I+PC9mb250PjwvZGl2PjwvZGl2PjwvZGl2PjwvZm9yZWlnbk9iamVjdD48dGV4dCB4PSI3MDQiIHk9IjEwMSIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPkdlbnRvbzwvdGV4dD48L3N3aXRjaD48L2c+PGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTAuNSAtMC41KSI+PHN3aXRjaD48Zm9yZWlnbk9iamVjdCBwb2ludGVyLWV2ZW50cz0ibm9uZSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5IiBzdHlsZT0ib3ZlcmZsb3c6IHZpc2libGU7IHRleHQtYWxpZ246IGxlZnQ7Ij48ZGl2IHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzdHlsZT0iZGlzcGxheTogZmxleDsgYWxpZ24taXRlbXM6IHVuc2FmZSBjZW50ZXI7IGp1c3RpZnktY29udGVudDogdW5zYWZlIGNlbnRlcjsgd2lkdGg6IDU1cHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogNzJweDsgbWFyZ2luLWxlZnQ6IDcwN3B4OyI+PGRpdiBkYXRhLWRyYXdpby1jb2xvcnM9ImNvbG9yOiByZ2IoMCwgMCwgMCk7ICIgc3R5bGU9ImJveC1zaXppbmc6IGJvcmRlci1ib3g7IGZvbnQtc2l6ZTogMHB4OyB0ZXh0LWFsaWduOiBjZW50ZXI7Ij48ZGl2IHN0eWxlPSJkaXNwbGF5OiBpbmxpbmUtYmxvY2s7IGZvbnQtc2l6ZTogMTJweDsgZm9udC1mYW1pbHk6IEhlbHZldGljYTsgY29sb3I6IHJnYigwLCAwLCAwKTsgbGluZS1oZWlnaHQ6IDEuMjsgcG9pbnRlci1ldmVudHM6IG5vbmU7IHdoaXRlLXNwYWNlOiBub3JtYWw7IG92ZXJmbG93LXdyYXA6IG5vcm1hbDsiPjxmb250IHN0eWxlPSJmb250LXNpemU6IDIwcHg7IiBjb2xvcj0iIzZiNmI2YiI+PGIgc3R5bGU9IiI+TEZTPC9iPjwvZm9udD48L2Rpdj48L2Rpdj48L2Rpdj48L2ZvcmVpZ25PYmplY3Q+PHRleHQgeD0iNzM1IiB5PSI3NSIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPkxGUzwvdGV4dD48L3N3aXRjaD48L2c+PGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTAuNSAtMC41KSI+PHN3aXRjaD48Zm9yZWlnbk9iamVjdCBwb2ludGVyLWV2ZW50cz0ibm9uZSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5IiBzdHlsZT0ib3ZlcmZsb3c6IHZpc2libGU7IHRleHQtYWxpZ246IGxlZnQ7Ij48ZGl2IHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzdHlsZT0iZGlzcGxheTogZmxleDsgYWxpZ24taXRlbXM6IHVuc2FmZSBjZW50ZXI7IGp1c3RpZnktY29udGVudDogdW5zYWZlIGNlbnRlcjsgd2lkdGg6IDQ4cHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogMzMycHg7IG1hcmdpbi1sZWZ0OiA3N3B4OyI+PGRpdiBkYXRhLWRyYXdpby1jb2xvcnM9ImNvbG9yOiByZ2IoMCwgMCwgMCk7ICIgc3R5bGU9ImJveC1zaXppbmc6IGJvcmRlci1ib3g7IGZvbnQtc2l6ZTogMHB4OyB0ZXh0LWFsaWduOiBjZW50ZXI7Ij48ZGl2IHN0eWxlPSJkaXNwbGF5OiBpbmxpbmUtYmxvY2s7IGZvbnQtc2l6ZTogMTJweDsgZm9udC1mYW1pbHk6IEhlbHZldGljYTsgY29sb3I6IHJnYigwLCAwLCAwKTsgbGluZS1oZWlnaHQ6IDEuMjsgcG9pbnRlci1ldmVudHM6IG5vbmU7IHdoaXRlLXNwYWNlOiBub3JtYWw7IG92ZXJmbG93LXdyYXA6IG5vcm1hbDsiPkTDqWJ1dGFudDwvZGl2PjwvZGl2PjwvZGl2PjwvZm9yZWlnbk9iamVjdD48dGV4dCB4PSIxMDEiIHk9IjMzNiIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPkTDqWJ1dGFudDwvdGV4dD48L3N3aXRjaD48L2c+PGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTAuNSAtMC41KSI+PHN3aXRjaD48Zm9yZWlnbk9iamVjdCBwb2ludGVyLWV2ZW50cz0ibm9uZSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5IiBzdHlsZT0ib3ZlcmZsb3c6IHZpc2libGU7IHRleHQtYWxpZ246IGxlZnQ7Ij48ZGl2IHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzdHlsZT0iZGlzcGxheTogZmxleDsgYWxpZ24taXRlbXM6IHVuc2FmZSBjZW50ZXI7IGp1c3RpZnktY29udGVudDogdW5zYWZlIGNlbnRlcjsgd2lkdGg6IDQ4cHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogMjYwcHg7IG1hcmdpbi1sZWZ0OiAyNjJweDsiPjxkaXYgZGF0YS1kcmF3aW8tY29sb3JzPSJjb2xvcjogcmdiKDAsIDAsIDApOyAiIHN0eWxlPSJib3gtc2l6aW5nOiBib3JkZXItYm94OyBmb250LXNpemU6IDBweDsgdGV4dC1hbGlnbjogY2VudGVyOyI+PGRpdiBzdHlsZT0iZGlzcGxheTogaW5saW5lLWJsb2NrOyBmb250LXNpemU6IDEycHg7IGZvbnQtZmFtaWx5OiBIZWx2ZXRpY2E7IGNvbG9yOiByZ2IoMCwgMCwgMCk7IGxpbmUtaGVpZ2h0OiAxLjI7IHBvaW50ZXItZXZlbnRzOiBub25lOyB3aGl0ZS1zcGFjZTogbm9ybWFsOyBvdmVyZmxvdy13cmFwOiBub3JtYWw7Ij5JbnRlcm3DqWRpYWlyZTwvZGl2PjwvZGl2PjwvZGl2PjwvZm9yZWlnbk9iamVjdD48dGV4dCB4PSIyODYiIHk9IjI2MyIgZmlsbD0icmdiKDAsIDAsIDApIiBmb250LWZhbWlseT0iSGVsdmV0aWNhIiBmb250LXNpemU9IjEycHgiIHRleHQtYW5jaG9yPSJtaWRkbGUiPkludGVybcOpZC4uLjwvdGV4dD48L3N3aXRjaD48L2c+PGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTAuNSAtMC41KSI+PHN3aXRjaD48Zm9yZWlnbk9iamVjdCBwb2ludGVyLWV2ZW50cz0ibm9uZSIgd2lkdGg9IjEwMCUiIGhlaWdodD0iMTAwJSIgcmVxdWlyZWRGZWF0dXJlcz0iaHR0cDovL3d3dy53My5vcmcvVFIvU1ZHMTEvZmVhdHVyZSNFeHRlbnNpYmlsaXR5IiBzdHlsZT0ib3ZlcmZsb3c6IHZpc2libGU7IHRleHQtYWxpZ246IGxlZnQ7Ij48ZGl2IHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzdHlsZT0iZGlzcGxheTogZmxleDsgYWxpZ24taXRlbXM6IHVuc2FmZSBjZW50ZXI7IGp1c3RpZnktY29udGVudDogdW5zYWZlIGNlbnRlcjsgd2lkdGg6IDQ4cHg7IGhlaWdodDogMXB4OyBwYWRkaW5nLXRvcDogMTE0cHg7IG1hcmdpbi1sZWZ0OiA0NzFweDsiPjxkaXYgZGF0YS1kcmF3aW8tY29sb3JzPSJjb2xvcjogcmdiKDAsIDAsIDApOyAiIHN0eWxlPSJib3gtc2l6aW5nOiBib3JkZXItYm94OyBmb250LXNpemU6IDBweDsgdGV4dC1hbGlnbjogY2VudGVyOyI+PGRpdiBzdHlsZT0iZGlzcGxheTogaW5saW5lLWJsb2NrOyBmb250LXNpemU6IDEycHg7IGZvbnQtZmFtaWx5OiBIZWx2ZXRpY2E7IGNvbG9yOiByZ2IoMCwgMCwgMCk7IGxpbmUtaGVpZ2h0OiAxLjI7IHBvaW50ZXItZXZlbnRzOiBub25lOyB3aGl0ZS1zcGFjZTogbm9ybWFsOyBvdmVyZmxvdy13cmFwOiBub3JtYWw7Ij5Db25maXJtw6k8L2Rpdj48L2Rpdj48L2Rpdj48L2ZvcmVpZ25PYmplY3Q+PHRleHQgeD0iNDk1IiB5PSIxMTgiIGZpbGw9InJnYigwLCAwLCAwKSIgZm9udC1mYW1pbHk9IkhlbHZldGljYSIgZm9udC1zaXplPSIxMnB4IiB0ZXh0LWFuY2hvcj0ibWlkZGxlIj5Db25maXJtw6k8L3RleHQ+PC9zd2l0Y2g+PC9nPjwvZz48c3dpdGNoPjxnIHJlcXVpcmVkRmVhdHVyZXM9Imh0dHA6Ly93d3cudzMub3JnL1RSL1NWRzExL2ZlYXR1cmUjRXh0ZW5zaWJpbGl0eSIvPjxhIHRyYW5zZm9ybT0idHJhbnNsYXRlKDAsLTUpIiB4bGluazpocmVmPSJodHRwczovL3d3dy5kcmF3aW8uY29tL2RvYy9mYXEvc3ZnLWV4cG9ydC10ZXh0LXByb2JsZW1zIiB0YXJnZXQ9Il9ibGFuayI+PHRleHQgdGV4dC1hbmNob3I9Im1pZGRsZSIgZm9udC1zaXplPSIxMHB4IiB4PSI1MCUiIHk9IjEwMCUiPlRleHQgaXMgbm90IFNWRyAtIGNhbm5vdCBkaXNwbGF5PC90ZXh0PjwvYT48L3N3aXRjaD48L3N2Zz4=
```

Attention, nous ne représentons pas ci-dessus l'intégralité des distributions GNU/Linux ; il s'agit uniquement de distributions qualifiées de 'majeures' et de "plus connues" : nous ne faisons donc pas mention de distributions telles que Elementary, Pop!OS, et consort, afin de ne pas surcharger le croquis. L'idée est de visualiser rapidement quel type de distribution peut vous convenir :
- Si vous pouvez investir du temps, vous pouvez vous diriger vers un système Debian aux petits oignons voire une Arch Linux
- Si vous n'avez pas de temps à investir, dirigez vous plutôt vers des distributions considérées comme "stables", sur une base Ubuntu LTS par exemple, comme Linux Mint ou Zorin OS
- Si vous avez quelques compétences ou de solides connaissances, vous pourriez envisager un système à base de Gentoo
{.grid-list}

Vous êtes bien entendu libre d'adopter d'autres systèmes.

> Ci-dessous vous retrouvez nos recommandations suivant le profil. 
> 
> **Nous avons scindé en différents onglets : 
> -- L'onglet "Pour débuter" pour les débutants et nouveaux venus sur Linux qui ne souhaitent pas creuser le sujet. 
> -- L'onglet "Aller plus loin" pour ceux qui souhaitent apprendre le monde Linux et une liste de distributions correspondant aux profils moins débutants.
> -- L'onglet "Pour les initiés" afin d'obtenir des informations complémentaires et une liste de distributions correspondant aux profils initiés.**
{.is-warning}

## Tabs {.tabset}
### Pour débuter
Pour informations :
- Si votre PC ne dispose pas d'un processeur 64 bits, orientez-vous vers une distro compatible 32 bits, pour PC anciens, mentionnés dans la section suivante.


Vous venez de Windows ou de Mac OS, ici vous trouverez les 3 distributions que nous recommandons lorsque vous débutez sur Linux et que vous ne souhaitez pas forcément configurer finement votre système :

| Nom distro | URL | Commentaires | Forum d'entraide | Installation |
|----------|----------|----------|----------|----------|
| Linux Mint | [Site de Linux Mint](https://linuxmint.com/download.php) | **Téléchargez la version "Cinnamon Edition"**<br>Distribution fondée par le français Clément Lefebvre. <br>Elle est très stable et maintenue à jour très régulièrement ce qui en fait une des distros les plus appréciées. | [Forum Linux Mint](https://forums.linuxmint.com/) | Suivre notre [tutoriel](/tutoriels/mint) |
| Zorin OS | [Site de Zorin OS](https://zorin.com/os/download/) | **Téléchargez la version "Pro" ou "Core"**<br>Pour PC plutôt récents, mais surtout pour ceux qui viennent de Windows.<br>Il existe l'édition Pro pour soutenir le projet et qui apporte des fonctionnalités supplémentaires. | [Forum ZorinOS](https://forum.zorin.com/) | Suivre notre [tutoriel](/tutoriels/zorin) |
| Ubuntu LTS | [Site de Ubuntu-FR](https://www.ubuntu-fr.org/download/) | Une des distributions les plus connues...<br>Nous conseillons la branche LTS (Long Term Support) car elle amène une certaine stabilité et permet un support et des mises à jour jusqu'à 5 ans.<br>**Attention cepandant, nous sommes de plus en plus méfiant vis à vis de Canonical, l'éditeur d'Ubuntu, car cette entité pousse son système de paquet Snap, au détriment de Flatpak, ce qui est contraire à la philosophie du Libre ! Il s'agit d'un point d'attention à considérer.** | [Forum de Ubuntu](https://forum.ubuntu-fr.org/) | Suivre notre [tutoriel](/tutoriels/ubuntu) |
{.dense}

### Aller plus loin

Pour informations :
- Si votre PC ne dispose pas d'un processeur 64 bits, orientez-vous vers une distro compatible 32 bits.
- [ReactOS](https://fr.wikipedia.org/wiki/ReactOS) n'est PAS un système d'exploitation \*NIX (Linux, BSD...).

Pour aller plus loin sur la compréhension de ce qu'est un "système d'exploitation" :
- [Vidéo de "Tech SAMA"](https://invidious.snopyta.org/watch?v=xLhCOFWaY_M&listen=false) Regarder entre 00:35 minute et 02:49 minutes
- [Vidéo de "Salut les Noobs"](https://invidious.snopyta.org/watch?v=8PtLsftCC70) Regarder entre 00:13 minute et 02:53 minutes (à 02:42 "les distributions sont des ~~versions~~ de Linux" :arrow_right: entendre ici des variantes de GNU/Linux, pour ne pas entretenir de confusion avec les versions (itérations) de l'OS)
{.links-list}

#### Les types d'approche
Deux principales façons de gérer une distribution existent :
- Les distributions de type _Développement Continu_ ("Rolling Release")
- Les distributions de type _Stable_

**Rolling Release :**
Les distributions GNU/Linux qui adoptent un cycle de vie appelé "Rolling Release" sont en fait des OS qui ne figent aucune version, mais qui implémentent petit à petit des mises à jour et montent en version petit à petit.

La plus connue reste Arch Linux, mais il y en a d'autres comme Manjaro, Gentoo, PC Linux, SparkyLinux, etc. et maintenant CentOS (issu de Red Hat, qui vient très récemment de basculer en Rolling Release).

**Stable :**
Contrairement aux Rolling Releases, les autres distributions GNU/Linux adoptent un cycle de vie par versions : une fois une version jugée **mature**, elle est figée et fait l'objet d'un support (mises à jour) sur quelques années, avant de passer à une version ultérieure. Ce cycle utilise plusieurs "branches" (développement, test, stable) afin de juger la maturité de l'OS.

#### Les environnements de bureau
Comme vous le verrez dans les tableaux ci-après, la plupart des distributions sont livrées avec un ou plusieurs environnements de bureau qu'on appelle aussi **DE** pour *desktop environment*.

Le DE, en définitive, c'est l'environnement graphique dans lequel vous allez évoluer avec votre ordinateur afin d'effectuer les actions nécessaires (par exemple traitement de texte, paramétrage, création de dossier...). Certains ressemblent graphiquement à ceux que vous connaissez peut-être sous Windows ou MacOS, d'autres s'en éloignent.

Cette section a pour but de vous présenter les plus communs :

**Gnome :**
[Gnome](https://www.gnome.org/) (GNU Network Object Model Environment) est un environnement de bureau très populaire sur Linux. C'est l'environnement de bureau livré par défaut sur de nombreuses distributions comme Debian, Ubuntu ou Fedora. Il est développé par *The Gnome Project* et soutenu par la *Fondation Gnome*.

C'est un environnement de bureau qui nécessite quelques heures afin d'être pris en main, mais qui s'avère très agréable au quotidien dans son utilisation. C'est aussi l'environnement de bureau qui nécessite a priori le plus de ressources système, notamment de mémoire vive.

Il est recommandé d'avoir un équipement avec 4 Go de RAM au minimum, même si 8 Go est conseillé.

**KDE Plasma :**
[KDE Plasma](https://kde.org/) constitue avec Gnome les deux DE les plus utilisés sur GNU/Linux.

Il est certainement un des DE qui ouvre le maximum de portes à la personnalisation mais, en contrepartie, les menus sont plus denses et s'y retrouver n'est pas forcément facile au début.

Il est un peu plus léger que Gnome, mais nécessite tout de même que votre équipement soit équipé de 4 Go de RAM.

**Xfce :**
[Xfce](https://www.xfce.org/) (XForms Common Environment) est avant tout un environnement de bureau orienté performance, compact, et n'offre donc pas pléthore de personnalisation. Pouvant être installé sur beaucoup de distributions GNU/Linux, mais aussi BSD.

Xfce est un environnement à choisir pour les vieilles machines, car peu gourmand en ressources.

Il peut très bien tourner sur un équipement avec 2 Go de RAM.

**Cinnamon :**
Cinnamon est l'environnement développé principalement pour s'adapter sur la distro Linux Mint Cinnamon. Environnement très personnalisable, intuitif, et plutôt rapide même si ce n'est pas l'environnement le plus rapide et le moins gourmand.

**MATE :**
**Mate** (prononcé [maté]) **est l'environnement de bureau qui est dans la continuité de Gnome2** (qui ne ressemble plus du tout à Gnome3 et +).

**Ce bureau, très léger** (nécessite minimum 512 Mo de RAM, 2 Go recommandé) reste **très personnalisable**. À ce prix, les animations visuelles sont par défaut minimalistes ce qui peut rendre l’usage plus "brut", mais ce qui en fait **un outil redoutablement efficace**.

**Souvent par défaut, il est muni d'une barre haute avec des menus et des accès rapides ainsi qu'une "zone de notification", et d'une barre basse avec les fenêtres actuellement ouvertes.**
Mais **cela varie selon les distributions**. Par exemple, sur Linux Mint (avec bureau Mate), vous ne trouverez qu'une barre en bas à la "WindowsXP amélioré", avec un **menu principal** à gauche, puis quelques accès rapides, suivis des fenêtres ouvertes, et enfin la zone de notification à droite. Cet agencement est donc beaucoup plus compact.

**Ce bureau vous permet donc de faire ce que vous voulez : personnaliser les apparences, l’agencement des "tableaux de bord" (les barres contenant les menus, etc), les menus utilisés (menu unique, menu séparé), le thème, les icônes, etc.**

Par défaut, Mate intègre un minimum de logiciels : pour gérer les fichiers (Caja), un éditeur de texte (Pluma), un lecteur d’image et de PDF ainsi qu’un gestionnaire d’archive (pour lire/créer des zip, et autre format compressé). Mais vous pourrez compléter la liste autant que souhaité en y installant tous les autres logiciels que vous voulez en fonction de ce que propose votre distribution.

**Autres :**
D'autres environnements sont disponibles :
-   LXQt
-   LXDE
-   Unity
-   Trinity
-   Deepin
-   Enlightenment

Nous vous laissons aller voir leurs caractéristiques si vous êtes intéressés.

##### Les distributions

- Dans la première colonne, **en gras**, le nom des distributions majeures/historiques "mères", c.à.d. qu’énormément de distributions "filles" se basent dessus. Elles existent depuis longtemps ! [Pour en savoir plus](https://en.wikipedia.org/wiki/List_of_Linux_distributions).
- Dans la deuxième colonne, **en gras**, l'environnement de bureau par défaut de la distro.
- Dans la troisième colonne, une indication sur la base des distros.
{.grid-list}

> Avant de graver un CD/DVD ou de créer votre clé USB bootable, faites toujours une **[vérification de l'intégrité du fichier](/tutoriels/verifier-integrite)** que vous venez de télécharger.
{.is-warning}

| Nom distro | Environnements<br>de Bureau | Base | CPU | URL | Gestionnaires<br>de paquets |  Commentaires | Installation |
|----------|----------|----------|----------|----------|----------|----------|----------|
| Debian (Stable) | **Gnome**<br>KDE Plasma<br>Xfce<br>LxQt<br>Mate | Indépendant | 32/64 bits<br>ou ARM | [Avec seulement des logiciels libres](https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/)<br>[Avec logiciels non libres](https://cdimage.debian.org/cdimage/unofficial/non-free/cd-including-firmware/current-live/amd64/iso-hybrid/) | dpkg (.deb)<br>apt<br>Flatpak | Certainement la distribution la plus connue à ce jour, mais pas la plus simple à prendre en main et configurer, bien que l'équipe ait fait d'énormes progrès dans l'expérience utilisateur. | Suivre notre [tutoriel](/tutoriels/debian) |
| Pop!OS | Gnome COSMIC | Ubuntu LTS | 64 bits | [Site de Pop! OS](https://pop.system76.com/) | dpkg (.deb)<br>apt<br>Snap Store<br>Flatpak | Une belle distribution orientée multimédia, développeurs voire gaming, mais tout à fait convenable pour la bureautique.<br> La distro permet de plus de nativement chiffrer son disque ! | |
| Feren OS | KDE Feren | Ubuntu LTS | 64 bits | [Site de Feren OS](https://ferenos.weebly.com/) | dpkg (.deb)<br>apt<br>Snap Store<br>Flatpak | - | |
| OpenSUSE OS | **KDE Plasma**<br>Gnome<br>Xfce<br>LXDE | Indépendant | 64 bits | [Site de openSUSE OS](https://www.opensuse.org/) | Zypper<br>Yast<br>SoftwareManager | Une très belle distribution, qui aurait peut-être méritée son apparition dans la partie pour Débutant. Cela dit, son utilisation reste un peu austère à notre goût.<br> OpenSUSE est la distribution communautaire de la société allemande SuSE entreprise, l'une des plus anciennes distributions. Même si cette communauté porte plus d'intérêt à KDE, les deux autres environnements sont très bien gérés. Il existe 2 versions de OpenSUSE : **Tumbleweed** une version dite "Rolling Release" et **Leap**, une version "Fixed Release".<br>La particularité de OpenSUSE réside dans un logiciel créé pour cette distribution : Yast. Il permet de gérer un grand nombre de tâches de façon très simple et efficace. | Suivre notre [tutoriel](/tutoriels/opensuse-temb) |
| Linux Mint LMDE (Debian Edition) | **Cinnamon**<br>Mate<br>Xfce | Debian Stable | 32/64 bits | [Site de LMDE](https://linuxmint.com/download_lmde.php) | dpkg (.deb)<br>apt<br>MintInstall | Vous l'aurez compris, cette distribution aura pour base Debian stable et non Ubuntu. | |
| Fedora | Gnome Fedora | RedHat | 64 bits | [Site de Fedora](https://getfedora.org/fr/workstation/download/) | dnf<br>FedoraSoftwareCenter | Fedora est la distribution communautaire de la société RedHat. Ce sont eux qui apportent les plus importantes donations et contributions à Gnome pour le développement de l'environnement de bureau. | Suivre notre [tutoriel](/tutoriels/fedora) |
| Elementary OS | Pantheon | Ubuntu LTS | 64 bits | [Site de Elementary OS](https://elementary.io/) | dpkg (.deb) | Elementary propose un bureau calqué sur MacOS, pour ceux qui ne souhaitent pas être trop perdus entre le passage MacOS - Linux. | |
| Manjaro | **KDE Plasma**<br>Gnome<br>Xfce | Arch Linux / Indépendant | 64 bits | [Site de Manjaro OS](https://manjaro.org/download/) | AUR (option)<br>pacman | Nous conseillons de ne prendre que les versions officielles GNOME, KDE ou XFCE.<br>Notez que Manjaro est certes basée sur Arch Linux, mais développe son propre kernel/système.<br>*Attention avec l'activation des paquets AUR, qui tend à parfois poser des problèmes de dépendances allant même jusqu'au crash.* | Suivre notre [tutoriel](/tutoriels/manjaro) |
| Endeavour OS | **Xfce**<br>Gnome<br>KDE Plasma | Arch Linux | 64 bits | [Site de Endeavour OS](https://endeavouros.com/latest-release/) | pacman<br>AUR | Distribution qui se veut tournée vers le gaming sur Linux. | |
| Pure OS | **Gnome**<br>KDE Plasma | Debian | 64 bits | [Site de Pure OS](https://pureos.net/download/) | dpkg (.deb)<br>apt | Que des logiciels FOSS, distro conseillée par la FSF (Free Software Fondation) | |
| Solus OS | **Budgie**<br>Gnome<br>KDE Plasma<br>Mate | Indépendant | 64 bits | [Site de Solus](https://getsol.us/download/) | eopkg | Distribution créée "from scratch", c'est-à-dire de zéro. Distribution simple sans fioriture. | |
| PCLinux OS | **Xfce**<br>Mate<br>KDE Plasma | Indépendant | 64 bits | [Site de PCLinux OS](https://www.pclinuxos.com/) | apt<br>rpm | - | |
{.dense}

### Pour les initiés
Nous ne décrivons pas ici les types d'approche (rolling release ou stable) et les environnements de bureau, nous estimons que vous avez déjà connaissance de ces sujets.

*Dans le cas contraire, rendez vous dans l'onglet "Aller plus loin..."*.

##### Les distributions

- Dans la première colonne, **en gras**, le nom des distributions majeures/historiques "mères", c.à.d. qu’énormément de distributions "filles" se basent dessus. Elles existent depuis longtemps ! [Pour en savoir plus](https://en.wikipedia.org/wiki/List_of_Linux_distributions).
- Dans la deuxième colonne, **en gras**, l'environnement de bureau par défaut de la distro.
- Dans la troisième colonne, une indication sur la base des distros.
{.grid-list}

> Avant de graver un CD/DVD ou de créer votre clé USB bootable, faites toujours une **[vérification de l'intégrité du fichier](/tutoriels/verifier-integrite)** que vous venez de télécharger.
{.is-warning}

| Nom distro | Environnements<br>de Bureau | Base | CPU | URL | Gestionnaires<br>de paquets |  Commentaires |
|----------|----------|----------|----------|----------|----------|----------|
| Debian (Testing) | **Gnome**<br>KDE Plasma<br>Xfce<br>LxQt<br>Mate | Indépendant | 32/64 bits<br>ou ARM | [Avec seulement des logiciels libres](https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/)<br>[Avec logiciels non libres](https://cdimage.debian.org/cdimage/unofficial/non-free/cd-including-firmware/current-live/amd64/iso-hybrid/) | dpkg (.deb)<br>apt<br>Flatpak | La version la plus à jour de Debian, mais qui peut potentiellement souffrir de quelques bugs. Ces bugs peuvent plus ou moins être gérés pour ceux qui maîtrisent l'environnement linux.<br><br>**Installation** : suivre notre [tutoriel](/tutoriels/debian-testing) |
| Arch Linux | [A choisir lors de l'installation](https://wiki.archlinux.org/title/Desktop_environment#Officially_supported) | Indépendant | 32/64 bits et ARM | [Site de Arch Linux](https://archlinux.org/download/) | pacman<br>AUR | Arch est rapide et légère. Elle est basée sur le principe de KISS (Keep It Simple, Stupid), c'est-à-dire de ne pas compliquer les choses. Ceci dit, nous la conseillons plutôt aux utilisateurs avancés car il devra chercher à comprendre son fonctionnement pour pouvoir l'utiliser et la maintenir. Elle met à disposition ses dépôts uniques nommés AUR ([Arch User Repository](https://wiki.archlinux.org/title/Arch_User_Repository_(Fran%C3%A7ais))) son [excellent wiki](https://wiki.archlinux.org/title/Main_page_(Fran%C3%A7ais)) et sa grande communauté. |
| Alpine Linux | **Gnome**<br>Xfce<br>KDE Plasma<br>Mate<br>LxQt | Indépendant | 32/64 bits et ARM | [Site de Alpine Linux](https://alpinelinux.org/downloads/) | custom | Une distro qui met l'accent sur la sécurité. Elle permet l'utilisation de logiciels système robustes (initrc, LibreSSL, etc...) au contraire de la plupart des distros mainstreams, surtout Desktop.<br>*La distro mobile PostMarketOS est notamment basée sur Alpine Linux.* |
| Qubes OS | Xfce | Fedora et Debian | 64 bits | [Site de Qubes OS](https://www.qubes-os.org/downloads/) | dnf<br>apt | Distribution orientée sécurité et anonymat par isolation via virtualisation Xen et un kernel durci.<br>L'anonymat se fait via une machine [Whonix](https://www.whonix.org). |
| Gentoo | Gnome<br>Xfce<br>KDE Plasma<br>Mate<br>LXDE | Source Based | 32/64 bits et ARM | [Site de Gentoo](https://www.gentoo.org/downloads/) | emerge | Une distribution qui vous permettra de compiler les sources pour votre machine afin de maîtriser l'ensemble du système ; ceci permet d'adapter et optimiser tous les logiciels à votre machine. |
| Caclulate Linux | **Cinnamon**<br>Xfce<br>KDE Plasma<br>Mate<br>LxQt | Gentoo | 64 bits | [Site de Calculate Linux](https://wiki.calculate-linux.org/download) | portage | Plus de 12000 paquets pré-compilés sont fournis pour toutes les applications de base. Plus simple et rapide à installer que Gentoo mais 100% compatible. |
| Slackware | Blackbox<br>Fluxbox<br>Xfce<br>KDE Plasma<br>FVWM<br>Wmaker | Source Based | 64 bits et ARM | [Site de Slackware](https://download.liveslak.org/latest/) | custom | C'est la plus ancienne distro, plutôt complexe à installer et à utiliser au quotidien ! |
| Void Linux | Xfce | Source Based | 32/64 bits et ARM | [Site de Void Linux](https://voidlinux.org/download/) | custom | - |
| LFS (Linux From Scratch) | n/a | Source Based | 32/64 bits et ARM | [Site de LFS](https://www.linuxfromscratch.org/) | XBPS | LFS est le nom du livre de Gerard Beekmans, ce n'est pas vraiment une distro, mais plus la recette de cuisine pour en construire une ! |
{.dense}

## Les distributions spécifiques
##### Tabs {.tabset}
###### PC Anciens

Vous trouverez ci-après une liste de distributions pour les machines anciennes.
Généralement, les PC sortis avant 2010 auront un processeur 32 bits ; ceux d'après 2010, un CPU 64 bits.

> Vous pouvez vérifier [ici](https://itsfoss.com/32-bit-64-bit-ubuntu/) le jeu d'instructions supportés le CPU de votre PC.
{.is-info}

| Nom distro | Environnements<br>de Bureau | Base | CPU | URL | Gestionnaires<br>de paquets |  Commentaires |
|----------|----------|----------|----------|----------|----------|----------|
| Zorin OS (Lite) | Xfce | Ubuntu LTS | 64 bits | [Site de Zorin OS](https://zorin.com/os/download/) | dpkg (.deb)<br>apt<br>Zorin SoftwareStore<br>Snap Store<br>Flatpak | Pour PC anciens qui ne peuvent pas faire tourner d'autres distributions. Seule la version 64 bits est maintenue ! |
| Linux Lite | Xfce | Ubuntu LTS | 64 bits | [Site de Linux Lite](https://www.linuxliteos.com/download.php#current) | dpkg (.deb) | Pour PC anciens mais avec un CPU 64 bits seulement. |
| MX Linux | **Xfce**<br>KDE Plasma<br>Fluxbox | Debian / AntiX | 32/64 bits | [Site de MXLinux](https://mxlinux.org/download-links/) | dpkg (.deb)<br>apt | Distribution légère. |
| Q4OS | **Trinity DE**<br>KDE Plasma | Debian | 32/64 bits | [Site de Q4OS](https://q4os.org/downloads1.html) | Q4OS SoftwareCentre | Pour PC très anciens. |
| AntiX | Fluxbox<br>IceWM<br>JWM | Debian | 32/64 bits | [Site de AntiX](https://antixlinux.com/download/) | pacman | Pour PC très anciens. |
{.dense}

###### Pour Gaming

Des distributions sont développées spécifiquement pour optimiser le système et sa gestion du matériel afin d'apporter une stabilité et une puissance accrue lors de l'utilisation en Gaming, Streaming ou création de contenus multimédia.

Une question revient souvent chez les débutants prêts à passer à Linux : peut-on jouer à des jeux vidéos ?

Il est clair que pendant longtemps Windows et MacOS étaient les plateformes privilégiées pour jouer. C'était possible avec Wine mais ça freinait quand même certaines personnes pour passer au libre. Maintenant, les choses sont devenues beaucoup plus simples et la réponse est oui, avec cependant quelques efforts...

**Wine & Consorts** :
Comment faire fonctionner un programme Windows (dont il n'existe pas de version Linux) sur GNU/Linux ?

Pour pouvoir faire fonctionner un programme Windows (dont il n'existe pas de version Linux) sur GNU/Linux, vous allez devoir **simuler** un environnement Windows, ou autrement dit implémenter une interface technique de type *windows*.

[Wine](https://www.winehq.org/) est crée en 1983 et c'est un acronyme : Wine Is Not a Emulator. C'est un logiciel qui reprend l'implémentation de Windows pour lancer des jeux vidéos sur GNU/Linux. En résumé, vous avez Linux mais vous avez une interface Windows qui vous permet de jouer à des jeux disponibles seulement sur Windows. 

Il est tout à fait possible d'utiliser Wine seul, sans autre programme pour vous aider. C'est très bien pour des utilisateurs confirmés, mais pour les débutants ou utilisateurs standards, nous allons préférer une "surcouche" avec une interface graphique claire et des fonctionnalités construites pour vous. 

Plusieurs programmes permettent de faire cela. Tous ceux cités dans cette liste utilisent en fait comme socle **Wine**, devenu le *saint-graal* ( :) ) pour tous ceux qui cherchent à utiliser des programmes Windows sur GNU/Linux :

- [Bottles](https://usebottles.com/) : Vous permet très facilement de faire fonctionner un programme Windows sur GNU/Linux avec une interface simple et efficace. Configurable selon vos besoins. Chaque application est confinée dans une "bouteille".

- [Lutris](https://lutris.net/) : Lutris permet à la base de faire fonctionner des jeux, mais peut être utilisé pour d'autres programmes. L'interface graphique est claire et épurée, quelques fonctionnalités de bases facilement repérables, et bonnes possibilités de configuration. Si vous jouez, il vous sera très facile d'installer des milliers de jeu en quelques clics sans connaissance technique.

- [PlayOnLinux](https://www.playonlinux.com/fr/) : PlayOnLinux est un logiciel libre basé sur Wine. C'est le même principe que Lutris, son ancêtre en quelque sorte. Efficace et relativement simple (moins que Lutris) et interface graphique potable.

- [CrossOver](https://www.codeweavers.com/) : Version professionnelle et payante de Wine. Utile si vous souhaitez faire tourner un programme et que vous rencontrez quelques difficultés. 30 jours d'essai gratuit, après c'est payant. Toutes les modifications de Wine apportées par CodeWeavers sont en retour utilisables par la communauté, conformément à la licence LGPL. CodeWeavers emploie la grande majorité des développeurs de Wine.

- [Proton](https://www.protondb.com/) : C'est un fork de Wine utilisé par Steam pour faire tourner une grande partie de ses jeux. Vous ne pouvez l'utiliser que pour Steam et ses jeux. Il fonctionne très bien, et est de plus en plus performant, et ça ne risque pas de s’arrêter avec la sortie de la Steam Deck. Pour voir les milliers de jeux compatibles, c'est ici :

- [Playnite](https://playnite.link/) est une bibliothèque de jeux unifiée avec une interface simple et esthétique.

**Steam :**
Lorsqu'on parle de jeux vidéo, on pense rapidement à **Steam**.

[Steam](https://store.steampowered.com/?l=french) est une plateforme de jeux vidéos. Elle dispose d'un magasin recensant de dizaines de milliers de jeux. Cette plateforme a été créée en 2003 par Valve Corporation (dirigée par Gabe Newell) et l'entreprise est connue pour ses jeux phares tels que *Half Life*, *Team Fortress* et *Counter-Strike* pour les connaisseurs.

En 2013, Steam a été adapté pour les systèmes GNU/Linux. Les utilisateurs pouvaient jouer à quelques jeux comme *Left 4 Dead*.

En 2015, Valve sort officiellement SteamOS, basé sur Debian dans un premier temps puis finalement sur un dérivé de Arch Linux.

En 2022, ils sortent la Steam Deck.

_Quelques articles complémentaires :_
- [Wine](https://fr.wikipedia.org/wiki/Wine)
- [Steam](https://fr.wikipedia.org/wiki/Steam)
- [SteamOS](https://fr.wikipedia.org/wiki/SteamOS)

---
_La communauté GLF :_

Une communauté de Gamers Linux (Fr, GLF) a vu le jour. Ils proposent des tutoriels vidéos, des challenges d'installation de distributions et d'optimisation afin de jouer sur Linux dans les meilleures conditions, des scripts facilitant la post-installation des kernels et pilotes, ainsi qu'un support technique bénévole en cas de besoin (uniquement sur Discord). Et en français, assez rare pour être souligné !
- [La chaine de Vinceff](https://inv.vern.cc/channel/UCu6YaQSJf6gUzAoszZniJ8g), qui couvre tous les besoins des profils débutants à initiés.
- [La chaine de CardiacMan](https://inv.vern.cc/channel/UC7VqJVFvk75-B0uKg4MWfpw), très porté sur Arch Linux avec pédagogie.
- [La chaine de AirMax](https://inv.vern.cc/channel/UCJEWcPNeBPtP8zX2k9lS-iA), contenu en anglais.
- Présence des développeurs de kernels et distros optimisées (TKG par ex.)
- [Le discord GLF](https://discord.gg/8J8vQPEG)

> **Attention** : le dernier lien est un lien "discord", cette communauté n'étant présente que sur cette plateforme. Il est possible pour les plus libristes d'entre vous d'utiliser un client alternatif ou d'isoler l'application afin d'y accéder et limiter la télémétrie, cf. notre article sur les [alternatives](/debutant/logiciel-alternative-libre).
{.is-info}

Certains développeurs de cette communautés mettent à disposition des scripts de post-installation qui vous permettront de vous faciliter la tâche pour configurer votre distribution :
- [Pour Arch Linux](https://github.com/Cardiacman13/Architect)
- [Pour Debian](https://github.com/Xdavius/postinstall-debian)
- [Pilotes Nvidia](https://github.com/Cardiacman13/NUDI) (toutes distributions)

**Les distros classiques :**

Théoriquement, toute distribution est capable de faire tourner les jeux vidéos, pour peu que celle-ci soit correctement configurée. En effet certains outils fonctionnent mieux suivant le paquet utilisé (deb, snap, flatpak) et suivant les distribution...

Nous répertorions les distributions sur lesquelles la configuration est la plus simple :

| Nom distro | DE à privilégier | Base | CPU | URL | Gestionnaires<br>de paquets |  Commentaires |
|----------|----------|----------|----------|----------|----------|----------|
| Linux Mint | Cinnamon | Ubuntu LTS | 64 bits | [Site de Linux Mint](https://linuxmint.com/download.php) | dpkg (.deb)<br>apt<br>MintInstall<br>Flatpak | Cette distribution est tellement stable que vous pourrez très bien partir sur une base Mint, puis installer les outils de gaming, Steam, Lutris, etc. et la plupart des jeux tourneront ! <br>**Néanmoins sur des configurations récentes, cette distribution n'exploitera pas tout le potentiel des composants CPU et graphique, un compromis à faire !** |
| Kubuntu | KDE Plasma | Debian Testing + Ajouts Canonical | 64 bits | [Site de Ubuntu-FR](https://www.ubuntu-fr.org/download/) | dpkg (.deb)<br>apt<br>Snap Store<br>Flatpak | Nous conseillons ubuntu et son DE KDE qui d'après certains tests permettent d'obtenir de bonnes performances en gaming. |
| OpenSuse TW | KDE Plasma | Indépendant | 64 bits | [Site de openSUSE OS](https://www.opensuse.org/) | Zypper<br>Yast<br>Flatpak | Une distribution (sa version rolling, Tembleweed) qui reste plutôt stable et fournit de bons résultats.<br>**Cela dit pour des profils intermédiaire.** |
| Arch Linux | KDE Plasma ou GNOME | Indépendant | 32/64 bits | [Site de Arch Linux](https://archlinux.org/download/) | pacman<br>AUR<br>Flatpak | Arch est rapide et légère et peut tout à fait être configurée aux petits oignons pour du Gaming.<br>**Cela nécessite tout de même d'être sur un profil plutôt initié.** |
{.dense}

**Les distros optimisées :**

Quelques distributions se concentrent sur l'aspect Gaming. Elles viennent avec un kernel modifié et des embarquent des pilotes récents, afin d'assurer une compatibilité avec tous les matériels sur le marché.

| Nom distro | DE à privilégier | Base | CPU | URL | Gestionnaires<br>de paquets |  Commentaires |
|----------|----------|----------|----------|----------|----------|----------|
| Nobara | Gnome ou KDE Plasma | Fedora | 64 bits | [Site de Nobara](https://nobaraproject.org/download-nobara/) | dnf | Nobara est l'une des distributions les plus prometteuses pour le gaming, le streaming et la création de contenus. Elle est cependant assez jeune mais évolue vite et possède déjà un bon socle d'utilisateurs. Basée sur le `kernel-zen` modifié et optimisé.<br>**Vous trouverez cependant certains jeux qui ne tourneront pas sans configuration préalable. Pour ce faire, il conviendra de s'appuyer sur le site [ProtonDB](https://www.protondb.com/).** |
| Garuda | KDE Plasma | Arch Linux | 64 bits | [Site de Garuda](https://garudalinux.org/downloads.html) | pacman | Distribution qui se veut tournée vers le gaming sur Linux. Basée sur le `kernel-zen` ou le `kernel-amd` (pour les possesseurs de matériels AMD).<br>**Vous trouverez également ici certains jeux qui devront être configurés grâce à [ProtonDB](https://www.protondb.com/).** |
{.dense}

**Les Kernels Gaming :**

Nous fournissons ici une solution différente : l'idée est d'installer une distribution standard, généralement basée sur Ubuntu ou Arch, puis d'installer un kernel GNU/Linux optimisé pour le Gaming. Il en existe quelques-uns que nous listons ci-après :

| Nom du Kernel | URL | Commentaires |
|----------|----------|----------|
| Liquorix | [Site de Liquorix](https://liquorix.net/) | Kernel pouvant être installé sur base Ubuntu ou Arch Linux.<br>**Une ligne de commande est nécessaire uniquement !** |
| Linux TKG | [Site de TKG](https://github.com/Frogging-Family/linux-tkg) | Ce n'est pas à proprement parlé un kernel, mais il s'agit d'un outil qui permet de patcher le kernel de votre distribuion afin de l'optimiser pour le gaming.<br>**Peut-être un peu plus complexe à mettre en place.**|
| XanMod | [Site de XanMod](https://xanmod.org/) | XanMod s'installe uniquement sur une distribution avec une base Debian ou Ubuntu.<br>**Quelques lignes de commande sont nécessaires pour utiliser ce kernel.**<br>_Attention_ : il est nécessaire de sélectionner le kernel Xanmod-RT pour le gaming. |
{.dense}

> Ces kernels s'installent plus ou moins simplement grâce à une ou plusieurs lignes de commande.
> 
> Mais attention, cela ne dispense pas d'installer et gérer convenablement les pilotes pour les cartes graphiques (surtout celles venant de Nvidia).
{.is-warning}


###### Pour MacOS

| Nom distro | Environnements<br>de Bureau | Base | CPU | URL | Gestionnaires<br>de paquets |  Commentaires |
|----------|----------|----------|----------|----------|----------|----------|
| Asahi Linux | - | Indépendant | 32/64 bits et ARM | [Site de Asahi Linux](https://asahilinux.org/) | custom | Asahi est plutôt jeune, et vise à porter Linux sur du matériel Apple à partir de 2020 (et les puces M1). **Pour les versions datant d'avant 2020 (et disons depuis 2012/2013), donc avec du matériel Intel, une distribution Linux standard (dans les tableaux ci-avant) sera installable sans souci.** |
{.dense}

###### Pour BSD

Il existe aussi, pour les plus curieux, des distros basées un autre noyau que Linux : le [noyau BSD](https://fr.wikipedia.org/wiki/Berkeley_Software_Distribution) (Berkeley Software Distribution) qui est un OS dérivé de UNIX créé à l'origine par l'université de Berkeley.

Si vous voulez tester et pourquoi pas adopter ce type d'OS, nous vous conseillons de commencer par [GhostBSD](https://fr.wikipedia.org/wiki/GhostBSD) car il est simple à installer et propose 2 environnements de bureau complets : MATE et XFCE.
Plus d'informations sur le [wiki de GhostBSD](https://wiki.ghostbsd.org/index.php/GhostBSD).

###### Pour Serveur

Généralement sur serveur, il n'y aura pas de DE installé. Nous vous recommandons d'utiliser des distributions Stable : sur un serveur, c'est la stabilité et un support long terme qui est recherché.

Les distributions que nous avons sélectionnées, classées par famille, avec **en gras les distros que nous conseillons** :

- [**Debian Stable**](https://www.debian.org/releases/stable/index.fr.html) : **Extrêmement stable dûe à son cycle de développement très robuste et éprouvé depuis plus de 30 ans !** Maintenance assurée pendant 5 ans gratuitement via la [prise en charge à long terme LTS](https://wiki.debian.org/fr/LTS). Il est possible d'obtenir 5 ans supplémentaires en payant pour accéder au [programme ELTS](https://wiki.debian.org/fr/LTS/Extended) de la société [Freexian](https://freexian.com/).
:arrow_right: **Nous recommandons** et vous proposons un tutoriel d'installation [Serveur sous Debian Stable](/tutoriels-serveur/serveur-debian-stable)
- [**Ubuntu Server LTS**](https://ubuntu.com/download/server) : Même si nous préférons Debian à Ubuntu sur serveur, il est à noter que **_Ubuntu Server LTS_ peut être très intéressant sur serveur pour les raisons suivantes** :
  - [Support de 5 ans par défaut sur la branche LTS](https://ubuntu.com/about/release-cycle).
  - depuis 2023, on peut l'étendre à 5 ans supplémentaires "gratuitement" jusqu'à 5 machines via le programme [Ubuntu Pro](https://ubuntu.com/pro/tutorial).
  - Ubuntu Pro apporte aussi la possibilité de mettre à jour le noyau Linux sans reboot grâce au service [LivePatch](https://ubuntu.com/security/livepatch), très intéressant pour les serveurs critiques devant assurer un uptime H24 !
  - Il existait une [version minimale `mini.iso` de Ubuntu Server LTS](http://cdimage.ubuntu.com/netboot/) qui était particulièrement intéressante mais qui a été abandonnée depuis Ubuntu 18.04 LTS. Récemment, [il a été décidé de la remettre officiellement à disposition pour les futures versions](https://www.omgubuntu.co.uk/2023/02/ubuntu-mini-iso-redux) !
  - Propose, en plus du support de la communauté, un support payant commercial.
  
- [**AlmaLinux**](https://almalinux.org/) : RedHat proposait une version communautaire CentOS qui était beaucoup utilisée. Depuis peu, ils ont modifié CentOS en une rolling release (CentOS Stream). C'est pourquoi la communauté a crée un fork 100% Compatible avec RHEL. **AlmaLinux est une excellente alternative à Red Hat Enterprise Linux** avec un suivi très rapide et strict.
- [RockyLinux](https://rockylinux.org/) : Quasiment identique à AlmaLinux mais maintenue par une autre communauté. **Nous ne la recommandons pas car ils sont moins réactifs** que AlmaLinux et ainsi les mises à jour de sécurité, par exemple, ont souvent plusieurs jours, voire semaines, de retard par rapport à Alma.
- [**OpenSUSE Leap**](https://get.opensuse.org/leap/) : **Sur serveur, n'utilisez _que la version LEAP de OpenSUSE_**. OpenSUSE propose de nombreux outils pour simplifier l'administration, **intéressant pour les débutants**. Attention cependant car [le support ne dure que 18 mois](https://endoflife.date/opensuse), donc vous devrez régulièrement mettre à niveau votre serveur.
- [Arch Linux](https://wiki.archlinux.org/title/Installation_guide_(Fran%C3%A7ais)) : Arch Linux est **extrêmement modulaire et personnalisable**, dû à son processus d'installation. C'est pourquoi, il est tout à fait possible de l'utiliser sur un serveur. Cependant attention : Arch est une rolling release et demandera une attention particulière pour sa maintenance !

> _Pour un particulier_ nous ne conseillons pas l'utilisation de Red Hat Enterprise Linux (RHEL), Oracle Linux, SUSE Linux Enterprise qui sont payantes, proposent un support commercial et qui sont plutôt destinées aux entreprises.
{.is-warning}

> Vous retrouverez les procédures d'installation sous la rubrique "Tutoriels Serveur" tout en bas du menu de gauche.
{.is-info}

# Après l'installation...

## Sécuriser son système

Après avoir installé votre distribution, il sera important de bien sécuriser le système.

- Pour sécuriser simplement le système dans un premier temps, se référer à ce [tutoriel](/tutoriels/distro-protect). 
- Pour ceux qui cherchent à sécuriser un maximum leur système et afin de vous guider dans son durcissement, rendez-vous sur ce [tutoriel](/tutoriels/distro-protect-hardening).
{.grid-list}

## Améliorer sa vie privée

- Pour choisir un VPN, se référer à cet [article](/debutant/vpn-tor).
- Pour choisir d'orienter ses DNS, se référer à cet [article](/debutant/dns).
- Pour améliorer son hygiène numérique, se référer à cet [article](/hygiene-numerique).
{.grid-list}

## Trouver ses applications

Afin de créer votre environnement de travail, il est bien sûr primordial de trouver les outils du quotidien, qui pourraient remplacer vos outils fermés ou peu respectueux de votre vie privée.

Pour bien débuter avec les applications classiques, voici les articles qui vous guideront dans votre choix :
- Pour choisir votre navigateur internet, se référer à cet [article](/debutant/navigateurs).
- Pour choisir votre moteur de recherche, se référer à cet [article](/debutant/moteurs-recherche).
{.grid-list}

Pour le reste, bien souvent, les applications de base sont déjà installées (ex. : LibreOffice pour la suite bureautique, VLC pour le lecteur vidéo, etc.) sur la distro et peuvent tout à fait convenir, mais si vous utilisez des applications différentes ou souhaitez faire le tour de toutes les alternatives à vos outils du quotidien, rendez vous ici :

- Trouver une [alternative "libre"](/debutant/logiciel-alternative-libre) à vos outils.
{.grid-list}

---
![CC BY-NC-SA](/by-nc-sa.png =9%x){.align-right} *Contributeur(s): Ayo, marmotte et Theudric*