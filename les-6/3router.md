---
nav_exclude: true
---

# React Router
Met een router kunnen we specifieke componenten laten zien op basis van de URL. Dus als we naar `localhost:5731/About` gaan krijgen we een andere pagina te zien dan wanneer we naar `localhost:5731/Games` gaan.

Hier gebruiken we de react router voor.

## Routing
Routing is hoe we refereren naar het gebruik van URLs om specifieke pagina's te laten zien. Routing kan via de **backend**, wat heel normaal is. Als je naar de ene url gaat, dan geeft de *server* jou een andere pagina. Maar het kan ook via de **frontend**. Wanneer je routing in de frontend gebruikt dan wordt er gekeken naar de URL en op basis daarvan de website aangepast.

```js
if(window.location.href.includes("About")){
    document.querySelector(".body").innerHTML = `
        <h1>Welcome to my website.</h1>
        <p>Ik ben silvan</p>`
}
```
Dit is *ongeveer* wat de React router straks gaat doen wanneer we frontend routing gaan doen. 

### Frontend en backend routing
Je kan dus aan de frontend en aan de backend aan routing gaan doen. Je kan het ook allebei gebruiken.
Maar doe dat niet want dan krijg je erg veel hoofdpijn, zeker bij 404 errors. 
Je kan ook een fullstack framework gebruiken zoals Next.js.

## Installeren
Maak gebruik van de officiele documentatie om de router werkend te krijgen.
[Zie Hier](https://reactrouter.com/start/declarative/installation)
Maar omdat wij geen complete toegang hebben tot onze host, maken we gebruik van de **HashRouter** in plaats van *BrowserRouter*.

Onze routes zijn nog erg simpel met maar 3 routes en geen nested routes. 

## En nu
In het vorige hoofdstuk heb je een navigatie-bar gemaakt, en de componenten verdeeld over de 3 verschillende routes. Nu moeten we de routes implementeren.

```jsx
function App() {
  return (
    <main>
      <nav>
        <ul className='navlist'>
          <li className='navlist__item'>
            <Link className='nav__link' to="/">Home</Link>
          </li>
          <li className='navlist__item'>
            <Link className='nav__link' to="/games">Games</Link>
          </li>
        </ul>
      </nav>
      <Routes>
        <Route index element={<Home />} />
        <Route path="/games" element={<Games/>} />
      </Routes>
    </main>
  )
}
```

Ik heb hier de **Home** en de **Games** route geimplementeerd, implementeer nu zelf ook de **Contact** route.
Ga nu ook kijken of je een *'page not found'* pagina kan implementeren. 

---

Dit is het einde van deze les. Volgende les gaan we aan de slag met het online zetten van onze applicatie en de gallerij.