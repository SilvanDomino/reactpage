---
nav_exclude: true
---

# Fetch

We gaan de gegevens van een pokemon fetchen, en we weten ondertussen wel hoe een fetch werkt.
Zet boven de return de volgende statement, en dan fetchen we de pokemon zodra het component wordt gebruikt.
```jsx
    let pokemon = null;
    fetch("https://pokeapi.co/api/v2/pokemon/254")
    .then(response => response.json())
    .then(data =>{
        pokemon = data;
    })
```

Laten we gelijk ook maar de pokemon renderen.

```jsx
return (
    <section className={styles.pokemon}>
        <h2 className={styles.name}>{pokemon.name}</h2>
        <img src={pokemon.sprites.front_default}/>
    </section>
)
```
Als we deze code uitproberen dan hebben we 2 problemen. 
1. De pokemon wordt gelijk gerendered, terwijl het fetchen nog niet klaar is. Om dit probleem op te lossen moeten we 2 verschillende return statements maken.
    * Wat gerendert wordt wanneer er nog geen pokemon gefetched is.
    * Wat gerendert wordt wanneer de pokemon wel gefetched is.
2. De informatie van de pokemon wordt nog niet weergeven. Hiervoor moeten we het pokemon component opnieuw renderen. Om dit op de lossen moeten we gebruik maken van states.

## Probleem 1: Twee return statements.
Een component moet altijd *iets* returnen. Omdat componenten synchroon zijn kunnen ze niet op iets wachten. Wat je wel kan doen is een component iets anders laten renderen, zolang er nog niks gefetched is.

```jsx
if(pokemon === null){
    return (
        <section className={styles.pokemon}>
            <h2>Fetching Pokemon</h2>
        </section>
    )
} else{
    return (
        <section className={styles.pokemon}>
            <h2 className={styles.name}>{pokemon.name}</h2>
            <img src={pokemon.sprites.front_default}/>
        </section>
    )
}
```

## Probleem 2: State
Het probleem hier is dat de informatie van onze pokemon nog niet gebruikt wordt/kan worden omdat we het component opnieuw moeten renderen. Daar moeten we een state voor gebruiken.

```jsx
    const [pokemon, setPokemon] = useState(null);
    fetch("https://pokeapi.co/api/v2/pokemon/254")
    .then(response => response.json())
    .then(data =>{
        setPokemon(data);
    })
```

Nu kunnen we de pokemon gebruiken bij het renderen.

## Resultaat
We hebben nu een component dat:
1. Laat een laadingsbericht zien
2. Gegevens van een pokemon fetcht
3. Het component opnieuw rendert, maar deze keer met gegevens van de pokemon
4. Gegevens van een pokemon fetcht.
5. Het component opnieuw rendert, maar deze keer met gegevens van de pokemon
4. Gegevens van een pokemon fetcht.
5. Het component opnieuw rendert, maar deze keer met gegevens van de pokemon

Dat laatste is niet helemaal de bedoeling. Het is niet de bedoeling dat de pokemon oneindig vaak gefetched wordt en opnieuw gerendert. 

[Volgend hoofdstuk: Probleem 3: Rerenderen van een component](3rerender)
