#uzo
# Morfologické operace

## Na binárním obraze
https://docs.opencv.org/4.x/d9/d61/tutorial_py_morphological_ops.html

### Dilatace 
Dilatace skládá body dvou množin pomocí vektorového součtu, $X \oplus B$ je bodovou množinou všech možných vektorových součtů pro dvojice pixelů, pro jeden z $X$ a jeden z $B$.
$$
X \oplus B = \{ p \in \varepsilon^2 : p = x + b \};\; x \subseteq X; b \subseteq B
$$

![[dilatace.PNG]]
Samostatně slouží k zaplnění malých děr, úzkých zálivů a pro další složitější operace, zvětšuje objekty, pro zachování původních rozměrů ji kombinujeme s erozí.

![binDilatace](https://user-images.githubusercontent.com/46580540/170106837-7fc97ad2-8ed6-483b-9577-a63de5b398a8.png)


### Eroze 
Duální operace k dilataci, dilatace ani eroze nejsou invertovatelné, skládá dvě množiny:
$$
X \ominus B = \{ p \in \varepsilon^2 : p + b \subseteq X\}  \; pro \; každé \; b \subseteq B
$$
Pro každý bod obrazu $p$ se ověřuje, zda výsledek $p + b$ leží v $X$.

![[eroze.PNG]]
Zjednodušení struktury objektů, složitější objekt se rozdělí na několik jednodušších.

![binEroze](https://user-images.githubusercontent.com/46580540/170105973-87ab9f34-987d-4bc4-8903-92e8f8db2247.png)

### Uzavření
- Uzavření = dilatace následovaná erozí
- Uzavření spojí objekty, které jsou blízko u sebe, zaplní malé díry a vyhladí obrys tím, že zaplní úzké zálivy

![binUzavreni](https://user-images.githubusercontent.com/46580540/170107325-6085ce8b-36b4-449b-b77f-c8a8ba6d42a7.png)


### Otevření
- Otevření = eroze následovaná dilatací
-  Otevření oddělí objekty spojené úzkou šíjí a tak zjednoduší strukturu objektů

![binOtevreni](https://user-images.githubusercontent.com/46580540/170106417-800cfab0-498e-41e5-a29b-5b76fe778ab5.png)
