# 20 - CSS framework
## O čem mluvit?
- k čemu to je?
- co to umí?
- využití
- příklady frameworků (Bootstrap, Foundation, ...)

## Frameworky
- = sada předpřipravených CSS stylů a komponentů
	- často tlačítka, formuláře, navigaci, tabulky, text, atd.
- způsob urychlení a ulehčení práce se styly pro webovky
- šetří to čas při front-end vývoji
- píšu přímo do html
	- přidávám elementům classy podle toho jak chci aby vypadali
	- stačí jen importnout linkem daný framework

#### Vlastnosti
- **Konzistence**
	- napříč celou stránkou je konzistentní design
	- uživatel ví že je furt na té samé stránce od stejných lidí
	- user-friendlines - uživatel ví co kde a jak je

- **Responsivita**
	- jsou designované tak aby byly responsivní
	- tím že mají dokumentaci tak je spíše jednoduší pomocí nich psát responsivní design než při pure CSS

- **Minimální kód**
	- psaní frameworky se zbavuju gigantických nepřehledných CSS souborů

- **Learning curve**
	- než se front-ender s nimi naučí může to být pain
	- jakmile s nimi ale umí je to lehčí než obyčejné CSS

- **Velikost souboru = performance hit**
	- když nainstaluju framework tak je v něm více funkcí než můžu potřebovat
	- = sníží rychlost stránky

- **Omezená customizace**
	- většina frameworků umožňuje lehkou úpravu vzhledu a barev 
	- v základu ale design bude stejný, nemůžu s tím nijak manipulovat
	- nemám nad tím plnou kontrolu


#### Frameworky
- **Bootstrap** 
	- asi nejrozšířenější
   	- starý
	- s bohatou sadou komponent a dobrou dokumentací
- **Tailwind CSS** 
	- nový, industry-standart
	- zaměřený na vytváření vlastního designu pomocí utility tříd
- **Foundation** 
	- populární framework s důrazem na responzivitu a flexibilitu
- **Bulma** 
	- jednoduchý a lehký framework s modulárním přístupem

#### Příklad Bootstrapu
[Výsledek zde](https://www.w3schools.com/bootstrap/tryit.asp?filename=trybs_default&stacked=h)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Bootstrap Example</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.7.1/jquery.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
</head>
<body>

<div class="jumbotron text-center">
  <h1>My First Bootstrap Page</h1>
  <p>Resize this responsive page to see the effect!</p> 
</div>
  
<div class="container">
  <div class="row">
    <div class="col-sm-4">
      <h3>Column 1</h3>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit...</p>
      <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris...</p>
    </div>
    <div class="col-sm-4">
      <h3>Column 2</h3>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit...</p>
      <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris...</p>
    </div>
    <div class="col-sm-4">
      <h3>Column 3</h3>        
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit...</p>
      <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris...</p>
    </div>
  </div>
</div>

</body>
</html>
```
