#SQL
# Transakce
**transakce** = je série příkazů čtení či zápisu na databázových objektech; základní vlastností transakce je [[SQL - ACID|ACID]]. Transakce o sobě navzájem nevědí, dokud nejsou ukončeny.

- čtení - db objekt se přenese do paměti z HDD a následně je pak do proměnné programu
- zápis - db objekt je modifikován v paměti a následně zapsán na disk
- db objekt - jednotky se kterými pracují programy

*Příklad transakce*
``` SQL
START TRANSACTION;
 UPDATE Account SET amount=amount-200 WHERE account_number=1234;
 UPDATE Account SET amount=amount+200 WHERE account_number=2345;

IF ERRORS=0 COMMIT;
IF ERRORS<>0 ROLLBACK;
```

``` SQL
TRANSACTION jméno_transakce 
	WHENEVER {ERROR|podmínka} ROLLBACK 
		příkazy 
COMMIT END
```

> [!tip] Postup modifikace dat v databázi:
>1. Začátek transakce.
>2. Otestujeme podmínku `WHERE` pomosí `SELECTu`.
>3. Modifikujeme požadovaná data vybraná podle `WHERE`.
>4. Konec transakce `COMMIT`.

Databáze je v konzistentním stavu, když splňuje všechny [[RMD - Relační model dat#Integrita databáze a integritní omezení|IO definované]] ve schématu databáze (požadavky od zadavatele, model reálného světa).
Správný výsledek paralelních transakcí je libovolný výsledek z kombinace jejich seriálového provádění (nikoli však žádný jiný). 
## ACID
![[SQL - ACID]]

## Typy konfliktů
> [!info] Typy konfliktů:
>- **WR** - čtení dat, která nebyla potvrzena (commit)
>- **RW** - neopakovatelné čtení dat; čteme 2x, ale po prvním čtení se data změní = výsledkem jsou dvě rozdílné sady dat
>- **WW** - přepsání nepotvrzených dat

#### Zámky
K eliminaci konfliktů se používá *přidělování sdílených zámků - 2PL a Strict 2PL*. Je třeba zaručit, že příkazy lock a unlock budou atomické operace - semafory.

**Strict 2PL**

Pravidla pro přidělování zámků transakcím:
1. Pokud chce transakce číst (modifikovat) objekt db, musí nejprve požádat o sdílený (exklusivní) zámek.
2. Všechny zámky držené transakcí jsou uvolněny po jejím skončení.

**2PL**
1. Pokud transakce chce číst (modifikovat) objekt db, nejprve musí požádat o sdílený (exklusivní) zámek.
2. Transakce nemůže požádat o nový zámek, pokud již nějaký neuvolnila.

Co zamykáme?
Tabulka -> řádek -> sloupec

Zamykání řádků probíhá přes indexy.
#### Souběh bez zámků
Optimistický algoritmus -> většinou ke kolizi nedochází.

Pracuje se s časovými značkami:
1. Načtou se data, včetně jejich času poslední úpravy,
2. Zpracující se,
3. Před COMMITem provedeme kontrolu časových značek, zda nebyli změněny. 
## Stupně izolace
U transakcí můžeme nastavit různé stupně izolace transakcí:
- **READ UNCOMMITTED** - čtení záznamů, které ještě nejsou potvrzeny (commit); nevyužívají zámky a tím nedokážou zabránit jiné transakci v modifikaci dat které zrovna čte současná transakce; označují se také jako "[[Dirty Reads|dirty reads]]".
- **READ COMMITTED** - čtení záznamů, které byly potvrzeny (commit); vylepšení oproti předchozímu "[[Dirty Reads|dirty reads]]", stále nám hrozí problém "fantomových" dat.
- **REPEATABLE READ** - čtení záznamů, které byly potvrzeny (commit) a zároveň jsou čtené záznamy zablokovány proti dalším modifikacím do skončení čtecí transakce. 
- **SERIALIZABLE** - čtení záznamů, které byly potvrzeny (commit) a zároveň jsou čtené záznamy zablokovány proti dalším modifikacím do skončení čtecí transakce; zároveň jiné transakce nemohou vkládat data, která by mohla ovlivnit současné čtení (že by se nově vkládaná data mohla objevit ve čtecí transakci); jedná se o nejvíce restriktivní stupeň izolace.

```SQL
SET TRANSACTION ISOLATION LEVEL { 
	READ UNCOMMITTED | 
	READ COMMITTED |
	REPEATABLE READ |
	SNAPSHOT |
	SERIALIZABLE |
}[ ; ]
```
### Fantom
#TODO

## Příklad
### Dirty read 
![[Dirty Reads]]
### Non-repeatable reads 
Nastávají pokud dva dotazy v rámci jedné transakce vrací jiná data. Nastává tehdy pokud jiná transakce modifikuje data, která jsou čtena. 

Transakce A začátek. 
```SQL
SELECT * FROM employee WHERE empno = '000090' 
```
Transakce B začátek. 
```SQL
UPDATE employee SET salary = 30100 WHERE empno='000090' 
```

> [!note]
> Transakce B upravuje data, která jsou čtena transakcí A, předtím než je transakce A potvrzena. 

Transakce A pokračuje.
```SQL
SELECT * FROM employee WHERE empno = '000090’‚ 
```

> [!warning]
> V tuto chvíli dostává jiný výsledek.

### Phantom Reads
Nové záznamy odpovídající podmínkám dotazu se objevují během čtení transakcí. Records that appear in a set being read by another transaction. 

Transakce A začátek. 
```SQL
SELECT * FROM employee WHERE salary > 30000 
```
Transakce B začátek. 
```SQL
INSERT INTO employee (empno, firstnme, midinit,lastname, job,salary) 
VALUES ('000350', 'NICK‘,'A','GREEN','LEGAL’ ,COUNSEL',35000) 
```

> [!note]
> Transacke B vkládá nový záznam, který odpovídá podmínce v dotazu transakce A.

Transakce A pokračuje. 
```SQL
SELECT * FROM employee WHERE salary > 30000
```