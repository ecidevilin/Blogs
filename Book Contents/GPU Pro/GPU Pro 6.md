# I Geometry Manipulation 1
Wolfgang Engel
## 1 Dynamic GPU Terrain 3
David Pangerl
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 3
1.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 4
1.3 Terrain Data . . . . . . . . . . . . . . . . . . . . . . . . . . . . 4
1.4 Rendering . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 4
1.5 Dynamic Modification . . . . . . . . . . . . . . . . . . . . . . . 11
1.6 Physics Synchronization . . . . . . . . . . . . . . . . . . . . . . 13
1.7 Problems . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 13
1.8 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15
## 2 Bandwidth-Efficient Procedural Meshes in the GPU via Tessellation 19
Gustavo Bastos Nunes and Jo˜ao Lucas Guberman Raza
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 19
2.2 Procedural Mesh and the Graphics Pipeline . . . . . . . . . . . 19
2.3 Hull Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 20
2.4 Domain Shader . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
2.5 Noise in Procedural Meshes . . . . . . . . . . . . . . . . . . . . 23
2.6 Performance Optimizations . . . . . . . . . . . . . . . . . . . . 23
2.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
2.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 25
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
vvi Contents
## 3 Real-Time Deformation of Subdivision Surfaces on Object Collisions 27
Henry Sch¨afer, Matthias Nießner, Benjamin Keinert, and Marc Stamminger
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 27
3.2 Deformable Surface Representation . . . . . . . . . . . . . . . . 29
3.3 Algorithm Overview . . . . . . . . . . . . . . . . . . . . . . . . 34
3.4 Pipeline . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 35
3.5 Optimizations . . . . . . . . . . . . . . . . . . . . . . . . . . . . 43
3.6 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 44
3.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 49
3.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 49
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 49
## 4 Realistic Volumetric Explosions in Games 51
Alex Dunn
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 51
4.2 Rendering Pipeline Overview . . . . . . . . . . . . . . . . . . . 52
4.3 Offline/Preprocessing . . . . . . . . . . . . . . . . . . . . . . . . 52
4.4 Runtime . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 53
4.5 Visual Improvements . . . . . . . . . . . . . . . . . . . . . . . . 56
4.6 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 58
4.7 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 59
4.8 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 62
4.9 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 62
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 62
# II Rendering 63
Christopher Oat
## 1 Next-Generation Rendering in Thief 65
Peter Sikachev, Samuel Delmont, Uriel Doyon, and Jean-Normand Bucci
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 65
1.2 Reflections . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 66
1.3 Contact-Hardening Shadows . . . . . . . . . . . . . . . . . . . . 79
1.4 Lit Particles . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 85
1.5 Compute-Shader-Based Postprocessing . . . . . . . . . . . . . . 85
1.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 88
1.7 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 88
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 89Contents vii
## 2 Grass Rendering and Simulation with LOD 91
Dongsoo Han and Hongwei Li
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 91
2.2 Render Grass Blades . . . . . . . . . . . . . . . . . . . . . . . . 92
2.3 Simulation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 94
2.4 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 100
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 100
## 3 Hybrid Reconstruction Antialiasing 101
Michal Drobot
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 101
3.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 101
3.3 Related Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 102
3.4 Hybrid Antialiasing Overview . . . . . . . . . . . . . . . . . . . 104
3.5 Temporally Stable Edge Antialiasing . . . . . . . . . . . . . . . 105
3.6 Temporal Super-Sampling . . . . . . . . . . . . . . . . . . . . . 118
3.7 Temporal Antialiasing (TAA) . . . . . . . . . . . . . . . . . . . 129
3.8 Final Implementation . . . . . . . . . . . . . . . . . . . . . . . 132
3.9 Results Discussion . . . . . . . . . . . . . . . . . . . . . . . . . 133
3.10 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 135
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 137
## 4 Real-Time Rendering of Physically Based Clouds Using
Precomputed Scattering 141
Egor Yusov
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 141
4.2 Light Transport Theory . . . . . . . . . . . . . . . . . . . . . . 142
4.3 Precomputed Solutions . . . . . . . . . . . . . . . . . . . . . . . 144
4.4 Volume-Aware Blending . . . . . . . . . . . . . . . . . . . . . . 146
4.5 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 147
4.6 Results and Discussion . . . . . . . . . . . . . . . . . . . . . . . 161
4.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 164
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 164
## 5 Sparse Procedural Volume Rendering 167
Doug McNabb
5.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 167
5.2 Overview of Current Techniques . . . . . . . . . . . . . . . . . 167
5.3 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 168
5.4 Metavoxels . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 170
5.5 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 172
5.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 180
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 180viii Contents
# III Lighting 181
Michal Valient
## 1 Real-Time Lighting via Light Linked List 183
Abdul Bezrati
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 183
1.2 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 183
1.3 Populating the Light Linked List . . . . . . . . . . . . . . . . . 186
1.4 Accessing the Light Linked List . . . . . . . . . . . . . . . . . . 190
1.5 Reduced Resolution . . . . . . . . . . . . . . . . . . . . . . . . 191
1.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 193
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 193
## 2 Deferred Normalized Irradiance Probes 195
John Huelin, Benjamin Rouveyrol, and Bartlomiej Wro´nski
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 195
2.2 Deferred Normalized Irradiance Probes Algorithm . . . . . . . 198
2.3 Tool Side of the Algorithm . . . . . . . . . . . . . . . . . . . . 202
2.4 Runtime Details of Algorithm . . . . . . . . . . . . . . . . . . . 207
2.5 Results and Discussion . . . . . . . . . . . . . . . . . . . . . . . 212
2.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 214
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 214
## 3 Volumetric Fog and Lighting 217
Bartlomiej Wro´nski
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 217
3.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 218
3.3 Volumetric Fog Algorithm . . . . . . . . . . . . . . . . . . . . . 222
3.4 Results and Discussion . . . . . . . . . . . . . . . . . . . . . . . 233
3.5 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 239
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 239
## 4 Physically Based Light Probe Generation on GPU 243
Ivan Spogreev
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 243
4.2 Light Probes Theory . . . . . . . . . . . . . . . . . . . . . . . . 244
4.3 Generating Light Probes on the GPU . . . . . . . . . . . . . . 245
4.4 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 263
4.5 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 265
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 265Contents ix
## 5 Real-Time Global Illumination Using Slices 267
Hugh Malan
5.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 267
5.2 Algorithm Overview . . . . . . . . . . . . . . . . . . . . . . . . 268
5.3 Approximating the Irradiance Due to an Emissive Plane . . . . 269
5.4 Building the Image Pyramid . . . . . . . . . . . . . . . . . . . . 270
5.5 Combining Multiple Slices . . . . . . . . . . . . . . . . . . . . . 279
5.6 Layered Heightfields . . . . . . . . . . . . . . . . . . . . . . . . 281
5.7 Slice Placement . . . . . . . . . . . . . . . . . . . . . . . . . . . 283
5.8 Propagating Irradiance . . . . . . . . . . . . . . . . . . . . . . . 289
5.9 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 290
5.10 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 292
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 292
# IV Shadows 295
Wolfgang Engel
## 1 Practical Screen-Space Soft Shadows 297
M´arton Tam´as and Viktor Heisenberger
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 297
1.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 297
1.3 History . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 298
1.4 Algorithm Overview . . . . . . . . . . . . . . . . . . . . . . . . 300
1.5 Shadow Map Rendering Pass . . . . . . . . . . . . . . . . . . . 301
1.6 Introducing Layers and Light Assignment . . . . . . . . . . . . 301
1.7 Layered Penumbra Map Pass . . . . . . . . . . . . . . . . . . . 304
1.8 Anisotropic Gaussian Blur Pass . . . . . . . . . . . . . . . . . . 306
1.9 Lighting Pass . . . . . . . . . . . . . . . . . . . . . . . . . . . . 308
1.10 Performance Considerations . . . . . . . . . . . . . . . . . . . . 309
1.11 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 309
1.12 Quality Tests . . . . . . . . . . . . . . . . . . . . . . . . . . . . 310
1.13 Performance Analysis . . . . . . . . . . . . . . . . . . . . . . . 310
1.14 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 312
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 312
## 2 Tile-Based Omnidirectional Shadows 315
Hawar Doghramachi
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 315
2.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 316
2.3 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 317
2.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 332x Contents
2.5 Discussion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 336
2.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 338
2.7 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 338
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 338
## 3 Shadow Map Silhouette Revectorization 341
Vladimir Bondarev
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 341
3.2 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 342
3.3 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 344
3.4 Future Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 346
3.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 346
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 347
# V Mobile Devices 349
Marius Bjørge
## 1 Hybrid Ray Tracing on a PowerVR GPU 351
Gareth Morgan
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 351
1.2 Review . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 351
1.3 Combining Ray Tracing with Rasterization . . . . . . . . . . . 355
1.4 Hard Shadows . . . . . . . . . . . . . . . . . . . . . . . . . . . . 357
1.5 Soft Shadows . . . . . . . . . . . . . . . . . . . . . . . . . . . . 358
1.6 Reflections . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 359
1.7 Transparency . . . . . . . . . . . . . . . . . . . . . . . . . . . . 360
1.8 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 362
1.9 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 364
1.10 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 368
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 368
## 2 Implementing a GPU-Only Particle-Collision System with ASTC
3D Textures and OpenGL ES 3.0 369
Daniele Di Donato
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 369
2.2 GPU-Only Particle System . . . . . . . . . . . . . . . . . . . . 370
2.3 Physics Simulation . . . . . . . . . . . . . . . . . . . . . . . . . 372
2.4 Rendering the Particles . . . . . . . . . . . . . . . . . . . . . . 379
2.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 384
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 385Contents xi
## 3 Animated Characters with Shell Fur for Mobile Devices 387
Andrew Girdler and James L. Jones
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 387
3.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 387
3.3 Creating a Shell Fur Texture . . . . . . . . . . . . . . . . . . . 388
3.4 Bone Batches or Single Pass? . . . . . . . . . . . . . . . . . . . 389
3.5 Model Data and Setup . . . . . . . . . . . . . . . . . . . . . . . 389
3.6 Animation with TF . . . . . . . . . . . . . . . . . . . . . . . . . 391
3.7 Instancing for Fur Shells . . . . . . . . . . . . . . . . . . . . . . 391
3.8 Lighting and Other Effects . . . . . . . . . . . . . . . . . . . . 393
3.9 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 395
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 395
## 4 High Dynamic Range Computational Photography on Mobile GPUs 397
Simon McIntosh-Smith, Amir Chohan, Dan Curran, and Anton Lokhmotov
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 397
4.2 Background . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 398
4.3 Tone-Mapping Operators . . . . . . . . . . . . . . . . . . . . . 401
4.4 Related Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 406
4.5 GPGPU Using OpenCL . . . . . . . . . . . . . . . . . . . . . . 407
4.6 OpenGL ES and Android . . . . . . . . . . . . . . . . . . . . . 411
4.7 Implementing an HDR Pipeline Using OpenCL and OpenGL ES 412
4.8 Android Implementation . . . . . . . . . . . . . . . . . . . . . . 421
4.9 Performance of Our HDR Effects . . . . . . . . . . . . . . . . . 426
4.10 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 429
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 430
# VI Compute 433
Carsten Dachsbacher
## 1 Compute-Based Tiled Culling 435
Jason Stewart
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 435
1.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 436
1.3 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 437
1.4 Optimization . . . . . . . . . . . . . . . . . . . . . . . . . . . . 443
1.5 Unreal Engine 4 Results . . . . . . . . . . . . . . . . . . . . . . 452
1.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 457
1.7 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 458
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 458xii Contents
## 2 Rendering Vector Displacement-Mapped Surfaces in a GPU
Ray Tracer 459
Takahiro Harada
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 459
2.2 Displacement Mapping . . . . . . . . . . . . . . . . . . . . . . . 459
2.3 Ray Tracing a Scene with Vector Displacement Maps . . . . . . 461
2.4 Ray Tracing a Vector Displacement Patch . . . . . . . . . . . . 461
2.5 Integration into an OpenCL Ray Tracer . . . . . . . . . . . . . 467
2.6 Results and Discussion . . . . . . . . . . . . . . . . . . . . . . . 470
2.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 473
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 474
## 3 Smooth Probabilistic Ambient Occlusion for Volume Rendering 475
Thomas Kroes, Dirk Schut, and Elmar Eisemann
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 475
3.2 Smooth Probabilistic Ambient Occlusion . . . . . . . . . . . . . 476
3.3 Approximating Ambient Occlusion . . . . . . . . . . . . . . . . 481
3.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 483
3.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 483
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 484
# VII 3D Engine Design 487
Wessam Bahnassi
## 1 Block-Wise Linear Binary Grids for Fast Ray-Casting Operations 489
Holger Gruen
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 489
1.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 489
1.3 Block-Wise Linear Memory Layout . . . . . . . . . . . . . . . . 490
1.4 Rendering Block-Wise Linear Binary Voxel Grids . . . . . . . . 491
1.5 Casting Rays through a Block-Wise Linear Grid . . . . . . . . 495
1.6 Detecting Occlusions during Indirect Light Gathering . . . . . 495
1.7 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 500
1.8 Future Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 500
1.9 External References . . . . . . . . . . . . . . . . . . . . . . . . 503
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 503
## 2 Semantic-Based Shader Generation Using Shader Shaker 505
Michael Delva, Julien Hamaide, and Ramses Ladlani
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 505
2.2 Previous Work . . . . . . . . . . . . . . . . . . . . . . . . . . . 506Contents xiii
2.3 Definitions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 508
2.4 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 508
2.5 Algorithm Explanation . . . . . . . . . . . . . . . . . . . . . . . 510
2.6 Error Reporting . . . . . . . . . . . . . . . . . . . . . . . . . . . 514
2.7 Usage Discussions . . . . . . . . . . . . . . . . . . . . . . . . . 515
2.8 What’s Next . . . . . . . . . . . . . . . . . . . . . . . . . . . . 516
2.9 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 517
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 517
## 3 ANGLE: Bringing OpenGL ES to the Desktop 521
Shannon Woods, Nicolas Capens, Jamie Madill, and Geoff Lang
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 521
3.2 Direct3D 11 . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 522
3.3 Shader Translation . . . . . . . . . . . . . . . . . . . . . . . . . 525
3.4 Implementing ES3 on Feature Level 10 . . . . . . . . . . . . . . 532
3.5 Future Directions: Moving to New Platforms . . . . . . . . . . 536
3.6 Recommended Practices . . . . . . . . . . . . . . . . . . . . . . 540
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 541
