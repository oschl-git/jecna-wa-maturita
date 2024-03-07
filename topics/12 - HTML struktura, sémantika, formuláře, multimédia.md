# 12 - HTML struktura, sémantika, formuláře, multimédia
- **HyperText Markup Language** 
- základní jazyk pro vytváření webových stránek a dokumentů
	- umožňuje definovat strukturu, obsah a styl webových dokumentů
#### Struktura
- HTML dokument je tvořen tagy
	- definují strukturu a obsah webové stránky
- **Základní tagy:** `<html>`, `<head>`, `<title>`, `<body>`,`<main>`,.... 
	- Seznam tagů: [https://developer.mozilla.org/en-US/docs/Web/HTML/Element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
- **Typy tagů:**
    - blokové tagy zabírají celý řádek a můžou obsahovat další blokové tagy 
	    - např. `<div>`, `<p>`
    - inline tagy se vkládají do blokových tagů a nezabírají celý řádek 
	    - např. `<span>`, `<strong>`
- **Struktura dokumentu:**
	- začíná značkou `<!DOCTYPE html>`
		- určuje verzi HTML používanou v dokumentu
	- hlavní část dokumentu je uzavřena mezi značkami `<html>` a `</html>`
	- obsah stránky je pak rozdělen na hlavičku `<head>` a tělo `<body>`
#### Sémantika
- definují význam obsahu pro webové prohlížeče a vyhledávače
	- pomáhá vyjádřit význam jednotlivých částí dokumentu a zlepšuje jeho dostupnost a SEO
- usnadňují přístupnost a srozumitelnost webové stránky
- **Příklad sématických tagů:** 
	- `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<footer>` 
#### Formuláře
- formuláře slouží k odesílání dat z webové stránky na server
	- dovolují uživatelům interagovat s webovou stránkou
- **Základní tagy formulářů:** `<form>`, `<input>`, `<select>`, `<textarea>`, `<button>`
- **Typy inputů:** text, number, email, datum, checkbox, radio button, textarea
	- `<input type="email">`,...
- **Odesílání dat:** GET, POST
#### Multimédia
- HTML dovoluje vkládání multimediálního obsahu, jako jsou obrázky, videa, audio soubory
- **Typy:**
	- obrázky: `<img>`
	- videa: `<video>`
	- audio: `<audio>`
- **Formáty:** 
	- JPEG, PNG
	- MP4, MOV
	- WAV, MP3
#### Další
- V rámci HTML se může také použí JavaScript pro tvorbu interaktivních stránek
	- `<script></script>` nebo `<script src="script.js"></script>`
- Do HTML hlavičky se může také zakomponovat CSS pro úpravu vzhledu stránky či jiné designové knihovny, např.: bootstrap atp..
	- `<style>display: prdel;</style>`
- Jednotlivé tagy mohou také obsahovat **id** nebo **class** pro přesnější odkazování na dané elementy v JS nebo CSS
	- id se používá pro jeden element na stránce
	- class může mít několik elementů na stránce
	- `<div id="prdel_1"></div>` nebo `<div class="prdelclass"></div>` 