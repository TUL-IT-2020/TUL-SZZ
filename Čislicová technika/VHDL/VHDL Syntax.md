# Syntax
> [!warning] Je vice verzí jazyka VHDL!
>- VHDL
>- VHDL 2008 (ten hezčí)

## Entity
Popis vstupů a výstupů černé skříňky.

### Generické návrhy
generic
Konstanty (při simulaci a syntéze konstantní)
Kapitálkami, první "C_..."

Deklarace:
```VHDL
entity RAM is
generic(
	data_width : integer := 64;
	addr_width : integer := 12;
	Taa : time := 50; 
	Toe : time := 40); 
port(
	oeb, wrb, csb : in std_logic;
	data : inout std_logic_vector(data_width-1 downto 0);
	addr : in std_logic_vector(addr_width-1 downto 0));
end RAM;
```

Výchozí instance:
```VHDL
RAM1 : RAM 
port map(
	oeb => oeb, 
	wrb => wrb, 
	csb => csb,
	data => data,
	addr => addr 
);
```

Úprava za pomoci genericity
```VHDL
RAM2 : RAM 
generic map(
	data_width => 32,
	addr_width => 20,
	Taa => 30 ns,
	Toe => 35 ns)
port map(
	oeb => oeb, wrb => wrb, csb => csb,
	data => data ,
	addr => addr );
```

### Porty
název : (in/out) typ (rozsah)


## Architecture
Popis vnitřního chování obvodu. 
- deklarační část (např. definice signálů)
- příkazová část (uzavřeno do begin - end)

Typy návrh:
1. Strukturální
   Popisujeme kombinaci logických hradel kódem.
2. Behaviorální
   Popisuje obvod dle jeho chování. Míra abstrakce nad jednotlivými hradly.

Své vlastní knihovny potřebuje každá architektura. 
Jedna entita může mít více architektur. 
Když IO piny nepřidáme do constrain. Syntéza nám je nepřipojí. 

dráty
signal nazev : typ (rozsah)


## Aggregate
Slučování vektorů: &
```VHDL
architecture example of assignment_vec is 	
	Signal y1,y2,y3 : STD_LOGIC_VECTOR (3 downto 0);
	Signal b,c: STD_LOGIC;
	signal max : std_logic_vector(3 downto 0) := ('0', others => '1');
	signal vec2 : std_logic_vector(3 downto 0) := ('0', 'X', others => '1');
	
	begin
		y1 <= (b,c,b,c);	--	() značí operátor aggregate
		y2 <= b&c&b&c; 	    -- 	& operátor sloučení
		Y3 <= y1&y2;
	end
end architecture example; 
```

```VHDL
signal B_BIT : bit;
signal BYTE : bit_vector (7 downto 0);
...
BYTE <= (7 => '1', 5 downto 1 => '1', 6 => B_BIT, others => '0');
```

## When
```VHDL
b <= "1000" when a = "00" else 
	 "0100" when a = "01" else 
	 "0010" when a = "10" else 
	 "0001" when a = "11";
```

## Process
Citlivostní seznam na všechny relevantní parametry.
`process(all)`

```VHDL
-- decoder
process(sel)
begin
	dec <= (others => '0');
	dec(to_integer(unsigned(sel))) <= '1';
end
```

v = dec and d;
q = or v;

q <= d(to_indeger(unsigned(sel)));

### Bloky if-else
![[priority encoder]]

### Case
![[7-seg_decoder]]

## Generate
![[AND of N inputs]]