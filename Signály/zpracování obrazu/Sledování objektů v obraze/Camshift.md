# Camshift

1. Výběr sledované barevné oblasti -> obraz I(x, y), převod do HUE
2. Výpočet histogramu ze sledované oblasti -> hist
3. První video snímek:
	1. F(y, x) -> převod do Hue: H(y, x) -> přepočet: $P(y, x) = hist[h(y, x)]$
	2. výpočet těžiště + oblast zájmu (ROI)
4. Další video snímky: 
	1. Výpočet jen z oblast zájmu (ROI) v předchozím snímku

```mermaid
flowchart TD
    B(["Výběr sledované barevné oblasti<br>obraz I(x, y), převod do HUE"])
    B --> C["Výpočet histogramu<br>ze sledované oblasti (hist)"]
    C --> D1

    subgraph First [První video snímek]
        direction TB
        D1["Převod do Hue:<br> F(y, x) ->  H(y, x)"]
        D1 --> D2["Přepočet: <br> P(y, x) = hist[h(y, x)]"]
        D2 --> D3["Výpočet těžiště<br>+ oblast zájmu (ROI)"]
    end
    
    subgraph Next [Další video snímky]
        direction TB
        D3 --> E1
        E1[Výpočet pouze z ROI<br>v předchozím snímku]
        E1 --> Last{Je to <br>poslední snímek?}
        Last -- Ne --> E1
    end
    
    Last -- Ano --> END[Konec]
```