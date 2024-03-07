# 4 - Asynchroní a synchroní komunikace na webu
- Asynchroní a synchroní komunikace na webu jsou dva způsoby, jakými mohou webové aplikace vyměňovat data s webovými servery.
- Z pohledu vývojáře webu je obecně doporučováno používat asynchronní komunikaci pro výkon a uživatelskou zkušenost. 
- Asynchronní komunikace také umožňuje využít výhod moderních webových technologií, jako jsou Promise, async/await, Service Worker a Web Worker Nicméně, v některých případech může být synchronní komunikace vhodnější nebo nevyhnutelná, například při načítání závislostí nebo při práci s omezenými prostředky.
## Synchronní komunikace: 
- ve setjném čase (i místě), okamžitá, telefonování, chat, videocall
- webová aplikace musí čekat, než se dokončí požadavek na server než může pokračovat v 
- může způsobit zablokování nebo zamrznutí uživatelského rozhraní, pokud je požadavek pomalý nebo selže
- příkladem synchronní komunikace je XMLHttpRequest s parametrem `false`
## Asynchronní komunikace: 
- na komunikaci nemusíme odpovídat hned (na stejném místě), reakce na příspěvky není okamžitá, email, forum
- znamená, že webová aplikace může pokračovat v dalších akcích, zatímco požadavek na server probíhá na pozadí
- když je požadavek dokončen, webová aplikace je informována pomocí zpětného volání nebo události
- umožňuje uživatelskému rozhraní být responzivní a interaktivní
- příkladem asynchronní komunikace je XMLHttpRequest s parametrem `true` nebo Fetch API


