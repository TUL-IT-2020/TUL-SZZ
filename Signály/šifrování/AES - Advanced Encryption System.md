# AES - Advanced Encryption System
blok má délku 128b (16B).
Klíč se "opotřebí" po zašifrování $2^{63}$ bloků

> [!tip] Délka klíče:
>- 128b - "OK"
>- 196b - bezpečné
>- 256b - "kvantově odolné"

> [!warning] Útok: 
> Pouze hrubá síla

Výhodou tohoto systému je výkon, dnešní CPU mají hardwarovou podporu. 

>[!info] Výkon: 
>- 15 GB/s (s HW podporou)
>- 11 MB/s (s HW bez podpory @200MHz)

> [!warning] Problém: 
> Distribuce klíče. To musí proběhnout po bezpečném kanálu.