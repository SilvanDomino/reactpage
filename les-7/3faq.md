---
nav_exclude: true
---

# FAQ
Deze afkorting staat voor Frequently Asked Questions. Dit is een veelkomend onderdeel op websites.

[https://mediacollege.dev/M8ReactEindproduct/#/contact](Hier een mooi voorbeeld van een FAQ)
[https://welkombijma.nl/contact/](Hier een minder mooi voorbeeld van een FAQ)
[https://www.ah.nl/klantenservice/spaaracties/koopzegels](Hier een ander voorbeeld van een FAQ)

Het idee is iedere keer hetzelfde. Er is een vraag, als je er op klikt komt het antwoord tevoorschijn. 

## Maak de componenten.

Maak een FAQ component waarin straks alle vragen komen, `FAQ.jsx`. Maak een Question component, `Questions.jsx`. 
```jsx
export function Question(){
    return(
        <li>
            <h3>Question?</h3>
            <p>Answer</p>
        </li>
    )
}
```

```jsx
export function FAQ(){
    return(
        <section>
            <h2>Frequently Asked Questions</h2>
            <ul>
                <Question/>
                <Question/>
                <Question/>
            </ul>
        </section>
    )
}
```
## Click Event
Een FAQ moet uitklappen als je op de vraag klikt. Daarvoor gebruik je een useState.
Voeg deze toe aan je Question component:

```jsx
import { useState } from "react";

export function Question() {
    const [open, setOpen] = useState(false);

    function handleClick() {
        setOpen(!open);
    }

    return (
        <li onClick={handleClick}>
            <h3>Question</h3>
            {open && <p>Answer</p>}
        </li>
    );
}
```

Je gebruikt hier een eenvoudige klik om iets zichtbaar of onzichtbaar te maken.
Later kan je dit uitbreiden met animatie of overgangen.

## Props
In de plaats van vaste vragen is het handig om net als in de top 10 props te gebruiken. Geef *props* mee in de FAQ component *en* vang ze op in de *Question* component.

```jsx
export function FAQ(){
    return(
        <section>
            <h2>Frequently Asked Questions</h2>
            <ul>
                <Question question="Is dit een vraag?" answer="Dit is een antwoord"/>
                <Question question="Is dit ook een vraag?" answer="Dit is ook een antwoord"/>
                <Question question="Een vraag is dit?" answer="Een antwoord dit is"/>
            </ul>
        </section>
    )
}
```


## Styling
Style de componenten.