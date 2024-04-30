# 18 - Cookies - formát, expirace, tracking cookies
## O čem mluvit?
- popsat, co to cookies jsou
- jakou mají velikost
- popsat, k čemu jsou vhodné, a k čemu je lepší použít např. localStorage
- vysvětlit jak fungují
	- jak je možné je nastavovat, mazat a číst
- jaké jsou speciální typy cookies
- jak je možné skrz cookies trackovat uživatele
## Cookies - formát, expirace, tracking cookies
- malé textové soubory, které se ukládají v prohlížeči klienta
- mají maximálně 4096 bytů
- cookies klient posílá serveru v každém requestu
- většinou obsahují údaje o klientovi
	- používají se k personalizaci obsahu, udržení přihlášení, sledování chování uživatelů
- **tři hlavní využití:**
	- session management (přihlášení, nákupní košík, cokoliv co by si měl server pamatovat)
	- personalizace (uživatelské nastavení, light/dark theme, atd.)
	- tracking (analyzování chování uživatelů)
## Nastavování cookies
### Skrz odpověď serveru
- server pošle `Set-Cookie` header:
```
Set-Cookie: <cookie-name>=<cookie-value>
```
- pokud se nenastaví expirace, cookie se smaže po restartu prohlížeče
- expirace se může nastavit přes `Expires` nebo `Max-Age` atributy
	- `Expires` nastaví datum a čas, po kterém už cookie nebude platit
	- `Max-Age` nastaví čas (v sekundách) jak dlouho má cookie zůstat uložena, má prioritu nad `Expires`
- např.:
```
HTTP/2.0 200 OK
Content-Type: text/html
Set-Cookie: yummy_cookie=choco; Max-Age=3600;
Set-Cookie: tasty_cookie=strawberry

[page content]
```
- prohlížeč pak serveru posílá cookie v každém requestu v `Cookie` headeru, např.:
```
GET /sample_page.html HTTP/2.0
Host: www.example.org
Cookie: yummy_cookie=choco; tasty_cookie=strawberry
```
### Skrz front-end JavaScript
- JavaScript může nastavovat cookies skrz document.cookie API
```
document.cookie = "delightful_cookie; Max-Age=3600;
```
- cookies lze získat přes `let cookies = document.cookie`;
	- vrátí string který obsahuje všechny cookies oddělené středníky, což je absolutní hrůza, např.:
	```
	cookie1=value; cookie2=value; cookie3=value;
	```
	- většinou se používají pomocné funkce/knihovny ke čtení cookies

- ve všech případech lze smazat cookies tím, že jim nastavíme expiraci na čas, který již uplynul (klasicky 01 Jan 1970 00:00:00 UTC)
## Typy cookies
- **Session cookie**: je smazaná při restartu prohlížeče
- **Persistent cookie**: je zachovaná, expiruje v určité datum a čas
- **Secure cookie**: posílá se jen skrz HTTPS
## Tracking
- cookies ze používají na sledování chování uživatelů
- při prvním requestu pošle server uživateli cookie, která uživatele unikátně identifikuje
- při dalších requestech uživatele prohlížeč cookie posílá, čímž může server sledovat, jaké stránky uživatel navštívil a jak dlouho na nich strávil