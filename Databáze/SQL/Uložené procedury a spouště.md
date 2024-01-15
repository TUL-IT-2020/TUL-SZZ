#SQL
# Uložené procedury a spouště (od SQL3)
**Trigger** (= spoušť) je procedura, která je automaticky spuštěna jako reakce na specifikovanou akci v databázi; trigger se vykoná, pokud nějakou hodnotu ve sloupci budeme přidávat, nebo modifikovat a nebo mazat; u všech tří akcí můžeme specifikovat, zdali se trigger vyvolá před vlastním příkazem, nebo až po vlastním příkazu >> **before triggery** a **after triggery**; lze kombinovat akce, při kterých se má trigger spustit - trigger reagující na UPDATE nebo DELETE 

Použití: 
- validace vstupních dat 
- automatické generování a doplňování dat pro nové řádky

Šablona spouště:
```SQL
CREATE TRIGGER <jméno_triggru>
BEFORE | AFTER | INSTEAD OF událost ON <jméno_tabulky>
[REFERENCING <referenční proměnné> AS <jména>]
[FOR EACH ROW | FOR EACH STATEMENT]
WHEN (podmínka)
[AS]
akce
```

*Příklad triggeru - automaticky odstranit záznam pracovníka, jehož záznam v tabulce LIDÉ mažeme*
``` sql
CREATE TRIGGER aktualizuj_platy
ON lidé
FOR DELETE
AS 
	DELETE FROM platy
	WHERE platy.osoba_id = lidé.id 
```

**Uložená procedura**  je databázový objekt, který neobsahuje data, ale část programu, který se nad daty v databázi má vykonávat. Lze se k ní chovat stejně jako ke každému jinému objektu databáze (založit, upravovat a smazat) pomocí příkazů dotazovacího jazyka databáze. Uložené procedury jsou vykonávány přímo databázovým serverem. Je to vlastně jakýsi skript - přesněji řečeno dávka - která je uložena přímo v databázi. Procedury mohou obsahovat vstupní parametry, výstupní parametry a návratové hodnoty.

*Příklad uložené procedury - vytvoření procedury vracející string a její následné volání*
``` sql
CREATE PROCEDURE my_hello_world
AS
	SELECT 'Hello, World!';
GO

my_hello_world;
```