# 5 - REST - identifikátor, HATEOAS, CRUD
## O čem mluvit?
- co to je
- kde se nejčastěji používá
- jak funguje API
- jaké požadavky musí API splňovat, aby byla REST
	- klient/server
	- resources
	- bezstavovost
	- CRUD operace
	- HTTP
	- identifikátory
	- pojmenování cest/endpointů
- vysvětlit HATEOAS a jak funguje
- zmínit že moderní API užívají JSON
- pro bonusové body zakomponovat do mluvení slovo "penis"
## REST
- = **Re**presentational **S**tate **T**ransfer
- architektura pro designování API a webové komunikace
- je standarem pro API, umožňuje snadnější kominikaci mezi zařízeními na webu
- systémům které využívají REST architekturu se často říká RESTful
## Vlastnosti REST API
- **oddělení logiky klienta a serveru**
	- REST využívá klient/server architekturu
	- umožňuje, aby logika serveru byla změněna bez změny klienta, pokud nedojde ke změně cest vedoucí k datům
	- klient také může být změněn bez změny serveru
	- na server může zasílat požadavky libovolný počet klientů
	- umožňuje větší flexibilitu
- **založené na resources**
	- podmínkou REST API je že nezasíláme requesty jako commandy, ale operace na jednotlivých resources
		- př. GET `http://myapi.com/products/420/`
	- resource je objekt, dokument, nebo jakákoliv věc se kterou chceme na API pracovat
	- tento přístup zajišťuje bezstavovost
- **bezstavovost / statelessness**
	- REST API jsou bezstavové
	- klient nemusí vědět o stavu serveru či předchozích zpracovaných požadavcích, server nemusí vědět o klientovi
- **CRUD operace**
	- REST API umožňují CRUD operace na resources
		- Create
		- Read
		- Update
		- Delete
- **HTTP**
	-  REST API dostávají požadavky a zasílají odpovědi přes HTTP requesty
		- GET = získání resource podle ID či získání seznamu resources
		- POST = vytvoření nové resource
		- PUT = aktualizace existující resource
		- DELETE = odstranění existující resource
- **užití identifikátorů**
	- REST architektura neurčuje, jaké identifikátory pro resources použijeme
	- pro uživatele např. můžeme použít ID nebo string username, záleží na aktuálních potřebách
		- GET `http://myapi.com/users/3/`
		- GET `http://myapi.com/users/karel/`
	- můžeme mít i více endpointů pro přístupu k resources podle různých identifikátorů
- **správné pojmenování cest/endpointů**
	- z názvu endpointů musí být jasné, co endpoint dělá, i když API neznáme
	- cesta vždy obsahuje název resource, typ HTTP requestu určuje operaci, co děláme:
		- GET `http://myapi.com/products/420/` = vrátí data produktu ID 420
		- GET `http://myapi.com/products/` = vrátí seznam všech produktů
		- POST `http://myapi.com/products/` = vytvoří nový produkt
		- PUT `http://myapi.com/products/420/` = aktualizuje data produktu ID 420
		- DELETE `http://myapi.com/products/420/` = smaže produkt ID 420
	- v reálných API jsou cesty často komplikovanější, ale vždy musí být založeny na operaci na resources
- **HATEOAS**
	- = Hypermedia as the Engine of Application State
	- způsob, kterým může klient zasílat požadavky na operaci s resources bez toho, aniž by věděl přímé endpointy na operace
	- při zažádání o informace o resources vrátí server i seznam endpointů, které umožní klientovi dělat operace na dané resource
	- např. klient zažádá o informace o zaměstnanci přes GET `http://myapi.com/employees/69` a získá následující JSON odpověď:
	```
	{
		"id": 69,
		"salary" : 1000,
		"links": {
			"incrementSalary": "/employees/69/salary/increment",
			"decrementSalary": "/employees/69/salary/decrement",
			"resetSalary": "/employees/69/salary/reset"
		}
	}
	```
	- umožňuje, aby se architektura a uspořádní endpointů na serveru mohlo změnit bez toho, aniž by se musel změnit klient
- **JSON**
	- moderní API by měly pro komunikaci zásadně používat JSON požadavky a odpovědi
	- historicky se častěji používalo XML