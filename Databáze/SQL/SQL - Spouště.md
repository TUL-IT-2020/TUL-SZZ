#SQL
# Spouště (od SQL3)
Ukládají se v databázi mezi ostatními scripty.

Trigger (= spoušť) je procedura, která je automaticky spuštěna jako reakce na specifikovanou akci v databázi. Trigger se vykoná, pokud nějakou hodnotu ve sloupci budeme přidávat, nebo modifikovat a nebo mazat. U všech tří akcí můžeme specifikovat, zdali se trigger vyvolá před vlastním příkazem, nebo až po vlastním příkazu >> **before triggery** a **after triggery**; lze kombinovat akce, při kterých se má trigger spustit - trigger reagující na `INSERT`, `UPDATE` nebo `DELETE`.

> [!info] Reagují na událost:
>- `INSERT`
>- `UPDATE`
>- `DELETE`

Není verze triggeru pro `SELECT`!

> [!example] Typy:
> - `BEFORE` - před vložením dat do databáze,
> - `AFTER/FOR` - po vlastním příkazu,
> - `INSTEAD_OF` - místo vykonání dotazu.

> [!tip] Použití: 
>- validace vstupních dat 
>- automatické generování a doplňování dat pro nové řádky

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

Příklad triggeru - automaticky odstranit záznam pracovníka, jehož záznam v tabulce LIDÉ mažeme:
``` sql
CREATE TRIGGER aktualizuj_platy
ON lidé
FOR DELETE
AS 
	DELETE FROM platy
	WHERE platy.osoba_id = lidé.id 
```