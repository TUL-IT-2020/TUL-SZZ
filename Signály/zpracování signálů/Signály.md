# Signály
Je nositel informace, co je informace závisí na konkrétní úloze. Signál je projevem činnosti systému.

## Druhy signálů
### Analogový signál
Je spojitý v čase i v hodnotách (definován v libovolném časovém okamžiku, může nabývat libovolné hodnoty).

### Číslicový signál 
Je nespojitý v čase (prostoru) i v hodnotách (nabývá jen určitých hodnot v určitém čase a v prostoru).

### Výhody číslicových signálů:
1. S diametrálně různými fyzikálními veličinami lze po převedení do číslicové podoby pracovat úplně stejnými metodami.
2. Číslicové výpočetní systémy (PC, notebooky, tablety, „chytré“ mobily, mikrokontroléry ,) jsou dnes velmi výkonné a zvládají i velmi složité algoritmy.
3. [[AD převod|Převod]] z a do analogové formy (pokud je nutný) je snadno a levně realizovatelný.

### Výhody číslicových signálů pro výuku:
1. I velmi složité algoritmy lze popsat jednoduchými aritmetickými operacemi: 
   - místo integrálu součet, 
   - místo derivace rozdíl, 
   - možnost simulace -> Matlab.
1. Na číslicových signálech se dají vysvětlit pojmy a metody používané v navazujících předmětech (strojové učení, rozhodování, řízení, ...).
2. Na tomto základě probíhá výuka na mnoha univerzitách ve světě (heslo „DSP first")

## Základní signály
![[Základní signály]]

## Výpočty se signály
### Derivace
- [[Derivace]]
Vyjadřuje míru změny signálu.
- zpětná(kauzální) $y[n] = x[n] - x[n-1]$
- dopředná (nekauzální) $y[n] = x[n+1] - x[n]$

### Integrace
- [[Integrace]]
Vyjadřuje obsah plochy pod signálem.
> [!tip] Spojité (analogové) signály:
$$
S = \int_{a}^{b} x(t) dt
$$
> [!tip] Digitální signály:
$$S = \sum_{i=0}^{N-1} x[i]
$$ 

### Střední hodnota
- [[Střední hodnota a rozptyl]]
1. U konečného signálu
$$
X = \frac{1}{N} \sum_{i=0}^{N-1} x[i]
$$
2. U nekonečného signálu (pouze u periodických)
$$
X = \lim_{N \to \infty} \frac{1}{N} \sum_{i=0}^{N-1} x[i]
$$
### Energie
![[Energie]]
### Výkon
![[Výkon]]
## Perioda
### Periodické signály
Se opakují se po určité době.
![[Analogová frekvence]]
### Harmonické signály
![[Sinus]]

To samé pro kosinusovku ta je jen posunutá o $\frac{\pi}{2}$ vůči sinusovce a symetrická vůči nule proto je více používaná.
> [!tip] Kosinus
$$
x(t) =A \cos(\omega t + \varphi)
$$
#### Exponencionální tvar

$$
x(t) = Ae^{j \omega t} = A \cos(\omega t) + j A \sin(\omega t)
$$
## Převod analogového signálu na číslicový
### Vzorkování / Sampling
- převod spojitého signálu na diskrétní
- vzorkovací frekvence $f_s$ (vzorků za sekundu)
- vzorkovací perioda $T_s = \frac{1}{f_s}$ (v sekundách)
- vzorkovací frekvence musí být větší než dvojnásobek nejvyšší frekvence v signálu (podle Nyquistova teorému)

### Kvantování / Quantization
- převod spojitého signálu na diskrétní
- kvantovací úroveň $Q$ (v jednotkách signálu)
- kvantovací úroveň musí být dostatečně malá, aby nedocházelo k velkým chybám při převodu
### A/D převod
![[AD převod]]

## Převzorkování signálů
![[Převzorkování]]
## Příklady
![[Signály příklady|Signály příklady]]

## Reálné signály
Vlastnosti reálných signálů:
- mají konečnou délku -> málo dat,
- nestacionarita -> frekvenční složka času se mění v čase,
- šum