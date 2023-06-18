#ML
# Lineární klasifikace v rámci nelineárních metod

1. Metoda zapojení vyšších mocnin příznaků. Lineární klasifikace probíhá v prostoru o vyšším počtu dimenzí, nové dimenze jsou dány vyššími mocninami.
2. Kernelové transformace. Lineární klasifikace probíhá v (nelineárně) transformovaném prostoru s vyšší dimenzí.
3. Neuronové sítě (sériové zapojení lin. klasifikátorů). Lineární klasifikace probíhá postupně v každé vrstvě.

## Umělé neuronové sítě
Podle uspořádání neuronů a jejich vzájemného propojení existuje celá řada typů umělých neuronových sítí, 3 hlavní jsou: 
- Konvoluční - Generátory příznaků, pro vícerozměrné signály.
- Sítě typu vícevrstvý perceptron = Multi-Layer Perceptron (MLP). Základní typ pro klasifikaci, budeme se jimi dále zabývat. Obsahuje paralelní a sériová spojení neuronů.
- Rekurentní - Nejobecnější typy, obsahuje navíc zpětnou vazbu.

### Aktivační funkce
- [[Sigmoid|sigmoida]]
- [[ReLU|ReLU]]

### Zpětná propagace
[[Zpětná propagace]]