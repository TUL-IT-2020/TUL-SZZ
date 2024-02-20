#NAT 

- Network Address Translation, RFC 3022
- mezi dvěma částmi sítě
- mění IP adresy a porty v procházejících IP datagramech
- typicky: lokální síť s neveřejnými adresami připojená NATem do Internetu – celá síť je adresována jedinou veřejnou IP adresou
- běžně implementováno např. v ADSL modemech
- - záznam v konverzní tabulce se vytváří, když počítač „zevnitř“ odesílá paket „ven“
#### problémy NATu:
- komunikaci nutno navazovat zevnitř – dokud není záznam v tabulce, jsou vnitřní počítače nedosažitelné (nemají veřejné adresy)
- narušuje přímou komunikaci (videokonference) – nutno přes prostředníka s veřejnou adresou
- omezení dostupnosti vnitřní sítě má pozitivní dopady na bezpečnost