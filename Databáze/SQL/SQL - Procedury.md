#SQL
# Uložené procedury
Uložená procedura je databázový objekt, který neobsahuje data, ale část programu, který se nad daty v databázi má vykonávat. Lze se k ní chovat stejně jako ke každému jinému objektu databáze (založit, upravovat a smazat) pomocí příkazů dotazovacího jazyka databáze. Uložené procedury jsou vykonávány přímo databázovým serverem. Je to vlastně jakýsi skript - přesněji řečeno dávka - která je uložena přímo v databázi. Procedury mohou obsahovat vstupní parametry, výstupní parametry a návratové hodnoty.

Příklad uložené procedury - vytvoření procedury vracející string a její následné volání
``` sql
CREATE PROCEDURE my_hello_world
AS
	SELECT 'Hello, World!';
GO

EXECUTE my_hello_world;
```

Procedury umožňují mít parametry:
``` sql
CREATE PROCEDURE uv_SoucastkyNad
@cena money
AS
	SELECT * FROM Soucastky WHERE cena > @cena;
GO

EXECUTE uv_SoucastkyNad 20;
```
