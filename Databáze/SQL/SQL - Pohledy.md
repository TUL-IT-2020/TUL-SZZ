#SQL 
# Pohledy
**Pohledy** (views) = virtuální tabulky. Slouží především pro dotazování. Umožňují značné zjednodušení zápisu dotazů (obdobně jako rozčlenění programu do procedur).

Lze je použít v selectech. 
## Příklady:

``` sql
CREATE VIEW Prazaci
AS 
	SELECT k_zamestnance, jmeno_z FROM Zamestnanci
	WHERE Adresa LIKE ‘%Praha%’;

SELECT k_zamestnance FROM Prazaci 
WHERE Plat > 10000;

DROP VIEW Prazaci;
```

``` sql
CREATE VIEW uv_SoucastkyNad20
AS
	SELECT * FROM Soucastky WHERE cena > 20;
GO

EXECUTE uv_SoucastkyNad20;
```
