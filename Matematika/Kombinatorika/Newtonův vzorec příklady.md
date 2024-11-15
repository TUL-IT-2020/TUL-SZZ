# Newtonův vzorec
## Příklad 
$$
(1+3x)^{1/2}
$$

Určete koeficienty u: $x^5$

### Řešení
$$
x^5 = \frac
{1/2 * (1/2 - 1) * (1/2 - 2) * (1/2 - 3) * (1/2 - 4)}
{5!} * 3^5
= \frac{1701}{256}
$$

## Příklad
$$
\frac{1}{(1-2x^2)^3}
$$

Určete koeficienty u: 
- $x^7$
- $x^8$

### Postup

Jaké exponenty můžeme dostat:
$x^2, x^4, x^6, x^8$

$x^8$: 
- $\alpha = -3$
- $n = 4$

$$
\frac
{(-3)(-3-1)(-3-2)(-3-3)}
{4!}* 2^4 = ...
$$

### Řešení
$0x^7$

## Příklad
> [!question] Jak na počítači výpočítat obecnou odmocninu?

$$
\sqrt{20} = ?
$$

### Postup
- $\sqrt{n}$ ... výpočet z Newtonova vzorce
$$
\sqrt{20} = (20)^{1/2}
$$
- $\alpha = 1/2$

Pro použití Newtonova vzorce musíme splnit:
- $|y| < 1$

Tedy:
$y \neq 19$

Zkusíme vytknout takové číslo, aby jsme získali adekvátní tvar.
$$
\sqrt{16(1+1/4)} = 4(1+1/4)^{1/2}
$$

### Řešení
$$
1+1/2(1/4) -1/8(1/4)^2 + 1/16(1/4)^3 - ... \approx 4.472
$$
- $1/2 = \alpha$ 
