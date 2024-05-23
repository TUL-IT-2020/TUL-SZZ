#SQL
# ACID
- **Atomicity** - buď proběhnout všechny operace transakce nebo neproběhnou žádné; uživatel se nemusí starat o výsledek nekompletní transakce (rollback).
- **Consistency** - transakce musí zachovávat konzistentní stav databáze; při spuštění transakce v db, která je v konzistentním stavu, ji tato transakce musí po svém ukončení opustit v konzistentním stavu; konzistenci musí zaručit uživatel; SŘBD se stará o to, aby to platilo i u paralelně pobíhajících transakcí.
- **Isolation** - v případě že v systému probíhá více transakcí paralelně, SŘBD zaručí, že transakce jsou izolované jedna od druhé, tedy že jedna nebude ovlivňovat druhou; pro uživatele to znamená, že pro něj DB vypadá jako, že aktuálně probíhá pouze jedna (jeho) transakce.
- **Durability** - pokud byla transakce jednou dokončena a potvrzena, pak SŘBD zaručí, že všechny změny provedené transakcemi zůstanou zachovány v db i při případném selhání systému (logování).