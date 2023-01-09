#MVD 
# Model vektorového prostoru 
Označujeme jako VSM (Vector Space Model). Dokumenty i dotazy jsou reprezentovány pomocí vektorů.

bag-of-words:
„Metody vytěžování dat“ -> \[“Metody”, “vytěžování”, “dat”\] 
BoW = {“Metody”: 1, “vytěžování”: 1, “dat”: 1}

## příklad: 
q = „Metody vytěžování dat“ 
doc1 = „… využité metody …“ 
doc2 = „… metody vytěžování dat …“ 

Slovník V = {využité, metody, vytěžování, dat} 

q = (0, 1, 1, 1) 
doc1 = (1, 1, 0, 0) 
doc2 = (0, 1, 1, 1) 

sim(q, doc1) = 0×1 + 1×1 + 0 ×0 + 0×0 = 1 
sim(q, doc2) = 0 + 1 + 1 + 1 = 3