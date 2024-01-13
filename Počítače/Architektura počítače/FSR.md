# FSR Registers and the INDF Operand

V jádru nepřímé adresování jsou tři sady registrů: `FSR0`, `FSR1` a `FSR2`. Každý z nich představuje pár 8bitových registrů, `FSRnH` a `FSRnL`. Každý pár `FSR` obsahuje plnou adresu umístění RAM. Hodnota `FSR` může adresovat celý rozsah paměti dat lineárním způsobem. Páry registrů `FSR` tedy slouží jako ukazatele na umístění paměti dat.

Nepřímé adresování se provádí pomocí sady nepřímých souborových operandů, `INDF0` až `INDF2`. Tyto lze považovat za „virtuální“ registry; jsou mapovány v prostoru `SFR`, ale nejsou fyzicky implementovány. Čtení nebo zápis do konkrétního registru `INDF` ve skutečnosti přistupuje k jeho odpovídajícímu páru registrů `FSR`. Čtení z `INDF1` například čte data na adrese uvedené `FSR1H:FSR1L`. Instrukce, které používají registry `INDF` jako operandy, ve skutečnosti používají obsah jejich odpovídajícího `FSR` jako ukazatele na cíl instrukce. Operand `INDF` je jen pohodlný způsob použití ukazatele.

Protože nepřímé adresování používá plnou adresu, může hodnota `FSR` cílit na libovolné umístění v libovolné bance bez ohledu na hodnotu `BSR`. Nicméně bit přístupu k RAM musí být nastaven na nulu, aby se zajistilo, že registr `INDF` v prostoru přístupu je objektem operace místo registru v jedné z ostatních bank. Výchozí hodnota assembleru pro bit přístupu k RAM je nula při cílení na libovolný z nepřímých operandů.

## Zdroje:
- https://onlinedocs.microchip.com/oxy/GUID-D364745C-8255-47AE-9528-9EB17646EE19-en-US-16/GUID-ECE40AEB-FA62-4D3D-9AA5-BB545091F1FB.html
- https://pictutorials.com/INDF%20and%20FSR.htm