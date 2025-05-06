---
nav_exclude: true
---

# Navigatie bar
Voor de navigatie bar willen we verschillende pagina's hebben. Ik heb bedacht:
* About
* Games
* Contact

Dat betekent dat bijna alle componenten die we de vorige lessen hebben gemaakt verdeeld worden over verschillende componenten.

De structuur die we dan hanteren is
* About
	* About Me *(les 2)*
	* Top 10 *(Les 3)*
* Games
	* Cookie Clicker *(Les 4)*
	* Pokemon *(Les 5)*
* Contact

## Home component
Alle componenten die we de vorige lessen hebben gemaakt

Maak een navbar component en css module.

```js
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
```
Dit is een eenvoudig voorbeeld van een navbar. De styling kan je zelf doen.

## Structuur 
Er komen componenten in componenten, daarom is het 