# I Geometry Manipulation 1
Wolfgang Engel, editor
## 1 Terrain and Ocean Rendering with Hardware Tessellation 3
Xavier Bonaventura
1.1 DirectX 11 Graphics Pipeline . . . . . . . . . . . . . . . . . . . 4
1.2 Definition of Geometry . . . . . . . . . . . . . . . . . . . . . . . 7
1.3 Vertex Position, Vertex Normal, and Texture Coordinates . . . 10
1.4 Tessellation Correction Depending on the Camera Angle . . . . 12
1.5 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 14
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 14
## 2 Practical and Realistic Facial Wrinkles Animation 15
Jorge Jimenez, Jose I. Echevarria, Christopher Oat, and Diego Gutierrez
2.1 Background . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
2.2 Our Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
2.3 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 23
2.4 Discussion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
2.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 26
2.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 26
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 26
## 3 Procedural Content Generation on the GPU 29
Aleksander Netzel and Pawel Rohleder
3.1 Abstract . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 29
3.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 29
3.3 Terrain Generation and Rendering . . . . . . . . . . . . . . . . 30
vvi Contents
3.4 Environmental Effects . . . . . . . . . . . . . . . . . . . . . . . 32
3.5 Putting It All Together . . . . . . . . . . . . . . . . . . . . . . 34
3.6 Conclusions and Future Work . . . . . . . . . . . . . . . . . . . 35
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 37
# II Rendering 39
Christopher Oat, editor
## 1 Pre-Integrated Skin Shading 41
Eric Penner and George Borshukov
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 41
1.2 Background and Previous Work . . . . . . . . . . . . . . . . . . 42
1.3 Pre-Integrating the Effects of Scattering . . . . . . . . . . . . . 42
1.4 Scattering and Diffuse Light . . . . . . . . . . . . . . . . . . . . 44
1.5 Scattering and Normal Maps . . . . . . . . . . . . . . . . . . . 47
1.6 Shadow Scattering . . . . . . . . . . . . . . . . . . . . . . . . . 48
1.7 Conclusion and Future Work . . . . . . . . . . . . . . . . . . . 51
1.8 Appendix A: Lookup Textures . . . . . . . . . . . . . . . . . . 52
1.9 Appendix B: Simplified Skin Shader . . . . . . . . . . . . . . . 53
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 54
## 2 Implementing Fur Using Deferred Shading 57
Donald Revie
2.1 Deferred Rendering . . . . . . . . . . . . . . . . . . . . . . . . . 57
2.2 Fur . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 59
2.3 Techniques . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 61
2.4 Fur Implementation Details . . . . . . . . . . . . . . . . . . . . 68
2.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 74
2.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 74
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 74
## 3 Large-Scale Terrain Rendering for Outdoor Games 77
Ferenc Pint´er
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 77
3.2 Content Creation and Editing . . . . . . . . . . . . . . . . . . . 79
3.3 Runtime Shading . . . . . . . . . . . . . . . . . . . . . . . . . . 84
3.4 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 90
3.5 Possible Extensions . . . . . . . . . . . . . . . . . . . . . . . . . 91
3.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 93
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 93Contents vii
## 4 Practical Morphological Antialiasing 95
Jorge Jimenez, Belen Masia, Jose I. Echevarria, Fernando Navarro,
and Diego Gutierrez
4.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 97
4.2 Detecting Edges . . . . . . . . . . . . . . . . . . . . . . . . . . 98
4.3 Obtaining Blending Weights . . . . . . . . . . . . . . . . . . . . 100
4.4 Blending with the Four-Neighborhood . . . . . . . . . . . . . . 105
4.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 106
4.6 Discussion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 110
4.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 111
4.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 112
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 112
## 5 Volume Decals 115
Emil Persson
5.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 115
5.2 Decals as Volumes . . . . . . . . . . . . . . . . . . . . . . . . . 115
5.3 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 120
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 120
# III Global Illumination Effects 121
Carsten Dachsbacher, editor
## 1 Temporal Screen-Space Ambient Occlusion 123
Oliver Mattausch, Daniel Scherzer, and Michael Wimmer
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 123
1.2 Ambient Occlusion . . . . . . . . . . . . . . . . . . . . . . . . . 124
1.3 Reverse Reprojection . . . . . . . . . . . . . . . . . . . . . . . . 126
1.4 Our Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . 127
1.5 SSAO Implementation . . . . . . . . . . . . . . . . . . . . . . . 134
1.6 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 137
1.7 Discussion and Limitations . . . . . . . . . . . . . . . . . . . . 140
1.8 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 140
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 141
## 2 Level-of-Detail and Streaming Optimized Irradiance Normal Mapping 143
Ralf Habel, Anders Nilsson, and Michael Wimmer
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 143
2.2 Calculating Directional Irradiance . . . . . . . . . . . . . . . . 144
2.3 H-Basis . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 146
2.4 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 149
2.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 155viii Contents
2.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 155
2.7 Appendix A: Spherical Harmonics Basis Functions
without Condon-Shortley Phase . . . . . . . . . . . . . . . . . . 157
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 157
## 3 Real-Time One-Bounce Indirect Illumination and Shadows
using Ray Tracing 159
Holger Gruen
3.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 159
3.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 159
3.3 Phase 1: Computing Indirect Illumination without Indirect Shadows . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 161
3.4 Phase 2: Constructing a 3D Grid of Blockers . . . . . . . . . . 165
3.5 Phase 3: Computing the Blocked Portion of Indirect Light . . . 168
3.6 Future Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 170
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 171
## 4 Real-Time Approximation of Light Transport in
Translucent Homogenous Media 173
Colin Barr´e-Brisebois and Marc Bouchard
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 173
4.2 In Search of Translucency . . . . . . . . . . . . . . . . . . . . . 174
4.3 The Technique: The Way Out is Through . . . . . . . . . . . . 175
4.4 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 179
4.5 Discussion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 181
4.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 182
4.7 Demo . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 183
4.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 183
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 183
## 5 Diffuse Global Illumination with Temporally Coherent
Light Propagation Volumes 185
Anton Kaplanyan, Wolfgang Engel, and Carsten Dachsbacher
5.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 185
5.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 186
5.3 Algorithm Detail Description . . . . . . . . . . . . . . . . . . . 187
5.4 Injection Stage . . . . . . . . . . . . . . . . . . . . . . . . . . . 189
5.5 Optimizations . . . . . . . . . . . . . . . . . . . . . . . . . . . . 199
5.6 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 200
5.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 202
5.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 203
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 203Contents ix
# IV Shadows 205
Wolfgang Engel, editor
## 1 Variance Shadow Maps Light-Bleeding Reduction Tricks 207
Wojciech Sterna
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 207
1.2 VSM Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . 207
1.3 Light-Bleeding . . . . . . . . . . . . . . . . . . . . . . . . . . . 209
1.4 Solutions to the Problem . . . . . . . . . . . . . . . . . . . . . . 210
1.5 Sample Application . . . . . . . . . . . . . . . . . . . . . . . . . 213
1.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 213
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 214
## 2 Fast Soft Shadows via Adaptive Shadow Maps 215
Pavlo Turchyn
2.1 Percentage-Closer Filtering with Large Kernels . . . . . . . . . 215
2.2 Application to Adaptive Shadow Maps . . . . . . . . . . . . . . 218
2.3 Soft Shadows with Variable Penumbra Size . . . . . . . . . . . 221
2.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 223
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 224
## 3 Adaptive Volumetric Shadow Maps 225
Marco Salvi, Kiril Vidimˇce, Andrew Lauritzen, Aaron Lefohn, and Matt Pharr
3.1 Introduction and Previous Approaches . . . . . . . . . . . . . . 225
3.2 Algorithm and Implementation . . . . . . . . . . . . . . . . . . 227
3.3 Comparisons . . . . . . . . . . . . . . . . . . . . . . . . . . . . 234
3.4 Conclusions and Future Work . . . . . . . . . . . . . . . . . . . 239
3.5 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 240
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 241
## 4 Fast Soft Shadows with Temporal Coherence 243
Daniel Scherzer, Michael Schw¨arzler and Oliver Mattausch
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 243
4.2 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 244
4.3 Comparison and Results . . . . . . . . . . . . . . . . . . . . . . 252
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 254
## 5 Mipmapped Screen-Space Soft Shadows 257
Alberto Aguado and Eugenia Montiel
5.1 Introduction and Previous Work . . . . . . . . . . . . . . . . . 257
5.2 Penumbra Width . . . . . . . . . . . . . . . . . . . . . . . . . 259
5.3 Screen-Space Filter . . . . . . . . . . . . . . . . . . . . . . . . 260
5.4 Filtering Shadows . . . . . . . . . . . . . . . . . . . . . . . . . . 263x Contents
5.5 Mipmap Level Selection . . . . . . . . . . . . . . . . . . . . . . 265
5.6 Multiple Occlusions . . . . . . . . . . . . . . . . . . . . . . . . 268
5.7 Discussion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 271
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 272
# V Handheld Devices 275
Kristof Beets, editor
## 1 A Shader-Based eBook Renderer 277
Andrea Bizzotto
1.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 277
1.2 Page-Peeling Effect . . . . . . . . . . . . . . . . . . . . . . . . . 278
1.3 Enabling Two Pages Side-by-Side . . . . . . . . . . . . . . . . . 283
1.4 Improving the Look and Antialiasing Edges . . . . . . . . . . . 285
1.5 Direction-Aligned Triangle Strip . . . . . . . . . . . . . . . . . 286
1.6 Performance Optimizations and Power Consumption . . . . . . 287
1.7 Putting it Together . . . . . . . . . . . . . . . . . . . . . . . . . 287
1.8 Future Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 288
1.9 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 288
1.10 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 289
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 289
## 2 Post-Processing Effects on Mobile Devices 291
Marco Weber and Peter Quayle
2.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 291
2.2 Technical Details . . . . . . . . . . . . . . . . . . . . . . . . . . 294
2.3 Case Study: Bloom . . . . . . . . . . . . . . . . . . . . . . . . . 296
2.4 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 298
2.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 304
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 305
## 3 Shader-Based Water Effects 307
Joe Davis and Ken Catterall
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 307
3.2 Techniques . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 307
3.3 Optimizations . . . . . . . . . . . . . . . . . . . . . . . . . . . . 318
3.4 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 325
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 325Contents xi
# VI 3D Engine Design 327
Wessam Bahnassi, editor
## 1 Practical, Dynamic Visibility for Games 329
Stephen Hill and Daniel Collin
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 329
1.2 Surveying the Field . . . . . . . . . . . . . . . . . . . . . . . . . 329
1.3 Query Quandaries . . . . . . . . . . . . . . . . . . . . . . . . . 330
1.4 Wish List . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 333
1.5 Conviction Solution . . . . . . . . . . . . . . . . . . . . . . . . 333
1.6 Battlefield Solution . . . . . . . . . . . . . . . . . . . . . . . . . 340
1.7 Future Development . . . . . . . . . . . . . . . . . . . . . . . . 342
1.8 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 345
1.9 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 346
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 346
## 2 Shader Amortization using Pixel Quad Message Passing 349
Eric Penner
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 349
2.2 Background and Related Work . . . . . . . . . . . . . . . . . . 349
2.3 Pixel Derivatives and Pixel Quads . . . . . . . . . . . . . . . . 350
2.4 Pixel Quad Message Passing . . . . . . . . . . . . . . . . . . . . 352
2.5 PQA Initialization . . . . . . . . . . . . . . . . . . . . . . . . . 353
2.6 Limitations of PQA . . . . . . . . . . . . . . . . . . . . . . . . 354
2.7 Cross Bilateral Sampling . . . . . . . . . . . . . . . . . . . . . 356
2.8 Convolution and Blurring . . . . . . . . . . . . . . . . . . . . . 357
2.9 Percentage Closer Filtering . . . . . . . . . . . . . . . . . . . . 359
2.10 Discussion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 365
2.11 Appendix A: Hardware Support . . . . . . . . . . . . . . . . . . 366
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 366
## 3 A Rendering Pipeline for Real-Time Crowds 369
Benjam´ın Hern´andez and Isaac Rudomin
3.1 System Overview . . . . . . . . . . . . . . . . . . . . . . . . . . 369
3.2 Populating the Virtual Environment and Behavior . . . . . . . 371
3.3 View-Frustum Culling . . . . . . . . . . . . . . . . . . . . . . . 371
3.4 Level of Detail Sorting . . . . . . . . . . . . . . . . . . . . . . . 377
3.5 Animation and Draw Instanced . . . . . . . . . . . . . . . . . . 379
3.6 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 379
3.7 Conclusions and Future Work . . . . . . . . . . . . . . . . . . . 382
3.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 383
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 383xii Contents
# VII GPGPU 385
Sebastien St-Laurent, editor
## 1 2D Distance Field Generation with the GPU 387
Philip Rideout
1.1 Vocabulary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 388
1.2 Manhattan Grassfire . . . . . . . . . . . . . . . . . . . . . . . . 390
1.3 Horizontal-Vertical Erosion . . . . . . . . . . . . . . . . . . . . 392
1.4 Saito-Toriwaki Scanning with OpenCL . . . . . . . . . . . . . . 394
1.5 Signed Distance with Two Color Channels . . . . . . . . . . . . 402
1.6 Distance Field Applications . . . . . . . . . . . . . . . . . . . . 404
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 407
## 2 Order-Independent Transparency using Per-Pixel Linked Lists 409
Nicolas Thibieroz
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 409
2.2 Algorithm Overview . . . . . . . . . . . . . . . . . . . . . . . . 409
2.3 DirectX 11 Features Requisites . . . . . . . . . . . . . . . . . . 410
2.4 Head Pointer and Nodes Buffers . . . . . . . . . . . . . . . . . 411
2.5 Per-Pixel Linked List Creation . . . . . . . . . . . . . . . . . . 413
2.6 Per-Pixel Linked Lists Traversal . . . . . . . . . . . . . . . . . . 416
2.7 Multisampling Antialiasing Support . . . . . . . . . . . . . . . 421
2.8 Optimizations . . . . . . . . . . . . . . . . . . . . . . . . . . . . 425
2.9 Tiling . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 427
2.10 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 430
2.11 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 431
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 431
## 3 Simple and Fast Fluids 433
Martin Guay, Fabrice Colin, and Richard Egli
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 433
3.2 Fluid Modeling . . . . . . . . . . . . . . . . . . . . . . . . . . . 434
3.3 Solver’s Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . 436
3.4 Code . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 440
3.5 Visualization . . . . . . . . . . . . . . . . . . . . . . . . . . . . 441
3.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 442
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 444
## 4 A Fast Poisson Solver for OpenCL using Multigrid Methods 445
Sebastien Noury, Samuel Boivin, and Olivier Le Ma^ıtre
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 445
4.2 Poisson Equation and Finite Volume Method . . . . . . . . . . 446
4.3 Iterative Methods . . . . . . . . . . . . . . . . . . . . . . . . . . 451Contents xiii
4.4 Multigrid Methods (MG) . . . . . . . . . . . . . . . . . . . . . 457
4.5 OpenCL Implementation . . . . . . . . . . . . . . . . . . . . . . 460
4.6 Benchmarks . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 468
4.7 Discussion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 470
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 470