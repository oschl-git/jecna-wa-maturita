# 12 - HTML struktura, sémantika, formuláře, multimédia

## O čem mluvit?
- HTML
	- jak, kdy, proč vzniklo
	- na čem je založené
	- jakou verzi HTML používáme teď
	- popsat k čemu ho používáme
	- tagy a elementy, rozdíl
- popsat strukturu HTML dokumentu
- co potřebujeme mít v dokumentu aby byl validní
- proč je dodržení struktury důležité
- co je sémantika
- k čemu využíváme formuláře
- jak zobraztit multimédia v HTML, jaké typy
- čím můžeme zlepšit náš HTML dokument?

## HTML
- **HyperText Mark-up Language**
- Vyvinut v roce 1990 anglickým informatikem Timem Bernersem-Leem (vytvořil i první webový prohlížeč)
- Tim Berners-Lee ho vydal společně s HTTP (Hypertext Transfer Protocol)
- Je založen na SGML (Standard Generalized Markup Language), což byl používaný jazyk na psaní mark-upových dokumentů
- HTML si od SGML bere zejména využití **tagů**, přímo *vypůjčené* jsou např.: `<title></title>`, `<h1></h1>`, `<ul></ul>`, `<li></li>`, a další..
- HTML má také o dost snažší syntaxi, než SGML, na pochopení a naučení, je proto více uživatelsky přívětivé, což pomohlo k jeho rozšíření 
- HTML bylo vyvinuto především jako možnost zobrazování dokumentů "s tlačítky", která by mohla zobrazovat jiný dokument, nebo část jiného dokumentu, jelikož Berners-Lee pracoval ve vědecké společnosti CERN, chtěl tímto usnadnit čtení vědeckých dokumentů, kde v jednom dokumentu by mohli být odkazy na jiné nebo související témata (hypertextové odkazy)
- Byli vytvořeny verze HTML, nejdřív jen HTML, pak HTML+, HTML3, ...
- Dnes se běžně používá HTML5, pro vytvoření struktury webové stránky
- Základní nástroj pro vytvoření nějakého webu
## Struktura
- HTML dokument je tvořen tzn. **tagy**
- Tagy jsou obvykle párové - mají tag na označení začátku a konce
- HTML dokumenty se řídí jasnou strukturou:
	- `<html>`
	- `<head>`
	- `<body>`
	- `<footer>`
- Tato struktura by měla být dodržena pro správnost dokumentu/stránky
- Také zajišťuje čitelnost a nějaký standart

### Tagy a elementy
- HTML tagy vytvoří tzn. HTML elementy
Příklad:
```html
<p>Lorem ipsum</p> -> paragraf
<title>Title</title> -> titul dokumentu
<h2>Hello</h2> -> nadpis
<div></div> -> vytvoří sekci dokumentu
<a>http://prdel.com</a> -> link
atd...
```

**Tag x element**
- Tag je např. pouze `<p>`
- Zatímco celé `<p>Lorem ipsum</p>` je element
- Element se běžně skládá z *opening tagu*, *obsahu* a *closing tagu*

Více příkladů [zde](https://www.w3schools.com/TAGs/)

## Validace
- HTML dokument by měl dodržovat nějakou strukturu
- Když ji nedodrží, HTML dokument je pak nevalidní
- Např. když nemá dokument `<DOCTYPE>`, nebo nemá stanovenou znakovou sadu
- Validaci našeho dokumentu je snadné zjistit pomocí webových stránek jako např.: [HTML Validator](https://validator.w3.org/index.html#validate_by_uri+with_options)

## Sémantika
- Definují význam obsahu pro webové prohlížeče a vyhledávače
	- Pomáhá vyjádřit význam jednotlivých částí dokumentu a zlepšuje jeho dostupnost a SEO
- Usnadňují přístupnost a srozumitelnost webové stránky
- **Příklad sématických tagů:** 
	- `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<footer>` 

## Formuláře
- Formuláře slouží k odesílání dat z webové stránky na server
	- Dovolují uživatelům interagovat s webovou stránkou
- **Základní tagy formulářů:** `<form>`, `<input>`, `<select>`, `<textarea>`, `<button>`
- **Typy inputů:** text, number, email, datum, checkbox, radio button, textarea
	- `<input type="email">`,...
- **Odesílání dat:** GET, POST
## Multimédia
- HTML dovoluje vkládání multimediálního obsahu, jako jsou obrázky, videa, audio soubory
- **Typy:**
	- obrázky: `<img>`
	- videa: `<video>`
	- audio: `<audio>`
- **Formáty:** 
	- JPEG, PNG
	- MP4, MOV
	- WAV, MP3
## Další
- V rámci HTML se může také použí JavaScript pro tvorbu interaktivních stránek
	- `<script></script>` nebo `<script src="script.js"></script>`
- Do HTML hlavičky se může také zakomponovat CSS pro úpravu vzhledu stránky či jiné designové knihovny, např.: bootstrap atp..
	- `<style>display: prdel;</style>`
- Jednotlivé tagy mohou také obsahovat **id** nebo **class** pro přesnější odkazování na dané elementy v JS nebo CSS
	- ID se používá pro jeden element na stránce
	- class může mít několik elementů na stránce
	- `<div id="prdel_1"></div>` nebo `<div class="prdelclass"></div>` 
