---
has_toc: false
nav_exclude: true
layout: default
---

# JSX
Dit hoofdstuk gaan we heel kort JSX behandelen. 
JSX staat voor JavaScript XML. Het laat ons HTML code schrijven *in* javascript. 
Vorig hoofdstuk hebben wij deze code geschreven, en dit is voornamelijk javascript, alleen het stukje `<h1>Hello World</h1>` is JSX. Het is geen echte HTML, maar ook geen JavaScript. Maar het lijkt toch 100% op HTML zou je denken, toch zijn er een paar hele kleine verschillen.
```jsx
  return (
    <h1>Hello world</h1>
  )
```


## Verschillen tussen JSX en HTML.
### Class vs Classname
In JavaScript is `class` een beschermde keyword. Dit woord mag je niet gebruiken, tenzij je een `class` aanmaakt. Je mag dus geen variabele of functie deze naam geven. In deze HTML code krijgt de afbeelding de class `aboutme__img`. In HTML is class niet een beschermd keyword, en is het een gewoon attribute, dus kan het gebruikt worden.
```html
    <img class="aboutme__img" src="image.png" alt="picture of a dog">
```

In JSX wordt daarom `className` gebruikt, inplaats van `class`.
```jsx
    return(
        <img className="aboutme__img" src="image.png" alt="picture of a dog"/>
    )
```
---
### Root element
In gewoon HTML kan je alles in de body gooien wat je wilt.
```html
<body>
    <img class="aboutme__img" src="image.png" alt="picture of a dog">
    <h1>Hello world</h1>
</body>
```
In JSX, moet jouw component een root element hebben om te returnen. **Onderstaande gaat niet**. Krijg je een error.
```jsx
function App() {
    return (
        <img className="aboutme__img" src="image.png" alt="picture of a dog"/>
        <h1>Hello world</h1>
    )
}
```
Onderstaande gaat wel, we hebben een div als root element van ons component.
```jsx
function App() {
    return (
        <div>
            <img className="aboutme__img" src="image.png" alt="picture of a dog"/>
            <h1>Hello world</h1>
        </div>
        
    )
}
```
---
### Gebruik van variabelen
In HTML kan je geen variabelen gebruiken. In JSX wel.
```jsx
function App() {
    const name = "Silvan";
    return (
            <h1>Hello {name}</h1>
    )
}
```
---
### Style als object
In HTML is style een string. 
```html
<h1 style="background: pink">Hello world</h1>
```
In JSX is de style een object.
```jsx
let h1Style = { color: "red", backgroundColor: "blue" };
<h1 style={h1Style}>Hello World</h1>
```
---
### Sluiten van tags
In HTML hoef je tags niet te sluiten.
```html
<img class="aboutme__img" src="image.png" alt="picture of a dog">
<br><br>
```

In JSX **moet** je tags sluiten, maar dat is gelukkig makkelijk gemaakt. 
```jsx
<img class="aboutme__img" src="image.png" alt="picture of a dog"></img>
```
Het bovenstaande is niet nodig (kan wel), maar met een trailing / kan je een tag gelijk afsluiten.
```jsx
<img class="aboutme__img" src="image.png" alt="picture of a dog"/>
<br/>
```
---
---

## Opdracht:
Nu we alle regels kennen van JSX kan je beginnen met het bouwen van jouw eerste site.
```jsx
function App() {
    return (
        <h1>Hello world</h1>
    )
}
```
Zo ziet onze app.js er nu uit. We gaan er een artikel van maken, net zoals je in de eerste periode bij de HTML/CSS lessen hebt geleerd.    
Ons artikel heeft een `h1`, `img` en `p`, net zoals het artikel hier onder. 
![Voorbeeld van een artikel](./images/Artikel.png)

In het volgende hoofdstuk gaan we dit artikel stylen met CSS.
[Volgend hoofdstuk: CSS](4css)