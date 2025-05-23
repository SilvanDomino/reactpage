---
has_toc: false
nav_exclude: true
layout: default
title: Top 10
---

# Arrays

Als het goed is ziet jouw `top10.js` er ongeveer als volgt uit:

```jsx
return (
    <section className={styles.top10}>
        <h1>Top 10 Favorite Books</h1>
        <ol className={styles.book__list}>
            <Top10Item title="The Final Empire" author="Brandon Sanderson" number="1"/>
            <Top10Item title="The Hobbit" author="Brandon Sanderson" number="2"/>
            <Top10Item title="The Girl Who Played With Fire" author="Stieg Larrson" number="3"/>
            <Top10Item title="Kono Subarashii Sekai ni Shukufuku wo! Oh! My Useless Goddess!" author="Natsume Akatsuki" number="4"/>
        </ol>
    </section>
)
```

Ik ga er wel vanuit dat je een andere Top 10 hebt dan ik. Jullie zullen wel andere hobbies of interesses hebben dan het lezen van boeken. 

Maar dit soort informatie, zoals een top 10, wil je eigenlijk niet in de JSX opslaan, dit wil je eigenlijk in een *array* hebben. Maak een **array** aan met alle items aan van jouw Top 10.
```jsx
let top10 = [
    {title: "The Final Empire", author: "Brandon Sanderson"},
    {title: "The Way of Kings", author: "Brandon Sanderson"},
    {title: "Harry Potter and the Sorcerer's Stone", author: "J.K. Rowling"},
    {title: "The Hobbit", author: "J.R.R. Tolkien"},
    {title: "The Fellowship of the Ring", author: "J.R.R. Tolkien"},
    {title: "Saga", author: "Brian K Vaughan"},
    {title: "52", author: "Geoff Johns, Grant Morrison, Greg rucka, Mark Waid, Keith Giffen"},
    {title: "Bad As I Wanna Be", author: "Dennis Rodman, Tim Keown"},
    {title: "Kono Subarashii Sekai ni Shukufuku wo! Oh! My Useless Goddess!", author: "Natsume Akatsuki"},
    {title: "So I'm a Spider, So What?", author: "Okina Baba"}
];
```
En zo zijn alle elementen in de top 10 in een array en dit kunnen we makkelijk in de JSX stoppen. 

```jsx
<Top10Item title={top10[0].title} author={top10[0].author} number="1"/>
<Top10Item title={top10[1].title} author={top10[1].author} number="2"/>
<Top10Item title={top10[1].title} author={top10[2].author} number="3"/>
```
Maar als developer wil je hier natuurlijk een loop voor gebruiken. Echter, je kan geen loop in de JSX stoppen, wel buiten de array en de array in de JSX knallen.
```jsx
let list = [];
for(let i = 0; i < top10.length; i++){
    list.push(
        <Top10Item title={top10[i].title} author={top10[i].author} number={i+1}/>
    )
}
return (
    <section className={styles.top10}>
        <h1>Top 10 Favorite Books</h1>
        <ol className={styles.book__list}>
            {list}
        </ol>
    </section>
)
```
Van elk object uit de array wordt een JSX element gemaakt, en deze elementen worden weer in een array gestopt. De array wordt gestopt in de JSX en de Top 10 wordt weergeven.

---

# Map

Map is een functie van een array. We kunnen deze gebruiken met `top10.map()`. Maar wat doet de map functie precies?

De map functie doet hetzelfde wat wij de vorige hoofdstuk hebben gedaan met een for-loop.

```jsx
let list = [];
for(let i = 0; i < top10.length; i++){
    list.push(
        <Top10Item title={top10[i].title} author={top10[i].author} number={i+1}/>
    )
}
```

Map maakt van een array een nieuwe array op basis van de gebruikte array. In de map functie geven we een functie mee die uitgevoerd wordt voor elk element in de array.
```jsx
let list = top10.map((item, index) =>{
    return <Top10Item title={top10[i].title} author={top10[i].author} number={index+1}/>
})
```

Omdat dit *technisch* gezien een enkele statement is, kunnen we dit wel in de JSX doen. Het is redelijk standaard om elementen van arrays op de onderstaande manier te renderen.

```jsx
return (
    <section className={styles.top10}>
        <h1>Top 10 Favorite Books</h1>
        <ol className={styles.book__list}>
            {top10.map((item, index) =>{
                return <Top10Item title={top10[i].title} author={top10[i].author} number={index+1}/>
            })}
        </ol>
    </section>
)
```

---

# Einde les 3: Props
Dit is het einde van deze les over props. Volgende les gaan we een cookie clicker maken en leren wat een state is.