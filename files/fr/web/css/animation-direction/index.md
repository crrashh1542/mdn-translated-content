---
title: animation-direction
slug: Web/CSS/animation-direction
---

{{CSSRef}}

La propriété **`animation-direction`** indique si les cycles de l'animation doivent être joués dans le sens inverse et/ou de façon alternée.

{{InteractiveExample("CSS Demo: animation-direction")}}

```css interactive-example-choice
animation-direction: normal;
```

```css interactive-example-choice
animation-direction: reverse;
```

```css interactive-example-choice
animation-direction: alternate;
```

```css interactive-example-choice
animation-direction: alternate-reverse;
```

```html interactive-example
<section class="flex-column" id="default-example">
  <div id="example-element"></div>
  <button id="play-pause">Play</button>
</section>
```

```css interactive-example
#example-element {
  animation-duration: 3s;
  animation-iteration-count: infinite;
  animation-name: slide;
  animation-play-state: paused;
  animation-timing-function: ease-in;
  background-color: #1766aa;
  border-radius: 50%;
  border: 5px solid #333;
  color: white;
  height: 150px;
  margin: auto;
  margin-left: 0;
  width: 150px;
}

#example-element.running {
  animation-play-state: running;
}

#play-pause {
  font-size: 2rem;
}

@keyframes slide {
  from {
    background-color: orange;
    color: black;
    margin-left: 0;
  }
  to {
    background-color: orange;
    color: black;
    margin-left: 80%;
  }
}
```

```js interactive-example
"use strict";

window.addEventListener("load", () => {
  const el = document.getElementById("example-element");
  const button = document.getElementById("play-pause");

  button.addEventListener("click", () => {
    if (el.classList.contains("running")) {
      el.classList.remove("running");
      button.textContent = "Play";
    } else {
      el.classList.add("running");
      button.textContent = "Pause";
    }
  });
});
```

Généralement, on passera par la propriété raccourcie {{cssxref("animation")}} qui permet de définir les différentes propriétés liées aux animations avec une déclaration.

## Syntaxe

```css
/* Valeurs avec un mot-clé */
animation-direction: normal;
animation-direction: reverse;
animation-direction: alternate;
animation-direction: alternate-reverse;

/* Gestion de plusieurs animations */
animation-direction: normal, reverse;
animation-direction: alternate, reverse, normal;

/* Valeurs globales */
animation-direction: inherit;
animation-direction: initial;
animation-direction: unset;
```

### Valeurs

- `normal`
  - : L'animation est jouée dans le sens normal à chaque cycle. Autrement dit, au début de chaque cycle, l'animation est initialisée dans l'état de début. C'est le réglage par défaut.
- `reverse`
  - : L'animation est jouée dans le sens inverse à chaque cycle. Au début de chaque cycle, l'animation reprend depuis l'état de fin.
- `alternate`
  - : La lecture de l'animation se fait de façon alternée et change de sens à chaque cycle en commençant par le sens normal. Lorsque le sens est inversé, les étapes de l'animation sont effectuées de façon inversée et les fonctions de progression (_timing functions_) sont également inversées (`ease-in` sera ainsi remplacée par `ease-out`). Le premier cycle se fait dans le sens normal, le deuxième dans le sens inverse et ainsi de suite.
- `alternate-reverse`
  - : La lecture de l'animation se fait de façon alternée et change de sens à chaque cycle en commençant par le sens inverse (cf. ci-avant). Le premier cycle se fait dans le sens inverse, le deuxième dans le sens normal et ainsi de suite.

> [!NOTE]
> Lorsqu'on utiliser plusieurs valeurs, séparées par des virgules, pour une propriété `animation-*`, selon leur quantité, elles seront différemment affectées aux animations définies par {{cssxref("animation-name")}}. Pour plus d'informations, voir : paramétrer [les valeurs des propriétés pour plusieurs animations](/fr/docs/Web/CSS/CSS_animations/Using_CSS_animations).

## Définition formelle

{{CSSInfo}}

## Syntaxe formelle

{{CSSSyntax}}

## Exemples

### CSS

```css
p {
  animation-duration: 5s;
  animation-name: glissement;
  animation-iteration-count: infinite;
}

.aller {
  animation-direction: normal;
}

.retour {
  animation-direction: reverse;
}
@keyframes glissement {
  from {
    margin-left: 100%;
    width: 300%;
  }

  to {
    margin-left: 0%;
    width: 100%;
  }
}
```

### HTML

```html
<p class="aller">
  La Chenille et Alice se considérèrent un instant en silence. Enfin la Chenille
  sortit le houka de sa bouche, et lui adressa la parole d’une voix endormie et
  traînante.
</p>

<p class="retour">
  «&nbsp;Revenez,&nbsp;» lui cria la Chenille. «&nbsp;J’ai quelque chose
  d’important à vous dire&nbsp;!&nbsp;»
</p>
```

### Résultat

{{EmbedLiveSample("Exemples","300","200")}}

## Spécifications

{{Specifications}}

## Compatibilité des navigateurs

{{Compat}}

## Voir aussi

- [Manipuler les animations CSS](/fr/docs/Web/CSS/CSS_animations/Using_CSS_animations)
- {{domxref("AnimationEvent", "AnimationEvent")}}
