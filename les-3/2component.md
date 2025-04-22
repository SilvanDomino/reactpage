---
has_toc: false
nav_exclude: true
layout: default
title: Top 10
---

## Maken van een (Top 10) component
We gaan een Top 10 component maken. 
* Maak een bestand genaamd `Top10.jsx`. Let op het hoofdletter gebruik. De eerste letter van een component is altijd met hoofdletter.
* Maak ook een **css** file aan. `Top10.module.css`. *Importeer* de CSS module in de **jsx**
* De Top 10 component bestaat uit een root *article* of *section*. 
    * Boven de Top 10 lijst is de `h2` met de titel van het component.
    * Daaronder is de lijst. De lijst heeft een volgorde, dus het is een ordered list. 
* Voeg het `Top10` component toe aan `App.js`, onder **AboutMe**.

Top10.js  
{: .code-label }
```js
import styles from './Top10.module.css'
export function Top10(){
    return(
        <section className={styles.top10}>
            <h2>Top 10 Books</h2>
            <ol className={styles.list}>
                <li>The Final Empire - Brandon Sanderson</li>
                <li>Game of Thrones - George RR Martin</li>
                <li>Saga - Brian K Vaughan</li>
                <li>The Girl Who Kicked the Hornet’s Nest - Stieg Larsson</li>
                <li>Harry Potter and the Prisoner of Azkaban - JK Rowling</li>
                <li>Watchmen - Alan Moore</li>
            </ol>
        </section>
    )
}
```

Top10.module.css  
{: .code-label }
```css
.top10{
    background: pink;
    border: 1px solid black;
}
.list{
    list-style: none;
}
```

Als we de list items willen gaan stylen, dan wordt de code groot en complex. Dan krijg je een component met een return van 90 regels code. En wanneer je alleen een list item wilt gaan aanpassen, dan ben je lang bezig.

```html
<li>
    <div>1</div>
    <div className="container">
        <h3>The Final Empire</h3>
        <h4>Brandon Sanderson</h4>
    </div>
</li>
```

[Volgende stap: Props]