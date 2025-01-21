# Generování kombinací

Relace uspořádání:
- $<$ - 
- $\subset$ -  podmnožina
- \ - býti dělitelem


Pořadí uspořádání:
$\emptyset \neq A, B, ...$ - konečné celočíselné množiny

> [!tip] $A < B$
$min((A-B) u (B-A)) \in A$

Symetrická diference:
$((AuB)-(AaB))$

$C^k_n$
$(1 \leq k \leq n)$

## Algoritmus
```Python
x = range(1,k)
while x != (n-k-1,...,n) do
	m = max(i | \exist j not \in) # posledni pozice v kombinaci ktera ma tu vlastnost, že existuje prvek větši než na te pozici
	# zkopiruje se vyrez:
	(x'_1, ..., x'_m-1) = (x_1, ..., x_m-1)
	x'_m+i = x_m + (i+1)
	i = 0,...,k-m
	x = x'
	print(x)
```

## Postup:
n = 5
k = 3

123 -> 124 -> 125 -> 134 -> 135 -> 145
-> 234 -> 235 -> 245 -> 345