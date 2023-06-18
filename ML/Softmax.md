#MVD
#ML
# Softmax
$$
\hat 𝑦_𝑐 = 𝑆𝑂𝐹𝑇𝑀𝐴𝑋(𝒖) = \frac{𝑒^{𝑢_𝑐} }{ \sum^𝐶_{𝑑=1} 𝑒^{𝑢_d}}
$$

Součet všech výstupů je roven 1.
Pravděpodobností. 
Není potřeba počítat při klasifikaci, pouze při trénování.
```
SMAX(u) = (e^ui)/sum(e^u)
```