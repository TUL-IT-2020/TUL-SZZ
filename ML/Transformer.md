#MVD 
# Transformer
Založeno na attention mechanismu. Vylepšení oproti RNN. 
Odstranění rekurencí => Paralelní zpracování vstupu (+positional encoding)
Encoder-Decoder architektura: 
Encoder
Obsahuje důležité self-attention vrstvy. Zpracovává vstupní informaci a jeho výstup obsahuje vektorovou reprezentaci vstupu. 
$$
Atention(Q,K,V) = Softmax\left( \frac{QK^T}{\sqrt{d_k}} \right)V
$$
- [[Softmax|Softmax()]]
- $Q$ - query
- $K$ - key
- $V$ - value
 
## Architektura modelu
![The-Transformer-model-architecture](https://upload.wikimedia.org/wikipedia/commons/8/8f/The-Transformer-model-architecture.png)
## Poziční enkoder
![Positional encoding](https://upload.wikimedia.org/wikipedia/commons/thumb/0/02/Positional_encoding.png/640px-Positional_encoding.png)
