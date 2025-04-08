Kazdy projekt ma prideleneho jedneho veduceho. Projekt je rozdeleny na ulohy, pri evidencii dochadzky je kazdemu
zamestnancovi pridelena uloha (napriklad osadzanie okien na holostavbe).
Tymto sposobom presne vieme kto co robil. Na jednej ulohe moze pracovat viacero zamestnancov.

Na zaklade odpracovaneho casu v dochadzke (attendance_end_time - attendance_start_time) a hodinovej sadzby
z udajov zamestnanca vieme vypocitat naklady na pracu robotnikov.

V databaze evidujeme sklady. Kazdy sklad ma prave jedneho veduceho. V skladoch su umiestnene vozidla a naradie.
Kazdy sklad ma svoje skladove zasoby jednotlivych druhov materialov. Prepravu materialu evidujeme v samostatnej tabulke.

Pri preprave materialu zaznamename kazdu prepravovanu polozku a jej mnozstvo. Jednou prepravou je tak mozne
transportovat viacero druhov materialov.
Cenu prepravy vypocitame: mnozstvo prepravovaneho materialu * jednotkova cena materialu + cena cesty.

Evidujeme vypozicky vozidiel, ktore su vzdy viazane na vozidlo, zamestnanca a projekt. Zaznamy o vypozicke a vrateni
vozidla uchovavame v dvoch samostatnych tabulkach. Pokial existuje zaznam v tabulke vypoziciek a neexistuje zodpovedajuci
zaznam v tabulke vrateni, vozidlo je aktualne vypozicane.
Cenu vypozicky vypocitame: (end_kilometers - start_kilometers) * (fuel_cost_per_km + depreciation_cost_per_km).
Pri kazdom zazname o vrateni vozidla sledujeme jeho stav, aby bolo mozne v pripade nehody urcit zodpovedneho pracovnik.

Podobnym sposobom evidujeme vypozicky naradia. Pri entitach vozidlo a naradie mame dynamicky atribut status,
vdaka ktoremu vieme rychlo zistit, v akom stave sa dane zariadenie nachadza.
