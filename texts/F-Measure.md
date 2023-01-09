#MVD 
# F-Measure
Kombinace Precision (P) a Recall (R).

**Precision** = Podíl navrácených výsledků, které jsou relevantní
**Recall** = Podíl relevantních dokumentů, které jsou navráceny

$𝑃𝑟𝑒𝑐𝑖𝑠𝑖𝑜𝑛 = \frac{𝑎}{𝑎 + c}$
$𝑅𝑒𝑐𝑎𝑙𝑙 = \frac{𝑎} {𝑎 + b}$

| Dokument | Navrácený | Nenavrácený |
| --- | --- | --- |
|Relevantní | a | b |
|Nerelevantní | c | d |

![# F-score](https://upload.wikimedia.org/wikipedia/commons/thumb/2/26/Precisionrecall.svg/422px-Precisionrecall.svg.png)

Ideální stav -> Recall = Precision = 1

## F-1 score
$$𝐹1 = \frac{2𝑃𝑅} {𝑃 + R}$$
