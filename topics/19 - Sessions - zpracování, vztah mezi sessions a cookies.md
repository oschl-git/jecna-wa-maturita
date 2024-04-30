# 19 - Sessions - zpracování, vztah mezi sessions a cookies
## O čem mluvit?
- co to jsou sessions
- jak jsou vyřešené, interakce klienta se serverem
- kam se ukládají data
- localStorage a sessionStorage
	- rozdíly
	- jak fungují
	- jaké podporují data, jak ukládat složitější data
	- jak ukládat, mazat, číst
## Sessions
- obecné označení, kdy zachováváme data a stavy jednotlivého uživatele a jeho chování na stránce
- využíváme pro zachování přihlášení uživatele, nastavení preferencí, data ve formulářích
- uživatele lze identifikovat pomocí session IDs, které mohou být zaslány jako cookies
## Web Storage API
- můžeme využít pro ukládání větších dat, narozdíl od cookies se neposílají serveru
- weby mohou ukládat a číst data, nemají přístup k datům ostatních webů
- jsou podporovaná jen string data, např. JavaScript objekty musí být serializované a uložené jako JSON
- **localStorage** je prezistentní
- **sessionStorage** se maže při restartu prohlížeče
- můžeme uložit data s velikostí až 5MiB pro sessionStorage i localStorage, takže celkem 10MiB
### Způsob uložení a čtení
- data ukládáme:
```js
 localStorage.setItem(key, value);
```
- čteme:
```js
const value = localStorage.getItem(key);
```
- mažeme:
```js
localStorage.removeItem(key);
```
- vymažeme všechny objekty:
```js
localStorage.clear();
```