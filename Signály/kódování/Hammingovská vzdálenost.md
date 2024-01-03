# Hammingovská vzdálenost

$\vec u, \vec v \in \{0,1\}^m$
$d_H(\vec u, \vec v)$ - počet odlišných bitů vektoru $\vec u, \vec v$

$m = 6$
$\vec u = 110101$
$\vec v = 010011$
$\vec u + \vec v = 100110$

Počet "1" v $\vec u + \vec v$


Kód, obsahující slova $\vec p, \vec q$
$d_H \left(\vec p, \vec q \right) = 1$
- žádná schopnost detekce

- d - nejmenší Hamm. vzdálenost K.S.
- zapisujeme $(n,k,d)$

Kód (4,3,2)
Kód (3,1,3)

Schopnost detekce: $e = d-1$
Schopnost opravy: $t = \lfloor\frac{d-1}{2}\rfloor$