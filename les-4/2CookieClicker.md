---
nav_exclude: true
---
# Cookie Clicker en Cookie

Maak het Cookie Clicker component. Vergeet hierbij niet de import voor de CSS.

```js
export function CookieClicker(){
    return(
        <section>
            <h2>Cookie Clicker</h2>
        </section>
    )
}
```

Geef de `CookieClicker` een class en style deze. Dit kan je het beste met een CSS module doen.


## Cookie
De volgende stap is de cookie. De Cookie is redelijk simpel. Het is iets waar we op kunnen klikken, het is een koekje en dus rond.
Maak een button aan en geef deze een classname, voeg deze toe aan het CookieClicker component.

```js
    <button className={styles.cookie}></button>
```

```css
.cookie{
    width: 200px;
    heigth: 200px;
    border: none;
    border-radius: 50%;
    background: brown;
}
```
Als het goed is heeft jouw component nu een cookie om op te klikken!

[Volgend hoofdstuk: Score](3Score)