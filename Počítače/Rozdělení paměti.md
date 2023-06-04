# Rozložení paměti 

Operační paměť v procesoru lze z pohledu spuštěné aplikace rozdělit na:
-   `stack`: obsahuje lokální proměnné funkcí
-   `heap`: dynamicky alokované paměť
-   `data`: globální proměnné
-   `text`: obsahuje spuštěný program

![memory_layout](https://courses.engr.illinois.edu/cs225/fa2022/assets/notes/stack_heap_memory/memory_layout.png)

## Text
Začíná od adresy `0x00000000` (32b), roste směrem nahoru. Je zde uložený program. Při spuštění počítače se čítač programu nastaví na nulu a program se začne vykonávat z této adresy, tedy v sekci data. 

## Data
Je sekce ve kterém jsou uložené konstanty programu. Jejich adresa se v průběhu celého programu nemění, zůstávají na jednom místě a díky tomu je možné na ně přistupovat z libovolné části programu, i když se rámec kontextu na zásobníku volně přesouvá. 

## Halda
Halda je část operační paměti, kam se ukládají rozměrné datové struktury (pole, struktury, objekty), se kterými je následně pracováno v programu pomocí reference (v jazyce C ukazatel). Paměťový prostor zde je potřeba pro použití v programu alokovat (dynamická alokace). 

Při statické alokaci víme při překladu jak data (pole) budou velká, zatímco při dynamické alokaci (Název je přejat od slova dynamit, u toho taky nikdy nevíte jak velká ta díra bude dokud to nevybouchne.) není při překladu jasné kolik paměti se má vyhradit (vektory, přidání záznamu do spojového seznamu).

Když data uložená v alokovaném prostoru již nejsou potřeba, tak prostor musíme před dalším použitím uvolnit (dealokovat). Při častém vytvářením objektů a jejich uvolňování může dojít k problému fragmentaci paměti. To je stav, kdy mezi alokovanými objekty zbývá malý prostor, do kterého se již nová data nevejdou. 

## Zásobník
Zásobník (stack) začíná na nejvyšší adrese `0xFFFFFFFF` (32b) a roste ze shora dolů. Zásobník obsahuje jednotlivé rámce. Ukazatel na vrchol rámce se standardně ukládá do jednoho z registrů procesoru. Při volání funkce se vytvoří nový rámec o velikost potřebné pro argumenty a lokání proměnné dané funkce (hodnota v registru se aktualizuje). Když se z lokálního kontextu volá další funkce, tak rámec pokračuje v růstu jako krápník od shora dolů. Při návratu z funkce se bloky odmazávají a krápník ustupuje nahoru. Tento paměťový prostor bývá standardně pro aplikace omezen a tak se velké datové struktury alokují na haldu (heap). Nejkrajnějším omezením zásobníku může být hranice oblasti text ve které je uložen program, další zápis do zásobníku by vedl na to že by se přepsal spouštěný program a aplikace by již nemohla zaručit své správné vykonání, tento problém se při detekci běžně označuje za "stack overflow".

Složení rámce:
- Návratová adresa (na řádek ze kterého byla funkce volaná).
- Vstupní argumenty funkce.
- Lokální proměnné kontextu funkce.
![Stack](https://upload.wikimedia.org/wikipedia/commons/thumb/3/36/ProgramCallStack2.svg/404px-ProgramCallStack2.svg.png)

- https://courses.engr.illinois.edu/cs225/fa2022/resources/stack-heap/
- https://en.wikibooks.org/wiki/Memory_Management/Stacks_and_Heaps
- https://cs.wikipedia.org/wiki/Zásobník_(datová_struktura)