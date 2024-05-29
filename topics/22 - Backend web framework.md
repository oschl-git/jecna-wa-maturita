# 22 - Backend web framework

## O čem mluvit
- co je to BE
	- z čeho se skládá
	- co obnáší
	- kde se sním setkáme
- BWF
	- proč ho používat
	- jaké má výhody/nevýhody
	- typy

## Backend (BE)
- Backend, neboli serverová část webové aplikace, je zodpovědný za zpracování dat a logiku aplikace na straně serveru. Jeho úkolem je odpovídat na požadavky z frontendu a manipulovat s daty v databázi.
- Cool popis Frontendu a Backendu co jsem našel
	*Představme si restauraci kde nám předají menu na které si objednáme salád a sodovku. To by byl FE. Číšník který to pak odnese do kuchyně a kuchaři kteří do uvaří je pak BE.*
- Části BE:
	1. **Server:** Sofrware, který poskytuje služby a zpracovává požadavky klientů z frontendu
	2. **Databáze:** Slouží k ukládání dat potřebných pro chod aplikace
	3. **Kód:** Programovací jazyk a logika, která řídí, jak aplikace reaguje na požadavky a manipuluje s daty

## Backend web framework (BWF)
- BWF je sada nástrojů, knihoven a konvencí, které usnadňují vývoj backendové části webových aplikací. Tyto frameworky poskytují strukturu a funkcionality, které programátor může využít, aby rychleji a efektivněji vyvíjel aplikace.
- Výhody používání BWF:
	- **Rychlejší vývoj**: Frameworky obsahují hotové komponenty a abstrakce, což umožňuje programátorům psát méně kódu a rychleji vytvářet aplikace.
	- **Standardizace**: Frameworky často implementují osvědčené postupy a konvence, což usnadňuje spolupráci mezi vývojáři a udržuje kód čitelný a srozumitelný.
	- **Bezpečnost**: Mnoho frameworků obsahuje zabudované zabezpečení a ochranu proti běžným útokům, což snižuje riziko bezpečnostních chyb.
- Možné nevýhody používání BWF:
	- **Naučení se nového frameworku:** Syntaxe, koncepty programování, jiné myšlení a postup pří vývoji
		- Ruby on Rails: nadměrná konvence nad konfiguraci
	- **Omezení flexibility:** Některé frameworky můžou být vnímány více restriktivní něž jíné
		- Django: kvůli konvenci co má, tak můžou být problémi
	- **Závislost na daném frameworku:** Pokud je celá aplikace napsaná v jednom frameworku, který časem zestárné, může pak být až skoro nemožné bezproblémově přejít na jiný
		- ASP .NET: závislost na Microsoftu
	- **Výkon a škálovatelnost:** Optimalizace, výkon, škálovatelnost, prdel
		- Ruby on Rails: mívá problémy se většími projekty
		- Django: velice obsáhly a nehodí se tak na menší projekty
- Příklady BWF:
	- **Django**
		- Pythonu
		- Jednoduchý, bezpečný 
		- Poskytuje řadu funkcí jako je ORM pro manipulaci s databází, správy uživatelských účtů, automatické administrace,...
		- Michal ho má rád 
	- **Express.JS**
		- Node.JS
		- Minimalistická a flexibilní
		- Modulární 
		- Oblíbený pro vývoj API, aplikací, web aplikací,...
	- **Ruby on Rails**
		- Ruby 
		- Robustní, konvence nad konfigurací
		- Big Boi
