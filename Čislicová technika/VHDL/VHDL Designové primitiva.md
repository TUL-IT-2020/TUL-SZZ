# Designové primitiva
### MUX
![[MUX 8 to 1]]

### Klopné obvody
```VHDL
-- flip_flop - D
architecture synth of flop is
begin
	process(clk)
	begin
		if rising_edge(clk) then
			q <= d;
		end if;
	end process;
end;
```
**D-čko**
Vstupy:
- clk (rising) - hodiny na náběžnou hranu
- SR - sinchroní reset
- D - data in
- EN - enable

Nedělej Latche, deska má flip flopy (hranové). Negejtuj hodiny v if.
Každé přiřazení pod hodinama vytvoří registr.

### Pamět
Pamět má vždy latenci jednoho cyklu. 
Nelze zapisovat do paměti ze dvou paraleních příkazů.
Při návrhu RAM, šahá na BRAM (block RAM) a skládá z ní.
Pro paralelní přístup do paměti vytvoří pole registrů RTLRAM. Nezávislé čtenní a zápis dat do registrů. 

Datavé slovo:
18b = 8+1 + 8+1
Pro každý Byte má uloženou paritu. CRC

Priorita:
čtení/zápis
RF/WF

### Registry
#### Posuvný registr
![[shift_register-small]]

### Čítače

Složí nám ho z registru a sčítačky, LUT dělá sčítačku, D složí registr.
Variable se nastaví hned, count až ukončením procesu.

Dělička hodinového signálu
Nikdy nevytvářet vlastní hodinové signály! 
Conuter na clock s comparátorem a ovládat EN -> (clock enable). 

Přiřazuje se do promených na konci waitu.
![[counter_generic]]

## Finate state machine

### Typy automatů
- [[Mooreův automat]] (výstup závisí pouze na aktuálním stavu)
- [[Mealyho automat]]

Implementujeme za pomoci třech procesů:
- aktualizace stavu na `next_state`,
- přechodová funkce,
- výstupní funkce.

![[FSM]]