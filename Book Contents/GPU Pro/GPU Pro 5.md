# I Rendering 1
Carsten Dachsbacher
## 1 Per-Pixel Lists for Single Pass A-Buffer 3
Sylvain Lefebvre, Samuel Hornus, and Anass Lasram
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 3
1.2 Linked Lists with Pointers (Lin-alloc) . . . . . . . . . . . . . 6
1.3 Lists with Open Addressing (Open-alloc) . . . . . . . . . . . 11
1.4 Post-sort and Pre-sort . . . . . . . . . . . . . . . . . . . . 14
1.5 Memory Management . . . . . . . . . . . . . . . . . . . . . . . 16
1.6 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
1.7 Experimental Comparisons . . . . . . . . . . . . . . . . . . . . 18
1.8 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
1.9 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 22
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22
## 2 Reducing Texture Memory Usage by 2-Channel Color Encoding 25
Krzysztof Kluczek
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
2.2 Texture Encoding Algorithm . . . . . . . . . . . . . . . . . . . 25
2.3 Decoding Algorithm . . . . . . . . . . . . . . . . . . . . . . . . 31
2.4 Encoded Image Quality . . . . . . . . . . . . . . . . . . . . . . 31
2.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 33
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 34
vvi Contents
## 3 Particle-Based Simulation of Material Aging 35
Tobias G¨ unther, Kai Rohmer, and Thorsten Grosch
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 35
3.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 36
3.3 Simulation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 37
3.4 Preview Rendering . . . . . . . . . . . . . . . . . . . . . . . . . 49
3.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 51
3.6 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 52
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 53
## 4 Simple Rasterization-Based Liquids 55
Martin Guay
4.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 55
4.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 55
4.3 Simple Liquid Model . . . . . . . . . . . . . . . . . . . . . . . . 56
4.4 Splatting . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 57
4.5 Grid Pass . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 59
4.6 Particle Update . . . . . . . . . . . . . . . . . . . . . . . . . . . 60
4.7 Rigid Obstacles . . . . . . . . . . . . . . . . . . . . . . . . . . . 60
4.8 Examples . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 61
4.9 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 63
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 63
# II Lighting and Shading 65
Michal Valient
## 1 Physically Based Area Lights 67
Michal Drobot
1.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 67
1.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 68
1.3 Area Lighting Model . . . . . . . . . . . . . . . . . . . . . . . . 70
1.4 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 91
1.5 Results Discussion . . . . . . . . . . . . . . . . . . . . . . . . . 93
1.6 Further Research . . . . . . . . . . . . . . . . . . . . . . . . . . 96
1.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 97
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 99
## 2 High Performance Outdoor Light Scattering Using Epipolar Sampling 101
Egor Yusov
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 101
2.2 Previous Work . . . . . . . . . . . . . . . . . . . . . . . . . . . 102Contents vii
2.3 Algorithm Overview . . . . . . . . . . . . . . . . . . . . . . . . 103
2.4 Light Transport Theory . . . . . . . . . . . . . . . . . . . . . . 103
2.5 Computing Scattering Integral . . . . . . . . . . . . . . . . . . 106
2.6 Epipolar Sampling . . . . . . . . . . . . . . . . . . . . . . . . . 108
2.7 1D Min/Max Binary Tree Optimization . . . . . . . . . . . . . 110
2.8 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 113
2.9 Results and Discussion . . . . . . . . . . . . . . . . . . . . . . . 119
2.10 Conclusion and Future Work . . . . . . . . . . . . . . . . . . . 124
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 124
## 3 Volumetric Light Effects in Killzone: Shadow Fall 127
Nathan Vos
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 127
3.2 Basic Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . 128
3.3 Low-Resolution Rendering . . . . . . . . . . . . . . . . . . . . . 132
3.4 Dithered Ray Marching . . . . . . . . . . . . . . . . . . . . . . 133
3.5 Controlling the Amount of Scattering . . . . . . . . . . . . . . 136
3.6 Transparent Objects . . . . . . . . . . . . . . . . . . . . . . . . 142
3.7 Limitations . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 144
3.8 Future Improvements . . . . . . . . . . . . . . . . . . . . . . . . 145
3.9 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 146
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 146
## 4 Hi-Z Screen-Space Cone-Traced Reflections 149
Yasin Uludag
4.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 149
4.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 150
4.3 Previous Work . . . . . . . . . . . . . . . . . . . . . . . . . . . 152
4.4 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 156
4.5 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 172
4.6 Extensions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 179
4.7 Optimizations . . . . . . . . . . . . . . . . . . . . . . . . . . . . 186
4.8 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 187
4.9 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 188
4.10 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 188
4.11 Future Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 189
4.12 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 190
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 190viii Contents
## 5 TressFX: Advanced Real-Time Hair Rendering 193
Timothy Martin, Wolfgang Engel, Nicolas Thibieroz, Jason Yang,
and Jason Lacroix
5.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 193
5.2 Geometry Expansion . . . . . . . . . . . . . . . . . . . . . . . . 194
5.3 Lighting . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 196
5.4 Shadows and Approximated Hair Self-Shadowing . . . . . . . . 198
5.5 Antialiasing . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 200
5.6 Transparency . . . . . . . . . . . . . . . . . . . . . . . . . . . . 201
5.7 Integration Specifics . . . . . . . . . . . . . . . . . . . . . . . . 204
5.8 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 206
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 208
## 6 Wire Antialiasing 211
Emil Persson
6.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 211
6.2 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 212
6.3 Conclusion and Future Work . . . . . . . . . . . . . . . . . . . 217
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 217
# III Image Space 219
Christopher Oat
## 1 Screen-Space Grass 221
David Pangerl
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 221
1.2 Motivation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 221
1.3 Technique . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 222
1.4 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 226
1.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 227
1.6 Limitations and Future Work . . . . . . . . . . . . . . . . . . . 228
1.7 Screen-Space Grass Source Code . . . . . . . . . . . . . . . . . 230
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 232
## 2 Screen-Space Deformable Meshes via CSG with Per-Pixel
Linked Lists 233
Jo˜ao Raza and Gustavo Nunes
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 233
2.2 Mesh Deformation Scenario . . . . . . . . . . . . . . . . . . . . 233
2.3 Algorithm Overview . . . . . . . . . . . . . . . . . . . . . . . . 234
2.4 Optimizations . . . . . . . . . . . . . . . . . . . . . . . . . . . . 239Contents ix
2.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 239
2.6 Acknowledgements . . . . . . . . . . . . . . . . . . . . . . . . . 240
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 240
## 3 Bokeh Effects on the SPU 241
Serge Bernier
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 241
3.2 Bokeh Behind the Scenes . . . . . . . . . . . . . . . . . . . . . 242
3.3 The Sprite-Based Approach . . . . . . . . . . . . . . . . . . . . 244
3.4 Let’s SPUify This! . . . . . . . . . . . . . . . . . . . . . . . . . 246
3.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 249
3.6 Future Development . . . . . . . . . . . . . . . . . . . . . . . . 250
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 250
# IV Mobile Devices 251
Marius Bjørge
## 1 Realistic Real-Time Skin Rendering on Mobile 253
Renaldas Zioma and Ole Ciliox
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 253
1.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 253
1.3 Power of Mobile GPU . . . . . . . . . . . . . . . . . . . . . . . 255
1.4 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 256
1.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 260
1.6 Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 261
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 262
## 2 Deferred Rendering Techniques on Mobile Devices 263
Ashley Vaughan Smith
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 263
2.2 Review . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 263
2.3 Overview of Techniques . . . . . . . . . . . . . . . . . . . . . . 264
2.4 OpenGL ES Extensions . . . . . . . . . . . . . . . . . . . . . . 270
2.5 Conclusion and Future Work . . . . . . . . . . . . . . . . . . . 272
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 272
## 3 Bandwidth Efficient Graphics with ARM Mali GPUs 275
Marius Bjørge
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 275
3.2 Shader Framebuffer Fetch Extensions . . . . . . . . . . . . . . . 275
3.3 Shader Pixel Local Storage . . . . . . . . . . . . . . . . . . . . 279
3.4 Deferred Shading Example . . . . . . . . . . . . . . . . . . . . . 283x Contents
3.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 287
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 288
## 4 Efficient Morph Target Animation Using OpenGL ES 3.0 289
James L. Jones
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 289
4.2 Previous Work . . . . . . . . . . . . . . . . . . . . . . . . . . . 289
4.3 Morph Targets . . . . . . . . . . . . . . . . . . . . . . . . . . . 290
4.4 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 291
4.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 295
4.6 Acknowledgements . . . . . . . . . . . . . . . . . . . . . . . . . 295
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 295
## 5 Tiled Deferred Blending 297
Ramses Ladlani
5.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 297
5.2 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 299
5.3 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 300
5.4 Optimizations . . . . . . . . . . . . . . . . . . . . . . . . . . . . 306
5.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 308
5.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 309
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 310
## 6 Adaptive Scalable Texture Compression 313
Stacy Smith
6.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 313
6.2 Background . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 313
6.3 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 314
6.4 Getting Started . . . . . . . . . . . . . . . . . . . . . . . . . . . 316
6.5 Using ASTC Textures . . . . . . . . . . . . . . . . . . . . . . . 317
6.6 Quality Settings . . . . . . . . . . . . . . . . . . . . . . . . . . 318
6.7 Other color formats . . . . . . . . . . . . . . . . . . . . . . . . 323
6.8 3D Textures . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 325
6.9 Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 325
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 326
## 7 Optimizing OpenCL Kernels for the ARM Mali-T600 GPUs 327
Johan Gronqvist and Anton Lokhmotov
7.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 327
7.2 Overview of the OpenCL Programming Model . . . . . . . . . 328
7.3 ARM Mali-T600 GPU Series . . . . . . . . . . . . . . . . . . . 328
7.4 Optimizing the Sobel Image Filter . . . . . . . . . . . . . . . . 331
7.5 Optimizing the General Matrix Multiplication . . . . . . . . . . 339
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 357Contents xi
# V 3D Engine Design 359
Wessam Bahnassi
## 1 Quaternions Revisited 361
Peter Sikachev, Vladimir Egorov, and Sergey Makeev
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 361
1.2 Quaternion Properties Overview . . . . . . . . . . . . . . . . . 361
1.3 Quaternion Use Cases . . . . . . . . . . . . . . . . . . . . . . . 362
1.4 Normal Mapping . . . . . . . . . . . . . . . . . . . . . . . . . . 362
1.5 Generic Transforms and Instancing . . . . . . . . . . . . . . . . 366
1.6 Skinning . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 368
1.7 Morph Targets . . . . . . . . . . . . . . . . . . . . . . . . . . . 371
1.8 Quaternion Format . . . . . . . . . . . . . . . . . . . . . . . . . 371
1.9 Comparison . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 373
1.10 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 374
1.11 Acknowledgements . . . . . . . . . . . . . . . . . . . . . . . . . 374
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 374
## 2 glTF: Designing an Open-Standard Runtime Asset Format 375
Fabrice Robinet, R´emi Arnaud, Tony Parisi, and Patrick Cozzi
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 375
2.2 Motivation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 375
2.3 Goals . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 376
2.4 Birds-Eye View . . . . . . . . . . . . . . . . . . . . . . . . . . . 379
2.5 Integration of Buffer and Buffer View . . . . . . . . . . . . . . 380
2.6 Code Flow for Rendering Meshes . . . . . . . . . . . . . . . . . 382
2.7 From Materials to Shaders . . . . . . . . . . . . . . . . . . . . . 382
2.8 Animation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 384
2.9 Content Pipeline . . . . . . . . . . . . . . . . . . . . . . . . . . 385
2.10 Future Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 390
2.11 Acknowledgements . . . . . . . . . . . . . . . . . . . . . . . . . 391
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 391
## 3 Managing Transformations in Hierarchy 393
Bartosz Chodorowski and Wojciech Sterna
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 393
3.2 Theory . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 394
3.3 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 399
3.4 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 402
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 403xii Contents
# VI Compute 405
Wolfgang Engel
## 1 Hair Simulation in TressFX 407
Dongsoo Han
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 407
1.2 Simulation Overview . . . . . . . . . . . . . . . . . . . . . . . . 408
1.3 Definitions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 409
1.4 Integration . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 410
1.5 Constraints . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 410
1.6 Wind and Collision . . . . . . . . . . . . . . . . . . . . . . . . . 412
1.7 Authoring Hair Asset . . . . . . . . . . . . . . . . . . . . . . . 413
1.8 GPU Implementation . . . . . . . . . . . . . . . . . . . . . . . 414
1.9 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 416
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 417
## 2 Object-Order Ray Tracing for Fully Dynamic Scenes 419
Tobias Zirr, Hauke Rehfeld, and Carsten Dachsbacher
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 419
2.2 Object-Order Ray Tracing Using the Ray Grid . . . . . . . . . 421
2.3 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 422
2.4 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 424
2.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 434
2.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 436
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 436
## 3 Quadtrees on the GPU 439
Jonathan Dupuy, Jean-Claude Iehl, and Pierre Poulin
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 439
3.2 Linear Quadtrees . . . . . . . . . . . . . . . . . . . . . . . . . . 440
3.3 Scalable Grids on the GPU . . . . . . . . . . . . . . . . . . . . 443
3.4 Discussion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 447
3.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 449
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 449
## 4 Two-Level Constraint Solver and Pipelined Local Batching for Rigid
Body Simulation on GPUs 451
Takahiro Harada
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 451
4.2 Rigid Body Simulation . . . . . . . . . . . . . . . . . . . . . . . 452
4.3 Two-Level Constraint Solver . . . . . . . . . . . . . . . . . . . . 454
4.4 GPU Implementation . . . . . . . . . . . . . . . . . . . . . . . 456Contents xiii
4.5 Comparison of Batching Methods . . . . . . . . . . . . . . . . . 459
4.6 Results and Discussion . . . . . . . . . . . . . . . . . . . . . . . 461
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 467
## 5 Non-separable 2D, 3D, and 4D Filtering with CUDA 469
Anders Eklund and Paul Dufort
5.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 469
5.2 Non-separable Filters . . . . . . . . . . . . . . . . . . . . . . . . 471
5.3 Convolution vs. FFT . . . . . . . . . . . . . . . . . . . . . . . . 474
5.4 Previous Work . . . . . . . . . . . . . . . . . . . . . . . . . . . 475
5.5 Non-separable 2D Convolution . . . . . . . . . . . . . . . . . . 475
5.6 Non-separable 3D Convolution . . . . . . . . . . . . . . . . . . 480
5.7 Non-separable 4D Convolution . . . . . . . . . . . . . . . . . . 481
5.8 Non-separable 3D Convolution, Revisited . . . . . . . . . . . . 482
5.9 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 483
5.10 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 486
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 490
