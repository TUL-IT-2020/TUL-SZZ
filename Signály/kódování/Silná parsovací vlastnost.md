# SPP - strong parsing property
Přesto, že zdrojovou zprávu tvoří bitový řetězec, je zřejmé, že zdrojovou abecedu nemůže tvořit množina {0,1}, ale musí ji tvořit vhodně vybraná množina binárních slov, která umožní prakticky libovolný zdrojový bitový řetězec zapsat jako zřetězení binárních slov ze zdrojové abecedy. Výše uvedený požadavek na zdrojovou abecedu lze formalizovat následovně: 

Množina binárních slov $𝑆 = \{𝒔_1, … , 𝒔_𝑘\}$, má silnou parsovací vlastnost (strong parsing property, zkráceně SPP), jestliže libovolný binární řetězec $𝒘 \in \{0,1\}^∗$ lze zapsat jediným způsobem ve tvaru:
$$
𝒘 = 𝒔_{𝑖_1} … 𝒔_{𝑖_𝑛} 𝒗,
$$kde:
- $𝒔_{𝑖_𝑗} \in 𝑆$, 
- 𝒗 ∈ {0,1}∗ 
	- $v$ takové, že nemá jako prefix žádné ze slov $𝒔1, … , 𝒔_𝑘$ 
	- a navíc platí $𝑙(𝒗) < max\{𝑙(𝒔_𝑖)|𝑖 = 1,2, … , 𝑘\}$. 
- 𝑙 označuje délku slova

Poměrně snadno lze ukázat, že množina binárních slov $𝑆 = \{𝒔_1, … , 𝒔_𝑘\}$ má silnou parsovací vlastnost právě tehdy, jestliže jsou splněny následující podmínky: 
1) Žádné slovo z množiny $𝑆$ není prefixem jiného slova z množiny $𝑆$. 
2) V Kraftově nerovnosti platí rovnost, tj. $∑^k_{𝑖=1} 2^{−𝑙(𝒔_𝑖)} = 1$.