# Le Projet

Depuis plusieurs années, nous avons rassemblé une communauté autour de la thématique large et impérieuse de la libération numérique, qui comptabilise aujourd'hui plusieurs milliers de membres.

Notre groupe Telegram "Numérique Libre & Résilient" aide notamment les néophytes à passer d'un système propriétaire sur ordinateur, téléphone, tablette, nano-PC, etc. à un système plus vertueux et respectueux de ses utilisateurs et de leurs données personnelles.

L'idée de ce wiki est de proposer une liste d'articles et de tutoriels pour accompagner toute personne souhaitant améliorer son environnement numérique et tendre vers sa libération numérique.

# Configuration à reporter
## index.html
```html
<link rel="icon" type="image/png" href="/favicon-32x32.png">
```

## style.css
```css
.june-address {
  overflow: auto!important;
  padding-top: .3em!important;
  padding-bottom: .5em!important
}
.red-text {
  color: red
}
.blue-text {
  color: #00f
}
.language-brainfuck {
  background-color: #3a3154!important;
  text-shadow: none!important
}
.language-brainfuck > code[class*=language-] > span[class*=token] {
  color: #d3d3d3!important
}

@media (min-width:1000px) {
  .frame-style {
    width: 700px;
    height: 380px
  }
}
@media (max-width:999px) {
  .frame-style {
    width: 370px;
    height: 200px
  }
}
```

# Utils - Conversion fichiers
CONVERSION MEDIAWIKI - MARKDOWN :
```bash
pandoc -f mediawiki -t markdown_strict --wrap=preserve XXXXXXXXXXXXXXXX.wiki -o XXXXXXXXXXXXXXXX.md
```
