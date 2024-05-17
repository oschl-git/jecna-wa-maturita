# 4 - Asynchroní a synchroní komunikace na webu

## O čem mluvit?
- popsat sync komunikaci
	- k čemu se používá
	- v čem je dobrá
	- příklad
- popsat async komunikaci
	- k čemu se používá
	- jaké má výhody
	- příklad

## Synchronní komunikace: 
- (Ve stejném čase (i místě), okamžitá, telefonování, chat, videocall)
- Klient odešle požadavek na server a čeká na odpověď, než bude pokračovat v dalších operacích
- Klient je zablokován, dokud server neodpoví, což může vést ke špatnému uživatelskému prostředí, zejména u pomalých nebo náročných odezev serveru. 
- Obvykle se používá v tradičních webových aplikacích, kde uživatel zahájí akci, jako je kliknutí na odkaz nebo odeslání formuláře, a server odpoví novou stránkou nebo částečnou aktualizací aktuální stránky.
- Jednoduchá implementace a pochopení
- Příkladem synchronní komunikace je XMLHttpRequest s parametrem `false`

**Příklad:**

```javascript
document.write("Hi");
document.write("<br>");

document.write("Bro");
document.write("<br>");

document.write("How are you");
```

- Synchronní znamená, že je v sekvenci, tj. každý příkaz kódu se provádí jeden po druhém
- Příkaz tedy musí počkat na provedení předchozího příkazu

## Asynchronní komunikace: 
- (Na komunikaci nemusíme odpovídat hned (na stejném místě), reakce na příspěvky není okamžitá, email, forum)
- Klient může odeslat požadavek na server, aniž by čekal na odpověď
- Klient může pokračovat v dalších operacích, zatímco server zpracuje požadavek a odešle odpověď zpět
- Obvykle se dosahuje pomocí technologií, jako je AJAX (asynchronní JavaScript a XML) nebo WebSockets
- Umožňuje citlivější a interaktivnější uživatelské prostředí, protože uživatel může pokračovat v interakci s aplikací, zatímco server zpracovává požadavek
- Běžně se používá v moderních webových aplikacích, jako jsou jednostránkové aplikace (SPA), kde se uživatelské rozhraní dynamicky aktualizuje bez nutnosti aktualizace celé stránky
- Může vést k plynulejšímu a efektivnějšímu uživatelskému prostředí, protože aplikace může aktualizovat konkrétní části stránky bez opětovného načtení celé stránky
- Příkladem asynchronní komunikace je XMLHttpRequest s parametrem `true` nebo Fetch API

**Příklad:**

```javascript
document.write("Hi");
document.write("<br>");

setTimeout(() => {
	document.write("Let us see what happens");
}, 2000);

document.write("<br>");
document.write("End");
document.write("<br>");
```
