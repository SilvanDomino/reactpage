---
nav_exclude: true
---
# Upgrades
Een echte cookie clicker heeft naast een **cookie** om op te klikken, ook verschillende upgrades die je kan kopen. Wij gaan ook upgrades beschikbaar maken.

## UI van Grandma
Deze *grandma* upgrade zorg er voor dat elke klik telt voor meer. Dus als je 2 oma's hebt, dan krijg je totaal 3 cookies wanneer je klikt. 

De eerste stap is de UI.

```js
<label htmlFor="button">Grandmas: 0 </label>
<button className={styles.upgrade}>Buy grandma</button>
```

## Logica van Grandma
Voor de **grandmas** moet ook een state gemaakt worden. 
```js 
const [grandmas, setGrandmas] = useState(0);
```

En net als voor de cookie moet er een functie gemaakt worden, voor wanneer de speler klikt op de cookie.
Maar je kan alleen een grandma kopen als je 20 cookies kan betalen.
```js
function buyGrandma(){
    if(cookies > 20){
        setGrandmas(grandmas+1);
        setCookies(cookies-20);
    }
}
```
Hoera! We kunnen grandma's kopen! De oma's hebben alleen nog geen effect. Verander de regel `setScore(score+1);` naar `setScore(score+1+grandmas);`. En nu hebben we een werkende cookie clicker met upgrades.
De prijs van onze oma's is nu standaard 20 cookies, alleen bij een echte cookie clicker worden grandmas steeds **duurder**. 

{% include test.md%}