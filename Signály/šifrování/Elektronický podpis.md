# Elektronický podpis

Samostudium:
- [Peterka - Jak na digitální kontinuitu, Lupa.cz](https://www.lupa.cz/serialy/jak-na-digitalni-kontinuitu/)
- Kechlibar.net - Tak ten mail zašifruj hlupáku
- [[bajecny_svet_elektronickeho_podpisu_cznic.pdf|Peterka - Báječný svět elektronického podpisu]]

Elektronický podpis je otisk dokumentu vypočtený kryptografickou [[Hashovací funkce|hashovací funkcí]] a následně zašifrovaný [[Asymetrické systémy|soukromým klíčem]]. 

Jak zaručit pravost veřejného klíče?
## Certifikáty
V reálném životě: občanka, pas, řidičák, ISIC, ...
- je provázán s nositelem:
	- foto, 
	- jméno, 
	- otisky.
- unikátní číslo "ID"
- kdo průkaz vydal 
- doba platnosti
- obtížně padělatelný

### Digitálně
- Provazuje veřejný klíč s konkrétní osobou. 
- Vydávají certifikační autority.
- Doba platnosti.
- Kryptografie

| Certifikát                              |
| --------------------------------------- |
| Veřejný klíč                            |
| Ověření: (tento veřejný klíč patří ...) |
| Digitální podpis C.A.                   | 

#### Certifikační autorita
Revokace = zneplatnění certifikátu

## Diffie - Hellmanova funkce
![[Diffie - Hellmanova funkce]]

## Komunikace

### Anča píše Bolkovi
![[Asymetricke_2.jpg]]
Anča:
- zpráva.txt -> ZIP -> zprava.zip -> SHA -> otisk zprávy
- certifikát Anča
- certifikát Robert
- Jednorázový klíč

Otisk zprávy
Klíč A_s
Systémový čas
->
RSA
-> Elektronický podpis

El. podpis
Zprava.zip
Certifikát A.
Jednorázový klíč
->
AES
->
Zašifrovaná zpráva

Jednorázový klíč
Certifikát Robert
B_v
->
RSA
Zašifrovaný jednorázový klíč

Zašifrovaná zpráva
Zašifrovaný jednorázový klíč
->
Odešleme

### Bolek obdrží zprávu od Anči
![[Asymetricke_1.jpg]]
Bolek
- Certifikát Robert
- Zašifrovaný email 
	-> klíč
	-> zpráva + podpis + certifikát A.

Certifikát Alice musíme ověřit u certifikační autority
Certifikát Alice -> certifikační autorita -> Ano/Ne

klíč
B_s 
-> 
RSA-1
->
Jednorázový klíč

jednorázový klíč
zpráva + podpis + certifikát A.
->
AES-1
->
zpráva.zip -> SHA -> otisk zprávy
elektronický podpis
Certifikát A.

elektronický podpis
Certifikát A. - A_v
->
RSA -1
->
Otisk původní zprávy

Integrita
Otisk původní zprávy ?= otisk zprávy

Zpráva.zip -> ZIP-1 -> Zpráva

> Dítě nesmíme nechat v kufru!
> - Otto Severín

## Pojmy spojené s E.P.
1. El. Podpis - nemá (příliš) význam
2. Zaručený el. podpis - založen na certifikátu vydaném [[Elektronický podpis#Certifikační autorita|C.A.]]
3. Uznávaný el. podpis - založen na certifikátu vydaném akreditovanou [[Elektronický podpis#Certifikační autorita|C.A.]]

### Elektronický podpis 
Je vždy od osoby.

### Elektronická značka
Zaručený elektronický podpis. Založený na certifikátu organizace / stroje. Může být vytvářený automaticky. 

### Časové razítko
Druh zaručeného elektronického podpisu, který obsahuje zaručený údaj o datu vzniku. 

### Kvalifikované časové razítko
Vydané někým koho uznává zákon. 
