#SQL
# Příklad Dirty Reads

Dirty read nastává, pokud transakce čte data, která byla modifikována jinou transakcí, která není potvrzena. Transakce B vidí data, která jsou upravena transakcí A. Tyto změny však nejsou potvrzeny.

*Transakce A*
``` sql
UPDATE employee SET salary = 31650 WHERE emp_no = '000090'
```

*Transakce B*
``` sql
SELECT * FROM employee
```