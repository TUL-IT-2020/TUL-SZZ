# UDP (User Datagram Protocol)
Transportní protokol, není záruka ani o potvrzení ani o doručení datagramu, používá se pro komunikaci typu otázka - odpověď (DNS, DHCP), rychlejší než [[TCP (Transmisson Control Protocol)|TCP]]. Jeho bezstavovost se využívá u serverů, které obsluhují mnoho klientů a nevadí, že se občas datagram ztratí (VoIP). 

Hlavička UDP: 
- zdrojový port, 
- cílový port, 
- délka, 
- kontrolní součet.