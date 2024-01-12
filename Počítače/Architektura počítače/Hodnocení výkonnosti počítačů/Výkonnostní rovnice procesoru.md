# Výkonnostní rovnice procesoru

**Výkonnost CPU závisí na:**

- počtu instrukcí (**IC** – Instruction Count)
- (průměrném) počtu taktů na instrukci (**CPI** – Cycles Per Instruction)
- periodě hodinového signálu ($T_{clk}$) – doba cyklu (taktu)

*Doba provádění programu TCPU je dána počtem hod. cyklů během programu násobená dobou cyklu Tclk (je-li konst.)*

$$
T_{CPU} = IC*CPI*T_{clk}
$$
(platí pro systémy bez cache)

$$
P_{MIPS} 
= \frac{IC}{
T_{CPU}
}*10^{-6} 
= \frac{10^{-6}}{
CPI*T_{clk}
} = \frac{f_{clk}}{
CPI
}*10^{-6}
$$

![[Výkonnostní rovnice příklad]]