# Radix sort (base 10)
Řadíme řetězce mající max d znaků (znaky 0,1,...,9 - base 10).

- $Q_0, ..., Q_9$ - řadící fronty
- $A[1,...,n]$ - vstupně výstupní pole

$A[j][i]$ - j-tý řetězec, i-tý nejméně významný znak

## Algoritmus
```Python
d = 10
for i in range(d):
	empty(Q[i])

	# roztridime pole do front podle j nevyzmaneho znaku
	for j in range(n):
		char = A[j][i]
		# vloz do prislusne fronty
		Q[char].push(A[j])

	# prendame vsechny polozky z front do pole
	A = []
	for i in range(d):
		# obsah frotny do pole
		A.append(Q)
```

## Příklad:
A: 21, 7, 15, 19, 30, 9
d = 2

i = 1
Q0 = 30
Q1 = 21
Q5 = 15
Q7 = 7
Q9 = 19, 9

A: 30, 21, 15, 7, 19, 9

i = 2
Q0 = 7, 9
Q1 = 15, 19
Q2 = 21
Q3 = 30
A: 7, 9, 15, 19, 21, 30
## Složitost
> [!info] O(dn)