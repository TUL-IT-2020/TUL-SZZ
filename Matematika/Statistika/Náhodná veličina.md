# Náhodná veličina
S každým pokusem nebo hrou je spojena množina všech možných výsledků. Označme symbolem $\Omega$ množinu všech možných, navzájem se vylučujících výsledků. Libovolný možný výsledek, označme $\omega \in \Omega$, nazveme elementární jev, $\Omega$ pak nazveme základní pravděpodobnostní prostor.

## Definice
Náhodná veličina X je zobrazení 𝑋 ∶ Ω → 𝑅 takové, že pro každé 𝑥 ∈ 𝑅 platí
$$
X^{-1} ((-\infty,x)) = \{\omega \in \Omega | X(\omega) \leq x\} = [X \leq x] \subset \Omega 
$$
Neboli: Náhodná veličina X je reálná funkce definovaná na množině všech elementárních jevů (=pokusů experimentu), která každému jevu přiřadí reálné číslo. Množina čísel přiřazených elementárním jevům tvoří obor hodnot náhodné veličiny.

## PŘÍKLAD: Hod 6 stěnnou kostkou 
- Pokus = hod kostkou, elementární jev $\omega \in \Omega$ = {1, 2, 3, 4, 5, 6}. 𝑋 je rovna hodnotě napsané na vrchní stěně kostky po dopadu. Obor náhodné veličiny je také {1, 2, 3, 4, 5, 6}.
- Pokus = hod 2 kostkami, pak $\omega \in \Omega = \{(𝑖,𝑗) |𝑖 = 1, … 6; 𝑗 = 1, … 6; 𝑖 \leq 𝑗 \}$. 𝑋 je rovna součtu padlých hodnot. Obor náhodné veličiny je {2, 3, … , 12} , jelikož např. 𝑋(1,1) = 2.

[[Diskrétní náhodné veličiny]]
[[Hustota pravděpodobnosti#Absolutně spojité náhodné veličiny|Spojité náhodné veličiny]]
