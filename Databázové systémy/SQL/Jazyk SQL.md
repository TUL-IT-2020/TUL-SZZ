# Jazyk SQL

> Jazyk SQL (DDL, DML, množinové operace), uložené procedury a spouště v SQL, transakce (ACID, typy konfliktů, stupně izolace).

## Jazyk SQL
**SQL** = Structured Query Language; standardizovaný strukturovaný dotazovací jazyk, který je používán pro práci s daty v relačních databázích; založen na relačním kalkulu a [relační algebře](https://cs.wikipedia.org/wiki/Rela%C4%8Dn%C3%AD_algebra)

SQL příkazy se dělí na čtyři základní skupiny:
- **DML** (data manipulation language) - příkazy pro manipulaci s daty (SELECT, INSERT, UPDATE, DELETE, ...),
- **DDL** (data definition language) - příkazy pro definici dat (CREATE, ALTER, DROP, ...),
- **DCL** (data control language) - příkazy pro řízení přístupových práv (GRANT, REVOKE),
- příkazy pro řízení transakcí (START TRANSACTION, COMMIT, ROLLBACK).

### Množinové oparace
![[SQL - Množinové operace]]

### Typy dat v SQL (SQL92)
**Numerické typy** - INTEGER, SMALLINT, NUMERIC, DECIMAL, FLOAT, REAL, DOUBLE  PRECISION

**Znakové řetězce** - CHARACTER (CHAR), CHARACTER VARYING (VARCHAR)

**Temporální data** - DATE (rrrr-mm-dd)

**Integritní omezení** - NOT NULL, DEFAULT, UNIQUE, PRIMARY KEY, FOREIGN KEY, CHECK

### DML / [SELECT](https://cs.wikipedia.org/wiki/SELECT)
Základním konstruktem pro výběr dat je **SELECT**-**FROM**-**WHERE** blok. Klauzule **SELECT** obsahuje seznam sloupců vytvářejících schéma tabulky. Klauzule **FROM** obsahuje seznam tabulek, nad kterými je dotaz definován a klauzule **WHERE** obsahuje podmínku, kterou musí splňovat vyhledávaná data. **Select** neeliminuje z výsledku duplicitní hodnoty (k tomu slouží další operátory).

#### Základní pojmy a klíčová slova

![[Agregační funkce]]

**Predikáty**: IN, ANY, ALL, SOME, EXISTS

**Poddotaz**: můžeme užít i s porovnávacími operátory, máme-li zaručeno, že výsledkem poddotazu je právě jedna hodnota

**GROUP BY**: tabulka se konceptuálně rozdělí na skupiny, pro které je hodnota zvoleného sloupce konstantní; řádky obsahující v tomto sloupci hodnotu NULL se seskupí do jedné skupiny; získáváme tzv. seskupenou tabulku; každá skupina přispívá do výsledné tabulky **jedním** řádkem; je syntaktická konstrukce jazyka SQL pro agregaci záznamů vybíraných pomocí příkazu SELECT

**HAVING**: je velmi podobná podmínce WHERE; rozdíl je v tom, že podmínka WHERE omezuje ještě neseskupené záznamy a podmínka HAVING omezuje seskupené záznamy

**LIKE**: podmínka za klíčovým slovem WHERE a slouží k vyhledání záznamů obsahujících určité výrazy; procento nahrazuje libovolný počet znaků; podtržítko zastupuje jeden libovolný znak

**EXISTS**: je test na neprázdnost množiny

**DISTINCT**: z výpisu odstraní záznamy, které se v dané hodnotě pole opakují

**UNION, INTERSECT, EXCEPT**: množinové operace; tabulky musejí být kompatibilní (stejný počet sloupců, stejný typy dat odpovídajících si sloupců). Slučujeme řádky.

![[SQL_commands.jpeg]]

#### Spojení tabulek
![[SQL - Spojení tabulek]]

#### Příklady

*Názvy kin*
``` sql
SELECT nazev_k
FROM Kina;
```
*Názvy kin bez duplicity*
``` sql
SELECT DISTINCT nazev_k
FROM Kina;
```
*Dvojice jaké filmy, které kino promítá?*
``` sql
SELECT DISTINCT k_filmu, k_kina 
FROM Program
ORDER BY k_filmu ASC;
```
*Všechny informace o promítáních po 5.4.2002*
``` sql
SELECT *
FROM Program
WHERE datum_prom > '5.4.2002';
```
*Všechny informace o promítáních od 1.4.2002 do 5.4.2002*
``` sql
SELECT *
FROM Program
WHERE datum BETWEEN ‘1.4.2002’ AND ‘5.4.2002’;
```
*Názvy filmů, které jsou promítány*
``` sql
SELECT DISTINCT nazev_f 
FROM Filmy, Program
WHERE Filmy.k_filmu = Program.k_filmu;
```
*Dvojice filmů se stejným režisérem?*
``` sql
SELECT X.k_filmu AS První, Y.k_filmu AS Druhý
FROM Filmy X, Filmy Y
WHERE X.reziser = Y.reziser AND X.k_filmu <> Y.k_filmu;
```
*Jaké budou ceny promítání při navýšení o 20%?*
``` sql
SELECT k_kina, k_filmu, cena*1.2 
FROM Promítání;
```
*Pro kino Blaník kódy filmů, které promítá a cenu promítání v eurech.*
``` sql
SELECT k_filmu, cena/31.2 
FROM Promítání X, Kina Y
WHERE X.k_kina = Y.k_kina AND X.nazev_k = ‘Blaník’;
```
*Počet kin*
``` sql
SELECT COUNT (*) AS počet_kin
FROM Kina;
```
*Kolik je promítáno filmů?*
``` sql
SELECT COUNT (DISTINCT k_filmu) AS počet_promítaných_filmů
FROM Promítání;
```
*Počet kin s kapacitou větší než 200*
``` sql
SELECT COUNT (*) AS počet_kin_s_kapacitou
FROM Kina
WHERE kapacita > 200;
```
*Jaká je průměrná cena za vstupenku na film Apollo 13?*
``` sql
SELECT AVG(Cena) AS průměrná_cena
FROM Promítání X, Filmy Y
WHERE X.k_filmu = Y.k_filmu AND Y.nazev_f = ‘Apollo 13’;
```
*Kolik filmů natočili jednotliví režiséři?*
``` sql
SELECT reziser, COUNT(k_filmu)
FROM Filmy
GROUP BY reziser;
```
*Kteří režiséři natočili alespoň tři filmy?*
``` sql
SELECT reziser
FROM Filmy
GROUP BY reziser 
HAVING COUNT(k_filmu) > 2;
```
*Jaká je průměrná cena vstupenek u jednotlivých filmů?*
``` sql
SELECT X.k_filmu, nazev_f, AVG(Cena)
FROM Filmy X, Promítání Y
WHERE X.k_filmu = Y.k_filmu
GROUP BY k_filmu;
```
*Hodnoty sloupce nazev_f  libovolné délky začínající na PS*
``` sql
nazev_f  LIKE ‘PS%’ 
```
*Adresy kin obsahující slovo Praha*
``` sql
adresa  LIKE ‘%Praha%’
```
*Adresy kin, ve kterých dávají film s kódem 6524*
``` sql
SELECT Adresa FROM Kina
WHERE k_kina IN (SELECT  k_kina  FROM Promítání WHERE k_filmu = ‘6524’);
```
*Adresy kin, ve kterých dávají film Gladiátor natočený roku 2000*
``` sql
SELECT Adresa FROM Kina
WHERE k_kina IN 
	(SELECT k_kina FROM Promítání P	WHERE P.k_filmu = 
		(SELECT F.k_filmu FROM Filmy F WHERE F.nazev_f = „Gladiátor“ AND rok_v = 2000));
```
*Jména filmů, kteří se v některém kině promítají.*
``` sql
SELECT nazev_f FROM Filmy F
WHERE EXISTS (SELECT * FROM Promítání
	WHERE k_filmu = F.k_filmu);
```
*Filmy, které natočil režisér Hřebejk nebo jsou promítány 2.4.2002*
``` sql
(SELECT k_filmu FROM Filmy 
WHERE reziser = ‘Hřebejk’)
UNION
(SELECT k_filmu FROM Promítání
WHERE datum = ‘2.4.2002’);
```

### DML / [[CRUD]] bez R
*Příklad na vložení záznamu*
``` sql
INSERT INTO example (field1, field2, field3) VALUES ('test', 'N', NULL);
```
*Příklad na aktualizaci záznamu*
``` sql
UPDATE example SET field1 = 'updated value' WHERE field2 = 'N';
```
*Příklad na smazání záznamu*
``` sql
DELETE FROM example WHERE field2 = 'N';
```
### DDL
Definování databázového schéma – datové typy, struktury. Vytváření, odstraňování, modifikace definic relací a pohledů (virtuální relace), definování integritních omezení.

[[RMD - Relační model dat#Integrita databáze a integritní omezení|Integritní omezení]]:
- NOT NULL – žádná hodnota v daném sloupci nesmí být NULL vždy musí být vyplněna datami. implicitně je nastavení NULL (není to však ani 0 ani mezera). 
- UNIQUE – všechny hodnoty v sloupci musí být unikátní, je přípustná jedna hodnota NULL. Vhodné pro kandidátní klíče, kombinace více atributů může být UNIQUE.
- PRIMARY KEY – sloupec je primárním klíčem. 
- REFERENCES – sloupec je cizím klíčem, definuje referenční integritu vzhledem k jiné tabulce.
- CHECK – IO zadané logickým výrazem. 
- DEFAULT – slouží k určení implicitní hodnoty sloupce: NULL nebo hodnota.

*Příklad na vytvoření entity*
``` sql
CREATE TABLE example(
 column1 INTEGER,
 column2 VARCHAR(50),
 column3 DATE NOT NULL,
 PRIMARY KEY (column1, column2)
);
```
*Příklad na změnu definice entity*
``` sql
ALTER TABLE example ADD column4 NUMBER(3) NOT NULL;
```
*Příklad na odstranění entity*
``` sql
DROP TABLE example;
```

## Uložené procedury a spouště
![[Uložené procedury a spouště (od SQL3)]]

## Pohledy
**Pohledy** (views) = virtuální tabulky. Slouží především pro dotazování. Umožňují značné zjednodušení zápisu dotazů (obdobně jako rozčlenění programu do procedur).

``` sql
CREATE VIEW Prazaci
AS 
	SELECT k_zamestnance, jmeno_z FROM Zamestnanci
	WHERE Adresa LIKE ‘%Praha%’;

SELECT k_zamestnance FROM Prazaci 
WHERE Plat > 10000;

DROP VIEW Prazaci;
```

## Transakce
![[SQL - Transakce]]

## Zdroje:
- [tkrizek/tul-szz-it-nv](https://github.com/tkrizek/tul-szz-it-nv/blob/master/16_jazyk_sql/16_jazyk_sql.md)