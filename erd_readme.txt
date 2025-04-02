Projekt je rozdeleny do uloh, pri evidencii je kazdemu zamestnancovi pridelena uloha.
Na jednej ulohe moze pracovat viacero zamestnancov.
Ci su uloha alebo projekt hotove pozorujeme na zaklade pritomnosti, resp. nepritomnosti
hodnoty NULL v atribute datum_do.
Na zaklade odpracovaneho casu v dochadzke a hodinovej sadzby v udajoch zamestnanca evidujeme
v kazdom zazname dochadzky, kolko penazi sa minulo na robotnikov (sazba_za_zmenu).

Evidujeme si vypozicky vozidiel, ktore su vzdy viazane k vozidlu, zamestnancovi a projektu.
Pokial pozicanym vozidlom prepravujeme material, zaznam evidujeme aj v Preprave materialu,
kde pomocou odobraneho mnozstva a jednotkovej ceny materialu dokazeme zistit celkovu cenu
prepravovaneho materialu.

Kazdy sklad ma prave jedneho veduceho skladu. V skladoch su umiestnene vozidla, naradie a skladove polozky.
Kazda skladova polozka je v sklade umiestnena v urcitom mnozstve. Jej jednotkovu cenu zistime v tabulke Material.

Vypozicky naradia evidujeme v samostatnej tabulke. Pri kazdej vypozicke kontorlujeme stav pred a po pouziti.
Pri poruche najdeme pachatela lahko pomocou triedenia podla najnovsich vypoziciek.

To, ci je konkretne naradie alebo vozidlo k dispozicii dokazeme vidiet v ich statuse, ktory sa dynamicky
meni na zaklade sledovania datum_do podobne ako pri ulohe a projekte.
Ak existuje vypozicka s datum_do = NULL  => naradie / vozidlo je na projekte
Inak					 => naradie / vozidlo je v domovskom sklade

Zoznam aktualne pouzivanych zariadeni na konkretom projekte najdeme hladanim vsetkych neukoncenych vypoziciek
spojenych s danym projektom.

Vypozicky vozidiel funguju podobne ako vypozicky naradia. cena_vypozicky sa vypocita ako 
palivo_cena_za_km * (konecne_kilometre - zaciatocne kilometre) + 
amortizaccia_cena_za_km * (konecne_kilometre - zaciatocne kilometre)

Zaznam kazdej vypozicky zvysi hodnotu nakladov pri konkretom projekte pridanim ceny_vypozicky.