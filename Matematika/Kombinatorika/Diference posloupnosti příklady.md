# Diference posloupnosti
- [[Diference posloupnosti]]
$$
\Delta a_n = a_{n+1}-a_n
$$

$\Delta^2 a_n = a_{n+2} -2a_{n-1} + a_n$
## Spočtete:
$\Delta^1 a_n$
$\Delta^2 a_n$
$\Delta^3 a_n$
$\Delta^4 a_n$
## Aritmetická posloupnost:
$$
a_n = 3n + 1
$$

### Postup:
$\Delta^1 a_n = a_{n+1} + a_n$
$\Delta^1 a_n = 3(n+1)+1 - (3n +1)$
$\Delta^1 a_n = 3n+3+1 - 3n -1$
$\Delta^1 a_n = +3$

$\Delta^2 a_n = a_{n+2} -2a_{n+1} + a_n$
$\Delta^2 a_n = 3(n+2)+1 -2*(3(n+1)+1) + 3n+1$
$\Delta^2 a_n = 6 + 3n+1 + 3n+1 -2(3n+3+1)$
$\Delta^2 a_n = 6 + 2(3n+1) -2(3n+1) -6$
$\Delta^2 a_n = 0$

Další diference nemají smysl, protože posloupnost je již neměnná.
### Řešení:
$\Delta^1 a_n = +3$
$\Delta^2 a_n = 0$
## Aritmetická posloupnost:
$$
a_n = 2n^3 - 3n +1
$$
### Postup:
$(n+1)^3 = (n+1)(n+1)(n+1)$
$(n+1)(n+1) = n^2 + 2n + 1$
$(n+1)(n+1)(n+1) = n^3 + 2n^2 +n +n^2 + 2n +1$
$(n+1)^3 = n^3 + 3n^2 +3n +1$

$a_{n+1} = 2(n+1)^3 - 3(n+1) +1$
$a_{n+1} = 2n^3 +6n^2 +6n +2 -3n-2$
$a_{n+1} = 2n^3 +6n^2 + 3n$

$\Delta^1 a_n =2n^3 +6n^2 + 3n- (2n^3 - 3n +1)$
$\Delta^1 a_n =2n^3 +6n^2 + 3n - 2n^3 + 3n -1$
$\Delta^1 a_n =6n^2 + 6n -1$

#TODO
$\Delta^2 a_n$
$\Delta^3 a_n$
$\Delta^4 a_n$
### Řešení:
$\Delta^1 a_n =6n^2 + 6n -1$
$\Delta^2 a_n = 12n + 12$
$\Delta^3 a_n = 12$
$\Delta^4 a_n = 0$

## Exponenciální Posloupnost:
$$
a_n = 3^n
$$
### Postup:
$a_{n+1} = 3^{n+1} = 3 * 3^n$

$\Delta^1 a_n =3 * 3^n - 3^n =3^{n + 1} - 3^n = 3^n(3-1) = 3^n *2$

#TODO 
### Řešení:
$\Delta^1 a_n = 2 *3^n$
$\Delta^2 a_n =  2^2 *3^n$
$\Delta^3 a_n =  2^3 *3^n$
$\Delta^4 a_n = 2^4 *3^n$

