# 5 - REST - identifikátor, HATEOAS, CRUD
## Identifikátor
- každá entita/zdroj v REST architektuře musí mít unikátní ID
- identifikátory jsou obvykle reprezentovány pomocí URL
	- slouží jako přístup k dané entitě/zdroji
- **Typy IDs:**
	- **UUID:** univerzálně unikátní identifikátor, generovány náhodně
	- **Auto-increment ID:** ID jako v DB, postupně se zvyšující číslo
	- **Kompozitní klíč:** Kombinace několika atributů, které společně identifikují entitu.
## REST
- **Representational State Transfer**
- cesta, jak jednoduše vytvořit, číst, aktualizovat (editovat) nebo smazat informace ze serveru pomocí jednoduchých HTTP volání
- požadavky na architektonický styl vyhovující paradigmatu REST:
	- client-server - client a server jsou nezávislí
	- bezestavový - server nezaznamenává stav clienta
	- cache - server označuje data ukládaná do mezipaměti
	- uniform interface - server vystavuje klientovi prostředky jednotným a předvídatelným způsobem
	- layered system - prostředníci mezi klientem a serverem chování neovlivňují
	- (volitelný) code-on-demand - server klientovi může přidat další funkce tím, že mu pošle kód, který může tento klient spustit

- použitelný pro snadný přístup ke zdrojům (data, stavy aplikace)
- orientován datově
## HATEOAS
- **Hypermedia As The Engine Of Application State**
- jeden ze základních principů REST architektury
- spočívá v komunikaci klientské aplikace s aplikačním serverem skrze dynamicky poskytované hypermédium
- komunikace probíhá v dotazech od REST klienta na serverovou REST aplikaci skrze URL
- umožňuje vytvořit flexibilní a samoobsahující API, které může být snadno rozšířeno nebo změněno bez nutnosti měnit klientskou aplikaci
- všechny další akce jsou obsažené v "resource", vrácené serverem
## CRUD
- **Create, Read, Update, Delete**
- základní operace pro manipulaci s daty
- POST/PUT *- Create*
- GET *- Read*
- PUT/PATCH *- Update*
- DELET *- Delete*
