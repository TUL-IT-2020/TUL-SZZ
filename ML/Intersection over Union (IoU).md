# Intersection over Union (IoU)
**IoU** je běžná metrika používaná v počítačovém vidění, zejména v úlohách, jako je **detekce objektů** nebo **segmentace obrazu**, pro porovnání podobnosti mezi dvěma oblastmi: **predikovanou** a **skutečnou** (ground truth).

## Definice IoU:

IoU je podíl mezi:
- **Průnikem** $\text{Intersection}$: oblast, kde se predikovaná a skutečná oblast překrývají.
- **Sjednocením** $\text{Union}$: celková oblast zahrnující obě tyto oblasti.

$$
\text{IoU} = \frac{\text{Area of Intersection}}{\text{Area of Union}}
$$
## Vzorec:

$$
\text{IoU} = \frac{|A \cap B|}{|A \cup B|}
$$

Kde:
- $|A \cap B|$: Plocha průniku predikované a skutečné oblasti.
- $|A \cup B|$: Plocha sjednocení predikované a skutečné oblasti.  
Lze vypočítat jako:
$$
|A \cup B| = |A| + |B| - |A \cap B|
$$

## Význam IoU:
- **IoU = 1.0:** Dokonalé překrytí predikované a skutečné oblasti.
- **IoU = 0.0:** Predikovaná a skutečná oblast se vůbec nepřekrývají.
- Hodnoty mezi 0 a 1 ukazují míru přesnosti.
