# I Mathematics 1
Sam Martin, editor
## 1 GPU Color Quantization 3
Chi Sing Leung, Tze-Yui Ho, and Yi Xiao
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 3
1.2 The Self-Organizing Map . . . . . . . . . . . . . . . . . . . . . . . 4
1.3 Color Quantization with SOM . . . . . . . . . . . . . . . . . . . . 6
1.4 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . . 7
1.5 Results and Discussion . . . . . . . . . . . . . . . . . . . . . . . . 10
1.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 12
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 13
## 2 Visualize Your Shadow Map Techniques 15
Fan Zhang, Chong Zhao, and Adrian Egli
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15
2.2 Article Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15
2.3 Scope of Analysis . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
2.4 Aliasing Revisited . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
2.5 A Representation of Aliasing Errors . . . . . . . . . . . . . . . . . 19
2.6 Visualization . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
viiviii Contents
2.7 Mismatch of View Direction and Warping Direction . . . . . . . . 25
2.8 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 27
2.9 Supplementary Materials . . . . . . . . . . . . . . . . . . . . . . . 27
2.10 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . 28
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 28
# II Geometry Manipulation 31
Natalya Tatarchuk, editor
## 1 As Simple as Possible Tessellation for Interactive Applications 33
Tamy Boubekeur
1.1 Basic Phong Tessellation Operator . . . . . . . . . . . . . . . . . . 34
1.2 Extension to Quads . . . . . . . . . . . . . . . . . . . . . . . . . . 36
1.3 Results and Discussion . . . . . . . . . . . . . . . . . . . . . . . . 38
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 38
## 2 Rule-Based Geometry Synthesis in Real-Time 41
Milán Magdics and Gergely Klár
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 41
2.2 Building Up the Scene with Procedures . . . . . . . . . . . . . . . 42
2.3 L-systems and the PGI . . . . . . . . . . . . . . . . . . . . . . . . 42
2.4 Model Details and Implementation . . . . . . . . . . . . . . . . . 44
2.5 Interaction with the Procedural Scene . . . . . . . . . . . . . . . . 59
2.6 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 62
2.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 65
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 65
## 3 GPU-Based NURBS Geometry Evaluation and Rendering 67
Graham Hemingway
3.1 A Bit of NURBS Background . . . . . . . . . . . . . . . . . . . . 67
3.2 Related Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 71
3.3 NURBS Surface and Curve Evaluation . . . . . . . . . . . . . . . 72
3.4 Trimmed NURBS Surface Evaluation . . . . . . . . . . . . . . . . 77
3.5 Results and Conclusion . . . . . . . . . . . . . . . . . . . . . . . . 82
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 84
## 4 Polygonal-Functional Hybrids for Computer Animation and Games 87
D. Kravtsov, O. Fryazinov, V. Adzhiev, A. Pasko, and P. Comninos
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 87
4.2 Background . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 88Contents ix
4.3 Working with FRep Models Using the GPU . . . . . . . . . . . . 94
4.4 Applications . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 103
4.5 Tools . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 110
4.6 Limitations . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 111
4.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 112
4.8 Source Code . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 112
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 113
# III Rendering Techniques 115
Wessam Bahnassi, editor
## 1 Quadtree Displacement Mapping with Height Blending 117
Michal Drobot
1.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 117
1.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 119
1.3 Overview of Ray-Tracing Algorithms . . . . . . . . . . . . . . . . 120
1.4 Quadtree Displacement Mapping . . . . . . . . . . . . . . . . . . . 125
1.5 Self-Shadowing . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 134
1.6 Ambient Occlusion . . . . . . . . . . . . . . . . . . . . . . . . . . 138
1.7 Surface Blending . . . . . . . . . . . . . . . . . . . . . . . . . . . . 139
1.8 General Advice . . . . . . . . . . . . . . . . . . . . . . . . . . . . 146
1.9 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 147
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 148
## 2 NPR Effects Using the Geometry Shader 149
Pedro Hermosilla and Pere-Pau Vázquez
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 149
2.2 Previous Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 149
2.3 Silhouette Rendering . . . . . . . . . . . . . . . . . . . . . . . . . 151
2.4 Pencil Rendering . . . . . . . . . . . . . . . . . . . . . . . . . . . . 159
2.5 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . 164
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 164
## 3 Alpha Blending as a Post-Process 167
Benjamin Hathaway
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 167
3.2 The Alternatives . . . . . . . . . . . . . . . . . . . . . . . . . . . . 168
3.3 The Source Artwork . . . . . . . . . . . . . . . . . . . . . . . . . . 169
3.4 Initial Attempts . . . . . . . . . . . . . . . . . . . . . . . . . . . . 170
3.5 The Screen-Space Alpha Mask . . . . . . . . . . . . . . . . . . . . 170x Contents
3.6 Alpha Reference Issues . . . . . . . . . . . . . . . . . . . . . . . . 179
3.7 Rendering Pipeline Integration . . . . . . . . . . . . . . . . . . . . 181
3.8 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 181
3.9 Demo . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 182
3.10 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . 183
3.11 Source Code . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 183
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 183
## 4 Virtual Texture Mapping 101 185
Matthäus G. Chajdas, Christian Eisenacher, Marc Stamminger,
and Sylvain Lefebvre
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 185
4.2 Virtual Texture Mapping . . . . . . . . . . . . . . . . . . . . . . . 185
4.3 Implementation Details . . . . . . . . . . . . . . . . . . . . . . . . 189
4.4 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 193
4.5 Shader Code . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 193
4.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . 194
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 194
# IV Global Illumination 197
Carsten Dachsbacher, editor
## 1 Fast, Stencil-Based Multiresolution Splatting for Indirect Illumination 199
Chris Wyman, Greg Nichols, and Jeremy Shopf
1.1 Quick Review: Instant Radiosity . . . . . . . . . . . . . . . . . . . 200
1.2 Quick Review: Reflective Shadow Maps . . . . . . . . . . . . . . . 201
1.3 Multiresolution Splatting . . . . . . . . . . . . . . . . . . . . . . . 202
1.4 Fast Stencil-Based Multiresolution Splatting . . . . . . . . . . . . 206
1.5 Results and Analysis . . . . . . . . . . . . . . . . . . . . . . . . . 210
1.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 212
1.7 Demo and Source . . . . . . . . . . . . . . . . . . . . . . . . . . . 212
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 213
## 2 Screen-Space Directional Occlusion 215
Thorsten Grosch and Tobias Ritschel
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 215
2.2 Screen-Space Ambient Occlusion . . . . . . . . . . . . . . . . . . . 216
2.3 Screen-Space Directional Occlusion . . . . . . . . . . . . . . . . . 218
2.4 Interleaved Sampling . . . . . . . . . . . . . . . . . . . . . . . . . 227
2.5 Discussion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 228Contents xi
2.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 229
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 229
## 3 Real-Time Multi-Bounce Ray-Tracing with Geometry Impostors 231
Péter Dancsik and László Szécsi
3.1 Geometry Impostors . . . . . . . . . . . . . . . . . . . . . . . . . . 232
3.2 Intersection Computation with an Environment Distance Impostor 234
3.3 Ray-Object Intersection Using Distance Impostors . . . . . . . . . 236
3.4 Ray-Object Intersection Using Height Maps . . . . . . . . . . . . 236
3.5 Tracing Multiple Refractions within a Single Object . . . . . . . . 238
3.6 Multiple Ray Bounces with Object Impostors Only . . . . . . . . 238
3.7 Multiple Ray Bounces with Environment Distance Impostors Only 238
3.8 Combination of Environment and Object Impostors . . . . . . . . 239
3.9 Caustics and Shadows . . . . . . . . . . . . . . . . . . . . . . . . . 240
3.10 Example Application: Glass Chess . . . . . . . . . . . . . . . . . . 241
3.11 Example Application: Alien Pool . . . . . . . . . . . . . . . . . . 242
3.12 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 243
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 243
# V Image Space 245
Christopher Oat, editor
## 1 Anisotropic Kuwahara Filtering on the GPU 247
Jan Eric Kyprianidis, Henry Kang, and Jürgen Döllner
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 247
1.2 Kuwahara Filtering . . . . . . . . . . . . . . . . . . . . . . . . . . 248
1.3 Generalized Kuwahara Filtering . . . . . . . . . . . . . . . . . . . 251
1.4 Anisotropic Kuwahara Filtering . . . . . . . . . . . . . . . . . . . 255
1.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 263
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 263
## 2 Edge Anti-aliasing by Post-Processing 265
Hugh Malan
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 265
2.2 Finding the Nearest Silhouette Edge . . . . . . . . . . . . . . . . . 268
2.3 The Post-Process . . . . . . . . . . . . . . . . . . . . . . . . . . . 271
2.4 Refinements . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 273
2.5 GPU Implementation and Results . . . . . . . . . . . . . . . . . . 275
2.6 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 278
2.7 Other Applications . . . . . . . . . . . . . . . . . . . . . . . . . . 280
2.8 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 288
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 289xii Contents
## 3 Environment Mapping with Floyd-Steinberg Halftoning 291
László Szirmay-Kalos, László Szécsi, and Anton Penzov
3.1 Parametrization of the Environment Map . . . . . . . . . . . . . . 292
3.2 Importance Sampling . . . . . . . . . . . . . . . . . . . . . . . . . 294
3.3 Proposed Solution . . . . . . . . . . . . . . . . . . . . . . . . . . . 296
3.4 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 303
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 303
## 4 Hierarchical Item Buffers for Granular Occlusion Culling 305
Thomas Engelhardt and Carsten Dachsbacher
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 305
4.2 Hierarchical Item Buffers . . . . . . . . . . . . . . . . . . . . . . . 306
4.3 Application . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 311
4.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 312
4.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 314
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 314
## 5 Realistic Depth of Field in Postproduction 315
David Illes and Peter Horvath
5.1 Depth-of-Field Equations . . . . . . . . . . . . . . . . . . . . . . . 315
5.2 Camera Lens Simulation . . . . . . . . . . . . . . . . . . . . . . . 317
5.3 Exposure Simulation . . . . . . . . . . . . . . . . . . . . . . . . . 317
5.4 CUDA-Accelerated Computation . . . . . . . . . . . . . . . . . . . 321
5.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 323
5.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 325
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 325
## 6 Real-Time Screen Space Cloud Lighting 327
Kaori Kubota
6.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 327
6.2 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . . 328
6.3 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 331
6.4 Extensions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 332
6.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 333
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 333
## 7 Screen-Space Subsurface Scattering 335
Jorge Jimenez and Diego Gutierrez
7.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 335
7.2 The Texture-Space Approach . . . . . . . . . . . . . . . . . . . . . 336
7.3 The Screen-Space Approach . . . . . . . . . . . . . . . . . . . . . 339Contents xiii
7.4 Model Preparation . . . . . . . . . . . . . . . . . . . . . . . . . . . 347
7.5 Discussion of Results . . . . . . . . . . . . . . . . . . . . . . . . . 347
7.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 350
7.7 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . 351
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 351
# VI Handheld Devices 353
Kristof Beets, editor
## 1 Migration to OpenGL ES 2.0 355
Ken Catterall
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 355
1.2 Key API Differences . . . . . . . . . . . . . . . . . . . . . . . . . . 356
1.3 The Shader Language . . . . . . . . . . . . . . . . . . . . . . . . . 360
1.4 Initialization . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 362
1.5 Basic Shaders: Implementing the Fixed-Function Pipeline . . . . . 363
1.6 Advanced Effects Made Easy . . . . . . . . . . . . . . . . . . . . . 368
1.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 373
1.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . 373
## 2 Touchscreen-Based User Interaction 375
Andrea Bizzotto
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 375
2.2 Motion Estimation . . . . . . . . . . . . . . . . . . . . . . . . . . 375
2.3 Position Prediction . . . . . . . . . . . . . . . . . . . . . . . . . . 378
2.4 Application: Controlling a Camera in a Spherical Coordinate
System . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 379
2.5 Algorithm Overview . . . . . . . . . . . . . . . . . . . . . . . . . . 381
2.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 383
2.7 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . 383
## 3 iPhone 3GS Graphics Development and Optimization Strategies 385
Andrew Senior
3.1 Software Development Kits . . . . . . . . . . . . . . . . . . . . . . 385
3.2 General Optimization Strategies . . . . . . . . . . . . . . . . . . . 389
3.3 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 395
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 395xiv Contents
## 4 Optimizing a 3D UI Engine for Mobile Devices 397
Hyunwoo Ki
4.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 398
4.2 Optimization Methods . . . . . . . . . . . . . . . . . . . . . . . . 399
4.3 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 410
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 410
# VII Shadows 413
Wolfgang Engel, editor
## 1 Fast Conventional Shadow Filtering 415
Holger Gruen
1.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 415
1.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 415
1.3 Uniform Shadow Filtering . . . . . . . . . . . . . . . . . . . . . . 416
1.4 Separable Shadow Filters . . . . . . . . . . . . . . . . . . . . . . . 420
1.5 Nonseparable Unique Weights per PCF Result . . . . . . . . . . . 428
1.6 Advanced Shadow Filtering Techniques . . . . . . . . . . . . . . . 430
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 445
## 2 Hybrid Min/Max Plane-Based Shadow Maps 447
Holger Gruen
2.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 447
2.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 447
2.3 Construction of an HPSM . . . . . . . . . . . . . . . . . . . . . . 448
2.4 Using an HPSM . . . . . . . . . . . . . . . . . . . . . . . . . . . . 453
2.5 Other Uses for the HPSM . . . . . . . . . . . . . . . . . . . . . . 454
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 454
## 3 Shadow Mapping for Omnidirectional Light Using Tetrahedron Mapping 455
Hung-Chien Liao
3.1 Shadow Mapping . . . . . . . . . . . . . . . . . . . . . . . . . . . 455
3.2 Tetrahedron Shadow Mapping . . . . . . . . . . . . . . . . . . . . 455
3.3 Optimization . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 464
3.4 Lookup Map . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 465
3.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 470
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 475Contents xv
## 4 Screen Space Soft Shadows 477
Jesus Gumbau, Miguel Chover, and Mateu Sbert
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 477
4.2 Previous Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 479
4.3 Screen Space Soft Shadows . . . . . . . . . . . . . . . . . . . . . . 480
4.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 485
4.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 488
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 490
# VIII 3D Engine Design 493
Wolfgang Engel, editor
## 1 Multi-Fragment Effects on the GPU Using Bucket Sort 495
Meng-Cheng Huang, Fang Liu, Xue-Hui Liu, and En-Hua Wu
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 495
1.2 Design of Bucket Array . . . . . . . . . . . . . . . . . . . . . . . . 496
1.3 The Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 497
1.4 Multi-pass Approach . . . . . . . . . . . . . . . . . . . . . . . . . 498
1.5 The Adaptive Scheme . . . . . . . . . . . . . . . . . . . . . . . . . 498
1.6 Applications . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 503
1.7 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 507
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 507
## 2 Parallelized Light Pre-Pass Rendering with the Cell Broadband Engine 509
Steven Tovey and Stephen McAuley
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 509
2.2 Light Pre-Pass Rendering . . . . . . . . . . . . . . . . . . . . . . . 510
2.3 The PLAYSTATION3 and the CBE . . . . . . . . . . . . . . . . . 512
2.4 GPU/SPE Synchronization . . . . . . . . . . . . . . . . . . . . . . 513
2.5 The Pre-pass . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 515
2.6 The Lighting SPE Program . . . . . . . . . . . . . . . . . . . . . . 516
2.7 The Main Pass . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 523
2.8 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 524
2.9 Further Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 524
2.10 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . 526
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 526xvi Contents
## 3 Porting Code between Direct3D9 and OpenGL 2.0 529
Wojciech Sterna
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 529
3.2 General Issues . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 529
3.3 Resources Management . . . . . . . . . . . . . . . . . . . . . . . . 533
3.4 Notes on Debugging . . . . . . . . . . . . . . . . . . . . . . . . . . 538
3.5 A Word on Sample Application . . . . . . . . . . . . . . . . . . . 539
3.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 539
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 540
## 4 Practical Thread Rendering for DirectX 9 541
David Pangerl
4.1 Abstract . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 541
4.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 541
4.3 Solution . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 542
4.4 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 546
4.5 Future Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 546
# IX Game Postmortems 547
Matthias Wloka, editor
## 1 Stylized Rendering in Spore 549
Shalin Shodhan and Andrew Willmott
1.1 Filter Chain System . . . . . . . . . . . . . . . . . . . . . . . . . . 549
1.2 Fun with Filters . . . . . . . . . . . . . . . . . . . . . . . . . . . . 554
1.3 Cheats . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 560
## 2 Rendering Techniques in Call of Juarez: Bound in Blood 561
Pawel Rohleder and Maciej Jamrozik
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 561
2.2 Deferred Shading . . . . . . . . . . . . . . . . . . . . . . . . . . . 561
2.3 Single Frame of CoJ:BiB, The Black Magic . . . . . . . . . . . . . 563
2.4 What Else Do We Have? . . . . . . . . . . . . . . . . . . . . . . . 567
2.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 568
2.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . 569
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 569Contents xvii
## 3 Making it Large, Beautiful, Fast, and Consistent: Lessons Learned
Developing Just Cause 2 571
Emil Persson
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 571
3.2 Making it Large and Beautiful . . . . . . . . . . . . . . . . . . . . 571
3.3 Making it Consistent . . . . . . . . . . . . . . . . . . . . . . . . . 585
3.4 Making it Fast . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 591
3.5 Conclusion and Future Work . . . . . . . . . . . . . . . . . . . . . 595
3.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . 595
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 596
## 4 Destructible Volumetric Terrain 597
Marek Rosa
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 597
4.2 Converting Custom 3D Models into Voxel Representations . . . . 598
4.3 Memory Requirements for Large Voxel Maps . . . . . . . . . . . 600
4.4 Polygonization from Voxels to Triangles . . . . . . . . . . . . . . . 601
4.5 Seamless Texture-Mapping for Free-Form Surfaces . . . . . . . . . 602
4.6 Reducing Repeated Texture Patterns . . . . . . . . . . . . . . . . 603
4.7 Tangent Space Calculation in the Pixel Shader . . . . . . . . . . . 604
4.8 Multi-material Voxel Maps . . . . . . . . . . . . . . . . . . . . . . 604
4.9 Level of Detail . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 606
4.10 Ambient Light . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 607
4.11 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 608
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 608
# X Beyond Pixels and Triangles 611
Sebastien St-Laurent, editor
## 1 Parallelized Implementation of Universal Visual Computer 613
Tze-Yui Ho, Ping-Man Lam, and Chi-Sing Leung
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 613
1.2 Background . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 614
1.3 CNN Implementation . . . . . . . . . . . . . . . . . . . . . . . . . 615
1.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 620
1.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 622
1.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . 622
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 622xviii Contents
## 2 Accelerating Virtual Texturing Using CUDA 623
Charles-Frederik Hollemeersch, Bart Pieters, Peter Lambert,
and Rik Van de Walle
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 624
2.2 Implementing Virtual Texturing . . . . . . . . . . . . . . . . . . . 626
2.3 Rendering with Virtual Texturing . . . . . . . . . . . . . . . . . . 628
2.4 GPU-Based Acceleration . . . . . . . . . . . . . . . . . . . . . . . 631
2.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 640
2.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 641
2.7 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . 641
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 641
## 3 Efficient Rendering of Highly Detailed Volumetric Scenes with
GigaVoxels 643
Cyril Crassin, Fabrice Neyret, Miguel Sainz, and Elmar Eisemann
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 643
3.2 Voxel Representations . . . . . . . . . . . . . . . . . . . . . . . . . 644
3.3 The GigaVoxels Approach . . . . . . . . . . . . . . . . . . . . . . 645
3.4 Data Structure . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 646
3.5 Rendering . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 650
3.6 Out-of-Core Data Management . . . . . . . . . . . . . . . . . . . . 656
3.7 Octree-Based Synthesis . . . . . . . . . . . . . . . . . . . . . . . . 670
3.8 Voxel Object Instancing . . . . . . . . . . . . . . . . . . . . . . . . 672
3.9 MipMap-Based Blur Effects . . . . . . . . . . . . . . . . . . . . . 673
3.10 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 676
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 677
## 4 Spatial Binning on the GPU 679
Christopher Oat, Joshua Barczak, and Jeremy Shopf
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 679
4.2 Binning . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 680
4.3 Applications . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 684
4.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 687
4.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 690
4.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . . 691
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 691Contents xix
## 5 Real-Time Interaction between Particles and the Dynamic Mesh on
the GPU 693
Vlad Alexandrov
5.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 693
5.2 Process Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . 693
5.3 Sorting the Triangles . . . . . . . . . . . . . . . . . . . . . . . . . 694
5.4 Building the Buffer Map . . . . . . . . . . . . . . . . . . . . . . . 699
5.5 Addressing the Buffer . . . . . . . . . . . . . . . . . . . . . . . . . 702
5.6 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 705
5.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 705
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 706