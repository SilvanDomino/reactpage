---
has_toc: false
nav_exclude: true
layout: default
---

# Componenten en props

In de vorige les hebben we een eerste component aangemaakt en deze (door middel van css module) gestyled. In deze les gaan we een tweede component maken, namelijk een top 10 component. In dit component gaat jouw top 10 staan. Dit kan een top 10 van alles zijn.

* Top 10 albums
* Top 10 TV series
* Top 10 games
* Top 10 boeken
* Top 10 vechtsporters
* Top 10 frisdrank
* Top 10 anime

Maakt niet uit wat voor top 10 je kiest.

## Stappen

1. Maken van een (Top10) component.
2. Invullen van de top 10.
3. Styling
4. Data verplaatsen naar props.
5. Data verplaatsen naar array.

## Maken van een (Top 10) component
Maak een Top 10 component. 

```js
import styles from './Top10.module.css'
import { Top10Item } from './Item';
export function Top10(){
    return(
        <section className={styles.top10}>
            <h2>Top 10 Albums</h2>
            <ol className={styles.list}>
                <li>Blink 182</li>
                <li>Ernesto Hoost</li>
                <li>Barry van Aerle</li>
                <li>George RR Martin</li>
                <li>The Last Empire</li>
                <li>Hot Fuzz</li>
            </ol>
        </section>
    )
}
```