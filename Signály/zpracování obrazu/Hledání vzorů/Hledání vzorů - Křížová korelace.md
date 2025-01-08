# Křížová korelace
- [[Autokorelace]]
## Jednoduché řešení
```Python
for y in range(0, výška_obr): 
	for x in range(0, šířka_obr): 
		okno = img[y-vel:y+vel, x-vel:x+vel] 
		podobnost[y, x] = korelace(okno, vzor)
```

> [!missing] Nevýhody
>- Velmi náročné na výkon,
>- Najde jen pokud je stejná orientace a velikost jako u vzoru.


> [!done] Výhody
>- Jednoduché řešení 

## Složitější řešení
```Python
for vel in mozne_velikosti: 
	for rot in mozne_rotace: 
		vzor_upraveny = transformuj(vzor, vel, rot) 
		for y in range(0, výška_obr): 
			for x in range(0, šířka_obr): 
				okno = img[y-vel:y+vel, x-vel:x+vel] 
				podobnost[y, x] = korelace(okno, vzor)
```

> [!missing] Nevýhody
>- Extrémně náročné na výkon

> [!done] Výhody
>- Stále programátorsky jednoduché řešení 
>- Najde i různé orientace a velikosti než u vzoru.
