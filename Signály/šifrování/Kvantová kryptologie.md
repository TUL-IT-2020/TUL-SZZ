# Kvantová kryptologie
## Kryptoanalýza
Jednou prolomí RSA.

Pracuje se na kvantově odolných šifry.

## Kryptografie
V Praze je zprovozněná první kvantově zabezpečená linka.
Mohla by být neprolomitelná.

- bit = foton

Informace je uložená v polarizaci fotonu.
Tedy v jaké rovině kmitají.
![[polarization.png]]Polarizaci značíme jako: $+$ vs $\times$ 
![[Polarized-photons-and-corresponding-bit-values-IV-Quantum-cryptography-possibilities-of.png]]
### Kvantová výměna klíčů po optickém kanálu
![[kvantová komunikace.png]]
#### Anča

| schéma | 1   | 0   |
| ------ | --- | --- |
| $+$    | \|  | -   |
| $\times$       | \\    |  /   |

Dvě stejně dlouhé náhodné sekvence.
1. informace: 
	- `001101`
2. použité schéma: 
	- `+x++xx`
Odeslaná zpráva: `-/||/\`

#### Bobeš
Má dva detektory:  $+$ a $\times$ 
Má však jen jeden pokus na každý foton. 

Tak je měří náhodně vybraným detektorem. 

Bobeš vybere náhodně: `++x++x`
Detekováno: `-??|?\`

Ale `?` nelze rozpoznat zda je užitečná informace.

Po detekci zprávy si A a B sdělí schémata. To mohou udělat nezabezpečeným kanálem. 
=> Oba vědí které bity B naměřil správně a které spatně. 
Špatně naměřené se zahodí. Správné lze použít jako klíč pro šifrování. 
Vzniká jejich společné tajemství. 
Následně provedou kontrolu náhodných bitů. Když je statisticky půlka bitů špatně, tak jejich zpráva byla odposlechnuta. 

#### Eva (padouch)
Měří náhodně vybranými detektory. Půlku informací změní, takže Bobeš dostane polovinu informací špatně. Tím se Eva nevyhnutelně prozradí. 