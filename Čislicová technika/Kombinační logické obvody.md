# Kombinační logické obvody
- **Definice:** Kombinační logické obvody jsou elektronické obvody, kde výstupní signál závisí pouze na aktuálním stavu vstupů a nezávisí na předchozích stavech nebo vstupních sekvencích.
- **Funkce:** Tyto obvody provádějí kombinaci vstupních signálů podle logických operací, jako jsou AND, OR, a NOT, k vytvoření výstupního signálu.
![[Kombinační obvod.png]]
Kombinační obvod - výstupní proměnná je jednoznačně určena proměnnou vstupní

| Funkce          | Anglický název | ČSN | Anglo-Americká konvence | Pravdivostní tabulka                                                                                                           |
| --------------- | -------------- | --- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Logický součet  | OR             | ≥1  |                         | \| a \| b \| y \|<br>\|---\|---\|---\|<br>\| 0 \| 0 \| 0 \|<br>\| 0 \| 1 \| 1 \|<br>\| 1 \| 0 \| 1 \|<br>\| 1 \| 1 \| 1 \|<br> |
| Logický součin  | AND            | &   |                         | \| a \| b \| y \|<br>\|---\|---\|---\|<br>\| 0 \| 0 \| 0 \|<br>\| 0 \| 1 \| 0 \|<br>\| 1 \| 0 \| 0 \|<br>\| 1 \| 1 \| 1 \|<br> |
| Negace          | NOT            | 1   |                         | \| a \| y \|<br>\|---\|---\|<br>\| 0 \| 1 \|<br>\| 1 \| 0 \|<br>                                                               |
| Negovaný součet | NOR            | ≥1  |                         | \| a \| b \| y \|<br>\|---\|---\|---\|<br>\| 0 \| 0 \| 1 \|<br>\| 0 \| 1 \| 0 \|<br>\| 1 \| 0 \| 0 \|<br>\| 1 \| 1 \| 0 \|<br> |
| Negovaný součin | NAND           | &º  |                         | \| a \| b \| y \|<br>\|---\|---\|---\|<br>\| 0 \| 0 \| 1 \|<br>\| 0 \| 1 \| 1 \|<br>\| 1 \| 0 \| 1 \|<br>\| 1 \| 1 \| 0 \|<br> |
| Nonekvivalence  | XOR            | =1  |                         | \| a \| b \| y \|<br>\|---\|---\|---\|<br>\| 0 \| 0 \| 0 \|<br>\| 0 \| 1 \| 1 \|<br>\| 1 \| 0 \| 1 \|<br>\| 1 \| 1 \| 0 \|<br> |
| Ekvivalence     | XNOR           | =1º |                         | \| a \| b \| y \|<br>\|---\|---\|---\|<br>\| 0 \| 0 \| 1 \|<br>\| 0 \| 1 \| 0 \|<br>\| 1 \| 0 \| 0 \|<br>\| 1 \| 1 \| 1 \|<br> |
# Boolova algebra - Logické axiomy

| Základní axiom | Součet                                    | Součin                                        |
| -------------- | ----------------------------------------- | --------------------------------------------- |
| Komutativita   | $a + b = b + a$                           | $a \cdot b = b \cdot a$                       |
| Asociativita   | $a + (b + c) = (a + b) + c$               | $a \cdot (b \cdot c) = (a \cdot b) \cdot c$   |
| Distributivita | $a + (b \cdot c) = (a + b) \cdot (a + c)$ | $a \cdot (b + c) = (a \cdot b) + (a \cdot c)$ |
| Neutralita     | $a + 0 = a$                               | $a \cdot 1 = a$                               |
| Komplement     | $a + a' = 1$                              | $a \cdot a' = 0$                              |
| Agresivita     | $a \cdot 0 = 0$                           | $a + 1 = 1$                                   |
| Idempotence    | $a + a = a$                               | $a \cdot a = a$                               |
| Absorbce       | $a + a \cdot b = a$                       | $a \cdot (a + b) = a$                         |

### Odvozené Logické Zákony

| Pravidlo           | Příklad                               |
|--------------------|----------------------------------------|
| Dvojí negace       | $a = \overline{\overline{a}}$          |
| Absorpce negace    | $a + a \cdot b = a + b$                |
|                    | $a \cdot (a + b) = a \cdot b$          |
| De Morgan          | $\overline{a + b} = \overline{a} \cdot \overline{b}$ |
|                    | $\overline{a \cdot b} = \overline{a} + \overline{b}$ |
| Consensus          | $a \cdot b + ac + b \cdot c = ab + ac$|
|                    | $(a + b)(a + c)(b + c) = (a + b) + (a + c)$ |
