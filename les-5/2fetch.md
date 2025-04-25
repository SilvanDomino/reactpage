---
nav_exclude: true
---

# Fetch

We gaan de gegevens van een pokemon fetchen, en we weten ondertussen wel hoe een fetch werkt.
Zet boven de return de volgende statement, en dan fetchen we de pokemon zodra het component wordt gebruikt.
```js
    let pokemonData = null;
    fetch("https://pokeapi.co/api/v2/pokemon/254")
    .then(response => response.json())
    .then(data =>{
        pokemonData = data;
    })
```

Laten we gelijk ook maar de pokemon renderen.

```js
return (
    <section className={styles.pokemon}>
        <h2 className={styles.name}>{pokemonData.name}</h2>
        <img src={pokemonData.sprites.front_default}/>
    </section>
)
```
Als we deze code uitproberen dan hebben we 2 problemen. 
1. De pokemon wordt gelijk gerendered, terwijl het fetchen nog niet klaar is. Om dit probleem op te lossen moeten we 2 verschillende return statements maken.
    * Wat gerendert wordt wanneer er nog geen pokemon gefetched is.
    * Wat gerendert wordt wanneer de pokemon wel gefetched is.
2. De informatie van de pokemon wordt nog niet weergeven. Hiervoor moeten we het pokemon component opnieuw renderen. Om dit op de lossen moeten we gebruik maken van states.

## Probleem 1: Twee return statements.
## Probleem 2: State
Het probleem hier is dat de informatie van onze pokemon nog niet gebruikt wordt/kan worden omdat we het component opnieuw moeten renderen. Daar moeten we een state voor gebruiken.

```js
    const [pokemon, setPokemon] = useState(0);
    fetch("https://pokeapi.co/api/v2/pokemon/254")
    .then(response => response.json())
    .then(data =>{
        setPokemon(data);
    })
```

Nu kunnen we de pokemon gebruiken bij het renderen, als de pokemon tenminste gefetched is. 
