# Syntax
> [!warning] Je více verzí jazyka VHDL!
>- VHDL
>- VHDL 2008 (ten hezčí)
## Operátory výrazů
logické			{and, or, nand, nor, xor, xnor, not}
relační			{=, /=, <, >, =>, >=}
posuv			{sll, srl, sla, sra, rol, ror}
aritmetické			{+, -, \*, /, mod, rem}
slučování polí 		{&}
další			{\*\*, abs}	

## Entity
Popis vstupů a výstupů černé skříňky.
```VHDL
entity entity_name is
	[generic ({id : type [:= expression];)};]
	[port ({id : [in|out|inout|buffer] [:= expression];)};]
end entity [entity name];
```
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

### Datové objekty
```VHDL
CONSTANT jméno_konstanty : datový_typ := hodnota ;
VARIABLE jméno_proměnné  : datový_typ [ := hodnota ] ;
SIGNAL   jméno_signálu   : datový_typ [ := hodnota ] ;
```

## Architecture
Popis vnitřního chování obvodu. 
- deklarační část (např. definice signálů)
- příkazová část (uzavřeno do begin - end)

```VHDL
architecture architecture_name of entity_name is
	[declaration & definition part]
begin
	[parallel commands]
end architecture [architecture name]
```

Typy návrh:
1. RTL
2. Strukturální
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

## Paralelní příkazy
> [!warning]
Příkazy v těle architektury se vykonávají souběžně

>[!info] Vykonání příkazu trvá nulovou dobu
Simulační delta cyklus

Přiřazení:
- Nepodmíněné, 
- podmíněné, 
- výběrové přiřazení

Strukturní:
- Generující příkaz
- Instance komponenty

Umožňující sekvenční zpracování:
- Process

Simulační:
- Assert, 
- Report

### Přiřazení
![[WHDL - Přiřazení]]
## Process
### Syntaxe deklarace procesu
```VHDL
[name] : PROCESS [(clock, reset)] --seznam citlivých proměnných
	-- deklarace procesu
	VARIABLE [var_name] : [type];
BEGIN
	-- příkazy procesu
END PROCESS [name];
```

> [!tip]
> proměnné deklarované uvnitř procesu si zachovávají svoji hodnotu při dalším průchodu procesem (na rozdíl od funkcí a procedur, kde se vždy inicializují)

### Citlivostní seznam hodnot
Uvádí, na kterých signálech je sledována změna a případně spustí proces. Proto se zde uvádí jen hodiny a asynchronní signály.

Standardní případy:
- clock,
- set/reset.

> [!note] 
> `process(all)` - Citlivostní seznam na všechny relevantní parametry.


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

Syntaxe:
```VHDL
IF podmínka1 THEN 
	{sekvence_příkazů1}
[ELSIF podmínka2 THEN {sekvence_příkazů2}]
[ELSE {sekvence_příkazů}]
END IF;
```

> [!note]
> Lze používat pouze uvnitř procesu (sekvenční příkaz);

> [!warning]
> Má charakter prioritního přiřazení => může vést na složitější obvodové zapojení (volit raději CASE – WHEN);

![[priority encoder]]

### Case
![[7-seg_decoder]]

## Generate
HW struktury mají nějaký vzorec

Generuje kód dle poskytnutého schéma
- Booleovská podmínka
- Schéma for (řídící proměnná má charakter konstanty)

Nemá sekvenční charakter
- Algoritmický popis struktury

### If - vygeneruj / nevygeneruj
```VHDL
label: if condition generate
    [declaration part (signals, procedures, functions)
begin]
     concurrent_expressions;
end generate [label];
```

### For - udělej n\*krát
```VHDL
label: for control_variable in range generate
    [declaration part (signals, procedures, functions)
begin]
	concurrent_expressions; 
end generate [label];
```


![[AND of N inputs]]
