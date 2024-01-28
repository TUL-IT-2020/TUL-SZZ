#příklad 
# Rozklad na prvočísla
## Příklad
Uvažujte:
- $a = 26 087 600$,
- $b = 5 005 000$, 
- $c = 5 236 000$. 

1) Určete, které z uvedených čísel má nejvíce dělitelů.
2) Určete počet kladných přirozených čísel nejvýše rovných b, která jsou s číslem b nesoudělná.
### Postup
Rozklad na prvočísla:
- $a = 26 087 600= 2^4×5^2×7^2×11^3$
- $b = 5 005 000= 2^3×5^4×7×11×13$
- $c = 5 236 000= 2^5×5^3×7×11×17$

[[Počet dělitelů příklad|Počet dělitelů]]:
$a = 2^4×5^2×7^2×11^3 = (4+1)(2+1)(2+1)(3+1) = 180$
$b = 2^3×5^4×7×11×13 = (3+1)(4+1)(2)(2)(2) = 160$
$c = 2^5×5^3×7×11×17 = (5+1)(3+1)(2)(2)(2) = 192$

[[Eulerova funkce|Nesoudělných čísel]]:
$\varphi(b) = (2^3-2^2)(5^4-5^3)(7-1)(11-1)(13-1)=4*500*6*10*12=1 440 000$

### Řešení
Nejvíce dělitelů má $c$.
$\varphi(b) = 1 440 000$

## Příklad
Nechť:
- m = 445 815 279,
- n = 19 864 845. 
1) Určete počet všech společných dělitelů čísel $\varphi(m)$ a $\varphi (n)$. 
2) Vypište šest největších společných dělitelů.