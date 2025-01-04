# Vykreslovaná objektů podle hloubky
## S průhlednými objekty
Průhledné objekty musí být předem zatříděné podle vzdálenosti od kamery.

Nastavit faktory (někde v init, obvykle už se nemění)
`glBlendFunc( GL_SRC_ALPHA, GL_ONE_MINUS_SRC_ALPHA )`

Každý snímek:
- Rozdělíme objekty na průhledné a neprůhledné.

### 1. Neprůhledná tělesa:
Vykreslit všechna neprůhledná tělesa v libovolném pořadí jako normálně podle z-bufferu.

1. vypneme alfa míchání,
2. vykreslíme neprůhledné.
### 2. Průhledná tělesa:
1. Povolit mísení:
`glEnable( GL_BLEND )`
2. Zablokovat paměť hloubky pouze pro čtení:
`glDepthMask( GL_FALSE )`

> [!note] Proč?
> Těleso je průhledné, neblokovat vykreslování když je něco za ním, 
chceme to vidět. Přepneme Z-buffer pouze pro čtení (aby se nezapisovalo pro z-bufferu, jinak by se z průhledných objektů nevykreslovala jejich zadní strana).

3. Zablokovat zahazování zadních stěn polygonu (vidíme skrz)
`glDisable( GL_CULL_FACE )`
4. Vykreslit průhledná tělesa (odzadu dopředu, nebo pomocí OIT)
5. Zablokovat mísení, povolit test hloubky, povolit zahazování
```C
glDisable( GL_BLEND )
glDepthMask( GL_TRUE )
glEnable( GL_CULL_FACE )
```

## Vykreslení vzdálených objektů v mlze

- Lineární
$$
f = \frac{end- z}{end - start}
$$

- Exponenciální
$$
f = e^{-(density*z)}
$$
- Exponenciální kvadratická
$$
f = e^{-(density*z)^2}
$$

Shader:
```C
#version 460 core

// black, non-transparent = night:
uniform vec4 fog_color = vec4(vec3(0.0f), 1.0f); 
uniform float near = 0.1f; 
uniform float far = 20.0f;

float log_depth(float depth, float steepness = 0.5f, float offset = 15.0f) {
	float linear_depth = (2.0 * near * far) / (far + near - (depth * 2.0 - 1.0) * (far - near));
	return (1 / (1 + exp(-steepness * (linear_depth - offset))));
}

void main() {
	vec4 color = ... lights ... textures ...
	
	// outputs final color
	float depth = log_depth(gl_FragCoord.z);
	//linear interpolation
	FragColor = mix(color, vec4(fog_color, 1.0), depth); 
}
```

> [!warning] Pozadí nemá barvu mlhy?
`gl_clear color` - nastavte na barvu mlhy.

