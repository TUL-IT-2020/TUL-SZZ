# Vyhodnocování klasifikace

> [!example] Pojmy
>- Accuracy - Kolik klasifikací bylo pravdivých 
>- Precision - Kolik pozitivních klasifikací bylo pravdivých 
>- Recall - Jak dobře klasifikátor dokáže najít všechny pozitivní předpovědi. 
>- F1 – Jak je klasifikátor efektivní. Precision nebo Recall -> 0, F1 -> 0

- **Accuracy** je intuitivní a jednoduchá, ale může být zavádějící při nevyvážených datech (např. když je 90 % dat negativních, klasifikátor, který vždy predikuje negativní, dosáhne 90% accuracy, ale ignoruje pozitivní případy).
- **Precision** je klíčová, když jsou důležité FP chyby (např. spam filtry).
- **Recall** je důležitý, když jsou klíčové FN chyby (např. při detekci nemocí).
- **F1-score** poskytuje rovnováhu mezi Precision a Recall.

## Matice záměn (Confusion matrix – CM)
Tabulka s přehledem výsledků klasifikace pro všechny třídy. Na diagonále jsou správné případy => součet je čitatel Acc. Mimo diagonálu chyby.

Pro výpočet těchto metrik potřebujeme 4 základní hodnoty z matice záměny:
- **TP**: True Positive (Správně klasifikované pozitivní případy)
- **FP**: False Positive (Falešně klasifikované pozitivní případy)
- **TN**: True Negative (Správně klasifikované negativní případy)
- **FN**: False Negative (Falešně klasifikované negativní případy)

![[CM.webp]]

### **Accuracy (Přesnost)**  
Podíl správných klasifikací vůči celkovému počtu vzorků:

$$
\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}
$$

### **Precision (Přesnost pro pozitivní třídu)**  
Podíl správně klasifikovaných pozitivních vzorků vůči všem vzorkům klasifikovaným jako pozitivní:

$$
\text{Precision} = \frac{TP}{TP + FP}
$$

### **Recall (Citlivost, True Positive Rate)**  
Podíl správně klasifikovaných pozitivních vzorků vůči všem skutečně pozitivním vzorkům:

$$
\text{Recall} = \frac{TP}{TP + FN}
$$

### **F1-score**  
Harmonický průměr mezi **Precision** a **Recall**. F1-score zohledňuje jak přesnost, tak citlivost a je vhodné, když je důležité vyvážit FP a FN:

$$
\text{F1} = 2 \cdot \frac{\text{Precision} \cdot \text{Recall}}{\text{Precision} + \text{Recall}}
$$
![[F-Measure]]