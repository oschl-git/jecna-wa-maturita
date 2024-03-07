# 6 - Optimalizace webu - caching , CDN, SEO, loading optimization
#### Caching
- klíčový prvek optimalizace webu
- výrazně zvyšuje rychlost načítání stránek
- ukládání často používaných dat nebo obsahu do mezipaměti (u klienta nebo serveru)
	- opětovní návštěvníci stránky získají obsah rychleji
- **Dvě formy chachingu:**
	- **Server-side caching**: ukládání dat přímo na serveru a jejich opětovné poskytování bez nutnosti opakovaného generování obsahu
	- **Client-side caching**: ukládání dat v prohlížeči návštěvníka, což snižuje počet dotazů na server a zrychluje načítání stránek
#### CDN (Content Delivery Network)
- CDN je distribuovaná síť serverů umístěných po celém světě
- slouží k distribuci obsahu na webu
- využitím CDN jsou statické soubory, jako jsou obrázky, styly a skripty, uloženy na servery blízko koncových uživatelů
- výrazně zvyšuje rychlost načítání stránek
	- obsah je stahován z nejbližšího dostupného serveru uživateli
#### SEO (Search Engine Optimization)
- proces optimalizace webových stránek s cílem zlepšit jejich viditelnost a pozici ve výsledcích vyhledávání
- správná SEO optimalizace zahrnuje:
	- **Klíčová slova**: využití relevantních klíčových slov ve struktuře stránky a obsahu pro zlepšení pozice ve výsledcích vyhledávání
	- **Obsah:** optimalizovaný obsahu, struktury stránek a technické parametry webu
	- **Odkazy**: budování kvalitních zpětných odkazů (backlinků) od důvěryhodných webů
- to vše vede k vyšší návětěvnosti webu
#### Optimalizace načítání
- slouží ke zkrácení času načítání stránky
- optimalizace webu je nekončící proces
- **Kroky optimalizace:**
	- **Snížení velikosti webových souborů:** snížení velikosti CSS, JavaScript a HTML souborů a jejich sjednocení pro snížení počtu HTTP dotazů
	- **Obsah:** používání optimalizovaných obrázků, formátů jako WebP a lazy loading pro zpožděné načítání obrázků a jiného obsahu mimo obrazovku
	- **Asynchronní načítání skriptů**: umožňuje načítání skriptů asynchronně, což zabraňuje blokování načítání stránky
