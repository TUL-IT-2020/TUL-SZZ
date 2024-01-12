# Metriky výkonosti

- **MIPS** (Million Instructions Per Second)
- **MOPS** (Million Operations Per Second)
- **MFLOPS** (Million FLoating point Operations Per Second)
## Výpočet
$$
P_{MIPS} = \frac{IC}{T_{CPU}}*10^{-6}
$$

$$
P_{MOPS} = \frac{OC}{T_{CPU}}*10^{-6}
$$

$$
P_{MFLOPS} = \frac{OC_{FP}}{T_{CPU}}*10^{-6}
$$
- $IC$ - počet instrukcí
- $T_{CPU}$ - doba výpočtu
- $OC$ - počet operací
- $OC_{FP}$ - počet operací v pohyblivé řádové čárce

Výjimečně se užívají GIPS (BIPS), GFLOPS, TFLOPS, …

![[Metriky výkonosti příklad]]