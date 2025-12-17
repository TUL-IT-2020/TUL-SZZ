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