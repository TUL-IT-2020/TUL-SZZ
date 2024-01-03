# Asymetrické systémy
Základ matematické operace, které je obtížné otočit. 

Příklad: RSA násobené/faktorizace
$p_1, p_2$ jsou prvočísla
$p_1 * p_2 = k$ - snadné, $O(n^{1,6})$

Určit však z $k$ čísla $p_1$ a $p_2$ je obtížné $O(e^n)$.
![[AES_1.jpg]]
Prakticky: dvojice klíčů
![[AES_2.jpg]]
Alice a Bob se snaží komunikovat.
Každý z nich má dvojic klíčů soukromý a veřejný. Tyto klíče jsou matematicky provázané, ale ze znalosti jednoho (veřejného) je těžké určit ten druhý (soukromý). (odvození veřejného klíče bývá jednoduché)

privátní klíč: $p_1, p_2$
veřejný klíč: $k$

Co se zašifruje jedním klíčem z dvojice, rozšifruje se **POUZE** druhým.

![[public-key.png]]
idea-instructions.com

Alice posílá zprávu Bobovi, čím šifruje?
- $A_s$ - lze rozšifrovat $A_v$
- $A_v$ - lze rozšifrovat $A_s$
- $B_s$ - lze rozšifrovat $B_v$
- $B_v$ - lze rozšifrovat $B_s$

=> zprávu šifrujeme **veřejným klíčem** protistrany !

Problém: výkon, při obdobné bezpečnosti jsou Asymetrické šifry asi $10^4 - 10^5*$ pomalejší než asymetrické šifry.

Nejsou tedy vhodné pro velké objemy dat. Lze tedy použít pouze pro malé objemy dat. Používáme ji jako bezpečný kanál pro výměnu klíčů symetrických šifer.

## Autentizace
Alice zašifruje zprávu $A_s$. 
=> rozšifruje pouze $A_v$
=> Tuto zprávu mohla zašifrovat pouze Alice, je to zpráva od ní a nemohla být změněna. 

Pokud chceme posílat velké sobory, tak můžeme podepisovat jen jejich [[Hashovací funkce|hashe]].

Problém 2: Pravdivost veřejného klíče -> řeší certifikáty