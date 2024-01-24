
# Převody KA <-> RG <-> RV
- RV - [[RV - regulární výrazy|Regulární výraz]]
- RG - [[Gramatika]]
- KA - [[Automaty]]

![[převody.png]]
## Příklad
#příklad 
Ukázka různých forem popisu téhož regulárního jazyka L.

RJ: L = {abn ; n ≥ 0} 

RV: α = ab* L = \[α\] 

RG: G = ({S, B}, {a, b}, P, S), kde P: 
S → aB 
B → bB | ε 

KA: A = ({S, B}, {a, b}, δ, S, {B}), kde δ:

## Převod NKA na RV
Již dříve jsme si ukazovali, jak převést RV na NKA. Nyní bychom si ukázali opačný algoritmus – převod NKA na RV (metodou eliminace stavů). 
1. Nejprve převedeme NKA, příp. DKA na ZNKA (NKA nebo DKA může mít hrany ohodnocené pouze symboly vstupní abecedy, ZNKA může v přechodech obsahovat jak ε-přechody, tak i regulární výrazy). 
2. Odstraníme jeden (libovolný) stav (různý od počátečního a koncového stavu) a následně správně pozměníme přechodové funkce tak, abychom získali ekvivalentní automat (viz dále). 
3. Bod 2 opakujeme, dokud nezbydou jen dva stavy – počáteční a koncový. Mezi nimi povede hrana ohodnocená příslušným RV.

## Převod NKA na ZNKA
1. Vytvoříme nový počáteční stav $q_s$ a vytvoříme ε-přechod do původního počátečního stavu. 
2. Vytvoříme nový koncový stav $q_f$ a ze všech původních koncových stavů povedeme ε-přechody do stavu $q_f$. Z původních koncových stavů uděláme normální stavy. 
3. Pokud někde existuje vícenásobný přechod (tj. pokud se ze stavu $q_1$ dostaneme do stavu $q_2$ např. přes symbol 0 i přes symbol 1), tak tato pravidla sloučíme do jednoho regulárního výrazu a všechny původní symboly spojíme operátorem sjednocení. 
4. Pokud v KA chybí nějaký přechod, který by tam měl dle definice být, vytvoříme ho a označíme ho regulárním výrazem ∅ (tím nezměníme přijímaný jazyk, protože se takový přechod nikdy neprovede).

## Převod RG na KA 
Ke každé regulární gramatice G = (N, T, P, S) existuje konečný automat A = (Q, Σ, δ, q0, F) takový, že L(G) = L(A). Automat A se vytváří podle následujících pravidel: 
- Stavy Q automatu A se ztotožní s neterminálními symboly N gramatiky G. Ke stavům automatu A se přidá ještě stav K takový, že tento stav neodpovídá žádnému neterminálnímu symbolu v gramatice G, tj. Q = N ∪ {K}, K ≠ N. 
- Počáteční stav q0 je shodný s počátečním symbolem S gramatiky G. 
- Koncové stavy F jsou určeny takto: 
  F = {S, K}, když (S → ε) ∈ P, 
  F = {K}, když (S → ε) ∉ P, 
  (je-li v pravidlech S → ε, pak označíme počáteční stav S také jako koncový, jinak je koncový pouze stav K).
- Abeceda Σ bude shodná s terminálními symboly T, tj. Σ = T. 
- Přechodová funkce δ se vytváří podle následujících pravidel: δ(B, a) = C, pokud (B → aC) ∈ P, δ(B, a) = K ∧ K ∈ F, pokud (B → a) ∈ P, δ(K, ⁎) = ∅, tj. q0 ∈ F, pokud (S → ε) ∈ P, kde a ∈ T a B,C,S ∈ N. Terminální symboly v pravidlech představují přechody mezi stavy. Máme-li pravidlo typu B → a (z neterminálu na terminál), přejdeme do nového (koncového) stavu K. Máme-li pravidlo B → ε, pak označíme stav B jako koncový nebo z něj vedeme ε-přechod do koncového stavu K.

## Převod KA na RG
Pro každý konečný automat A = (Q, Σ, δ, q0, F) existuje regulární gramatika G = (N, T, P, S) taková, že L(A) = L(G). Gramatika se tvoří podle následujících pravidel: 
- Neterminální symboly gramatiky G budou stavy automatu A, tj. N = Q. 
- Množina terminálních symbolů gramatiky G bude abeceda automatu A, tj. T = Σ. 
- Počáteční symbol gramatiky G bude počáteční stav automatu A, tj. S = q0.
- Přepisovací pravidla gramatiky pak budou mít následující tvar: 
B → aC ∈ P, když δ(B, a) = C, 
B → a ∈ P, když δ(B, a) = K ∧ K ∈ F, 
S → ε ∈ P, když q0 ∈ F, kde a ∈ Σ a B,C,K ∈ Q. 
Pokud odchozí hrana vede do nekoncového stavu, generuje se jedno pravidlo. Pokud odchozí hrana vede do koncového stavu, generují se dvě pravidla. Pokud je počáteční stav současně koncový, gramatika generuje prázdný řetězec

## Převod RG na RV
Metoda regulárních rovnic 
Vyjdeme z pravidel gramatiky a sestavíme z nich regulární rovnice (místo „→“ píšeme „=“ a místo „|“ píšeme „+“). S rovnicemi pracujeme podobně jako s algebraickými rovnicemi s určitými rozdíly (součin představuje zřetězení, které není komutativní). 
Vzniklou soustavu rovnic vyřešíme pro proměnnou, která odpovídá počátečnímu neterminálu (S). 
Ke každé regulární gramatice existuje ekvivalentní regulární gramatika, která má pravidla pouze následujících typů: X → aY nebo X → Y nebo X → ε, kde X,Y ∈ N ∧ a ∈ T 
Cyklické závislosti neterminálů v rovnicích nahrazujeme regulárními výrazy: 
X = a.X + b = a*.b X ∈ N, a,b ∈ T 
X = X.a + b = b.a* X ∈ N, a,b ∈ T 