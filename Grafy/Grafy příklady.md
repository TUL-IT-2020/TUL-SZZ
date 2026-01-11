# Grafy příklady

## Příklad

V = {1,2,3,4,5}

Seznam sousedů:
- 1: 2,3,5
- 2: 1,3
- 3: 1,2,4
- 4: 3,5
- 5: 1,4

### Postup:
Hrany:
H = {(1,2),(1,3),(1,5),(2,3),(3,4),(4,5)}

Matice sousednosti:
$$
A = \begin{pmatrix}
0 1 1 0 1 \\
1 0 1 0 0 \\
1 1 0 1 0 \\
0 1 0 0 1 \\
1 0 0 1 0 
\end{pmatrix}
$$

Matice incidence:
$$
A = \begin{pmatrix}
1 1 1 0 0 0 \\
1 0 0 1 0 0 \\
0 1 0 1 1 0 \\
0 0 0 0 1 1 \\
0 0 1 0 0 1
\end{pmatrix}
$$

Stupeň vrcholu:
- d(1) = 3
- d(2) = 2
- d(3) = 3
- d(4) = 2
- d(5) = 2

Skóre grafu:
- (3,3,2,2,2)

## Příklad

V = {a,b,c,d,e}

H = {(a,b),(b,c),(c,d),(d,a),(b,d),(c,e)}

### Postup:
Graf:
```
a - b
| / |
d - c - e
```

- a,b,c,d,a - kružnice
- a,b,d,c,e - cesta
- a,b,a,d,c - sled
- e,c,b,d,a,c - nelze

## Příklad

V = {1,2,3,4,5,6}
H = {(1,2),(2,3),(3,1),(3,4),(4,5),(5,6),(6,4)}

Určete všechny komponenty souvislosti.

### Postup:

graf:
```
1 - 2
|  /
3 
|
4
| \
5 - 6
```

Kružnice:
- {1,2,3}
- {4,5,6}

Komponenty souvislosti:
- jedna.

## Příklad - sociální síť

V malé sociální síti máme uživatele: 
A, B, C, D, E, F, G, H. 

Vztahy přátelství mezi nimi jsou následující:

H = {(A,B), (A,C), (B,C), (C,D), (E,F), (F,G), (G,E)}

- Nakreslete graf přítelství.
- Najděte všechny komunity.

### Postup:
Graf:
```
A - B
|  /
C - D

E - F
|  /
G

H
```

Komunity:
- Komunita 1: {A, B, C, D}
- Komunita 2: {E, F, G}
- Komunita 3: {H} (izolovaný uživatel)

## Příklad - Havlův algoritmus

Skóre grafu:
(3, 3, 2, 2, 2)

### Postup:

| Odečítám: | | | | |
|-----------|---|---|---|---|
| 3       | 3 | 2 | 2 | 2 |
| 2       | 2 | 1 | 1 |   |
| 1       | 1 |   |   |   |
| 0       |   |   |   |   |

Graf je realizovatelný.

## Příklad - Zápisy grafu + stupně + souvislost
Nechť G = (V, E). 
- V = {1,2,3,4,5},
- E = {{1,2}, {1, 3}, {2,3}, {2,4}, {4,5}}.

1. Napište seznam sousedů.
2. Napište matici sousednosti.
3. Určete stupně vrcholů a rozhodněte: zda je graf souvislý.

### Řešení

1. Seznam sousedů:
- 1: 2, 3
- 2: 1, 3, 4
- 3: 1, 2
- 4: 2, 5
- 5: 4

2. Matice sousednosti:
$$
A = \begin{pmatrix}
0 1 1 0 0 \\
1 0 1 1 0 \\
1 1 0 0 0 \\
0 1 0 0 1 \\
0 0 0 1 0
\end{pmatrix}
$$

3. Stupně vrcholů:
- d(1) = 2
- d(2) = 3
- d(3) = 2
- d(4) = 2
- d(5) = 1

Graf je souvislý, protože existuje cesta mezi každými dvěma vrcholy.

Např cesta celým grafem: 3 - 1 - 2 - 4 - 5

## Příklad - Minimální kostra (Kruskal) + nejkratší cesta (Dijkstra) (střední)
Neorientovaný ohodnocený graf s vrcholy A, B, C, D, E, F má hrany:
- BC(1), AC(2), DE(2), EF(3), AB(4), BD(5), DF(6), BE(7), CD(8), CE(10).

1. Najděte minimální kostru a její váhu.
2. Najděte délku nejkratší cesty z A do F.

### Řešení

Minimální kostra (Kruskalův algoritmus):
BC(1)
AC(2)
DE(2)
EF(3)
AB - vynecháme (uzavře kruh)
BD(5) 
DF - vynecháme (uzavře kruh)
BE - vynecháme (uzavře kruh)
CD - vynecháme (uzavře kruh)
CE - vynecháme (uzavře kruh)

```txt
B - C - A
|   
D - E - F
```

Váha minimální kostry: 1 + 2 + 2 + 3 + 5 = 13

Nejkratší cesta z A do F:

```txt
    A
  / |
B - C
| x |
D - E
  \ |
    F
```

| Vrchol | Cesta z A |          |          |          |        |        |
| ------ | --------- | -------- | -------- | -------- | ------ | ------ |
| A      | **0**     |          |          |          |        |        |
| B      | $\infty$  | 4        | **3**    |          |        |        |
| C      | $\infty$  | **2**    |          |          |        |        |
| D      | $\infty$  | $\infty$ | 10       | **8**    |        |        |
| E      | $\infty$  | $\infty$ | 12       | 10       | **10** |        |
| F      | $\infty$  | $\infty$ | $\infty$ | $\infty$ |        | **13** |

Uzavřené vrcholy: A - C - B - D - E - F

Délka nejkratší cesty: 2 + 1 + 5 + 2 + 3 = 13

