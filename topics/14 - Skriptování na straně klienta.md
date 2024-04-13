# 14 - Skriptování na straně klienta
- psaní kódu, který se spouští v prohlížeči klienta
- zdrojový kód si uživatel může zobrazit
- využívá se k tvoření interaktivních a dynamických stránek
- může ulehčit zátěž na serveru přesnesením logiky na stranu klienta

## JavaScript
- prakticky jediný frontend jazyk, který moderní prohlížeče dokáží spustit
- nabízí možnosti interakce a manipulace s DOM i BOM
  - DOM = document object model, objekty na stránce
    - úprava layoutu, animace, změny stylů a obsahu, atd.
  - BOM = browser object model, objekty v prohlížeči
    - vysílání alertů, ukládání a čtení cookies a localstorage, atd.
- existuje mnoho alternativních jazyků a frameworků pro frontend skriptování, ty se ale ve výsledku také kompilují do JavaScriptu
  - React
  - Svelte
  - Vue.js
  - HTMX

### Hlavní využití
- interaktivní a dynamické weby
- změna stavů HTML prvků
- přidání vlastní logiky do formulářů
  - input validace
- offline funkce
- dynamická změna obsahu, není nutné vždy načítat novou stránku
  - "Single Page Applications"

### Nevýhody
- kód je všem viditelný, může být změněn
- kód nemusí být vždy kompatibilní s prohlížečem, může se chovat různě mezi prohlížeči
- JavaScript je relativně pomalý
- někteří uživatelé mohou mít JavaScript vypnutý

## WebAssembly
- způsob low-level skriptování na straně klienta
- umožňuje spouštět C, C++, Rust, atd. kód v prohlížeči
- není náhradou za JavaScript, fungují dohromady
- kód webových stránek může běžet stejně rychle a efektivně, jako kód desktopových aplikací
  - umožňuje tvořit např. náročné 3D hry v prohlížeči
  - složité vědecké komputace
  - přímé porty namáhavých počítačových aplikací do prohlížeče (editování videa, 3D modelování, ...)
- kód běží v sandboxovaném virtuálním prostředí
- WebAssembly a JavaScript spolu mohou sdílet data a spolupracovat