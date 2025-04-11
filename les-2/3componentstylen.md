---
has_toc: false
nav_exclude: true
layout: default
title: Componenten Stylen
---
# Componenten Stylen
Er zijn verschillende manieren om in React styling te gebruiken. Onder andere de volgende drie:

* 1 Import CSS
* 2 CSS modules
* 3 JavaScript style objecten
* 4 CSS library (zoals Tailwind of Bootstrap)

## Globale CSS
Deze hebben jullie al gebruikt. Boven in het project staat bijvoorbeeld `import './App.css'`, om de CSS te importeren.
De CSS regels zijn globaal en beinvloeden alle componenten die dezelfde class of tag gebruiken. Dus je kan maar 1x `.card` aanpassen bij globale code, als je verschillende soorten *Card* componenten hebt, moet je ze allemaal een andere classname geven. Een voordeel is wel dat het heel erg veel lijkt op gewoon HTML/CSS.

## CSS Modules
Deze manier van CSS werkt anders dan de globale CSS, en dus anders dan gewoon HTML en CSS. Op deze manier heeft alleen de componenten in het bestand dat de module importeert deze stijl. 
```js
import styles from "./MyComponent.module.css";

function MyComponent() {
  return <h1 className={styles.title}>Hello, Scoped CSS!</h1>;
}
```

De class namen worden automatisch uniek gemaakt, zodat je verschillende *card* classes zou kunnen hebben, mocht je dat willen. Belangrijk is dat jouw css bestand niet alleen eindigt met `.css`, maar met **.module.css**. 

## Javascript Style-Objecten
Dit is eigenlijk *inline* style, zoals ook in HTML gebruikt wordt, alleen worden er Javascript objecten gebruikt.
```js
function MyComponent() {
  return <h1 style={{ color: "red", fontSize: "24px" }}>Hello, Inline!</h1>;
}
```

## CSS Library 
Net als in Laravel of HTML kan je CSS libraries gebruiken.
```js
function App() {
  return (
    <div className="min-h-screen bg-gray-100 flex flex-col items-center justify-center">
      <h1 className="text-4xl font-bold text-blue-600 mb-4">Welkom bij React + Tailwind</h1>
    </div>
  );
}
```

# About Me stylen
Maak een nieuw bestand aan genaamd `AboutMe.css`.
Style jouw AboutMe component. Kies zelf of je een grid of flexbox gebruikt om de elementen naast elkaar te krijgen.
Kleur en margins mag je ook zelf bedenken.

