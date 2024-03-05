#ALD
# Vyhledávání

## Lineární vyhledávání
![[Lineární vyhledávání]]

## Binární vyhledávání
![[Binární vyhledávání]]

## Datové struktury optimalizované pro vyhledávání

### Binární vyhledávací strom (BST)
![[Binární vyhledávací strom (BST)]]

### Hashování
![[Hashovaní]]

## Prohledávání řetězců
Hledaní vzoru/patternu uvnitř textu. Dnes textové editory, vyhledávání na webu, zpracování obrazu, strukturní rozpoznávání. 

Základní pojmy:
- **Řetězec** S o velikosti m
- **Podřetězec** `S[i:j]` je část řetězce S mezi indexy i a j
- **Prefix** (předpona) S je podřetězec `S[0:i]`
- **Suffix** (přípona) S je podřetězec `S[i:m-1]`, kde i je libovolný index mezi 0 a m-1
Každé slovo je prefixem i sufixem sebe sama – takový prefix nazýváme nevlastní.

### Příklady algoritmů:
- [[Přirozené prohledávání]]
- [[KMP (Knouth-Morris-Pratt)]]
- [[Boyer-Moore]]
- [[Rabin-Karp]]