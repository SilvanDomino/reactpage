---
nav_exclude: true
---
# Deployen van React website

Als je een React-website online wilt gaan zetten, dan kan je helaas niet gewoon het project online zetten. React maakt gebruik van moderne JavaScript-functionaliteiten die eerst moeten worden omgezet naar gewone HTML, CSS en JavaScript die een browser begrijpt. Dit proces heet builden.
Tijdens het builden wordt je code geoptimaliseerd en worden alle losse onderdelen samengevoegd tot één pakketje dat je wél online kunt zetten.

Je gebruikt hiervoor meestal het commando npm run build. Dit maakt een map genaamd **dist** (kort for distribution), en daarin zit je kant-en-klare website. Die map kun je vervolgens uploaden naar een webserver. Bijvoorbeeld de ma-cloud. Ook kan je deze *dist* website openen via *liveserver*.

## Build je reactproject
Voer de commando uit:
`npm run build`

## Test uit in liveserver
Open jouw project in de liveserver om te kijken of het werkt. 
De kans is groot dat je een error krijgt. De HTML verwacht namelijk een `asset` folder in de root van het project, maar de *asset folder* zit niet in de root, maar in de **dist** folder. Dit kan je aanpassen door de JS en de CSS imports te veranderen. 
Verander `/assests/...` naar `./assets/...`. Dat gaat de HTML niet kijken naar de root van het project, maar naar de eigen locatie.

## Uploaden
Load het project up naar de ma-cloud (of een andere provider).

[Volgend hoofdstuk: Gallery](2gallery)