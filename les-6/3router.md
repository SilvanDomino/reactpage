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
Dit is ongeveer wat de React router straks gaat doen wanneer we frontend routing gaan doen. 

### Frontend en backend routing
Je kan dus aan de frontend en aan de backend aan routing gaan doen. Je kan het ook allebei gebruiken.
Maar doe dat niet want dan krijg je erg veel hoofdpijn, zeker bij 404 errors. 
Je kan ook een fullstack framework gebruiken zoals Next.js.

## Installeren
Maak gebruik van de officiele documentatie om de router werkend te krijgen.
[https://reactrouter.com/start/declarative/installation](Zie hier)

Onze routes zijn nog erg simpel met maar 3 routes.