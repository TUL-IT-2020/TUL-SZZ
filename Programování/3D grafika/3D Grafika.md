# 3D Grafika
> [!info] Qualcom grafiky:
ADRENO -> RADEON

## Zkratky
- DSA - Direct State Access
- VAO - Vertex Array Object
- GLSL - OpenGL Shading Language
- HLSL - High Level Shading Language

## Základní pojmy
![[Základní pojmy počítačové grafiky|Základní pojmy]]

## Ovladače
- DirectX
- OpenGL
	- multiplatformní
- Vulcan
	- multiplatformní
	- složité

> [!info] Ovladače grafické karty kompilují naše shadery: 
>- GLSL
>- HSLS
>- Vulcan
>- ...
## OpenGL
![[OpenGL]]

## GPU pipeline zpracování obrazu

![[graphics-pipeline.png]]

```mermaid
graph TD
	V[Vertex] 
	R[Raster]
	F[Fragment]

	V --> R
	R --> F
```
