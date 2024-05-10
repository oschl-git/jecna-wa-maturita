# 23 - Responzivní design a přístupnost

## O čem mluvit
- Responzivní design
	- proč se serem s responzivním designem?
	- jak zlepšuje uživatelský zážitek
	- jak ho dosáhnem
	- jak se testuje, co za nástroje jsou k tomu dispozici
	- nějaké principy přístupu (Mobile first např.)
- SEO optimalizace
	- k čemu je


## Responzivní design
- Responzivní design je přístup k návrhu webových stránek a aplikací, který zajišťuje, že se obsah přizpůsobí různým zařízením a velikostem obrazovek.
- **Responzivita podle zařízení:** Jeho cílem je zajistit optimální uživatelský zážitek bez ohledu na to, zda uživatel používá mobilní zařízení, tablet, notebook nebo desktop.
- **Responzivní mřížky:** Základní principy responzivního designu zahrnují použití pružných mřížek, které se přizpůsobují šířce obrazovky, flexibilních obrázků a media dotazů pro získání informací o zařízení uživatele.
- **SEO optimalizace:** Responzivní design je klíčový pro optimalizaci uživatelského zážitku a SEO (Search Engine Optimization), protože vyhledávací algoritmy jako Google preferují responzivní weby při hodnocení výsledků vyhledávání.
- **Postup při vývoji:** 

## Jak toho dosáhnout
- Namísto používání `px` je lepší použít "ohebné" jednotky jako jsou `%` nebo `em` 
- Použít mřížkoví systém jako je například Bootstrap nebo CSS grid
- Media Queries která se dokážou orientovat podle velikosti zařízení
```css
@media screen and (min-width: 480px) {  
	body {    
	background-color: lightgreen;  
	}
}
```
- Nastavit responzivní velikost na obrázky
```css
img {
    max-width: 100%;
    height: auto;
}
```
- Otestovat to na různých zařízení a prohlížečů
	- různé web-browsers pluginy
	- web tools
	- Lighthouse od google

## Přístupnost
- Přístupnost se týká zajištění toho, aby webové stránky a aplikace byly dostupné pro všechny uživatele, včetně těch s různými typy postižení, jako jsou zrakové, sluchové, motorické nebo kognitivní.
- Přístupnost zahrnuje použití správných technologií, jako jsou  jazyky HTML, CSS a JavaScript, aby byly stránky snadno čitelné pro čtečky obrazovky a další asistivní technologie.
- Dalšími prvky přístupnosti jsou alternativní texty pro obrázky, kontrastní barvy pro lepší viditelnost, přizpůsobení klávesových zkratek pro uživatele s omezenou pohyblivostí a jednoduchá navigace pro uživatele s kognitivními obtížemi.
- Zlepšení přístupnosti nejenže pomáhá lidem s postižením, ale také přispívá k lepšímu uživatelskému zážitku pro všechny uživatele a může zvýšit dosah webových stránek a aplikací.

