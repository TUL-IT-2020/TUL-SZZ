## Dynamic Host Configuration Protocol - #DHCP

je síťový protokol, který umožňuje automatickou přidělování IP adres a dalších síťových konfigurací zařízením v počítačové síti. DHCP hraje klíčovou roli ve správě IP adres a minimalizuje ruční konfiguraci na každém zařízení v síti.

### Principy a Funkce DHCP:

- poskytuje vše pro automatickou konfiguraci sítě:
	- IP adresu
	- masku podsítě
	- implicitní cestu (default route)
	- adresu lokálního DNS serveru
	- případné další parametry...
- základem DHCP server(y)

### Postup Funkce DHCP:

1. **Discover (Objev):**
    - Klient vysílá broadcast zprávu (DHCP Discover) do sítě, hledá DHCP server.
2. **Offer (Nabídka):**
    - DHCP server odpovídá broadcast zprávou (DHCP Offer), nabízí IP adresu a další konfigurační informace.
3. **Request (Žádost):**
    - Klient vybírá nabídku a posílá zprávu (DHCP Request) o potvrzení použití dané nabídky.
4. **Acknowledgment (Potvrzení):**
    - DHCP server potvrzuje vybranou nabídku pomocí broadcast zprávy (DHCP Acknowledgment). Klient tím získává přidělenou IP adresu a další konfigurační informace.

### DHCP a Bezpečnost:

DHCP je náchylný na potenciální hrozby, jako jsou neoprávněné DHCP servery nebo útoky typu "DHCP Spoofing." Pro zvýšení bezpečnosti se mohou používat různé mechanismy, jako jsou DHCP snooping nebo statická konfigurace na zařízeních, která nevyžadují dynamickou konfiguraci.