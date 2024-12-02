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


## Shaders
Soubor: `basic_core.vert`
```C
#version 460 core
in vec3 aPos;

// mat4(1.0) - indentita
uniform mat4 uM_m = mat4(1.0); // model
uniform mat4 uV_m = mat4(1.0); // viue
uniform mat4 uP_m = mat4(1.0); // projection

void main()
{
    // Outputs the positions/coordinates of all vertices
    gl_Position = uP_m * uV_m * uM_m * vec4(aPos, 1.0f);
}
```

Soubor: `basic.frag`
```C
#version 460 core
in vec3 color; // input from vertex stage of graphics pipeline, automatically interpolated
out vec4 FragColor; // output color of current fragment: MUST be written

void main()
{
    // copy RGB color, add Alpha=1.0 (not transparent)
    FragColor = vec4(color, 1.0f); 
}
```