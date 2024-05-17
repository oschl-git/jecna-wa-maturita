# 2 - Webový server - konfigurace, provoz, cachování, bezpečnost

## O čem mluvit?

- uvést web server
  - co to je, k čemu slouží
  - základní info o funkcích a vlastnostech
  - jaké máme web servery
- co můžeme nastavit na web serveru
- co je dobré nastavit na web serveru
- popis provozu a implementace web serveru
- cache
  - k čemu slouží
  - proč ji využívat
  - typy
  - jak funguje
- bezpečnost
  - způsoby jak zajistit bezpečný w. server

### Ondrova poznámka:
>"Myslím ale že tam chybí věci jako NodeJS, Flask, atd. které neběží přes Apache nebo Nginx ale jsou webservery samotné, že je pustíš na serveru jako daemon a zvládají ty requesty samy. Když jsem tohle řešil s Adámkem tak vím že jsme porovnávali rychlosti, že je PHP pomalejší protože běží přes Apache/Nginx.
>Oh ye a v praxi se daleko častěji Apache a Nginx používá na PHP než na statické HTML určitě. 
>Jakoby většina jazyků ve kterých programuješ backend běží jako samotný webserver proces, nepotřebuješ Apache nebo Nginx, i když se třeba často používají ve spojení protože umí udělat věci jako reverse proxy atd."


## Webový server

- Druh serveru, který poskytuje klientům, nejčastěji webovým prohlížečům, požadovaný webový obsah specifikovaný URL adresou, typicky webové stránky
- Počítač nebo daemon, který komunikoje s klientem prostřednictvím HTTP/HTTPS protokolu
- Nejpoužívanější web servery jsou _Apache HTTP Server_, _Internet Information Service_ (IIS) a _nginx_ (nejpoužívanější overall je stejně Apache, 50% aktivních webů na něm běží)

**Základní funkce, které většina webových serverů obvykle má:**

- _Obsluha statického obsahu_: aby bylo možné obsluhovat statický obsah (webové soubory) klientům prostřednictvím protokolu HTTP
- _HTTP_: podpora jedné nebo více verzí HTTP protokolu pro zasílání verzí HTTP odpovědí kompatibilních s verzemi HTTP požadavků klienta, např. HTTP/1.0, HTTP/1.1 (případně i se šifrovaným spojením HTTPS), plus HTTP/2, HTTP/3, pokud je k dispozici
- _Protokolování (logování)_: webové servery mají obvykle také schopnost zaznamenávat některé informace o požadavcích klientů a odpovědích serveru do souborů protokolu pro bezpečnostní a statistické účely

**Další, pokročilejší vlastnosti a funkce:**

- _Poskytování dynamického obsahu_: aby bylo možné klientům poskytovat dynamický obsah (generovaný za běhu) prostřednictvím protokolu HTTP
- _Virtuální hosting_: aby bylo možné obsluhovat mnoho webových stránek (doménových jmen) pomocí pouze jedné IP adresy
- _Autorizace_: aby bylo možné povolit, zakázat nebo autorizovat přístup k částem cest webových stránek (webových zdrojů)
- _Mezipaměť obsahu_: možnost ukládat statický a/nebo dynamický obsah do mezipaměti, aby se urychlily odezvy serveru
- _Podpora velkých souborů_: aby bylo možné obsluhovat soubory, jejichž velikost je větší než 2 GB na 32bitovém operačním systému
- _Omezení šířky pásma_: omezit rychlost odpovědí na obsah, aby nedošlo k nasycení sítě a aby bylo možné obsluhovat více klientů
- _Přepisovací modul_: pro mapování částí čistých URL adres (nalezených v požadavcích klientů) na jejich skutečná jména
- _Vlastní chybové stránky_: podpora přizpůsobených chybových zpráv HTTP

**Průběh zpracování dotazu**

- Odkaz `http://www.example.com/path/file.html` je klientem převeden na HTTP 1.1 požadavek ve tvaru:

```
GET /path/file.html HTTP/1.1
Host: www.example.com
```

- Webový server na adrese `www.example.com` přidá tuto cestu k cestě kořenového adresáře příslušného webového serveru (pro Linux typicky `/var/www/html`) a výsledkem bude cesta k lokálnímu souboru:

```
/var/www/html/path/file.html
```

- Tento soubor se odešle v odpovědi serveru

![webserver](https://github.com/oschl-git/jecna-wa-maturita/blob/main/images/02_webserver.jpg)

> Autor: Pastorius na projektu Wikipedie v jazyce čeština, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=4921354

### Konfigurace

- Každý z uvedených web serverů se konfiguruje trochu jinak, např. Apache používá _konfigurační soubory_, IIS má GUI prostředí ke konfiguraci
- I tak mají ale společné věci, které je potřeba nastavit:
  - Výchozí adresář přístupný z internetu
  - Které přípony přímo posílat
  - Které přípony zpracovávat a přes které preprocesory
  - Pro které adresáře vypíše seznam souborů
  - MIME typy a jak je zpracovat
  - Konfigurace modulů (modů)
  - Nastavení IP adresy a portů

## Provoz webového serveru

- **Vybrat software webového serveru**
  - Vybrat si software webového serveru, který vyhovuje našim potřebám, Apache, Nginx a LiteSpeed jsou oblíbené volby v závislosti na našich požadavcích
- **Instalace a konfigurace**
  - Instalace vybraného softwaru webového serveru na náš server nebo hostitelské prostředí
  - Konfigurace nastavení, jako je kořen dokumentu, pravidla zabezpečení a virtuální hostitelé
- **Nahrání svého webu**
  - Nahrání souborů naši webové stránky na server
  - Obvykle se jedná o HTML, CSS, JavaScript a další datové zdroje, jako jsou obrázky nebo videa
- **Testování webu**
  - Testování webu tak, že k němu přistoupíte prostřednictvím webového prohlížeče
  - Ujistětíme se, že se správně načítá a všechny funkce fungují podle našeho očekávání
- **Monitorování a údržba**
  - Pravidelně sledujeme webový server z hlediska výkonu, zabezpečení a aktualizací (k tomu nám můžou pomoct aplikace třetích stran, jako např. _pm2_)
  - Implementujte bezpečnostní opatření na ochranu před hrozbami

## Cachování ve webovém serveru

- Ukládání obsahu do mezipaměti je jedním z nejúčinnějších způsobů, jak zlepšit zážitek návštěvníků vašeho webu
- Ukládání do mezipaměti, neboli dočasné ukládání obsahu z předchozích požadavků, je součástí základní strategie doručování obsahu implementované v rámci protokolu HTTP
- Komponenty v celé cestě doručení můžou všechny položky ukládat do mezipaměti, aby se urychlily následné požadavky, a to v souladu se zásadami ukládání do mezipaměti deklarovanými pro obsah
- Co cachujeme? Jakýkoliv statický obsah, jako jsou obrázky, styly, JS soubory a i stažitelný obsah
- Obsah který rozhodně necachujeme jsou např. citlivé údaje, nebo obsah, který je uživatelsky specifický
- Typicky se cachuje buďto na straně server (Server-side caching) nebo na straně uživatele (Client-side caching), liší se v tom, kde je obsah stránky ukládán

**Jak funguje ukládání webových stránek do mezipaměti?**

- Uživatel vytvoří požadavek na webovou stránku prostřednictvím svého prohlížeče na prostředek ze zdrojového serveru
- Tímto datovým zdrojem je webová adresa – `https://www.example.com/how-it-works`
- Na základě tohoto požadavku prohlížeč, CDN nebo mezipaměť serveru nejprve zkontroluje, zda kopie požadované webové stránky již existuje
- V procesu kontroly, zda je mezipaměť k dispozici, uživatel odešle požadavek na webovou stránku a výsledek se rozdělí mezi 2 možné scénáře:
  - **Scénář 1**: Chyba mezipaměti: Pokud v mezipaměti není nalezena žádná kopie požadované webové stránky, bude to mít za následek chybějící odpověď mezipaměti – a prohlížeč bude muset provést nový požadavek z hlavního serveru. Mezitím, pokud je webová stránka uložena v mezipaměti, prohlížeč pokračuje v doručování verzí uložených v mezipaměti z místa, kde je uložena, dokud není vymazána nebo nevyprší její platnost.
    ![scene1](https://github.com/oschl-git/jecna-wa-maturita/blob/main/images/02_cache1.png)
  - **Scénář 2**: Požadavek na mezipaměť: Předpokládejme, že kopie požadované webové stránky je uložena v mezipaměti. V takovém případě dojde k odpovědi na přístup do mezipaměti a prostředek obsažený v mezipaměti se doručí uživateli.
    ![cache2](https://github.com/oschl-git/jecna-wa-maturita/blob/main/images/02_cache2.png)

**Výhody**

- _Snížené náklady na síť_: Obsah je možné ukládat do mezipaměti v různých bodech síťové cesty mezi příjemcem obsahu a původem obsahu. Když je obsah uložen do mezipaměti blíže k příjemci, požadavky nezpůsobí mnoho dalších síťových aktivit nad rámec mezipaměti.
- _Vylepšená odezva_: Ukládání do mezipaměti umožňuje rychlejší načítání obsahu, protože není nutná celá síť. Mezipaměti udržované v blízkosti uživatele, jako je mezipaměť prohlížeče, mohou toto načtení téměř okamžitě načíst.
- _Vyšší výkon na stejném hardwaru_: Na serveru, ze kterého obsah pochází, lze ze stejného hardwaru vymáčknout více výkonu povolením agresivního ukládání do mezipaměti. Vlastník obsahu může využít výkonné servery podél doručovací trasy, aby převzal hlavní nápor určitého načítání obsahu.

## Bezpečnost webového serveru

- **Běžné hrozby:**
  - útoky - DDoS, SQL injection, Code injection, XSS,...
  - malware a phishing
  - krádeže dat
- **Preventivní opatření:**
  - nastavení firewallu a Access Control Lists (ACL) pro omezení přístupu k serveru na základě IP adres a portů
  - konfigurace HTTPS a SSL certifikátů
    - SSL/TLS šifrování: zabezpečení komunikace mezi klientem a serverem
  - implementace bezpečnostních protokolů (HSTS, CSRF, XSS,...)
  - silná hesla pro přístup k DB a správě serveru
  - pravidelná aktualizace softwaru a záplatování zranitelností
