# TCP (Transmisson Control Protocol)
Transportní protokol, zaručuje spolehlivé potvrzení o doručení dat (pomocí sequence a acknowledge čísel), je spojový, kontrolním součtem ověřuje data, udržuje spojení. Je spolehlivý, ale právě kvůli režii spojení je pomalejší než [[UDP (User Datagram Protocol)|UDP]]. 

TCP handshake - 3 kroky
![[TCP.PNG]]

## Port 
Slouží k rozlišení komunikujících aplikací, počet je 2^16 192.168.56.101:12345 - jednoznačné určení IP adresy i komunikujícího portu na síti, některé porty jsou rezervované pro klasické protokoly (HTTP - 80).
