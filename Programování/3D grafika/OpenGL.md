# OpenGL

OpenGL EXTension
Popisuje vlastnosti grafické karty.

## Dokumentace:
docs.gl
## GLEW
OpenGL Extension Wrangler
Knihovna pro povolování rozšíření na grafice.

```Cpp
// pro x-window na Linuxu
#include "xglew.h"
```

## GLSL

> [!warning] GPU počítá vše ve **floatech**
> Všechny ostatní typy jsou pomalé!

> [!warning] GLSL nemá pointery!
> Pole musím mít pevně danou velikost.

Problém s pointery řeší předávání parametrů do funkce:
- `in`
- `out`
- `inout`

> [!note] VRAM paměť přiřazené jednotlivým výpočetním jádrům grafické karty je značně omezená
> Proměné definovat nejmenším možném kontextu jejich platnosti!

> [!warning] Shadery podporují sloupcové matice místo řádkových
> - ručně transponovat všechny matice?
> - Používejte: `GLM::MAT4`

