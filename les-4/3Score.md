---
has_toc: false
nav_exclude: true
layout: default
---
# Score
We hebben een eenvoudig cookie clicker component gemaakt, alleen de logica ontbreekt nog.
* De OnClick event voor de cookie
* De zichtbare score.

## Score
Maak in de javascript een variabele aan voor de score.
```jsx
export function CookieClicker(){
    let score = 0;
    return(
        //blablaba
    )
}
```
Deze score moeten we weergeven in de *html/jsx*.
`<div>{score}</div>`
We gebruiken *div* html tags. Omdat we *curly brackets* gebruiken, wordt de inhoud van de score variabele in de HTML gezet, en niet de text 'score'.

## OnClick event
Maak een onClick functie aan. Deze functie wordt aangeroepen wanneer op de cookie geklikt wordt. 
```jsx
function cookieClick(){
    score+=1;
    console.log(score);
}
```
Voeg de onClick event toe aan de cookie.
```jsx
<button className={styles.cookie} onClick={cookieClick}></button>
```

## Resultaat
Als we nu op de knop drukken, dan wordt de functie `cookieClick()` uitgevoerd. Als we in de console kijken, dan zien we dat de score omhoog gaat. Maar als we op onze website zelf kijken, dan gebeurt er niks. Dat komt omdat de score variabele wel verandert, maar we geven niet aan dat de website iets moet veranderen. Om te zorgen dat de wijziging van score weergeven wordt, moeten we het component opnieuw renderen. 

[Rerenderen en State](4State)