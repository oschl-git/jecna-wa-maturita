# 3 - Webový klient - konfigurace, jádro prohlížeče, DOM, BOM
## Konfigurace webového klienta
- **Obecné:** 
	- jazyk, vzhled, domovská stránka
- **Soukromí:** 
	- cookies, historie, blokování reklamy
- **Zabezpečení:** 
	- certifikáty, HTTPS, phishing
	- blokování skriptů a cookies
- **Síť:** 
	- Proxy, cache, offline režim
## Jádro prohlížeče
- **Komunikuje se serverem:**
	- načítaní webových stránek
	- odesílání formulářů
	- příjímání odpovědí
	- stahování souborů
- **Rendering engine:** 
	- načítání a vykreslování webových stránek (zobrazuje HTML, CSS,...)
- **JavaScript engine:** 
	- spouští JS kód stránek
	- např.: V8 (Chrome), SpiderMonkey (Firefox),...
- **Spravuje historii, sobory a cookies:**
	- to umí každý webbrowser
## DOM (Document Object Model)
- reprezentuje strukturu a obsah webové stránky
	- HTML nebo XML dokument
- struktura je hiearchická
- pomocí DOM můžeme dynamicky manipulovat s HTML a CSS
	- klient může přidávat, měnit nebo odstraňovat prvky na stránce, reagovat na události a aktualizovat zobrazení bez nutnosti obnovení celé stránky
## BOM (Browser Object Model)
- reprezentuje prostředí prohlížeče
- poskytuje přístup k funkcím prohlížeče
	- navigace, manipulace s okny, správa historie,....
- umožňuje zobrazování oken, dialogů a potvrzovacích okének uživateli
