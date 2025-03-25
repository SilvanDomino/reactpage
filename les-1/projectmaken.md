---
has_toc: false
nav_exclude: true
layout: default
---

# React project aanmaken

Het aanmaken van een React project gebeurt kan op verschillende manieren.

|Vite|Handmatig|
|-----|--------|
`npm create vite@latest`<br>`npm install`| - Projectmap aanmaken. <br>- NPM initialiseren.<br>- React en ReactDOM installeren. <br>- Webpack en Babel installeren.<br>- Project structuur aanmaken.<br>- Babel configureren.<br>- Webpack configureren.<br>- index.html aanmaken.<br>- React code schrijven om framework op te starten. 

1. npm create vite@latest
De Node Package Manager maakt 
2. npm install
Met npm installeren we alle nodige node packages. Welke node packages dat zijn staat beschreven in `package.json`. 
3. npm run dev
Met dit commando activeren we het `dev` script. Wat dat script doet staat ook beschreven in `package.json`. 

## React project maken
Maak de CSS bestanden leeg. We gaan onze eigen CSS schrijven.
Open `App.jsx`, en haal het meeste weg. Alleen het volgende moet overblijven. 

app.js  
{: .code-label }

```js 
import './App.css'

function App() {
  return (
    <h1>Hello world</h1>
  )
}

export default App
```