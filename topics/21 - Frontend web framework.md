## Co je to Frontend Web Framework?

Frontend web framework (FWF) je nástroj, který vývojářům usnadňuje tvorbu a správu uživatelského rozhraní webových aplikací. Pomáhá organizovat kód, zjednodušuje vývoj a zlepšuje údržbu aplikací. FWF nabízí strukturu a sadu nástrojů pro práci s frontendem.

## Frontend

- **Frontend (FE)**: Část webové aplikace, kterou uživatel vidí a se kterou interaguje. Zahrnuje:
    - Tlačítka
    - Layout
    - Navigace
    - Obrázky
    - Organizace obsahu
- **Základní Složky Frontendu**
	1. **HTML (HyperText Markup Language)**:
	    
	    - **Kostra webové stránky**: HTML je základním stavebním kamenem webové stránky, definuje strukturu a obsah.
	    - **Elementy a značky**: Umožňuje vkládat různé elementy jako nadpisy, odstavce, odkazy, obrázky, formuláře apod.
	    - **Semantika**: Pomáhá při správném označení obsahu pro lepší SEO a přístupnost (např. `<header>`, `<nav>`, `<section>`, `<footer>`).
	2. **CSS (Cascading Style Sheets)**:
	    
	    - **Styling a layout**: CSS se používá k aplikování stylů na HTML elementy, včetně barev, fontů, rozložení a animací.
	    - **Responsivita**: Umožňuje přizpůsobit vzhled stránky různým zařízením (mobilní telefony, tablety, desktopové počítače) pomocí media queries.
	    - **Flexbox a Grid**: Moderní techniky layoutu pro vytvoření komplexních a flexibilních rozložení.
	3. **JavaScript (JS)**:
	    
	    - **Interaktivita**: JavaScript umožňuje vytvářet dynamické a interaktivní prvky na stránce, jako jsou formuláře, galerie obrázků, animace apod.
	    - **Manipulace s DOM**: JavaScript může dynamicky měnit obsah a strukturu HTML dokumentu.
	    - **Asynchronní operace**: Umožňuje načítání dat na pozadí (AJAX) bez nutnosti obnovovat stránku.
	4. **WebAssembly (Wasm)**:
	    
	    - **Alternativa k JavaScriptu**: WebAssembly umožňuje běh kódu napsaného v jiných programovacích jazycích (např. C, C++, Rust) v prohlížeči.
	    - **Výkon**: Poskytuje vyšší výkon pro výpočetně náročné aplikace jako hry, CAD aplikace, zpracování videa apod.
#### Rozdíl mezi Frameworkem a Knihovnou

#### Knihovna

- **Definice**:
    - Knihovna je soubor předem napsaného kódu, který lze použít k provádění běžných úkolů.
    - Poskytuje specifické funkce nebo metody, které lze volat v rámci vašeho vlastního kódu.
- **Kontrola**:
    - Vývojář má plnou kontrolu nad tokem aplikace.
    - Kód vývojáře volá funkce knihovny dle potřeby.
- **Použití**:
    - Např. jQuery: knihovna pro manipulaci s DOM, animace, eventy apod.
    - Lodash: knihovna pro práci s datovými strukturami (např. pole, objekty).

#### Framework

- **Definice**:
    - Framework je komplexnější než knihovna. Poskytuje základní strukturu a architekturu aplikace.
    - Určuje, jak by měla být aplikace strukturována a jaký by měl být tok řízení.
- **Kontrola**:
    - Framework řídí tok aplikace a volá kód vývojáře.
    - Vývojář doplňuje framework o specifické implementace dle potřeby.
- **Použití**:
    - Např. Angular: framework pro vývoj webových aplikací s kompletními nástroji pro správu dat, routing, formuláře apod.
    - Django: framework pro vývoj webových aplikací v Pythonu, poskytující ORM, autentizaci, administraci apod.

### Příklad Proporce Kontroly

#### Knihovna:

```javascript
// Použití knihovny Lodash
const balls = require('lodash');
let array = [1, 2, 3, 4, 5];
let reversedArray = balls.reverse(array);
console.log(reversedArray); // [5, 4, 3, 2, 1]
```

V tomto případě vývojář volá funkci `balls.reverse` z knihovny Lodash, aby otočil pole.

#### Framework:

javascript
```javascript
// Použití frameworku Express.js v Node.js
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello World');
});

app.listen(3000, () => {
  console.log('Server is running on port 3000');
});
```

Zde framework Express.js určuje základní strukturu aplikace, včetně způsobu obsluhy HTTP požadavků. Vývojář doplňuje specifické implementace jako reakce na požadavky.

### Shrnutí

- **Knihovna**:
    - Nabízí specifické funkce.
    - Vývojář má kontrolu nad tokem aplikace.
- **Framework**:
    - Poskytuje strukturu a pravidla pro tvorbu aplikace.
    - Framework má kontrolu nad tokem aplikace a volá kód vývojáře.
#### Kde se s Frontendem Setkáme?

- **Webové stránky**: Všechny klasické webové stránky, které navštěvujete denně, od osobních blogů po zpravodajské servery.
- **Webové aplikace**: Interaktivní aplikace běžící v prohlížeči, jako jsou Gmail, Google Docs, Trello, Slack.
- **Mobilní aplikace**: Některé hybridní nebo progresivní webové aplikace (PWA) využívají frontendové technologie k poskytování zážitků podobných nativním mobilním aplikacím.

#### Role Frontend Vývojáře

- **Implementace designu**: Převádění grafických návrhů do funkčního kódu pomocí HTML, CSS a JavaScriptu.
- **Zajištění interaktivity**: Programování funkcí, které umožňují uživateli interagovat s webem.
- **Optimalizace výkonu**: Zajištění rychlého načítání a plynulého fungování webové stránky.
- **Responzivní design**: Přizpůsobení webu pro různé velikosti a typy zařízení.
- **Cross-browser kompatibilita**: Ujištění se, že webová stránka funguje správně ve všech moderních prohlížečích.


## Rozdělení Frontend Frameworků

### Opinionated vs. Unopinionated Frameworky

- **Opinionated Frameworky**:
    - Nabízí jasně definovanou strukturu a způsob, jakým by měl být kód psán.
    - Příklady: Angular, Ember.js
- **Unopinionated Frameworky**:
    - Neomezují vývojáře v tom, jak by měl být kód strukturován, poskytují více volnosti.
    - Příklady: React, Vue.js

### Historický Vývoj a Současné Použití

- **Historicky**:
    - Jquery: Populární v minulosti, jednoduchý pro manipulaci s DOM.
    - Backbone.js: Umožnil lepší organizaci kódu pomocí modelů a kolekcí.
- **Současnost**:
    - React: Nejpopulárnější knihovna pro budování uživatelských rozhraní.
    - Angular: Kompletní framework pro robustní webové aplikace.
    - Vue.js: Flexibilní a snadno integrovatelný framework, oblíbený mezi menšími týmy a projekty.

## Hlavní Frontend Frameworky

### React

- **Specifika**:
    - Komponentově orientovaný přístup.
    - Virtuální DOM pro efektivní aktualizace uživatelského rozhraní.
    - Velká komunita a podpora.
- **Použití**:
    - Ideální pro dynamické a vysoce interaktivní aplikace.
    - Používán firmami jako Facebook, Instagram, Airbnb.

### Angular

- **Specifika**:
    - Kompletní framework poskytující vše potřebné pro vývoj aplikací.
    - Používá TypeScript, což zlepšuje typovou bezpečnost.
    - Dvoucestná datová vazba pro synchronizaci modelu a pohledu.
- **Použití**:
    - Vhodný pro enterprise aplikace s komplexní logikou.
    - Používán firmami jako Google, Microsoft, IBM.

### Vue.js

- **Specifika**:
    - Progresivní framework, který lze snadno integrovat do stávajících projektů.
    - Flexibilní a méně náročný na učení než Angular.
    - Reaktivní data binding a komponentový systém.
- **Použití**:
    - Vhodný pro menší a středně velké projekty.
    - Používán firmami jako Alibaba, Xiaomi.

### Ember.js

- **Specifika**:
    - Silně opinionated framework s vlastním stylem a konvencemi.
    - Dvoucestná datová vazba, podobně jako Angular.
    - Inženýrské zaměření na produktivitu a výkonnost.
- **Použití**:
    - Ideální pro ambiciózní webové aplikace.
    - Používán firmami jako LinkedIn, Netflix.

## Uživatelská Rozhraní a Stylizace

- **UI Frameworky**:
    - **Bootstrap**: Sada CSS a JS nástrojů pro responzivní a mobilní-first vývoj.
    - **Materialize**: Framework založený na Material Design od Googlu.
    - **Foundation**: Flexibilní front-end framework s množstvím komponent a grid systémem.
    - **Semantic UI**: Framework zaměřený na vývoj s použitím čitelného HTML.
