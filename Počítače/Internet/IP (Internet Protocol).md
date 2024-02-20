#IP
Je datový protokol na síťové vrstvě a tvoří základní protokol dnešnímu internetu. Data se posílají po blocích (datagramy, pakety), putují sítí nezávisle, není zajištěna spolehlivost doručení (to se řeší o vrstvu výš např. TCP). Každé rozhraní má svoji IP adresu a v každém datagramu je IP příjemce i odesílatele. Na základě těchto adres probíhá směrování. 

## Verze IP: 
### IPv4 
Každý datagram má hlavičku (Id, celk. délka, TTL, adresa odesílatele a příjemce) adresa 32 bitů, zápis v desítkové soustavě (192.168.56.101), rozdělení na privátní a veřejné adresy (privátní se nesměrují), obsahuje NET ID (část adresy pro sítě) a HOST ID (část adresy konkrétního rozhraní).

#### Privátní IP adresy
Jsou neveřejné rozsahy adres, které jsou rezervovány pro použití v soukromých sítích a nejsou směrovány přímo na veřejný internet. Hlavní důvod použití je rozšíření privátního adresního rozsahu:

1. 10.0.0.0/8 až 10.255.255.255:
   Tento rozsah je známý jako třída A privátních adres a zahrnuje veškeré adresy začínající číslem 10. Tento rozsah nabízí obrovskou kapacitu pro privátní sítě a je často používán ve velkých organizacích.

2. 172.16.0.0/16 až 172.31.255.255:
   Tento rozsah je známý jako třída B privátních adres a obsahuje adresy začínající čísly od 172.16 až 172.31. Tento rozsah poskytuje střední kapacitu pro privátní sítě a je často využíván ve středně velkých sítích.

3. 192.168.0.0/16 až 192.168.255.255:
   Tento rozsah je známý jako třída C privátních adres a zahrnuje adresy začínající čísly od 192.168.0 až 192.168.255. Tento rozsah nabízí menší kapacitu pro privátní sítě a je často používán v domácích nebo malých podnikových sítích.

### IPv6 
128 bitů dlouhé adresy, zápis v šestnáctkové soustavě výhody:
- dostatečně bohatý adresní prostor
- podpora služeb se zaručenou kvalitou
- design odpovídající vysokorychlostním sítím
- bezpečnostní mechanismy přímo v IP
- podpora mobilních zařízení
- automatická konfigurace
- kooperace s IPv4 a co nejhladší přechod ze stávajícího protokolu na nový