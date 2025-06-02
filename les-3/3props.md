---
has_toc: false
nav_exclude: true
layout: default
title: Top 10
---

## Props
Door middel van props gebruiken kunnen we veel van onze code herbruikbaar maken. Ons top 10 component, als we deze willen stylen door middel van oa de layout aan te passen, zou dat er uit kunnen komen te zien zoals hieronder.
```jsx
<li>
    <div>1</div>
    <div className="container">
        <h3>The Final Empire</h3>
        <h4>Brandon Sanderson</h4>
    </div>
</li>
```
Deze code willen we niet **10 keer** herhalen, want dan hebben we 70 regels code geschreven, waarbij 90% daarvan code is die we herhalen. Om herbruikbare code te schrijven gaan we gebruik maken van props. Props zijn eigenschappen die je aan een child component kan mee geven, en we gaan de titel en auteur mee geven.

### Maken van een Component
Maak een nieuw component aan. Dit component is een enkel item uit de top 10, en dit component gaan we meerdere keren herhalen.

Top10Item.jsx 
{: .code-label }
```jsx
import styles from './Top10Item.module.css'
export function Top10Item(){
    return(
        <li className={styles.book}>
            <div className={styles.number}>1</div>
            <div className={styles.bookInfo}>
                <h3>The Final Empire</h3>
                <h4>Brandon Sanderson</h4>
            </div>
        </li>
    )
}
```

Importeer dit component in `Top10.jsx`. Vervang alle *li* elementen met dit component. Pas zelf de styling aan.

### Props meegeven
De Top10 ziet er nu als volgt uit:
```html
<section className='top10'>
    <h1>Top 10 Favorite Books</h1>
    <ol className='book__list'>
        <Top10Item/>
        <Top10Item/>
        <Top10Item/>
        <Top10Item/>
    </ol>
</section>
```

We kunnen props mee geven op dezelfde manier zoals we attributes mee geven aan een HTML element.
```html
<img src="./dog.jpg" alt="picture of cat" style="width: 50px" class="img" id="img--js">
```
Dit *img* element heeft de attributes van *src, alt, style, class en id*. 

Voor ons `Top10Item` component kunnen we op dezelfde manier props meegeven.
```html
<Top10Item title="The Final Empire" author="Brandon Sanderson" number="1"/>
<Top10Item title="The Girl Who Played With Fire" author="Stieg Larrson" number="3"/>
<Top10Item title="Kono Subarashii Sekai ni Shukufuku wo! Oh! My Useless Goddess!" author="Natsume Akatsuki" number="4"/>
<Top10Item title="The Hobbit" author="Brandon Sanderson" number="2"/>
```

### Props gebruiken
We hebben nu props meegegeven, deze moeten alleen nog opgevangen worden en gebruikt worden.

```jsx
export function Top10Item(props){
//...
//...
}
```
In de functie worden de props meegegeven als argument. Dit props object bevat alle attributen en de waardes die daar bij horen. Dit props object kunnen we gebruiken in onze JSX.
```jsx
return (
    <li className={styles.book}>
        <div className={styles.bookNumber}>
            {props.number}
        </div>
        <div className={styles.bookContainer}>
            <h1 className={styles.bookTitle}>{props.title}</h1>
            <p className={styles.bookAuthor}>by {props.author}</p>
        </div>
    </li>
)
```

Als het goed is heb je nu een hele mooie top 10. Maar de code kan nog beter. Dit gaan we doen in het volgende hoofdstuk door arrays en objecten te gebruiken.

[Arrays en objecten](4arrays)