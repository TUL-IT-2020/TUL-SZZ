# Protokol IP (Internet Protocol)
Je datový protokol na síťové vrstvě a tvoří základní protokol dnešnímu internetu. Data se posílají po blocích (datagramy, pakety), putují sítí nezávisle, není zajištěna spolehlivost doručení (to se řeší o vrstvu výš např. TCP). Každé rozhraní má svoji IP adresu a v každém datagramu je IP příjemce i odesílatele. Na základě těchto adres probíhá směrování. 

## Verze IP: 
### IPv4 
Každý datagram má hlavičku (Id, celk. délka, TTL, adresa odesílatele a příjemce) adresa 32 bitů, zápis v desítkové soustavě (192.168.56.101), rozdělení na privátní a veřejné adresy (privátní se nesměrují), obsahuje NET ID (část adresy pro sítě) a HOST ID (část adresy konkrétního rozhraní).

### IPv6 
128 bitů dlouhé adresy, zápis v šestnáctkové soustavě výhody:
-  dostatečně bohatý adresní prostor
- podpora služeb se zaručenou kvalitou
- design odpovídající vysokorychlostním sítím
- bezpečnostní mechanismy přímo v IP
- podpora mobilních zařízení
- automatická konfigurace
- kooperace s IPv4 a co nejhladší přechod ze stávajícího protokolu na nový