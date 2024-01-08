# Euklidův algoritmus
Pro hledání největšího společného dělitele:
a, b ∈ N^+ ∧ a > b : 

$a = bq_0 + r1; 0 < r_1 < b$ 
$b = r_1q_1 + r2; 0 < r_2 < r_1$
$r_1 = r_2q_2 + r3; 0 < r_3 < r_2$ 
· · · 
$r_{n−2} = r_{n−1}q_{n−1} + r_n$ 
$r_{n−1} = r_nq_n$

Hledaným největším společným dělitelem je číslo $r_n$. Tím je poslední nenulový zbytek v algoritmu. 

Algoritmus se sestává z konečného počtu kroků (triviální důsledek nerovností uvedených napravo: 0 < rn < rn−1... < r1 < b) 

Zároveň platí: $NSD(a, b) = NSD(b, r_1) = NSD(r_1, r_2) = ... = NSD(r_{n−1}, r_n) = r_n$