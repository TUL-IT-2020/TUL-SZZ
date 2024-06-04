#SQL
# Dirty Reads
Nastanou pokud transakce čte data, která byla modifikována jinou transakcí, která není potvrzena.

Transakce A začátek:
```SQL
UPDATE employee 
SET salary = 31650 
WHERE empno = '000090' 
```
Transakce B začátek:
```SQL
SELECT * FROM employee
```

> [!note]
> Transakce B vidí data, která jsou upravena transakcí A. Tyto změny nejsou potvrzeny.
