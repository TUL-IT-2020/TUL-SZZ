# Spojení filtrů
> [!example]
>- Sériové,
>- Paralelní, 
>- Zpětná vazba.

## Sériové
```mermaid
graph LR
    A((Input)) 
    A -->|x| B[h_1]
    B -->|z| C[h_2]
    C -->|y| D
    D((Output))
```

$$
y[n] = h_1 * h_2 * x
$$

$$
Y(e^{j\omega}) = H_1(e^{j\omega})H_2(e^{j\omega})X(e^{j\omega})
$$

$$
H(e^{j\omega}) = H_1(e^{j\omega})H_2(e^{j\omega})
$$

Frekvenční komponenta musí ležet v propustném pásmu obou filtrů.
## Paralelní
```mermaid
graph LR
    A((Input)) 
    A -->|x| B[h_1]
    A -->|x| C[h_2]
    D((+))
    B -->|z_1| D
    C -->|z_2| D
    D -->|y| Out
    Out((Output))
```

$$
y[n] = h_1 * x + h_2 * x
$$

$$
Y(e^{j\omega}) = H_1(e^{j\omega})X(e^{j\omega}) + H_2(e^{j\omega})X(e^{j\omega})
$$

$$
H(e^{j\omega}) = H_1(e^{j\omega}) + H_2(e^{j\omega})
$$

Frekvenční komponenta musí ležet v propustném pásmu alespoň jednoho z filtrů.

## Zpětná vazba
```mermaid
graph LR
    In((Input)) 
    Out((Output))
    Sum((+))
    Filter_1((h_1))
    Filter_2((h_2))

    In -->|x| Sum
    Sum -->|x+z| Filter_1
    Filter_1 -->|y| Out
    Filter_1 -->|y| Filter_2
    Filter_2 -->|z| Sum
```
Používá se u řízení.

$$
H(e^{j\omega}) = \frac{H_1(e^{j\omega})}{1 - H_1(e^{j\omega})*H_2(e^{j\omega})}
$$