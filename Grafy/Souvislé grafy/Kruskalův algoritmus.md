> [!info] Kruskalův algoritmus  
Slouží k nalezení **minimální kostry grafu (Minimum Spanning Tree, MST)** v **ohodnoceném neorientovaném grafu**.

> [!tip] Intuice jednou větou:  
„Beru nejlevnější hrany, ale nikdy nesmím vytvořit cyklus.“

Postup (základní algoritmus):
1. Seřaď všechny hrany podle váhy od nejmenší po největší
2. Začni s grafem, kde jsou jen vrcholy (žádné hrany)
3. Postupně přidávej hrany:
    - vezmi nejlevnější ještě nepoužitou hranu
    - pokud **nevytvoří cyklus**, přidej ji
    - pokud by cyklus vytvořila, přeskoč ji
4. Konec, jakmile máš |V| − 1 hran