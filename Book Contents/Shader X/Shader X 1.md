# Part1: Introduction to Shader Programming
## Fundamentals of Vertex Shaders . . . . . . . . . . . . . . . . . . . . . . . . . . . 4
Wolfgang F. Engel
What You Need to Know/Equipment . . . . . . . . . . . . . . . . . . . . . . . . . 5
Vertex Shaders in the Pipeline . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 5
Why Use Vertex Shaders? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 7
Vertex Shader Tools . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 8
NVIDIA Effects Browser 2/3 . . . . . . . . . . . . . . . . . . . . . . . . . . 8
NVIDIA Shader Debugger . . . . . . . . . . . . . . . . . . . . . . . . . . . 9
Shader City . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 10
Vertex Shader Assembler. . . . . . . . . . . . . . . . . . . . . . . . . . . . 10
NVIDIA NVASM — Vertex and Pixel Shader Macro Assembler . . . . 10
Microsoft Vertex Shader Assembler . . . . . . . . . . . . . . . . . . . 11
Shader Studio . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 11
NVLink 2.x . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 12
NVIDIA Photoshop Plug-ins. . . . . . . . . . . . . . . . . . . . . . . . . . 13
Diffusion Cubemap Tool . . . . . . . . . . . . . . . . . . . . . . . . . . . . 14
DLL Detective with Direct3D Plug-in . . . . . . . . . . . . . . . . . . . . . 15
3D Studio Max 4.x/gmax 1.1. . . . . . . . . . . . . . . . . . . . . . . . . . 16
Vertex Shader Architecture . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
High-Level View of Vertex Shader Programming . . . . . . . . . . . . . . . . . . 18
Check for Vertex Shader Support . . . . . . . . . . . . . . . . . . . . . . . 19
Vertex Shader Declaration . . . . . . . . . . . . . . . . . . . . . . . . . . . 19
Set the Vertex Shader Constant Registers . . . . . . . . . . . . . . . . . . . 22
Write and Compile a Vertex Shader . . . . . . . . . . . . . . . . . . . . . . 22
Application Hints . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 26
Complex Instructions in the Vertex Shader. . . . . . . . . . . . . . . . 27
Putting It All Together . . . . . . . . . . . . . . . . . . . . . . . . . . 27
Swizzling and Masking . . . . . . . . . . . . . . . . . . . . . . . . . . 31
Guidelines for Writing Vertex Shaders . . . . . . . . . . . . . . . . . . 32
Compiling a Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . 33
Create a Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 34
Set a Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 34
Free Vertex Shader Resources . . . . . . . . . . . . . . . . . . . . . . . . . 35
Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 35
What Happens Next? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 35
iii
## Programming Vertex Shaders . . . . . . . . . . . . . . . . . . . . . . . . . . . . 38
Wolfgang F. Engel
RacorX . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 38
The Common Files Framework . . . . . . . . . . . . . . . . . . . . . . . . 40
Check for Vertex Shader Support. . . . . . . . . . . . . . . . . . . . . 42
Vertex Shader Declaration . . . . . . . . . . . . . . . . . . . . . . . . 42
Set the Vertex Shader Constant Registers . . . . . . . . . . . . . . . . 43
The Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . 43
Compile a Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . 45
Create a Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . 46
Set a Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . 47
Free Vertex Shader Resources . . . . . . . . . . . . . . . . . . . . . . 47
Non-Shader Specific Code . . . . . . . . . . . . . . . . . . . . . . . . 47
Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 49
RacorX2. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 49
Create a Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 51
Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 53
RacorX3. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 53
Vertex Shader Declaration . . . . . . . . . . . . . . . . . . . . . . . . . . . 54
Set the Vertex Shader Constant Registers . . . . . . . . . . . . . . . . . . . 54
The Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 55
Directional Light . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 57
Diffuse Reflection . . . . . . . . . . . . . . . . . . . . . . . . . . . . 57
Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 59
RacorX4. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 59
Vertex Shader Declaration . . . . . . . . . . . . . . . . . . . . . . . . . . . 59
Set the Vertex Shader Constants . . . . . . . . . . . . . . . . . . . . . . . . 60
The Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 61
Specular Reflection . . . . . . . . . . . . . . . . . . . . . . . . . . . . 62
Non-Shader Specific Code . . . . . . . . . . . . . . . . . . . . . . . . . . . 65
Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 66
RacorX5. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 66
Point Light Source . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 66
Light Attenuation for Point Lights . . . . . . . . . . . . . . . . . . . . . . . 66
Set the Vertex Shader Constants . . . . . . . . . . . . . . . . . . . . . . . . 67
The Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 68
Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 70
What Happens Next? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 70
## Fundamentals of Pixel Shaders . . . . . . . . . . . . . . . . . . . . . . . . . . . 72
Wolfgang F. Engel
Why Use Pixel Shaders? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 72
Pixel Shaders in the Pipeline . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 74
Pixel Shader Tools . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 79
Microsoft Pixel Shader Assembler. . . . . . . . . . . . . . . . . . . . . . . 79
MFC Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 80
iv Contents
Team LRNATI ShadeLab. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 80
Pixel Shader Architecture . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 81
Constant Registers (c0-c7) . . . . . . . . . . . . . . . . . . . . . . . . . . . 82
Output and Temporary Registers (ps.1.1-ps.1.3: r0+r1; ps.1.4: r0-r5) . . . . 82
Texture Registers (ps.1.1-ps.1.3: t0-t3; ps.1.4: t0-t5) . . . . . . . . . . . . . 82
Color Registers (ps.1.1-ps.1.4: v0+v1) . . . . . . . . . . . . . . . . . . . . 83
Range . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 83
High-Level View of Pixel Shader Programming . . . . . . . . . . . . . . . . . . 84
Check for Pixel Shader Support . . . . . . . . . . . . . . . . . . . . . . . . 84
Set Texture Operation Flags (D3DTSS_* flags). . . . . . . . . . . . . . . . 85
Set Texture (with SetTexture()) . . . . . . . . . . . . . . . . . . . . . . . . 86
Define Constants (with SetPixelShaderConstant()/def ) . . . . . . . . . . . 86
Pixel Shader Instructions . . . . . . . . . . . . . . . . . . . . . . . . . . . . 87
Texture Address Instructions . . . . . . . . . . . . . . . . . . . . . . . 88
Arithmetic Instructions . . . . . . . . . . . . . . . . . . . . . . . . . 101
Instruction Modifiers . . . . . . . . . . . . . . . . . . . . . . . . . . 110
Instruction Modifiers . . . . . . . . . . . . . . . . . . . . . . . . . . 116
Instruction Pairing . . . . . . . . . . . . . . . . . . . . . . . . . . . . 119
Assemble Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . 120
Create a Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 120
Set Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 121
Free Pixel Shader Resources . . . . . . . . . . . . . . . . . . . . . . . . . 121
Summary. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 121
What Happens Next? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 122
## Programming Pixel Shaders . . . . . . . . . . . . . . . . . . . . . . . . . . . . 125
Wolfgang F. Engel
RacorX6 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 125
Check for Pixel Shader Support . . . . . . . . . . . . . . . . . . . . . . . 126
Set Texture Operation Flags (with D3DTSS_* flags) . . . . . . . . . . . . 126
Set Texture (with SetTexture()) . . . . . . . . . . . . . . . . . . . . . . . . 127
Define Constants (with SetPixelShaderConstant()/def) . . . . . . . . . . . 127
Pixel Shader Instructions . . . . . . . . . . . . . . . . . . . . . . . . . . . 128
Per-Pixel Lighting . . . . . . . . . . . . . . . . . . . . . . . . . . . . 130
Assemble Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . 134
Create Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 134
Set Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 136
Free Pixel Shader Resources . . . . . . . . . . . . . . . . . . . . . . . . . 136
Non-Shader Specific Code . . . . . . . . . . . . . . . . . . . . . . . . . . 136
Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 136
RacorX7 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 137
Define Constants (with SetPixelShaderConstant()/def) . . . . . . . . . . . 137
Pixel Shader Instructions . . . . . . . . . . . . . . . . . . . . . . . . . . . 137
Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 140
RacorX8 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 140
Set Texture Operation Flags (with D3DTSS_* flags) . . . . . . . . . . . . 140
Contents v
Team LRNSet Texture (with SetTexture()) . . . . . . . . . . . . . . . . . . . . . . . . 140
Pixel Shader Instructions . . . . . . . . . . . . . . . . . . . . . . . . . . . 142
Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 143
RacorX9 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 144
Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 147
Further Reading . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 147
## Basic Shader Development with Shader Studio . . . . . . . . . . . . . . . . . . 149
John Schwab
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 149
What You Should Know . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 149
Installation. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 149
Directories . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 149
Coordinate Systems . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 150
Features . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 150
Limitations . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 151
Default Light . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 152
Controls . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 152
Create a Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 152
Step 1: Loading a Mesh . . . . . . . . . . . . . . . . . . . . . . . . . . . . 153
Step 2: Transformations. . . . . . . . . . . . . . . . . . . . . . . . . . . . 153
Step 3: Starting a Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . 154
Step 4: Editing Code . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 154
Step 5: Adding Some Color. . . . . . . . . . . . . . . . . . . . . . . . . . 155
Step 6: Saving Your Work . . . . . . . . . . . . . . . . . . . . . . . . . . 155
Step 7: Loading a Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . 156
Step 8: Settings . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 157
Step 9: Texture Control . . . . . . . . . . . . . . . . . . . . . . . . . . . . 157
Create a Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 159
Step 1: Configuration . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 159
Step 2: Writing a Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . 159
Shaders Reference. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 160
Workspace . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 160
Menu Layout . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 160
Files . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 161
Shaders Dialog . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 161
Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 162
Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 162
Declarations . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 163
Constant Properties Dialog . . . . . . . . . . . . . . . . . . . . . . . . . . 163
Materials Dialog. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 164
Textures Dialog . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 165
Browser . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 165
Transformations Dialog . . . . . . . . . . . . . . . . . . . . . . . . . . . . 165
Object . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 166
Light . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 166
vi Contents
Team LRNCamera. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 166
Statistics Dialog . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 167
Settings Dialog . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 167
State Methods . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 167
Camera Projection . . . . . . . . . . . . . . . . . . . . . . . . . . . . 168
Configure Dialog . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 168
Assets . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 169
Further Info . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 169
# Part2: Vertex Shader Tricks
## Vertex Decompression in a Shader . . . . . . . . . . . . . . . . . . . . . . . . 172
Dean Calver
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 172
Vertex Compression Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . 172
Vertex Shader Data Types. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 173
Compressed Vertex Stream Declaration Example . . . . . . . . . . . . . . . . . 174
Basic Compression . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 174
Quantization . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 174
Compression. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 174
Decompression . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 175
Practical Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . 175
Scaled Offset . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 175
Compression. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 175
Decompression . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 176
Practical Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . 176
Compression Transform. . . . . . . . . . . . . . . . . . . . . . . . . . . . 176
Compression. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 177
Decompression . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 178
Practical Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . 178
Optimizations . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 179
Practical Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . 180
Advanced Compression . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 180
Multiple Compression Transforms . . . . . . . . . . . . . . . . . . . . . . 180
Compression. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 181
Decompression . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 181
Practical Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . 181
Sliding Compression Transform . . . . . . . . . . . . . . . . . . . . . . . 182
Compression. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 182
Decompression . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 183
Displacement Maps and Vector Fields . . . . . . . . . . . . . . . . . . . . 184
Basic Displacement Maps . . . . . . . . . . . . . . . . . . . . . . . . 184
Entering Hyperspace . . . . . . . . . . . . . . . . . . . . . . . . . . 186
Conclusion. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 187
Contents vii
## Shadow Volume Extrusion Using a Vertex Shader. . . . . . . . . . . . . . . . . 188
Chris Brennan
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 188
Creating Shadow Volumes . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 189
Effect File Code . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 191
Using Shadow Volumes with Character Animation . . . . . . . . . . . . . . . . 192
## Character Animation with Direct3D Vertex Shaders . . . . . . . . . . . . . . . . 195
David Gosselin
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 195
Tweening . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 195
Skinning . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 197
Skinning and Tweening Together . . . . . . . . . . . . . . . . . . . . . . . 199
Animating Tangent Space for Per-Pixel Lighting . . . . . . . . . . . . . . . . . 202
Per-Pixel Lighting. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 203
Compression. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 206
Summary. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 208
## Lighting a Single-Surface Object. . . . . . . . . . . . . . . . . . . . . . . . . . 209
Greg James
Vertex Shader Code . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 211
Enhanced Lighting for Thin Objects . . . . . . . . . . . . . . . . . . . . . . . . 213
About the Demo . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 214
## Optimizing Software Vertex Shaders . . . . . . . . . . . . . . . . . . . . . . . 215
Kim Pallister
Introduction to Pentium 4 Processor Architecture . . . . . . . . . . . . . . . . . 216
Introduction to the Streaming SIMD Extensions . . . . . . . . . . . . . . . . . 217
Optimal Data Arrangement for SSE Instruction Usage . . . . . . . . . . . . . . 218
How the Vertex Shader Compiler Works . . . . . . . . . . . . . . . . . . . . . . 220
Performance Expectations . . . . . . . . . . . . . . . . . . . . . . . . . . 221
Optimization Guidelines . . . . . . . . . . . . . . . . . . . . . . . . . . . 221
Write Only the Results You’ll Need. . . . . . . . . . . . . . . . . . . 221
Use Macros Whenever Possible . . . . . . . . . . . . . . . . . . . . 222
Squeeze Dependency Chains . . . . . . . . . . . . . . . . . . . . . . 222
Write Final Arithmetic Instructions Directly to Output Registers . . . 223
Reuse the Same Temporary Register If Possible . . . . . . . . . . . . 223
Don’t Implicitly Saturate Color and Fog Values . . . . . . . . . . . . 223
Use the Lowest Acceptable Accuracy with exp and log Functions. . . 223
Avoid Using the Address Register When Possible . . . . . . . . . . . 223
Try to Order Vertices . . . . . . . . . . . . . . . . . . . . . . . . . . 224
Profile, Profile, Profile… . . . . . . . . . . . . . . . . . . . . . . . . 224
A Detailed Example . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 224
viii Contents
## Compendium of Vertex Shader Tricks . . . . . . . . . . . . . . . . . . . . . . . 228
Scott Le Grand
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 228
Periodic Time . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 228
One-Shot Effect . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 229
Random Numbers . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 229
Flow Control. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 230
Cross Products. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 230
Examples . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 230
Summary. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 231
## Perlin Noise and Returning Results from Shader Programs . . . . . . . . . . . 232
Steven Riddle and Oliver C. Zecha
Limitations of Shaders . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 232
Perlin Noise and Fractional Brownian Motion . . . . . . . . . . . . . . . . . . . 234
Final Thoughts. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 251
# Part3: Pixel Shader Tricks
## Blending Textures for Terrain . . . . . . . . . . . . . . . . . . . . . . . . . . . 256
Alex Vlachos
## Image Processing with 1.4 Pixel Shaders in Direct3D. . . . . . . . . . . . . . . 258
Jason L. Mitchell
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 258
Simple Transfer Functions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 259
Black and White Transfer Function . . . . . . . . . . . . . . . . . . . . . 260
Sepia Tone Transfer Function. . . . . . . . . . . . . . . . . . . . . . . . . 260
Heat Signature. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 261
Filter Kernels . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 261
Texture Coordinates for Filter Kernels . . . . . . . . . . . . . . . . . . . . 261
Edge Detection . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 262
Roberts Cross Gradient Filters . . . . . . . . . . . . . . . . . . . . . . . . 262
Sobel Filter . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 263
Mathematical Morphology . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 265
The Definition of Dilation . . . . . . . . . . . . . . . . . . . . . . . . . . 265
A Dilation Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 266
The Definition of Erosion. . . . . . . . . . . . . . . . . . . . . . . . . . . 267
An Erosion Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 267
Conclusion. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 268
Hardware Support . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 269
Sample Application . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 269
Contents ix
## Hallo World — Font Smoothing with Pixel Shaders. . . . . . . . . . . . . . . . 270
Steffen Bendel
## Emulating Geometry with Shaders — Imposters . . . . . . . . . . . . . . . . . 273
Steffen Bendel
## Smooth Lighting with ps.1.4 . . . . . . . . . . . . . . . . . . . . . . . . . . . . 277
Steffen Bendel
## Per-Pixel Fresnel Term . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 281
Chris Brennan
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 281
Fresnel Effects. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 281
Effect Code . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 283
## Diffuse Cube Mapping . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 287
Chris Brennan
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 287
Using Diffuse Cube Maps. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 287
Generating Dynamic Diffuse Cube Maps . . . . . . . . . . . . . . . . . . . . . 288
## Accurate Reflections and Refractions by Adjusting for Object Distance . . . . . 290
Chris Brennan
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 290
The Artifacts of Environment Mapping . . . . . . . . . . . . . . . . . . . . . . 290
## UV Flipping Technique to Avoid Repetition . . . . . . . . . . . . . . . . . . . . 295
Alex Vlachos
## Photorealistic Faces with Vertex and Pixel Shaders . . . . . . . . . . . . . . . 296
Kenneth L. Hurley
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 296
Software . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 296
Resources . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 297
3D Model . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 297
Setup for Separation of Lighting Elements. . . . . . . . . . . . . . . . . . 298
Diffuse Lighting Component . . . . . . . . . . . . . . . . . . . . . . . . . 298
Extracting the Bump and Specular Map . . . . . . . . . . . . . . . . . . . 299
Separating Specular and Bump Maps . . . . . . . . . . . . . . . . . . . . 299
Normal Maps . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 300
More on Normal Maps . . . . . . . . . . . . . . . . . . . . . . . . . 301
A Word About Optimizations . . . . . . . . . . . . . . . . . . . . . . . . . . . . 302
Half Angle . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 303
Vertex Shader Explanation Pass 1 (Listing 1) . . . . . . . . . . . . . . . . 303
Vertex Shader Explanation Pass 1 (Listing 2) . . . . . . . . . . . . . . . . 305
Pixel Shader Explanation (Listing 3) . . . . . . . . . . . . . . . . . . . . . 307
x Contents
Team LRNFull Head Mapping . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 309
Getting Started . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 310
Mapping the Photographs . . . . . . . . . . . . . . . . . . . . . . . . . . . 310
Creating a Single Texture Map . . . . . . . . . . . . . . . . . . . . . . . . 310
Putting It All Together . . . . . . . . . . . . . . . . . . . . . . . . . . . . 312
What’s Next? . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 312
Environmental Lighting. . . . . . . . . . . . . . . . . . . . . . . . . . . . 312
How to Get Diffusion Cube Maps. . . . . . . . . . . . . . . . . . . . 312
Generating the Cube Maps . . . . . . . . . . . . . . . . . . . . . . . 313
The Pixel Shader to Use All These Maps . . . . . . . . . . . . . . . . 314
Environment Mapping for Eyes. . . . . . . . . . . . . . . . . . . . . . . . . . . 315
Final Result . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 316
Facial Animation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 317
Conclusion. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 317
## Non-Photorealistic Rendering with Pixel and Vertex Shaders . . . . . . . . . . 319
Drew Card and Jason L. Mitchell
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 319
Rendering Outlines . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 319
Cartoon Lighting Model. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 322
Hatching . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 324
Gooch Lighting . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 326
Image Space Techniques . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 328
Compositing the Edges . . . . . . . . . . . . . . . . . . . . . . . . . . . . 330
Depth Precision . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 331
Alpha Test for Efficiency . . . . . . . . . . . . . . . . . . . . . . . . . . . 331
Shadow Outlines . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 331
Thickening Outlines with Morphology . . . . . . . . . . . . . . . . . . . . 332
Summary of Image Space Technique. . . . . . . . . . . . . . . . . . . . . 332
Conclusion. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 333
## Animated Grass with Pixel and Vertex Shaders . . . . . . . . . . . . . . . . . . 334
John Isidoro and Drew Card
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 334
Waving the Grass . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 334
Lighting the Grass . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 334
## Texture Perturbation Effects . . . . . . . . . . . . . . . . . . . . . . . . . . . . 337
John Isidoro, Guennadi Riguer, and Chris Brennan
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 337
Wispy Clouds . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 337
Perturbation-Based Fire . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 342
Plasma Glass. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 344
Summary. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 346
Contents xi
## Rendering Ocean Water . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 347
John Isidoro, Alex Vlachos, and Chris Brennan
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 347
Sinusoidal Perturbation in a Vertex Shader. . . . . . . . . . . . . . . . . . . . . 348
CMEMBM Pixel Shader with Fresnel Term . . . . . . . . . . . . . . . . . . . . 350
Ocean Water Shader Source Code . . . . . . . . . . . . . . . . . . . . . . . . . 352
Sample Applications . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 356
## Rippling Reflective and Refractive Water . . . . . . . . . . . . . . . . . . . . . 357
Alex Vlachos, John Isidoro, and Chris Oat
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 357
Generating Reflection and Refraction Maps . . . . . . . . . . . . . . . . . . . . 358
Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 358
Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 360
Conclusion. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 362
## Crystal/Candy Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 363
John Isidoro and David Gosselin
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 363
Setup . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 363
Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 364
Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 365
Summary. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 368
## Bubble Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 369
John Isidoro and David Gosselin
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 369
Setup . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 369
Vertex Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 370
Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 372
Summary. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 375
## Per-Pixel Strand-Based Anisotropic Lighting . . . . . . . . . . . . . . . . . . . 376
John Isidoro and Chris Brennan
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 376
Strand-Based Illumination . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 376
Rendering Using the Texture Lookup Table . . . . . . . . . . . . . . . . . 377
Per-Pixel Strand-Based Illumination . . . . . . . . . . . . . . . . . . . . . . . . 378
Per-Pixel Strand-Based Illumination with Colored Light and Base Map . . 379
Per-Pixel Strand-Based Illumination with Four Colored Lights and
Base Map in One Pass . . . . . . . . . . . . . . . . . . . . . . . . . . . 379
Per-Pixel Bump-Mapped Strand-Based Illumination Using Gram-Schmidt
Orthonormalization . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 380
Summary. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 382
xii Contents
## A Non-Integer Power Function on the Pixel Shader . . . . . . . . . . . . . . . . 383
Philippe Beaudoin and Juan Guardado
Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 383
Traditional Techniques . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 384
Texture Lookup . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 384
Successive Multiplications . . . . . . . . . . . . . . . . . . . . . . . . . . 386
The Need for a New Trick . . . . . . . . . . . . . . . . . . . . . . . . . . 386
Mathematical Details . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 387
Power Function on the Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . 391
Constant Exponent . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 392
Per-Pixel Exponent . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 395
Applications . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 396
Smooth Conditional Function. . . . . . . . . . . . . . . . . . . . . . . . . 396
Volume Bounded Pixel Shader Effects . . . . . . . . . . . . . . . . . 398
Phong Shading . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 399
Phong Equation with Blinn Half-Vector . . . . . . . . . . . . . . . . 400
Expressing the Inputs . . . . . . . . . . . . . . . . . . . . . . . . . . 400
The Pixel Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . 401
Summary. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 402
## Bump Mapped BRDF Rendering . . . . . . . . . . . . . . . . . . . . . . . . . . 405
Ádám Moravánszky
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 405
Bidirectional Reflectance Distribution Functions . . . . . . . . . . . . . . . . . 406
Decomposing the Function . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 407
Reconstruction. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 407
Adding the Bumps. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 410
Conclusion. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 412
## Real-Time Simulation and Rendering of Particle Flows. . . . . . . . . . . . . . 414
Daniel Weiskopf and Matthias Hopf
Motivation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 414
Ingredients . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 415
How Does a Single Particle Move?. . . . . . . . . . . . . . . . . . . . . . . . . 416
Basic Texture Advection: How Do a Bunch of Particles Move? . . . . . . . . . 417
Inflow: Where are the Particles Born? . . . . . . . . . . . . . . . . . . . . . . . 421
How Can Particles Drop Out? . . . . . . . . . . . . . . . . . . . . . . . . . . . 423
Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 423
Summary. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 425
Contents xiii
# Part4: Using 3D Textures with Shaders
## 3D Textures and Pixel Shaders. . . . . . . . . . . . . . . . . . . . . . . . . . . 428
Evan Hart
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 428
3D Textures . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 428
Filtering . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 429
Storage. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 429
Applications . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 430
Function of Three Independent Variables . . . . . . . . . . . . . . . . 430
Noise and Procedural Texturing. . . . . . . . . . . . . . . . . . . . . 431
Attenuation and Distance Measurement . . . . . . . . . . . . . . . . 432
Representation of Amorphous Volume . . . . . . . . . . . . . . . . . 435
Application . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 435
Volumetric Fog and Other Atmospherics. . . . . . . . . . . . . . . . . . . 435
Light Falloff . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 436
## Truly Volumetric Effects . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 438
Martin Kraus
The Role of Volume Visualization . . . . . . . . . . . . . . . . . . . . . . . . . 438
Basic Volume Graphics . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 439
Animation of Volume Graphics . . . . . . . . . . . . . . . . . . . . . . . . . . . 441
Rotating Volume Graphics . . . . . . . . . . . . . . . . . . . . . . . . . . 441
Animated Transfer Functions . . . . . . . . . . . . . . . . . . . . . . . . . 441
Blending of Volume Graphics . . . . . . . . . . . . . . . . . . . . . . . . 442
High-Quality but Fast Volume Rendering . . . . . . . . . . . . . . . . . . . . . 444
Where to Go from Here . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 446
Acknowledgments. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 447
# Part5: Engine Design with Shaders
## First Thoughts on Designing a Shader-Driven Game Engine . . . . . . . . . . . 450
Steffen Bendel
Bump Mapping . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 450
Real-time Lighting . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 450
Use Detail Textures . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 451
Use Anisotropic Filtering . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 451
Split Up Rendering into Independent Passes . . . . . . . . . . . . . . . . . . . . 451
Use _x2 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 452
xiv Contents
## Visualization with the Krass Game Engine . . . . . . . . . . . . . . . . . . . . 453
Ingo Frick
Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 453
General Structure of the Krass Engine . . . . . . . . . . . . . . . . . . . . . . . 453
Developmental History of the Rendering Component . . . . . . . . . . . . . . . 454
Previous Drawbacks of Hardware Development . . . . . . . . . . . . . . . . . . 455
Current Drawbacks . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 455
Ordering Effects in the Krass Engine . . . . . . . . . . . . . . . . . . . . . . . . 456
Application of the IMG Concept for Terrain Rendering . . . . . . . . . . . . . . 457
Particle Rendering to Exemplify a Specialized Effect Shader . . . . . . . . . . . 460
Summary. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 461
## Designing a Vertex Shader-Driven 3D Engine for the Quake III Format . . . . . 463
Bart Sekura
Quake III Arena Shaders . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 463
Vertex Program Setup in the Viewer . . . . . . . . . . . . . . . . . . . . . . . . 464
Vertex Shader Effects . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 467
Deformable Geometry . . . . . . . . . . . . . . . . . . . . . . . . . . . . 467
Texture Coordinate Generation . . . . . . . . . . . . . . . . . . . . . . . . 468
Texture Matrix Manipulation . . . . . . . . . . . . . . . . . . . . . . . . . 469
Rendering Process. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 471
Summary. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 472
