# ISA (Instruction set architecture)

Rozhraní mezi programem a hardware. Vlastnosti výpočetního systému viděné z pohledu programátora.
## Vlastnosti ISA
Kódování instrukcí (binární, # operandů)
Nakládání s operandy (přímé vs. nepřímé adresování, akumulátor vs. registry)
Podporované operace (+|-|\*|/|^|…)
Nakládání s výsledkem (where to place result)

> [!example] Větvení programu:
>- Podmínky (flags, predikce)
>- Volání podprogramů (zásobník, registrová okna)
>- Interrupt (priorita, počet)

# Dělení architektur dle ISA

Postupně historicky od nejjednodušší po nejsložitější.

## Střadačově orientovaná ISA
![[Střadačově orientovaná ISA]]

## Zásobníkově orientovaná ISA
![[Zásobníkově orientovaná ISA]]

## General Purpose Register ISA
![[General Purpose Register ISA]]