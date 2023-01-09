#MVD 
# Algoritmus LBG (Linde, Buzo, Gray) 
Na rozdíl od [[K-means|K-means]] řeší též nalezení čísla 𝐾. Dvojnásobně iterační procedura (pro 𝐾, i pro určení centroidů) 

## Algoritmus
1. Inicializace: Nastav 𝐾 = 1. Najdi centroid. 
2. Rozdělení (𝐾=2𝐾): Pro každou dosavadní skupinu urči dva nové počáteční centroidy. 
3. Nalezení nových centroidů: S celou TrM a s číslem 𝐾 proveď K-means alg. Urči hodnotu kriteriální funkce. 
4. Ukončení: Je-li dosaženo cílové číslo 𝐾 nebo se hodnota kriteriální funkce již významně nemění, skonči, jinak zpět na krok 2. 

Pozn: V kroku 2 je také možné rozdělit pouze největší shluk. Pak 𝐾=𝐾+1