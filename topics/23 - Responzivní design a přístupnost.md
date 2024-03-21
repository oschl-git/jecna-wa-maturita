# 23 - Responzivní design a přístupnost

## Responzivní design
- Responzivní design je přístup k návrhu webových stránek a aplikací, který zajišťuje, že se obsah přizpůsobí různým zařízením a velikostem obrazovek.
- Jeho cílem je zajistit optimální uživatelský zážitek bez ohledu na to, zda uživatel používá mobilní zařízení, tablet, notebook nebo desktop.
- Základní principy responzivního designu zahrnují použití pružných mřížek, které se přizpůsobují šířce obrazovky, flexibilních obrázků a media dotazů pro získání informací o zařízení uživatele.
- Responzivní design je klíčový pro optimalizaci uživatelského zážitku a SEO (Search Engine Optimization), protože vyhledávací algoritmy jako Google preferují responzivní weby při hodnocení výsledků vyhledávání.

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

## Přístupnost
- Přístupnost se týká zajištění toho, aby webové stránky a aplikace byly dostupné pro všechny uživatele, včetně těch s různými typy postižení, jako jsou zrakové, sluchové, motorické nebo kognitivní.
- Přístupnost zahrnuje použití správných technologií, jako jsou  jazyky HTML, CSS a JavaScript, aby byly stránky snadno čitelné pro čtečky obrazovky a další asistivní technologie.
- Dalšími prvky přístupnosti jsou alternativní texty pro obrázky, kontrastní barvy pro lepší viditelnost, přizpůsobení klávesových zkratek pro uživatele s omezenou pohyblivostí a jednoduchá navigace pro uživatele s kognitivními obtížemi.
- Zlepšení přístupnosti nejenže pomáhá lidem s postižením, ale také přispívá k lepšímu uživatelskému zážitku pro všechny uživatele a může zvýšit dosah webových stránek a aplikací.

