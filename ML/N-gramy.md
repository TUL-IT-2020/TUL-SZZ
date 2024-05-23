#MVD 
# N-gramy 
> [!summary]
>Sekvence N slov. Využívané k základnímu modelování jazyka. Aplikace např. na slovech, písmenech nebo fonémech.

## Příklady:
Rozdělení na N-gramy řetězce: *Metody vytěžování dat* 
- Unigramy -> (Metody), (vytěžování), (dat) 
- Bigramy -> (Metody, vytěžování), (vytěžování, dat) 
- Trigramy -> (Metody, vytěžování, dat) 

Příklad výpočtu pravděpodobnosti bigramu: 

> `<s>` **Metody** vytěžování dat `<end>`
> `<s>` Aplikace metody Monte-Carlo `<end>`
> `<s>` **Metody** psychologie … `<end>`

Pravděpodobnost výskytu slova „metody“ na začátku věty: 
$$
𝑝(𝒎𝒆𝒕𝒐𝒅𝒚 | <s>) = \frac{𝑐(<𝑠> 𝑚𝑒𝑡𝑜𝑑𝑦)}{𝑐(<𝑠>)} = \frac{2}{3}
$$

