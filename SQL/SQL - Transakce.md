## Transakce
**transakce** = je série příkazů čtení či zápisu na databázových objektech; základní vlastností transakce je ACID

- čtení - db objekt se přenese do paměti z HDD a následně je pak do proměnné programu
- zápis - db objekt je modifikován v paměti a následně zapsán na disk
- db objekt - jednotky se kterými pracují programy

*Příklad transakce*
``` sql
START TRANSACTION;
 UPDATE Account SET amount=amount-200 WHERE account_number=1234;
 UPDATE Account SET amount=amount+200 WHERE account_number=2345;

IF ERRORS=0 COMMIT;
IF ERRORS<>0 ROLLBACK;
```
### ACID
![[SQL - ACID]]

### Typy konfliktů
- **WR konflikt** - čtení dat, která nebyla potvrzena (commit)
- **RW konflikt** - neopakovatelné čtení dat; čteme 2x, ale po prvním čtení se data změní = výsledkem jsou dvě rozdílné sady dat
- **WW konflikt** - přepsání nepotvrzených dat

K eliminaci konfliktů se používá *přidělování sdílených zámků - 2PL a Strict 2PL*. Je třeba zaručit, že příkazy lock a unlock budou atomické operace - semafory.

**Strict 2PL**

Pravidla pro přidělování zámků transakcím:

1. Pokud chce transakce číst (modifikovat) objekt db, musí nejprve požádat o sdílený (exklusivní) zámek.
2. Všechny zámky držené transakcí jsou uvolněny po jejím skončení.

**2PL**

1. Pokud transakce chce číst (modifikovat) objekt db, nejprve musí požádat o sdílený (exklusivní) zámek.
2. Transakce nemůže požádat o nový zámek, pokud již nějaký neuvolnila.

### Stupně izolace
- **READ UNCOMMITTED** - čtení záznamů, které ještě nejsou potvrzeny (commit); nevyužívají zámky a tím nedokážou zabránit jiné transakci v modifikaci dat které zrovna čte současná transakce; označují se také jako "dirty reads"
- **READ COMMITTED** - čtení záznamů, které byly potvrzeny (commit); vylepšení oproti předchozímu "dirty reads"
- **REPEATABLE READ** - čtení záznamů, které byly potvrzeny (commit) a zároveň jsou čtené záznamy zablokovány proti dalším modifikacím do skončení čtecí transakce 
- **SERIALIZABLE** - čtení záznamů, které byly potvrzeny (commit) a zároveň jsou čtené záznamy zablokovány proti dalším modifikacím do skončení čtecí transakce; zároveň jiné transakce nemohou vkládat data, která by mohla ovlivnit současné čtení (že by se nově vkládaná data mohla objevit ve čtecí transakci); jedná se o nejvíce restriktivní stupeň izolace

**Příklad Dirty Reads**

Dirty read nastává, pokud transakce čte data, která byla modifikována jinou transakcí, která není potvrzena. Transakce B vidí data, která jsou upravena transakcí A. Tyto změny však nejsou potvrzeny.

*Transakce A*
``` sql
UPDATE employee SET salary = 31650 WHERE empno = '000090'
```

*Transakce B*
``` sql
SELECT * FROM employee
```