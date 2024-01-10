# Výkonnostní rovnice procesoru

**Výkonnost CPU závisí na:**

- počtu instrukcí (IC – Instruction Count)
- (průměrném) počtu taktů na instrukci (CPI – Cycles Per Instruction)
- periodě hodinového signálu (Tclk) – doba cyklu (taktu)

*Doba provádění programu TCPU je dána počtem hod. cyklů během programu násobená dobou cyklu Tclk (je-li konst.)*

![Výkonostní rovnice](26_vykonostni_rovnice.png)

*Výkonostní rovnice*

**Příklad**

Počítač zpracovává program, který má 5 miliónů 1-CPI (jednotaktových instrukcí), 1 milión 2-CPI a 1 milión 3-CPI. Kmitočet hodinových taktů je 100 MHz. Jaká je jeho výkonnost v MIPS?

![Příklad použití výkonostní rovnice](26_vykonostni_rovnice_priklad.png)

*Příklad použití výkonostní rovnice*