# 16 - PHP (Hypertext Preprocesor PHP) - základní konstrukce jazyka
- **PHP** je programovací jazyk, který se používá především pro dynamické generování webových stránek a webových aplikací
- zkratka je *rekurzivním akronymem* který znamená "Hypertext Preprocessor PHP", původně znamenal "personal homepage", pak byl význam kvůli nevhodnosti změněn
- je specifický tím, že se používá jako webový backend, a ne na nic moc jiného 
- PHP kód se spouští na serveru a generuje HTML, které se pak odesílá do prohlížeče klienta
- je open-source
- je platformově nezávislý, funguje na všech operačních systémech
- asi 76% webů běží na PHP
## Historie
- PHP (Hypertext Preprocessor) byl vytvořen v roce 1994 Rasmusem Lerdorfem jako nástroj pro sledování návštěvnosti jeho osobních webových stránek
- původně se jednalo o jednoduchý nástroj nazvaný "Personal Home Page Tools" (PHP Tools)
- první veřejná verze PHP, PHP/FI (Personal Home Page/Forms Interpreter), byla vydána v roce 1995
- PHP/FI umožňovala tvorbu dynamických webových stránek, ale byla omezená a nedokázala řešit složitější úkoly
- v roce 1997 se PHP přesunulo do rukou vývojářské komunity a vznikla nová verze PHP 3, která již byla robustnější a plně vybavená
- PHP 4, vydáno v roce 2000, přineslo mnoho nových funkcí a vylepšení, včetně podpory pro objektově orientované programování
- PHP 5, které vyšlo v roce 2004, přidalo další výkonné funkce jako například rozšířenou podporu pro objekty, refaktorizaci kódu a nový systém správy paměti
- PHP 6 mělo být významnou aktualizací s podporou pro Unicode, avšak bylo nakonec zrušeno kvůli technickým obtížím
- PHP 7, vydáno v roce 2015, přineslo výrazné zrychlení díky optimalizacím kódu a nové funkce jako například typovou deklaraci pro parametry a návratové hodnoty funkcí
- PHP 8, vydáno v roce 2020, přineslo další výkonnostní optimalizace, nové funkce a vylepšení, včetně JIT kompilátoru pro ještě rychlejší provádění kódu
## Syntaxe
- C-like syntaxe, používá středníky a curly závorky
- proměnné se nedeklarují, označují se $ (např. `$waluigi = 69420`)
- začátek PHP kódu se označuje `<?php` a konec `?>`, v .php souborech se dá kombinovat s HTML
	- je to ale trochu prasárna, místo toho se používají templatovací jazyky frameworků, jako např. Twig, Latte, Blade
- komentáře se píšou klasicky `//` nebo `/*` a `*/`
- PHP je dynamicky typované, v některých případech ale lze (a je dobrý nápad) typ proměnných specifikovat
	- je možné určit typ, co vrací funkce:
	```php
	function add(int $a, int $b): int {
	    return $a + $b;
	}
	```
	- je možné specifikovat typ class properties a konstant:
	```php
	class User
	{
	    public int $id;
	    const string OBLIBENE_JIDLO = 'hamnburger';
	    // může být konstanta protože to je oblíbené jídlo všech uživatelů
	}
	```
	- atd.
## PHP OOP
- PHP obsahuje klasické OOP možnosti, velmi podobné C# nebo Javě
- zajímavě se mohou psát konstruktory (dají se i klasicky, ale tímto způsobem není nutné deklarovat proměnnou mimo konstruktor):
```
public function __construct(
	public int $id,
	private ?string $name,
)
{
}
```
