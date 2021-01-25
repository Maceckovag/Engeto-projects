# Engeto-projects
## SQL PROJECT

### 1. Časové proměnné
* binární proměnná pro víkend / pracovní den
	dayofweek -> case
* roční období daného dne (zakódujte prosím jako 0 až 3)
	quarter -> case

### 2. Proměnné specifické pro daný stát
- hustota zalidnění - ve státech s vyšší hustotou zalidnění se nákaza může šířit rychleji
	join s tabulkou countries - levý -> vše z tab. differences a k tomu spojí údaje z tab. countries, pokud by statistik chtěl ve výsledku pouze country, které mají všechny chtěné hodnoty, může to omezit přímo přes join (left, right, inner atd.) 
- HDP na obyvatele - použijeme jako indikátor ekonomické vyspělosti státu
	join s tabulkou economies přes country a volíme hodnoty z roku 2020 
	pro rok 2020 chybí hodnoty HDP v tabulce economies, v době kontroly tohoto projektu (2021) už data možná budou
- GINI koeficient - má majetková nerovnost vliv na šíření koronaviru?
	join s tabulkou economies přes country a volíme hodnoty z roku 2020
	pro rok 2020 chybí hodnoty gini v tabulce economies, v době kontroly tohoto projektu (2021) už data možná budou
- dětská úmrtnost - použijeme jako indikátor kvality zdravotnictví
	join s tabulkou economies přes country a volíme hodnoty z roku 2020
	pro rok 2020 chybí hodnoty mortality_under5 v tabulce economies, v době kontroly tohoto projektu (2021) už data možná budou
- medián věku obyvatel v roce 2018 - státy se starším obyvatelstvem mohou být postiženy více
	z tabulky countries - získáme díky joinu
- podíly jednotlivých náboženství - použijeme jako proxy proměnnou pro kulturní specifika. Pro každé náboženství v daném státě bych chtěl procentní podíl jeho příslušníků na celkovém obyvatelstvu
	zde jsou dvě možnosti - náboženství máme v tabulce religion - všechna náboženství v dané zemi a také v tabulce countries, kde je to hlavní náboženství - nejspíš je to dle zadání myšleno pro všechna náboženství a ne jen pro to hlavní
	v zemích bývá více náboženství, tudíž vznikne z jednoho řádku pro zemi a datum hned několik (tolik, kolik je náboženství) řádků pro danou zemi a daný den
	další zádrhel vidím v tom, že údaj o celkové populaci státu najdeme ve 3 různých tabulkách a v každé je údaj malinko jiný - já jsem zvolila údaj z tabulky lookup table
	data nejspíš nejsou v pořádku - část populace patřící k danému náboženství může být i vyšší než celková populace - tudíž procentní podíl je vyšší než 100% např. Afganistan a Islam
- rozdíl mezi očekávanou dobou dožití v roce 1965 a v roce 2015 - státy, ve kterých proběhl rychlý rozvoj mohou reagovat jinak než země, které jsou vyspělé už delší dobu
	join dvakrát stejné tabulky, jen s různými roky

### 3. Počasí (ovlivňuje chování lidí a také schopnost šíření viru)
- průměrná denní (nikoli noční!) teplota
	denní považuji od 6 do 18
- počet hodin v daném dni, kdy byly srážky nenulové
	beru již celý den, ne od 6 do 18, nevím, zda jsem správně pochopila zadání
- maximální síla větru v nárazech během dne
	beru již celý den, ne od 6 do 18, nevím, zda jsem správně pochopila zadání
	

## PYTHON PROJECT
