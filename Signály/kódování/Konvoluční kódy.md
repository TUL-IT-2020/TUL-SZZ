# Konvoluční kódy
Základem je posuvný registr.
Př. 3,1

![[Convolutional_encoder_non-recursive.png]]

Zpráva: 011010

| Posuvný registr | Zakódováno |
| --------------- | ---------- |
| 0 0 0           | 000        |
| 1 0 0           | 110        |
| 1 1 0             | 011       |
| 0 1 1             | 001        | 

Na straně příjemce 
Na začátku: m_0 = m_1 = 0
První slovo bude buď $000$ nebo $101$

Pojmy: Rekurzivní / nerekurzivní
Má zpětnou vazbu?

Systematické / nesystematické

