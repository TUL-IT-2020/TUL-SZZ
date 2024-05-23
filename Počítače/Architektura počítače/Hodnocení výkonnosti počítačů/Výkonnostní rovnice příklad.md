#příklad
# Výkonnostní rovnice příklad

## Příklad

Počítač zpracovává program, který má 5 miliónů 1-CPI (jednotaktových instrukcí), 1 milión 2-CPI a 1 milión 3-CPI. Kmitočet hodinových taktů je 100 MHz. Jaká je jeho výkonnost v MIPS?

### Postup
- $5M$ - 1-CPI
- $1M$ - 2-CPI
- $1M$ - 3-CPI

$IC = 7*10^6$ (instruction count)
$N_{CLK} = 5*10^6*1 + 1*10^6*2 + 1*10^6*3 = 10*10^6$
$$
T_{CPU} = \frac{N_{CLK}}{F_{CLK}} = \frac{10^7}{10^8} = 0.1s
$$
$$
P_{MIPS} = \frac{IC}{T_{CPU}}*10^{-6} = \frac{7*10^6}{0.1}*10^{-6} = 70
$$
### Řešení
Výkonost je $70$ MIPS.