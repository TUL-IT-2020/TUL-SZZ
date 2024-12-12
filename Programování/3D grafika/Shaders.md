# Shaders
## Shader Use HOWTO
1) Create shader
Allocate handle for each shader.
2) Specify shader
Pass shader source code as a string.
3) Compile shader
Driver really does compilation, checking syntax etc. Result is a binary 
object, that must be linked into a program. DO check compilation return 
code and compiler log!
4) Create program object
Compiled shaders will be linked into that.
5) Attach compiled shaders to the program object
Attach already compiled binary shader objects using handles.
6) Link all attached shaders to the final program
That means, that you can use single compiled shader in many different 
programs = shared libraries. DO check linker return code and linker log!!
7) Enable linked program
Since now the program will be used

### Programově
0) GLuint VS_h, FS_h, prog_h;
1) VS_h = glCreateShader(GL_VERTEX_SHADER);
FS_h = glCreateShader(GL_FRAGMENT_SHADER);
2) glShaderSource(VS_h, 1, &VS_string, NULL);
glShaderSource(FS_h, 1, &FS_string, NULL);
3) glCompileShader(VS_h);
glCompileShader(FS_h);
4) prog_h = glCreateProgram();
5) glAttachShader(prog_h, VS_h);
glAttachShader(prog_h, FS_h);
6) glLinkProgram(prog_h);
7) glUseProgram(prog_h);
8) ( glDeleteShader(), glDeleteProgram())

## Příklady Schaderů
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

## Programujeme Sadery

shortening, enlarging
```C
vec4 color_rgba;
vec3 color_rgb = vec3(color_rgba);
vec4 my_rgba = vec4( vec3(r,g,b), alpha);
```

### Vector items swizzle
three possibilities: 
- .xyzw, 
- .rgba, 
- .stpq
```C
vec4 v4;
v4.rgba //same as v4
v4.rgb //result is vec3
v4.b //result is scalar float
v4.xy //result is vec2
v4.xgba //error, items not from same set
v4.arrr //result is vec4, items can repeat or change order
```

### GLSL Type Modifiers
●
„in“
● Input to a shader stage
● Usually internally as vec4 → group scalars together
●
„smooth in“ = „in“ = varying, default
– variable for data transfer into fragment shader, only float 
(+vector, matrix)
– in FS automatically interpolated in polygon including 
perspective
eg.: in vec3 lightVec;
●
„flat in“
– Non-interpolated input into FS
●
„out“
● Output from a shader to next pipeline stage

●
„uniform“
● set as a parameter by CPU application
● constant in whole primitive and all shaders
eg.: uniform bool lightsOn;
●
„const“
● constant value
●
„buffer“
● Data accessible by shader and CPU
●
„shared“
● Compute shaders, data shared in workgrou

### Accessing uniforms
get location of the variable in the compiled source 
GLint location = glGetUniformLocation( GLuint prog, char * varName)
- set value to location
```C
void glUniform{1|2|3|4}{f|i|ui}(GLint location, TYPE value1, TYPE value2, … )
void glUniform{1|2|3|4}{f|i|ui}v(GLint location, GLsizei cnt, TYPE *values)
void glUniformMatrix{2|3|4|2x3|…}fv(GLint location, GLsizei cnt,
GLboolean transpose, const float * values)
```


Shader:
```C
#version 430 core
out vec4 color; 
uniform vec4 myrgba;
void main( void ) {
	color = myrgba;
}
```

Program zapisující hodnotu do uniformní proměnné `myrgba`:
```C
// C++ program
int main() {
	// …
	glm::vec4 rgba = ...;
	// …
	while (!glfwWindowShouldClose(window)) {
		// …
		glUseProgram(prog_ID);
		GLint h = glGetUniformLocation(prog_ID, “myrgba“);
		glUniform4fv(h, 1, glm::value_ptr(rgba));
		// …
	}
}
``` 
