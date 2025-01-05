# Obsluha periferií

## polling

Aktivní kontrola stavu periferie.

![[polling.jpg]]

Model obsluhy v nekonečné smyčce:
### A)
Kontrola periferie0→ akce0
Kontrola periferie1→ akce1
…

### B)
Kontrola periferie0, perfierie1..N
Dle stavu akce0, akce1…N

> [!question] K zamyšlení:
Využití CPU, priority, výpočty mimo obsluhu

## přerušení, výjimka

Kontrola periferie vyvolána událostí.

> [!example] Termíny
>- Exception – výjimka – událost uvnitř CPU
>- Interrupt – přerušení – žádost o obsluhu vyvolaná změnou stavu ext. signálu
>- Handler – obsluha – obsluhující funkce
>- Interrupt vector table - tabulka vektorů přerušení – adresy funkcí obsluh
>- Callback – kólbek – uživatelská funkce
>- IRQ – Interrupt Request – Identifikátor přerušení

CPU – podpora zpravidla 1-2 signály přerušení

```mermaid
flowchart TD
    A([HW: Skok na předem danou adresu])
    B[Exception handler]
    C["Zdroj výjimky? 
    –> zavolání Interrupt handler"]

    A --> B
    B --> C
    C --> D

    subgraph Find_Interrupt_handler [Find Interrupt Handler]
        direction TB
        D[Rozhodnutí o zdroji přerušení]        
        E["Skok na specifickou obsluhu přerušení 
        (Tabulka vektorů přerušení)"]
        F[Obsluha události, smazání příznaku]
        J[Smazání příznaku v CPU, návrat]
        
        D --> E
        E --> F

        subgraph Interrupt_handler [Interrupt Handler]
            direction TB
			H[Smazání příznaku ve zdroji]
			return_h[návrat]
            call_back[Vykonání uživatelské funkce]
			
            F --> G{Uživatelský callback?}
            G -->|Ano| call_back
            G -->|Ne| I[Smazání příznaku přerušení v řadiči]

            call_back --> H
            H --> return_h
	        I --> return_h
        end

        return_h --> J
    end
```

> [!question] K zamyšlení:
Přerušení v přerušení, moc přerušení