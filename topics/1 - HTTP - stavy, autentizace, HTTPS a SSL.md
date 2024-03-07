# 1 - HTTP - stavy, autentizace, HTTPS a SSL
- **Hyper Text Transfer Protocol** (Insecure TwT 👉👈)
- nejpoužívanější proces pro přenos hypertextových dokumentů mezi klientem a serverem
- funguje způsobem dotaz-odpověď (GET, POST, PUT, DELETE)
- čitelný člověkem - je to čistý text
	- formát HTML, XML
- používá port TCP/80
- *bezestavový protokol* - neumí uchovat stav komunikace, dotazy nemají souvislost
- **verze**:
	- HTTP/1.1 až HTTP/3
	- HTTP/1.1 je doposud nejpoužívanější
## Stavy 
- **2xx - Úspěšné:**
    - 200 OK: Požadavek byl úspěšně zpracován.
    - 201 Created: Požadavek byl úspěšně zpracován a byl vytvořen nový zdroj.
- **3xx - Presměrování:**
    - 301 Moved Permanently: Požadovaný zdroj byl trvale přesunut na jinou adresu.
    - 302 Found: Požadovaný zdroj byl dočasně přesunut na jinou adresu.
- **4xx - Chyba klienta:**
    - 400 Bad Request: Požadavek klienta je chybný.
    - 404 Not Found: Požadovaný zdroj neexistuje.
- **5xx - Chyba serveru:**
    - 500 Internal Server Error: Na serveru došlo k chybě.
    - 503 Service Unavailable: Server je dočasně nedostupný.
## Autentizace
- Autentizace je proces ověřování identity uživatele/zařízení 
- Používá k ochraně přístupu k citlivým zdrojům
- **Základní typy autentizace:**
	- **Basic:** Uživatel zadává své uživatelské jméno a heslo v hlavičce požadavku, 2FA,...
	- **Digest:** Uživatelské jméno a heslo se neodesílají v čistém textu, ale v zašifrované podobě
## HTTPS & SSL/TLS
- Hypertext Transfer Protocol Secure
- šifruje data při komunikaci mezi klientem a serverem
	- zajišťuje integritu, autentizaci a důvěrnost posílaných dat
	- chrání data před odposlechem a manipulací
- používá HTTP s SSL/TLS (Secure Sockets Layer/Transport Layer Security)
	- SSL/TLS šifrují data - vytváří šifrovaný kanál mezi klientem a serverem
- standartní port je 443 TCP
- zabezpečení pomocí podepisování a ověřování certifikátů třetích stran
- nemusí být kompatibilní se staršími prohlížeči (Internetový explorér 🤮)