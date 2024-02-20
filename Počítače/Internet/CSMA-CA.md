#CSMA/CA

## Carrier Sense Multiple Access with Collision Avoidance
1. je-li médium volné po dobu DIFS, začne vysílat pokud protějšek nepotvrdí příjem, zahájí exp. čekání
2. je-li obsazeno, počká na uvolnění a zahájí exp. čekání
3. exponenciální čekání: po uplynutí DIFS začíná soutěžní
   okno – rozděleno na sloty; stanice náhodně vybere slot a pokud nikdo nezačne dříve,
   zahájí vysílání (jinak zpět na krok 2); při neúspěchu zdvojnásobí počet slotů
4. omezený počet pokusů

### Formát rámce
| řízení | trvání | adresa 1 | adresa 2 | adresa 3 | poř. | adresa 4 | data | CRC |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
- řízení: příznaky určující typ rámce (datový, řídicí, správní) a další parametry
- trvání: očekávaná doba přenosu následujícího rámce (nastavení NAV)
- adresy: odesilatel, příjemce a až dva AP (význam závisí na typu rámce)
- pořadí: umožňuje číslovat rámce
- CRC: kontrolní součet

### Bezpečnost
- dva okruhy problémů:
	- využití sítě neoprávněnými stanicemi
	- odposlech dat
- vstup do buňky:
	- autentizace – ověření, zda smí být vpuštěna
	- asociace – technické začlenění do buňky

### Autentizace
- **volný přístup**
	- implicitní nastavení nových AP
- **podle MAC adres**
	- obtížně se udržuje, snadno se falšuje
- **šifrování + heslo**
	- nejčastější, dostatečně bezpečné a jednoduché
- **IEEE 802.1X**
	- centrálně řízené, pro větší počty uživatelů

### IEEE 802.1X
- obecné pro lokální sítě (i pro Ethernet)
- **autentizuje uživatele, nikoli hardware** umožňuje vzájemnou autentizaci obou stran
- zpočátku provoz počítače blokován, umožněny jen pakety 802.1X, po úspěšné autentizaci se otevře
- na počítači nutný klient, tzv. suplikant; AP ověřuje proti autentizačnímu serveru protokolem RADIUS
- vychází z Extensible Authentication Protocol (EAP)

### IEEE 802.11i
- vylepšené zabezpečení, dva různé protokoly:
- **Temporal Integrity Key Protocol (TKIP)**
	- též WEP2, WPA
	- využívá čipy pro WEP, ale s individuálními a dočasnými klíči (každý rámec jiný) a delšími inicializačními vektory
- **Counter Mode with CBC-MAC Protocol (CCMP)**
	- silnější šifrovací algoritmy, vyžaduje jiný hardware
	- vychází z šifry Advanced Encryption Standard (AES)