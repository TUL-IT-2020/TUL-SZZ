# Kongruence

![[Redukovaná soustava zbytků mod m]]

## Kongruence prvního stupně

Kongruence 1. stupně a jejich řešení. Obecně má kongruence prvního stupně tvar: 
$$
ax ≡ b(m)
$$
kde: 
- a, b, m ∈ Z ∧ m ≥ 2.

### Věta: 
Nechť NSD(a, m) = 1, potom má kongruence pro libovolné b právě jedno řešení (mod m). Toto řešení je tvaru: 
$$
x ≡ (−1)^nP_{n−1}b \;\; mod(m)
$$
kde $P_{n−1}$ představuje čitatel předposledního řetězového zlomku rozvoje čísla $\frac{m}{a}$ v [[Řetězové zlomky|řetězový zlomek]].

### Příklady
[[Kongruence příklady]]
## Soustavy kongruencí prvního stupně

Upravíme jednotlivé kongruence do základního tvaru:
$$
x_i \equiv b_i(m_i)
$$
Zkontrolujeme:
$\forall i\neq j \;; NSD(m_i,m_j) = 1$ ... Po dvou nesoudělná.

Spočítáme $M$ dle vzorce:
$$
M = NSN(m_1,...,m_n)
$$

Sestavíme tabulku:

| $M_i$ | $M_1$ | ... | $M_n$ |
| ---- | ---- | ---- | ---- |
| $\bar{M_i}$ | $\bar{M_1}$ | ... | $\bar{M_n}$ |
Kde:
- $M_i = \frac{M}{m_i}$
- $M_i*\bar{M_i} \equiv 1 (m_i)$

Nakonec vyjádříme výslednou kongruenci podle vzorce:
$$
x \equiv M_1\bar{M_1}b_1 + ... + M_4\bar{M_4}b_4(M)
$$
### Příklady
[[Soustavy kongruencí prvního stupně příklady]]

## Soustavy kongruencí
ZLO