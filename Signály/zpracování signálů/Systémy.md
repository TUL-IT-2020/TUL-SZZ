# Systémy

> [!attention] Funkce vs Operátor
>- **Funkce** zobrazuje číslo na číslo
>- **Operátor** zobrazuje funkci na funkci

## Vlastnosti systémů
> [!example] Vlastnosti systémů
> - Bez paměti - neuchovává žádné předchozí stavy
>- Kauzální - nedívá se do budoucnosti
>- Stabilita  - BIBO - Vstup i výstup jsou amplitudově omezené. 
>- Časově invariantní - V čase se funkce filtru nemění.

### Klasifikace systémů podrobněji
![[Klasifikace systémů]]
## LTI (Linear Time-Invariant)

Jsou systémy s pěknými vlastnostmi:
- Lineární
- Časově nezávislé

Díky tomu na nich platí:
- Aditivita - Sčítání signálů
- Homogenita - Násobení konstantou

> [!warning] Důležité:
> Nejdůležitější charakteristikou LTI systému je jeho impulzní odezva, protože konvolucí vstupu s impulzní odezvou můžeme získat výstup LTI systému.
### Filtry
![[Filtrace]]

