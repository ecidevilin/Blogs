# I Geometry Manipulation 1
Wolfgang Engel, editor
## 1 Vertex Shader Tessellation 3
Holger Gruen
1.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 3
1.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 3
1.3 The Basic Vertex Shader Tessellation Algorithm . . . . . . . . 4
1.4 Per-Edge Fractional Tessellation Factors . . . . . . . . . . . . . 7
1.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 11
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 12
## 2 Real-Time Deformable Terrain Rendering with DirectX 11 13
Egor Yusov
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . 13
2.2 Algorithm Overview . . . . . . . . . . . . . . . . . . . . . . . . 15
2.3 Compressed Multiresolution Terrain Representation . . . . . . 15
2.4 Hardware-Accelerated Terrain Tessellation . . . . . . . . . . . 23
2.5 Texturing . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 31
2.6 Dynamic Modifications . . . . . . . . . . . . . . . . . . . . . . 33
2.7 Implementation Details . . . . . . . . . . . . . . . . . . . . . . 34
2.8 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . 36
2.9 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 38
2.10 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . 38
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 38
vvi Contents
## 3 Optimized Stadium Crowd Rendering 41
Alan Chambers
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 41
3.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 42
3.3 Content Pipeline . . . . . . . . . . . . . . . . . . . . . . . . . . 43
3.4 Rendering . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 47
3.5 Further Optimizations . . . . . . . . . . . . . . . . . . . . . . . 60
3.6 Limitations . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 67
3.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 67
3.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 68
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 68
## 4 Geometric Antialiasing Methods 71
Emil Persson
4.1 Introduction and Previous Work . . . . . . . . . . . . . . . . . 71
4.2 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 71
4.3 Conclusion and Future Work . . . . . . . . . . . . . . . . . . . 86
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 87
# II Rendering 89
Christopher Oat, editor
## 1 Practical Elliptical Texture Filtering on the GPU 91
Pavlos Mavridis and Georgios Papaioannou
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 91
1.2 Elliptical Filtering . . . . . . . . . . . . . . . . . . . . . . . . . 92
1.3 Elliptical Footprint Approximation . . . . . . . . . . . . . . . . 97
1.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 101
1.5 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 103
1.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 103
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 103
## 2 An Approximation to the Chapman Grazing-Incidence Function for
Atmospheric Scattering 105
Christian Schuler ¨
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 105
2.2 Atmospheric Scattering . . . . . . . . . . . . . . . . . . . . . . 105
2.3 The Chapman Function . . . . . . . . . . . . . . . . . . . . . . 107
2.4 Towards a Real-Time Approximation . . . . . . . . . . . . . . . 109
2.5 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 111
2.6 Putting the Chapman Function to Use . . . . . . . . . . . . . . 114
2.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 115Contents vii
2.8 Appendix . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 117
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 117
## 3 Volumetric Real-Time Water and Foam Rendering 119
Daniel Scherzer, Florian Bagar, and Oliver Mattausch
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 119
3.2 Simulation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 120
3.3 Rendering . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 122
3.4 Artist Control . . . . . . . . . . . . . . . . . . . . . . . . . . . . 129
3.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 131
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 131
## 4 CryENGINE 3: Three Years of Work in Review 133
Tiago Sousa, Nickolay Kasyan, and Nicolas Schulz
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 133
4.2 Going Multiplatform . . . . . . . . . . . . . . . . . . . . . . . . 134
4.3 Physically Based Rendering . . . . . . . . . . . . . . . . . . . . 137
4.4 Forward Shading Passes . . . . . . . . . . . . . . . . . . . . . . 155
4.5 Batched HDR Postprocessing . . . . . . . . . . . . . . . . . . . 158
4.6 Stereoscopic 3D . . . . . . . . . . . . . . . . . . . . . . . . . . . 163
4.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 167
4.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 167
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 167
## 5 Inexpensive Antialiasing of Simple Objects 169
Mikkel Gjøl and Mark Gjøl
5.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 169
5.2 Antialiasing via Smoothed Lines . . . . . . . . . . . . . . . . . 169
5.3 Rendering Lines . . . . . . . . . . . . . . . . . . . . . . . . . . 171
5.4 Discussion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 175
5.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 176
5.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 177
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 177
# III Global Illumination Effects 179
Carsten Dachsbacher, editor
## 1 Ray-Traced Approximate Reflections Using a Grid of Oriented Splats 181
Holger Gruen
1.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 181
1.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . 181viii Contents
1.3 The Basic Algorithm . . . . . . . . . . . . . . . . . . . . . . . . 182
1.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 187
1.5 Future Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 189
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 190
## 2 Screen-Space Bent Cones: A Practical Approach 191
Oliver Klehm, Tobias Ritschel, Elmar Eisemann, and Hans-Peter Seidel
2.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 191
2.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 191
2.3 Ambient Occlusion . . . . . . . . . . . . . . . . . . . . . . . . . 192
2.4 Our Technique . . . . . . . . . . . . . . . . . . . . . . . . . . . 195
2.5 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 199
2.6 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 202
2.7 Discussion and Conclusion . . . . . . . . . . . . . . . . . . . . . 205
2.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 206
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 206
## 3 Real-Time Near-Field Global Illumination Based on a Voxel Model 209
Sinje Thiedemann, Niklas Henrich, Thorsten Grosch, and Stefan Muller ¨
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 209
3.2 Binary Boundary Voxelization . . . . . . . . . . . . . . . . . . . 210
3.3 Hierarchical Ray/Voxel Intersection Test . . . . . . . . . . . . . 215
3.4 Near-Field Indirect Illumination . . . . . . . . . . . . . . . . . . 222
3.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 225
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 228
# IV Shadows 231
Wolfgang Engel, editor
## 1 Efficient Online Visibility for Shadow Maps 233
Oliver Mattausch, Jiri Bittner, Ari Silvennoinen, Daniel Scherzer,
and Michael Wimmer
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 233
1.2 Algorithm Overview . . . . . . . . . . . . . . . . . . . . . . . . 234
1.3 Detailed Description . . . . . . . . . . . . . . . . . . . . . . . . 236
1.4 Optimization: Shadow-Map Focusing . . . . . . . . . . . . . . . 238
1.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 239
1.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 241
1.7 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . 241
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 241Contents ix
## 2 Depth Rejected Gobo Shadows 243
John White
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 243
2.2 Basic Gobo Shadows . . . . . . . . . . . . . . . . . . . . . . . . 243
2.3 Depth Rejected Gobo Shadows . . . . . . . . . . . . . . . . . . 245
2.4 Extensions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 247
2.5 Failure Case . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 248
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 248
# V 3D Engine Design 249
Wessam Bahnassi, editor
## 1 Z3 Culling 251
Pascal Gautron, Jean-Eudes Marvie, and Ga¨el Sourimant
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 251
1.2 Principle . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 253
1.3 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 253
1.4 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 254
1.5 Performance Analysis . . . . . . . . . . . . . . . . . . . . . . . 261
1.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 263
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 263
## 2 A Quaternion-Based Rendering Pipeline 265
Dzmitry Malyshau
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 265
2.2 Spatial Data . . . . . . . . . . . . . . . . . . . . . . . . . . . . 265
2.3 Handedness Bit . . . . . . . . . . . . . . . . . . . . . . . . . . . 266
2.4 Facts about Quaternions . . . . . . . . . . . . . . . . . . . . . . 267
2.5 Tangent Space . . . . . . . . . . . . . . . . . . . . . . . . . . . 268
2.6 Interpolation Problem with Quaternions . . . . . . . . . . . . . 270
2.7 KRI Engine: An Example Application . . . . . . . . . . . . . . 271
2.8 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 272
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 273
## 3 Implementing a Directionally Adaptive Edge AA Filter Using
DirectX 11 275
Matthew Johnson
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 275
3.2 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 285
3.3 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 288x Contents
3.4 Appendix . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 289
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 290
## 4 Designing a Data-Driven Renderer 291
Donald Revie
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 291
4.2 Problem Analysis . . . . . . . . . . . . . . . . . . . . . . . . . . 292
4.3 Solution Development . . . . . . . . . . . . . . . . . . . . . . . 304
4.4 Representational Objects . . . . . . . . . . . . . . . . . . . . . 307
4.5 Pipeline Objects . . . . . . . . . . . . . . . . . . . . . . . . . . 310
4.6 Frame Graph . . . . . . . . . . . . . . . . . . . . . . . . . . . . 313
4.7 Case Study: Praetorian Tech . . . . . . . . . . . . . . . . . . . 314
4.8 Further Work and Considerations . . . . . . . . . . . . . . . . . 317
4.9 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 318
4.10 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 318
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 318
# VI GPGPU 321
Sebastien St-Laurent, editor
## 1 Volumetric Transparency with Per-Pixel Fragment Lists 323
L´aszl´ o Sz´ecsi, P´al Barta, and Bal´azs Kov´acs
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 323
1.2 Light Transport Model . . . . . . . . . . . . . . . . . . . . . . . 324
1.3 Ray Decomposition . . . . . . . . . . . . . . . . . . . . . . . . . 325
1.4 Finding Intersections with Ray Casting . . . . . . . . . . . . . 327
1.5 Application for Particle System Rendering . . . . . . . . . . . . 330
1.6 Finding Intersections with Rasterization . . . . . . . . . . . . . 331
1.7 Adding Surface Reflection . . . . . . . . . . . . . . . . . . . . . 333
1.8 Shadow Volumes . . . . . . . . . . . . . . . . . . . . . . . . . . 333
1.9 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 334
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 335
## 2 Practical Binary Surface and Solid Voxelization with Direct3D 11 337
Michael Schwarz
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 337
2.2 Rasterization-Based Surface Voxelization . . . . . . . . . . . . . 338
2.3 Rasterization-Based Solid Voxelization . . . . . . . . . . . . . . 342
2.4 Conservative Surface Voxelization with DirectCompute . . . . . 344
2.5 Solid Voxelization with DirectCompute . . . . . . . . . . . . . . 349Contents xi
2.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 351
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 352
## 3 Interactive Ray Tracing Using the Compute Shader in DirectX 11 353
Arturo Garc´ıa, Francisco Avila, Sergio Murgu ´ ´ıa, and Leo Reyes
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 353
3.2 Ray Tracing . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 354
3.3 Our Implementation . . . . . . . . . . . . . . . . . . . . . . . . 357
3.4 Primary Rays Stage . . . . . . . . . . . . . . . . . . . . . . . . 361
3.5 Intersection Stage . . . . . . . . . . . . . . . . . . . . . . . . . . 363
3.6 Color Stage . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 367
3.7 Multipass Approach . . . . . . . . . . . . . . . . . . . . . . . . 371
3.8 Results and Discussion . . . . . . . . . . . . . . . . . . . . . . . 371
3.9 Optimization . . . . . . . . . . . . . . . . . . . . . . . . . . . . 373
3.10 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 374
3.11 Further Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 374
3.12 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 375
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 376