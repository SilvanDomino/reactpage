---
nav_exclude: true
---

# Navigatie bar
Voor de navigatie bar willen we verschillende pagina's hebben. Ik heb bedacht:
* About
* Games
* Contact

Dat betekent dat bijna alle componenten die we de vorige lessen hebben gemaakt verdeeld worden over verschillende componenten.

## Structuur 
Er komen componenten in componenten, daarom is het handig om dit visueel te maken.
De structuur die we dan hanteren is
* About
	* About Me *(les 2)*
	* Top 10 *(Les 3)*
* Games
	* Cookie Clicker *(Les 4)*
	* Pokemon *(Les 5)*
* Contact
	* FAQ *(Volgende les)*
Dat betekent dat je 3 componenten moet maken. **About**, **Games** en **Contact**. Ieder van deze component wordt straks een pagina waar je naar toe kan *browsen*. Met de juiste URL kan je naar die pagina gaan, en mensen kunnen dan die pagina ook bookmarken. 


```jsx
export function About(){
	return(
		<main>
			<h1>About</h1>
			<AboutMe/>
			<Top10/>
		<main>
	)
}
```
Hierboven hebben we een voorbeeld van de *About* pagina. 

## Navbar component
Maak een navbar component en css module. 

App.jsx  
{: .code-label }

```jsx
<navbar className={styles.navbar}>
	<ul className={styles.list}>
	<li className={styles.listItem}>
		<a href="#">Home</a>
	</li>
	<li className={styles.listItem}>
		<a href="/about">About</a>
	</li>
	<li className={styles.listItem}>
		<a href="/contact">Contact</a>
	</li>
  </ul>
</navbar>
...
///rest van de return van de app.jsx
...
```
Dit is een eenvoudig voorbeeld van een navbar. De styling kan je zelf doen.

We hebben nu onze losse, maar functionele componenten. Nu moeten we alleen nog zorgen dat we kunnen browsen. Dat wanneer we op de navbar op een link klikken, dat we naar de juiste pagina/component gaan.

[Volgende hoofdstuk: React Router](3router)
