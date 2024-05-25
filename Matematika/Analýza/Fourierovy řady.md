# Fourierovy řady
> [!note]
>Umožňují rozložit a složit libovolný periodický spojitý signál na harmonické složky.

## Typy tvarů Fourierových řad:
### Polární tvar Fourierovy řady
$$
x(t) = \sum_{k=0}^{\infty} c_k cos(k 2 \pi  f_0+ \varphi_k)
$$
- Libovolný periodický spojitý signál $x(t)$ lze rozložit na součet dílčích složek
- Dílčí složky jsou harmonicky vázané kosinusovky s amplitudami $c_k$ a a fázovými posuny $\varphi_k$
- při analýze signálu je nutné spočítat koeficienty $c_k$ a $\varphi_k$

### Exponenciální tvar Fourierovy řady
- Je vhodnější pro praktický výpočet.
$$
x(t) = \sum_{k=-\infty}^{\infty} X_k e^{j k 2 \pi f_0 t}
$$
- funkce $exp(x)$ je alternativní zápis místo $e^x$
- jedná se součet harmonicky vázaných exponenciál
- $X_k$ je komplexní koefficient, definová i pro záporné indexy $k$

## Praktické využití

- umožňuje provést **frekvenční analýzu** signálu, tj. určit z jakých dílčích signálů ( kosinusovek o různých frekvencích a amplitudách) se skládá
- výsledkem je **spektrum signálu**, ze spektra lze získat detailní informace o obsahu signálu
- spektrum period. signálů lze jednoduše zobrazit jakožto z**ávislost amplitudy a fáze na frekvenci**
- znalost spektra umožňuje analýzu ale i např. kompresi signálů - je li spektrum signálu v čase proměnné, počítá se postupně v rámci *kratších úseků* signálu (krátkodobé spektrum) a zobrazuje se pak pomocí **spektrogramu**

## Diskrétní Fourierova transformace
$$
X[k] = \sum_{n=0}^{N-1} x[n]e^{-j\frac{2\pi*kn}{N}}
$$

![[DFT - Diskrétní Fourierova transformace]]

## Číslicové filtry FIR a IIR
- [[Filtrace]]
### FIR
![[FIR - Finite Impulse Response]]

---
## Z-transformace
![[Z-transformace]]

---
## Filtrace v čase nebo prostoru

### Spektrum signálu
- je závislost amplitudy a fáze na frekvenci

**Jednostranné spektrum** vychází z polárního tvaru a zobrazuje pouze kladné frekvence.
**Dvoustranné spektrum** vychází z exponenciálního tvaru a zobrazuje kladné a záporné frekvence.

![[DTFT spektrum]]