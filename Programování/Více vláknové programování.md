# Více vláknové programování

```C
std::atomic<T>
std::swap
```

atomic - jednoduchá proměnná s zajištěným atomickým přístupem (sama zamaká a odemyká)

Alokuje se tolikrát kolik je vláken:
```C
thread_local int[100] data;
```

Dynamicky lze měnit velikost poolu vláken.

> [!tip] 
> Když nepoužívám std::mutex tak jen dobře.

Lepší je:
`std::scoped_lock`
Zamknuto v celém těle závorek. Při destrukci se sám vždy odemkne.

