# Rank counting sort
Vypočte pořadí prvku a pak jej zařadí na index

- $A[1,n]$ - vstupní pole
- $B[1,n]$ - výstupní pole
- $C[1,kn]$ - pracovní pole

$A[i] \ge 0$
$i \neq j$ -> $A[i] \neq A[j]$

$max(\{A[i]\}) \leq kn$
## Algoritmus
```Python
# vynuluj
for i in range(length(C)): # kn
	C[i] = 0

# dame 1 na index v C, ktery odpovida hodnote A[i]
for i in range(length(A)): # n
	C[A[i]] = 1

for i in range(2, length(A)): # kn
	C[i] = C[i] + C[i-1]

for i in range(length(B)): # n
	B[C[A[i]]] = A[i]
```
## Složitost
> [!info] O(kn)