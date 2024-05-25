# Signály
Je nositel informace, co je informace závisí na konkrétní úloze. Signál je projevem činnosti systému.

## Druhy signálů
### Analogový signál
- spojitý v čase i v hodnotách (definován v libovolném časovém okamžiku, může nabývat libovolné hodnoty)

### Číslicový signál 
- nespojitý v čase (prostoru) i v hodnotách (nabývá jen určitých hodnot v určitém čase a v prostoru)

### Výhody číslicových signálů:
1. S diametrálně různými fyzikálními veličinami lze po převedení do číslicové podoby pracovat úplně stejnými metodami
2. Číslicové výpočetní systémy (PC, notebooky, tablety, „chytré“ mobily, mikrokontroléry ,) jsou dnes velmi výkonné a zvládají i velmi složité algoritmy
3. Převod z a do analogové formy (pokud je nutný) je snadno a levně realizovatelný.

### Výhody číslicových signálů pro výuku:
1. I velmi složité algoritmy lze popsat jednoduchými aritmetickými operacemi : místo integrálu součet, místo derivace rozdíl, možnost simulace Matlab
2. Na číslicových signálech se dají vysvětlit pojmy a metody používané v navazujících předmětech (strojové učení, rozhodování, řízení, ...)
3. Na tomto základě probíhá výuka na mnoha univerzitách ve světě (heslo „DSP first)

## Základní signály
![[Základní signály]]

## Výpočty se signály
### Derivace
- vyjadřuje míru změny signálu
- zpětná(kauzální) $y[n] = x[n] - x[n-1]$
- dopředná (nekauzální) $y[n] = x[n+1] - x[n]$

### Integrace
- vyjadřuje obsah plochy pod signálem
- $S = \int_{a}^{b} x(t) dt$ $S = \sum_{i=0}^{N-1} x[i]$ 

### Střední hodnota
1. U konečného signálu
    - $X = \frac{1}{N} \sum_{i=0}^{N-1} x[i]$
2. U nekonečného signálu (pouze u periodických)
    - $X = \lim_{N \to \infty} \frac{1}{N} \sum_{i=0}^{N-1} x[i]$
### Energie
 ![[Energie]]
### Výkon
![[Výkon]]
## Perioda
$x[x] = sin(\pi/8 * n)$
$2\pi = \pi/8 * N$
$N = 16$

Změna vzorkování:
$x[n] = sin(1/8n)$
$2\pi = 1/8*N$
$N = 16\pi$

V diskrétních čísel musí být perioda celočíselná a proto tento signál není periodická. 

### Periodické signály
- opakují se po určité době
- perioda $T$ (v sekundách)
- frekvence $f = \frac{1}{T}$ (v Hz)

### Harmonické signály
- sinusovka $x(t) = A \sin(2 \pi f t + \varphi)$
- amplituda $A$ (v jednotkách signálu)
- frekvence $f$ (v Hz)
- fáze $\varphi$ (v radiánech)
- úhlová frekvence $\omega = 2 \pi f$ (v radiánech za sekundu)
- to samé pro kosinusovku ta je jen posunutá o $\frac{\pi}{2}$ vůči sinusovce a symetrická vůči nule proto je více používaná

$$
x(t) =A \cos(\omega t + \varphi)
$$

#### Exponencionální tvar

$$
x(t) = Ae^{j \omega t} = A \cos(\omega t) + j A \sin(\omega t)
$$
## Převod analogového signálu na číslicový
![[Převod analogového signálu na číslicový]]

## Převzorkování signálů
![[Převzorkování]]

$m = 2n - 3$
Inverzní funkce:
$n = \frac{m+3}{2}$

## Příklady
![[Signály příklady|Signály příklady]]

## Reálné signály
Vlastnosti reálných signálů:
- mají konečnou délku -> málo dat,
- nestacionarita -> frekvenční složka času se mění v čase,
- šum