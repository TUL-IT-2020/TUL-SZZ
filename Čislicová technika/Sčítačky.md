# Sčítačky 
## Sčítačky pro nezáporná čísla
U sčítaček nezáporných čísel rozlišujeme přenos do řádu i, který budeme označovat $p_i$ přenos z řádu i, $q_i$ přenos z posledního řádu $q*$(přenos anglicky nazýváme carry). K přeplnění sčítačky dojde tehdy, když $q* =1$. Přenos $q*$ nazýváme přeplněním (overflow). Případné přeplnění je třeba při sčítání monitorovat a jeho výskyt ošetřit jako chybový výsledek.

![[Úplná jednobitová sčítačka.png]] 
>Úplná jednobitová sčítačka

Základním blokem sčítačky je úplná jednobitová sčítačka Obr. 60. Úplná jednobitová sčítačka se skládá ze dvou polosčítaček a obvodu logického součtu. Polosčítačka vytváří na výstupu s XOR ze vstupních bitů. Výstup q polosčítačky odpovídá logickému součinu vstupních proměnných
polosčítačky. Propojením polosčítaček podle Obr. 60 získáme na výstupu s součet mod 2 vstupních proměnných, na výstupu q získáme logickou hodnotu odpovídající výrazu q = ab + ap + bp.
Porovnáme-li výstupní hodnoty úplné jednobitové sčítačky s hodnotami, které odpovídají hodnotám součtu a přenosu do vyššího řádu v jednom řádu při sčítání binárních čísel, vidíme, že kaskádní spojení úplných jednobitových sčítaček bude realizovat operaci sčítání binárních čísel

![[Paralelní sčítačka se sériovým přenosem.png]]
>Paralelní sčítačka se sériovým přenosem

> [!NOTE] Binární sčítání
> **Sečtěte čísla $11_{10}$ a $6_{10}$.**
> ---
> $0 1011_2$ | $11_{10}$
> $0 0110_2$ | $6_{10}$
> ---
> $10001_2$ | $17_{10}$

Vícebitové paralelní sčítačky vytvářejí vzhledem ke zřetězení jednobitových sčítaček značné zpoždění výstupu oproti některým vstupním proměnným. Je při tom otázkou, jak minimalizovat zpoždění sčítačky, popřípadě jak přizpůsobit sčítačku taktu hodinových pulsů, které synchronizují případné vstupní a výstupní registry. Maximální redukce nejdelšího zpoždění sčítačky je dosažena u sčítačky s predikcí přenosu. Tato sčítačka je vybavena rozsáhlým obvodem, který samostatně paralelním způsobem vypočítává přenosy mezi jednotlivými řády sčítačky a tím dochází ke zkrácení nejdelšího zpoždění v obvodu. Podrobnosti jsou složité.

![[Sériová sčítačka.png]]
>Sériová sčítačka

Hardwarově nejjednodušší sčítačkou je sčítačka sériová. Její výhodou kromě jednoduchého zapojení je malé zpoždění v kombinační logice a tím i možnost vyšší frekvence taktování. Principiální schéma je uvedeno na Obr. 63. Sčítačka vyžaduje současné přivádění odpovídajících sečítaných bitů vícebitového čísla od nejnižšího řádu po nejvyšší, přičemž v klopném obvodě D se vždy uloží výstupní přenos, který je použit jako vstupní přenos pro následující zpracovávaný řád sčítání. Výhybka ve zpětné vazbě sčítačky přepíná mezi vnějším vstupním přenosem, který se může
uplatnit u nejnižšího řádu sčítání a přenosy uchovávanými v klopném obvodě. Vzhledem k tomu, že sčítání dvou m-bitových čísel trvá u sériové sčítačky m hodinových taktů, je možné zvolit jako kompromisní řešení sério-paralelní sčítačku

![[Sérioparalelní sčítačka.png]]
>Sérioparalelní sčítačka