#MVD 
# Word2Vec 
Využívá neuronovou síť s jednou skrytou vrstvou. Dva možné algoritmy: 
- Skip-gram 
	- Založen na predikce slov v okolí daného slova 
- Continuous bag of words (CBOW)
	- Založen na predikci daného slova pomocí okolních slov

Několik trénovacích metod:
- [[Softmax|Softmax]]
- Hierarchical Softmax
- Negative sampling

## Skip-gram 
Maximalizujme pravděpodobnost výskytu okolních slov
### Příklad:
*Petr dnes šel do kina*
Při šířce okolí 2 maximalizujeme pro slovo šel pravděpodobnost:
𝑃(𝑃𝑒𝑡𝑟│š𝑒𝑙,𝑾)+𝑃(𝑑𝑛𝑒𝑠│š𝑒𝑙,𝑾)+𝑃(𝑑𝑜│š𝑒𝑙,𝑾)+𝑃(kina | šel,𝑾)

Model přitom odpovídá neuronové síti s parametry $𝑾$. Parametry $𝑾$ jsou matice vah skryté a výstupní vrstvy ($𝑾1$ a $𝑾2$ ).
Matice $𝑾1$ pak představuje matici embeddingů pro všechna slova ze slovníku. Její rozměry (počet neuronů skryté vrstvy) určují dimenzi nalezeného prostoru. Nalezený prostor má požadované vlastnosti.

## Nevýhody popsaného způsobu trénování 
Výše popsané trénování má nevýhody: 
1. Výpočet softmaxu pro velké slovníku je náročný (exponenciála) 
2. Pro dané cílové slovo se významně mění hodnoty pouze omezeného počtu vah, ostatní váhy se přesto aktualizují nadbytečně o zanedbatelně malé hodnoty 

Příklad:
Před trénovaný Google model má 3 miliony slov. Při trénování je pouze 1 slovo ze 3M cílové. Většinu času aktualizujeme váhy, které nesouvisí s cílovým slovem o malé hodnoty (viz 2.)
Řešení ve výběru trénovací metody: 
- **Hierarchical softmax** -> Složitější na implementaci 
- **Negative sampling** -> Dosahuje lepších výsledků
