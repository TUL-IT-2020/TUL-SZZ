# Generovaní permutací v lexikografickém pořadí

lexikografické pořadí (uspořádání):
"abecedně"
$A = \{a_1, ..., a_r\}$

$a_1 < a_2 < ... < a_r$

$x, y \in A^*$
- $A^*$ - všechna slova abecedy
- $x = (x_1,...,x_n)$
- $y = (y_1,...,y_n)$

Stejná slova:
$x = y$
$(m = n) a (\forall i x_i = y_i )$

Kratší slova:
$x < y$
buď
$(m < n) a (\forall i x_i = y_i )$
nebo
$\exists k \leq min\{m, n \} a (\forall i x_i = y_i) a (x_k < y_k)$ 

## Algoritmus:
```Python
n = 4
x = range(1,n)
while x != (n, n-1, ..., 1) do
	k = max(i | x_i < x_{i+1}) # posledni pozice v permutaci kde nasleduje vetsi prvek
	(x'_1, ..., x'_k-1) = (x_1, ..., x_k-1)
	x'_k = min(x_i | x_i > x_k)
	(x'_k+1,...,x'_n) = zbyvajici prvky seratene
	x = x'
	print(x)
end
```

Poslední pozice následovaná větším prvkem

## Postup:
n = 4

1, 2, 3, 4
->
1 2 4 3
->
1324
-> 1342
-> 1423
-> 1432

## K zamyšlení:
Generování subfaktoriálů (permutace, kde žádný prvek není na svém místě)