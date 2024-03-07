# 13 - CSS syntaxe, selektory, box model
#### Syntaxe
- skládá se ze selektoru, deklaračního bloku a vlastností
	- uvnitř bloku se určijí vlastnosti
```css 
body {
	background-color: black; 
	color: white;
} 
```
#### Selektory
- určuje, kterých HTML elementů se pravidlo týká
- **Typy:**
		- `body` - jméno elementu, tag: body
		- `.body` - class jménem "body"
		- `#body` - id jménem "body"
- **Typy selektorů:** 
	-  **tag** - vybere všechny elementy daného typu
		- `h1`, `p`, `div`, `body`,`main`
	- **třída** - vybere elementy s danou třídou 
		- `.moje_třída`
	- **id** - vybere element s daným ID 
		- `#moje_id`
	- **child** - vybere přímé potomky elementu 
		- `div > p` - pouze přímé p
	- **all-children** - vybere všechny potomky elementu 
		- `div p` - všechny p (a mnoho dalších) v divu
	- **neighbour** - vybere elementy, které přímo následují po daném elementu 
		- `div + p`
	- **následník** - vybere elementy, které následují po daném elementu, ale ne nutně přímo 
		- `div ~ p`
	- **combination** - vyberu několik elementů
		- `.class1 h1, .class2 p` - upraví h1 a p zároveň
	- **interaction** - vyberu element s kterým se něco děje
		- `div:hover` - když nad divem je kurzor
		- `input:focus` - když je input vybrán
		- ...
#### Box model
- box model je základním konceptem v CSS, který popisuje, jak jsou prvky na stránce zobrazeny a jak zabírají místo
- každý prvek v HTML dokumentu je reprezentován jako obdélníkový "box", který se skládá z několika částí:
	- **Obsah** - skutečný obsah elementu (text, obrázky, atd.).
	- **Padding** - mezera mezi obsahem a hranicí elementu.
	- **Border** - obrys elementu, který odděluje padding od marginu.
	- **Margin** - mezera mezi okrajem elementu a jeho sousedy.