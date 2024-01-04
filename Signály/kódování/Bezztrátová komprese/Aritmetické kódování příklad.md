#příklad
# Příklady

## Příklad 1.

Je dána zdrojová abeceda A,B,C,D. 
Pravděpodobnosti výskytu jednotlivých znaků jsou: p(A) = 0.4, p(B) = 0.3, p(C) = 0.2 a p(D) = 0.1.  
Zakódujte zprávu ADCB aritmetickým kódováním.  

Jaká je minimální a maximální délka zprávy než bude dosaženo strojové přesnosti typu float (IEE754, 32-bit)?

### Řešení

Interval (0.3912, 0.3936)  
Minimální délka 7 znaků (samá 'D') - dosáhneme délky intervalů okolo 10^-7, což je strojová přesnost 32-bitového float-u.  
Maximální délka 17 znaků (samá 'A') - 0.4^17 = 1.72*10^-7

## Příklad 2.

Je dána zdrojová abeceda A,B,C,D,E. 
Pravděpodobnosti výskytu jednotlivých znaků jsou: p(A) =  p(B) = p(C) = p(D) = p(E) = 0.2. 

Aritmetickým kódováním byla zakódována zpráva o délce čtyři znaky. Zpráva po zakódování je číslo 0.385.  
Jaká je nezakódovaná zpráva?

### Řešení

BEDA

