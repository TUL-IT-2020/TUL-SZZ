# Přiřazení
## Nepodmíněné
```VHDL
object <= expression;
```
## Podmíněné - When
```VHDL
b <= "1000" when a = "00" else 
	 "0100" when a = "01" else 
	 "0010" when a = "10" else 
	 "0001" when a = "11";
```

## Výběrové přiřazení - With select
```VHDL
[label]: with selection_expression select object <=
     expression1 when choice01 [| choice02 | ...],
    [expression2 when choice11 [| choice12 | ...],
		  ...
      expressionn when choicen1 [| choicen2 | ...],
      expressiono when others;]
```