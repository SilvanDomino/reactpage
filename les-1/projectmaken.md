---
has_toc: false
nav_exclude: true
---

# React project aanmaken

`npm create vite@latest`

Volg het menu. Gebruik geen typescript aub

2. npm install
Met npm installeren we alle nodige node packages. Welke node packages dat zijn staat beschreven in `package.json`. 
3. npm run dev
Met dit commando activeren we het `dev` script. Wat dat script doet staat ook beschreven in `package.json`. 

## React project maken
Maak de CSS bestanden leeg. We gaan onze eigen CSS schrijven.
Open `App.jsx`, en haal het meeste weg. Alleen het volgende moet overblijven. 

```js
import './App.css'

function App() {
  return (
    <h1>Hello world</h1>
  )
}

export default App
```