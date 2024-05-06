---
toc: "true"
---
# Definice pojmů
---
- Soubor rejstříku
	- Textový soubor, který obsahuje výčet kapitol a na kterých stránkách kapitoly začínají. Definován jeden v rámci jedné poddatabáze. Nelze předefinovat v aplikaci, pouze externě přepsáním JSON souboru.
- Vyhledávání
	- Proces porovnávání dvou textových řetězců a zobrazování v případě shody.
# Načítání dat
---
## Struktura dat 
![[JSONimg.png]]
POZOR: Informace za pomlčkami jsou pouze informativní a nesmí být součástí JSON souboru.

## Načtení dat

Pro načtení dat je nutné mít JSON soubor, který má správnou strukturu. 
### Načtení dat při startu aplikace
V případě, že má soubor správnou strukturu, budou ve výpisovém okně informace o databázi. V případě, že má soubor špatnou strukturu, bude ve výpisovém okně "Database Error".
![[PDO_im1.png]]
![[PDO_im2.png]]
Pokud je v okně "Database Error", budete muset vytvořit nový JSON soubor tak, aby vyhovoval [[##Struktura dat|Struktuře dat]].
### Načtení dat při běhu aplikace
Pro načtení dat můžete využít tlačítka Import dat nebo klávesovou zkratku definovanou v  [[#Nastavení]] aplikace. Obvykle se jedná o Ctrl + D.
![[PDO_load_db.png]]
POZOR: V případě, že má soubor špatnou strukturu, nenačte se.
# Prohlížení
---
## Prohlížení záznamů
Pro přesun mezi záznamy můžete využít tlačítek Předchozí záznam a Následující záznam nebo klávesových zkratek definovaných v [[#Nastavení]] aplikace. Obvykle se jedná o Ctrl + Levá šipka a Ctrl + Pravá šipka.
## Prohlížení rejstříkem
Pro přesun mezi záznamy můžete využít rejstříku, který je generován na základě [[#Struktura dat|Načítaných dat]]. Zde se po vybrání databáze zobrazí výčet kapitol. 
![[PDO_Rejstrik.png]]
Okno s rejstříkem můžete otevřít stisknutím tlačítka Rejstřík v hlavním okně, nebo klávesovou zkratkou definovanou v [[#Nastavení]] aplikace. Obvykle se jedná o Ctrl + N.
![[PDO_rejst_main.png]]
# Editace
---
## Editace textu
Pro editaci textu přepište text v hlavním okně a pomocí klávesové zkratky definované v [[#Nastavení]] aplikace změnu uložte. Obvykle se jedná o Ctrl + S.

Pro vrácení textu do stavu před editací, stiskněte klávesovou zkratku definovanou v [[#Nastavení]] aplikace. Obvykle se jedná o Ctrl + Z.

Pro vrácení textu do stavu po editací, stiskněte klávesovou zkratku definovanou v [[#Nastavení]] aplikace. Obvykle se jedná o Ctrl + Y.

Změny se projevují jak v textu, tak v ukazateli změn v levém dolním rohu hlavního okna.
![[PDO_edit_main.png]]
UPOZORNĚNÍ: Maximální počet změn jsou čtyři. Následně se začnou přepisovat staré změny.
## Editace Obrazu
Aplikace neumožňuje přímou úpravu obrazu, ale můžete načíst nová obrazová data. Buď stiskem tlačítka Načíst obrázek, nebo pomocí klávesové zkratky definované v [[#Nastavení]] aplikace. Obvykle se jedná o Ctrl + I.
![[PDO_load_im.png]]
# Vyhledávání
---
## Vyhledávání v aktuálním záznamu
Pro započetí vyhledávání můžete využít tlačítka Vyhledávání, nebo klávesové zkratky definované v [[#Nastavení|nastavení]]. Obvykle se jedná o Ctrl + R. V tomto okně si vyberte Aktuální záznam, do textového pole vepište text, který chcete hledat a stiskněte tlačítko Hledat.
![[PDO_search2.png]]

V hlavním okně se zobrazí hledaný text.
![[PDO_search3.png]]
## Vyhledávání ve všech záznamech
Pro započetí vyhledávání můžete využít tlačítka Vyhledávání, nebo klávesové zkratky definované v [[#Nastavení|nastavení]]. Obvykle se jedná o Ctrl + R. V tomto okně si vyberte Všechny záznamy, do textového pole vepište text, který chcete hledat a stiskněte tlačítko Hledat.
![[PDO_search2.png]]


Tento typ vyhledávání otevře okno se všemi záznamy obsahující text. V tomto okně si můžete vybrat jaký záznam si chcete nechat zobrazit pomocí tlačítka Zobraz v textu. V hlavním okně aplikace se zobrazí vybraný záznam s nalezeným hledaným textem. Tento typ vyhledávání kontroluje všechny záznamy
![[PDO_search4.png]]
## Vyhledávání v rejstřících
Pro započetí vyhledávání můžete využít tlačítka Vyhledávání, nebo klávesové zkratky definované v [[#Nastavení|nastavení]]. Obvykle se jedná o Ctrl + R. V tomto okně si vyberte Všechny záznamy, do textového pole vepište text, který chcete hledat a stiskněte tlačítko Hledat.
![[PDO_search2.png]]


Tento typ vyhledávání otevře okno se všemi záznamy obsahující text. V tomto okně si můžete vybrat jaký záznam si chcete nechat zobrazit pomocí tlačítka Zobraz v textu. V hlavním okně aplikace se zobrazí vybraný záznam s nalezeným hledaným textem. Tento typ vyhledávání kontroluje pouze soubory definované v [[#Struktura dat|JSON souboru]] jako Lookup_File.
![[PDO_search5.png]]
# Nastavení
---
## Klávesové zkratky
V nastavení můžete nastavit preferované klávesové zkratky. Lze nastavit, jaké klávesy je nutné držet aby se opravdu jednalo o klávesovou zkratku. K tomu slouží pole Akční tlačítka. Ostatními poli nastavujete jakou další klávesu musíte stisknout pro chtěný efekt. Tlačítkem uložit nastavení se nastavení uloží.
POZOR: Konfliktní klávesové zkratky vedou k neuložení nastavení.
![[PDO_sett 1.png]]

Příklad konfliktního nastavení:
![[PDO_sett_inv.png]]
# Propojení s Elasticsearch databází
---
Pro propojení s Elasticsearch databází je potřeba pracovat s daty, která mají vyplněný ES_index, odkaz a přihlašovací údaje na ElasticSearch databázi a data načtena do této databáze.

Propojit se lze při [[#Načtení dat při startu aplikace|načtení dat při startu aplikace]] nebo za běhu aplikace v [[#Nastavení|nastavení]]. Do pole URI vyplníte adresu ElasticDB se kterou chcete pracovat. Do pole Uživatel uživatelské jméno a do pole Heslo heslo uživatele pro práci s danou ElasticDB.

V případě při startu aplikace, stačí stisknout tlačítko Importovat data. V případě při běhu aplikace, musíte stisknout tlačítko Připojit se.
![[PDO_im_is.png]]![[PDO_sett_es.png]]

POZOR: Pro správnou funkci je nutné mít data v ElasticDB uložena s tímto mapováním:![[PDO_ES.png]]

