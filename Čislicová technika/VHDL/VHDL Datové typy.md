# Datové typy

## Standardní skupiny datových typů
Datové typy lze dělit (sdružovat) do skupin, z nichž nejdůležitější jsou: 
- **Číselné** - např. integer, real, natural, positive, signed, unsigned; 
- **Logické** - bit, boolean, std_logic, std_ulogic; 
- **Znakové** - character, string; 
- **Složené** - více elementů v jednom objektu (vector, array, record), zápis bitových polí: b”11001001”, X”C3F”, O”754”; 28 
- **Fyzikální** - vyžadují připojení fyzikální jednotky (např. time);

## Datové typy podrobněji
- Integer
Implicitní celočíselný typ 
Nepoužíváme pro porty nebo signály - pouze vnitřní proměnné (for, generate…)

### `ieee.std_logic_1164`
Používáme v entity:
- std_logic - ‘U’, ‘X’, ‘0’, ‘1’, ’Z’, ‘W’, ‘L’, ‘H’, ‘-’
- std_logic_vector(X downto Y) - array of std_logic.

```VHDL
TYPE std_ulogic IS (
 ‘U’,-- neinicializováno (signál nebyl dosud buzen), implicitní
 ‘X’,-- neznámá hodnota (vzniká při konfliktu ‘0’ a ‘1’)
 ‘0’,-- log. 0 z tvrdého zdroje
 ‘1’,-- log. 1 z tvrdého zdroje
 ‘Z’,-- vysoká impedance
 ‘W’,-- neznámá hodnota (vzniká při konfliktu H a L) 
 ‘L’,-- log. 0 z měkkého zdroje
 ‘H’,-- log. 1 z měkkého zdroje 
 ‘-’ -- neurčená hodnota (don’t care), na hodnotě nezáleží.
);
```

### `ieee.numeric_std`
Užíváme v architektuře:
- unsigned(X downto Y)
- signed(X downto Y)

## Hodiny
```VHDL
clk’event AND clk = ‘1’ -- náběžná hrana
clk’event AND clk = ‘0’ -- sestupná hrana

-- v knihovně IEEE 1164 existují fce:
rising_edge(clk)
falling_edge(clk)
```

## Vectors
Aggregates are a grouping of values to form an array or record expression. The first form is called **positional association**, where the values are associated with elements from left to right:
```VHDL
signal Z_BUS : bit_vector (3 downto 0);
signal A_BIT, B_BIT, C_BIT, D_BIT : bit;
...
Z_BUS <= (A_BIT, B_BIT, C_BIT, D_BIT);
```
Equivalent Assignments:
```VHDL
Z_BUS(3) <= A_BIT;
Z_BUS(2) <= B_BIT;
Z_BUS(1) <= C_BIT;
Z_BUS(0) <= D_BIT;
```

## Atributy
K atributům je možné přistoupit pomocí zápisu apostrofu.

- A'left(N) 	Levá mez pole A	
- A'right(N) 	Pravá mez pole A	
- A'high(N) 	Nejvyšší mez pole A	
- A'low(N) 	Nejnižší mez pole A	
- A'range(N) 	Rozsah pole A
- A'reverse_range(N) 	Obrácený rozsah pole A	
- A'length(N) 	Počet prvků pole A	
	U jednorozměrných polí není třeba uvádět dimenzi N

> [!example] Příklad:  
> *x´left*  je levá mez jednorozměrného pole x.

## Typová konverze:
[fpgatutorial](https://fpgatutorial.com/vhdl-types-and-conversions/)
Lze použít konverzní funkce:
- std_logic_vector(unsigned/signed) - vrací std_logic_vector stejné délky
- unsigned(std_logic_vector) - vrací unsigned stejné délky
- signed(std_logic_vector) - vrací signed stejné délky

![[VHDL-peklo.gif]]

## User defined types
### enumerate
Výčtový datový typ. 
```VHDL
type my_enum is (S0, S1, S2);
```
###  record
Assignment to a whole record must be done using an aggregate. Positional or named association may be used
```VHDL
type T_PACKET is record
	BYTE_ID : std_ulogic;
	PARITY  : std_ulogic;
	ADDRESS : integer range 0 to 3;
	DATA    : std_ulogic_vector (3 downto 0);
end record
signal TX_DATA : T_PACKET;
...
TX_DATA <= ('1', '0', 2, "0101");
```