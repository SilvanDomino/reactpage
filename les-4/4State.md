---
nav_exclude: true
---
# Rerenderen en State
Om een element in onze component te veranderen moeten we dus ons component gaan rerenderen. Bij het **(re-)renderen** gaat alle code van begin tot eind opnieuw uitgevoerd worden. Ook het definieren en initialiseren van variabelen gebeurt weer helemaal op nieuw.    
Kijk eens naar `let score = 0`. Iedere keer dat het component rerendert wordt deze code opnieuw uitgevoerd, waardoor de score weer opnieuw op 0 gezet wordt, ongeacht hoevaak de score is verandert. 

## Re-renderen
Er zijn 2 manieren waarop een component getriggered kan worden om te re-renderen.
1. Verandering van State
2. Parent component wordt opnieuw gerenderd.

Volgende les gaat dit voor leuke problemen zorgen.

## State
Een state is een manier om gegevens op te op slaan ook wanneer een component wordt re-rerendert. 
We beginnen met de import.
```jsx
import {useState} from 'react';
```
Nu kunnen we *useState* gebruiken in onze code.

Vervang `let score = 0` met de voglende regel code:
```jsx
const [score, setScore] = useState(0);
```
---
Het eindresultaat ziet er ongeveer zo uit:


CookieClicker.jsx
{: .code-label }
```jsx
export function CookieClicker(){
    const [score,  setScore] = useState(0);

    return (
        <section className={styles.cookieClicker}>
            <button className={styles.cookie} onClick={onClick}></button>
            <div className={styles.container}>
                <div className={styles.score}>{score} Cookies</div>
            </div>
        </section>
    )
}
```
### Uitleg

* `useState(0)` - We maken gebruik van de useState hook, die maakt een nieuwe **state** aan. Ook wordt een initiele waarde meegegeven, *0*. Je kan hier alles in meegeven, niet alleen een getal. Je kan een *string* meegeven, een *boolean*, een **object of zelfs een array**.
* `[score, setScore]` - Hier wordt gebruik van array destructuring. Er worden 2 items aangemaakt:
    * `score` - Dit is de huidige waarde van de score.
    * `setScore` - Met deze functie passen we de waarde aan van de state. 

{: .small-note }
Array destructuring is typische javascript onzin. Het is niet logisch, maar het werkt hardstikke fijn.


## State aanpassen
Nu moeten we de state aanpassen. Onze huidige code, `let score +=1` kunnen weghalen, en vervangen met
```js
setScore(score+1);
```

### Uitleg
We passen de state aan. De huidige state is de score+1.

---

## Cookie Clicker
Als het goed is werkt de cookie clicker nu! We kunnen op de cookie clicker klikken en de score gaat omhoog.

[Upgrades](5upgrades)