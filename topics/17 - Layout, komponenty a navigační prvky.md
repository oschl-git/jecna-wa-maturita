# 17 - Layout, komponenty a navigační prvky
## O čem mluvit?
- popsat, co to je
- mluvit o HTML
- popsat nejčastější rozložení, co jaké komponenty hrají za roli
- zmínit templatování
## Layout, komponenty a navigační prvky
- rozložení webové stránky, definování jaké prvky obsahuje
- používá se HTML
## HTML
- *HyperText Markup Language*
- není programovací jazyk!
- skládá se z tagů které definují jednotlivé komponenty ze kterých je stránka složená
- komponenta je skupinou tagů, uskupení funkcionalit
- tagy
	- většinou musí být otevřené a uzavřené `<html> ... </html>`
	- např. `<div>`, `<header>`, `<a>`, `<img>`, ...
	- kompletní seznam lze najít zde: https://developer.mozilla.org/en-US/docs/Web/HTML/Element
	- elementy mají své atributy, např. `<img>` má atribut alt, který specifikuje text, který se zobrazí, pokud se obrázek napodaří načíst (`<img src="http://spsejecna.cz/spongebob" alt="Spongebobg!">`)
- prvky na stánce mohou mít třídy a ID
## Nejčastější způsob rozložení stránky
- **Hlavička/Header**  
	- `<header>`
	- horní část stránky
	- obsahuje veci jako je logo a navigační menu
- **Navigační menu/Navbar**
	- `<nav>`
	- obsahuje prokliky na ostatni části stránky a jiné věci
- **Obsah/Content/Main**
	- `<main>`
	- hlavní obsah stránky
- **Patička/Footer**
	- `<footer>`
	- spodní část stránky
	- nejčastěji soucástí footeru jsou kontakty, sociální sítě a copyright info
## Templatování
- mnoho frameworků a webových nástrojů umožňují vytváření HTML šablon
- šablony definují strukturu stránky, data uvnitř se ovšem mohou měnit
- často můžeme definovat hierarchii šablon, takže např. header a footer definujeme zvlášť a pak můžeme používat pro všechny stránky