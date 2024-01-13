# Slovníkové metody - LZ
Statický slovník - moc nefunguje.
Dynamický slovník:
- LZ77
- LZ78
- LZW

## LZ 77
Dvě okna, průběžně se posouvají.
Větší okno, menší okno.
Úsek v malém okně nahradíme odkazem do většího okna, kde hledáme výskyty.

| Velké okno                  | Malé okno      |
| --------------------------- | -------------- |
| She sells sea shells on     | the sea shore. |
| S[he se]lls sea shells on | "he se"        |
| She sells se[a sh]ells on | "a sh"         |

## LZ 78 
LZ78 je slovníková kompresní metoda, kterou v roce 1978 publikovali Abraham Lempel a Ja'akov Ziv. Metoda je nástupcem LZ77, na rozdíl od které ale nemá pohyblivé okno, ale jen vyhledávací okno a slovník. Slovník obsahuje fragmenty nekomprimovaného souboru. Každý řetězec ve slovníku má svůj index (identifikátor). Kompresor hledá ve vyhledávacím okně nejdelší řetězec obsažený ve slovníku. Čte tedy vstupní tok symbol po symbolu až do okamžiku, kdy načte symbol, který způsobí neshodu. Značky produkované touto kompresní metodou mají tvar (index, symbol), kde index je ukazatel na řetězec ve slovníku a symbol je následující symbol, který způsobil neshodu. Každá taková značka udává nový řetězec, který se umístí do slovníku. Slovník je na počátku komprese prázdný. Dekodér buduje svůj slovník ve shodě s kodérem.

Variantou LZ78 je LZW.

## LZW (LZW84)
![[LZW (Lempel-Ziv-Welchův algoritmus)]]