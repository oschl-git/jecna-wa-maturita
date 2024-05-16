# 1 - HTTP - stavy, autentizace, HTTPS a SSL

## HTTP - Hyper Text Transfer Protocol
- Internetový bezstavový protokol určený pro komunikaci s WWW serverem
- Slouží pro přenost hypertextových dokumentů ve formátu HTML nebo XML
- Pomocí rozšíření MIME (Multipurpose Internet Mail Extension) dokáže přenos jakéhokoliv typu souboru
- Samotný protokol neumožňuje šifrování
- Založen na TCP/IP protokolu
- Protokol funguje způsobem *dotaz-odpověď*
- Verze HTTP/1.1, HTTP/2 a HTTP/3
- Používá port 80
### Průběh komunikace
- Uživatel zašle dotaz serveru ve formě čistého textu(většinou pomocí porohlížeče)
- Tento text obsahuje označení požadovaného dokumentu + info o prohlížeči, apod.
- Server potom odpoví pomocí několika řádků textu popisující výsledek dotazu
- Zda dokument existuje, typ dokumentu, apod.
- Za tímto textem už jsou data samotného požadovaného dokumentu

![http_communication](https://github.com/oschl-git/jecna-wa-maturita/blob/main/images/01_http.jpg)

**Příklad:**

Uživatelský program (klient) se připojí na server cs.wikipedia.org a zašle následující dotaz:

```
GET /wiki/Wikipedie HTTP/1.1
Host: cs.wikipedia.org
User-Agent: Opera/9.80 (Windows NT 5.1; U; cs) Presto/2.5.29 Version/10.60
Accept-Charset: UTF-8,*
```

Server pak odpoví:

```
HTTP/1.0 200 OK
Date: Fri, 15 Oct 1654 08:20:25 GMT
Server: Apache/1.3.29 (Unix) PHP/4.3.8
X-Powered-By: PHP/4.3.8
Vary: Accept-Encoding,Cookie
Cache-Control: private, s-maxage=0, max-age=0, must-revalidate
Content-Language: cs
Content-Type: text/html; charset=utf-8
```

### Stavové kódy
Stavové kódy odpovědí HTTP označují, jestli byl konkrétní požadavek HTTP úspěšně dokončen.

- **1xx - Informační:**
	- 100 Continue: Server dostal hlavičky dotazu a klient by měl zaslat tělo dotazu
	- 101 Switching Protocols: Žadatel požádal server o změnu protokolů
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

Víc příkladů [zde](https://status.js.org/)
### Autentizace
- Autentizace je proces ověřování identity uživatele/zařízení 
- Používá se k ochraně přístupu k citlivým zdrojům
- HTTP poskytuje několik schémat autentizace, např.: *základní ověřování přístupu* (header `Authentication: Basic`) a *ověření přístupu digsetem*, které fungují prostřednictvím mechanismu *výzva-odpověď*, kdy server identifikuje a vydá výzvu před doručením požadovaného obsahu
- Industry standard je protokol OAuth 2.0


## HTTPS - Hypertext Transfer Protocol Secure
- Protokol umožňující zabezpečenou komunikaci v počítačové síti - především v komunikaci prohlížeče a webového serveru
- Využívá protokol HTTP společně s TLS nebo SSL
- Ocharana spočívá v podepisování digitálních certifikátů třetích stran na straně serveru
- Historicky se používala pouze na zabezpečených službách platebních transakcích a jiných systémech, které nutně vyžadovaly zabezpečení, toto bylo z důvodu nákladnosti operace ověřování certifikátů
- Všeobecně je dnes doporučeno používat HTTPS na všech webových stránkách
- Používá port 443

![https](https://github.com/oschl-git/jecna-wa-maturita/blob/main/images/01_https.png)

### Princip funkce zabezpečení
- Bezpečnost komunikace zaručuje protokol SSL(Secure Socket Layer) anebo novější TLS(Transport Layer Security)
- Tyto protokoly šifrují komunikaci mezi klientem a serverem
- Začne se s **SSL/TLS handshake**, kdy dochází k dotazování podepsaného certifikátu od serveru
- Pokud je platný, prohlížeč vytvoří, zašifruje a odešle zpět symetrický klíč pomocí veřejného klíče serveru
- Server ho dešifruje pomocí svého privátního klíče, a klient i server používají tento symterický klíč k šifrování a dešifrování posílaných dat
- Toto zajišťuje bezpečnost proti *man in the middle* útokům

#### SSL
- Aby byl zajištěn vysoký stupeň soukromí, SSL šifruje data, která jsou přenášena po webu
- To znamená, že každý, kdo se pokusí tato data zachytit, uvidí pouze zašifrované zprávy, které je velice těžké dešifrovat bez toho, aniž by jsme neměli klíč
- SSL iniciuje proces ověřování nazývaný handshake mezi dvěma komunikujícími zařízeními, aby se zajistilo, že obě zařízení jsou skutečně tím, za koho se vydávají 
- SSL také digitálně podepisuje data, aby byla zajištěna integrita dat, a ověřuje, že s daty není manipulováno, než se dostanou k zamýšlenému příjemci

- Došlo k několika iteracím SSL, z nichž každá byla bezpečnější než ta předchozí. V roce 1999 byl protokol SSL aktualizován na TLS

**Typy SSL certifikátů:**

- *Single-domain*: certifikát pouze pro jednu doménu
- *Wildcard*: taky pouze pro jednu doménu, ale také pro její subdomény (např.: erik-smrdi.com a blog.erik-smrdi.com)
- *Multi-domain*: certifikát pro více domén, které spolu nesouvisí

**Typy SSL validace:**

- *Domain Validation*: nejméně přísná a nejlevnější úroveň validace, jediné co musí firma udělat, je prokázat se, že doménu ovládá
- *Organization Validation*: certifikační autorita přímo kontaktuje osobu nebo firmu, která certifikát žádá, tyto certifikáty jsou pro uživatele důvěryhodnější
- *Extended Validation*: úplný background check organizace, než se vydá SSL certifikát
