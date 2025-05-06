---
nav_exclude: true
---

# Rerender van component
Wanneer je de state aanpast van een component, dan wordt ook alle code die voor de *return* staat ook uitgevoerd. Dus het fetchen wordt opnieuw gedaan, en het setten van de state ook, wat dus een rerender triggert. Maar we willen niet dat iedere keer als we het component laden dat er opnieuw gefetched wordt, we willen dat dit alleen de eerste keer gefetcht wordt. Dat kunnen we op 2 manieren doen. 

## Manier 1: De simpele manier.
Alleen fetchen als de data leeg is. 

```js
    if(pokemon === null){
        fetch("https://pokeapi.co/api/v2/pokemon/254")
        .then(response => response.json())
        .then(data =>{
            pokemon = data;
        })
    }
```

### Voordelen
* Het is simpel, duidelijk en leesbaar.
* Het werkt
### Nadelen
* Bij een error kan je problemen krijgen. 

## Manier 2: De juiste manier
Fetch alleen bij het mounten/opstarten van het component door middel van een effect.
```js
useEffect(()=>{
    fetch("https://pokeapi.co/api/v2/pokemon/254")
    .then(response => response.json())
    .then(data =>{
        pokemon = data;
    })
}, [])
```
We maken gebruik van useEffect, en als 2e argument geven we een lege array may om aan te geven dat deze useEffect alleen bij het mounten van het component moet worden uitgevoerd.

### Voordelen
* Industrie standaard.
* Minder gevoelig voor errors.
* Kan je *netjes* uitbreiden.

### Nadelen
* Niet erg logisch.
    * WTF is een effect? 
    * Wat is die array die we mee geven?

## Resultaat
We hebben nu een component, en dit component rendert de informatie van de pokemon en een afbeelding.
---

[Volgend hoofdstuk: Types](4types)