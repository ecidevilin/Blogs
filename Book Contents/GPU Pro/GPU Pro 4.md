# I Geometry Manipulation 1
Wolfgang Engel
## 1 GPU Terrain Subdivision and Tessellation 3
Benjamin Mistal
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 3
1.2 The Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . 4
1.3 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
1.4 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 20
## 2 Introducing the Programmable Vertex Pulling Rendering Pipeline 21
Christophe Riccio and Sean Lilley
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
2.2 Draw Submission Limitations and Objectives . . . . . . . . . . 22
2.3 Evaluating Draw Call CPU Overhead and the GPU Draw
Submission Limitation . . . . . . . . . . . . . . . . . . . . . . . 23
2.4 Programmable Vertex Pulling . . . . . . . . . . . . . . . . . . . 28
2.5 Side Effects of the Software Design . . . . . . . . . . . . . . . . 34
2.6 Future Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 35
2.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 36
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 37
## 3 A WebGL Globe Rendering Pipeline 39
Patrick Cozzi and Daniel Bagnell
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 39
3.2 Rendering Pipeline Overview . . . . . . . . . . . . . . . . . . . 39
vvi Contents
3.3 Filling Cracks in Screen Space . . . . . . . . . . . . . . . . . . . 40
3.4 Filling Poles in Screen Space . . . . . . . . . . . . . . . . . . . 42
3.5 Overlaying Vector Data . . . . . . . . . . . . . . . . . . . . . . 44
3.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 47
3.7 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 47
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 48
# II Rendering 49
Christopher Oat and Carsten Dachsbacher
## 1 Practical Planar Reflections Using Cubemaps and Image Proxies 51
S´ebastien Lagarde and Antoine Zanuttini
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 51
1.2 Generating Reflection Textures . . . . . . . . . . . . . . . . . . 52
1.3 Using Reflection Textures . . . . . . . . . . . . . . . . . . . . . 63
1.4 Conclusion and Future Work . . . . . . . . . . . . . . . . . . . 66
1.5 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 67
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 67
## 2 Real-Time Ptex and Vector Displacement 69
Karl Hillesland
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 69
2.2 Packed Ptex . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 70
2.3 Runtime Implementation . . . . . . . . . . . . . . . . . . . . . . 72
2.4 Adding Displacement . . . . . . . . . . . . . . . . . . . . . . . . 75
2.5 Performance Costs . . . . . . . . . . . . . . . . . . . . . . . . . 76
2.6 Memory Costs . . . . . . . . . . . . . . . . . . . . . . . . . . . 78
2.7 Alternatives and Future Work . . . . . . . . . . . . . . . . . . . 79
2.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 79
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 80
## 3 Decoupled Deferred Shading on the GPU 81
G´abor Liktor and Carsten Dachsbacher
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 81
3.2 Decoupled Sampling in a Rasterization Pipeline . . . . . . . . . 82
3.3 Shading Reuse for Deferred Shading . . . . . . . . . . . . . . . 84
3.4 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 87
3.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 93
3.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 97
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 97Contents vii
## 4 Tiled Forward Shading 99
Markus Billeter, Ola Olsson, and Ulf Assarsson
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 99
4.2 Recap: Forward, Deferred, and Tiled Shading . . . . . . . . . . 101
4.3 Tiled Forward Shading: Why? . . . . . . . . . . . . . . . . . . 104
4.4 Basic Tiled Forward Shading . . . . . . . . . . . . . . . . . . . 104
4.5 Supporting Transparency . . . . . . . . . . . . . . . . . . . . . 106
4.6 Support for MSAA . . . . . . . . . . . . . . . . . . . . . . . . . 109
4.7 Supporting Different Shaders . . . . . . . . . . . . . . . . . . . 111
4.8 Conclusion and Further Improvements . . . . . . . . . . . . . . 111
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 113
## 5 Forward+: A Step Toward Film-Style Shading in Real Time 115
Takahiro Harada, Jay McKee, and Jason C. Yang
5.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 115
5.2 Forward+ . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 116
5.3 Implementation and Optimization . . . . . . . . . . . . . . . . 117
5.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 123
5.5 Forward+ in the AMD Leo Demo . . . . . . . . . . . . . . . . . 124
5.6 Extensions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 127
5.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 133
5.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 134
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 134
## 6 Progressive Screen-Space Multichannel Surface Voxelization 137
Athanasios Gaitatzes and Georgios Papaioannou
6.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 137
6.2 Overview of Voxelization Method . . . . . . . . . . . . . . . . . 138
6.3 Progressive Voxelization for Lighting . . . . . . . . . . . . . . . 144
6.4 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 145
6.5 Performance and Evaluation . . . . . . . . . . . . . . . . . . . . 145
6.6 Limitations . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 151
6.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 153
6.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 153
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 153
## 7 Rasterized Voxel-Based Dynamic Global Illumination 155
Hawar Doghramachi
7.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 155
7.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 155
7.3 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 156
7.4 Handling Large Environments . . . . . . . . . . . . . . . . . . . 168viii Contents
7.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 168
7.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 169
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 171
# III Image Space 173
Michal Valient
## 1 The Skylanders SWAP Force Depth-of-Field Shader 175
Michael Bukowski, Padraic Hennessy, Brian Osman, and Morgan McGuire
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 175
1.2 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 177
1.3 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 184
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 184
## 2 Simulating Partial Occlusion in Post-Processing
Depth-of-Field Methods 187
David C. Schedl and Michael Wimmer
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 187
2.2 Depth of Field . . . . . . . . . . . . . . . . . . . . . . . . . . . 187
2.3 Algorithm Overview . . . . . . . . . . . . . . . . . . . . . . . . 189
2.4 Rendering . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 190
2.5 Scene Decomposition . . . . . . . . . . . . . . . . . . . . . . . . 190
2.6 Blurring and Composition . . . . . . . . . . . . . . . . . . . . . 194
2.7 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 197
2.8 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 198
2.9 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 199
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 199
## 3 Second-Depth Antialiasing 201
Emil Persson
3.1 Introduction and Previous Work . . . . . . . . . . . . . . . . . 201
3.2 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 202
3.3 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 209
3.4 Conclusion and Future Work . . . . . . . . . . . . . . . . . . . 211
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 211
## 4 Practical Framebuffer Compression 213
Pavlos Mavridis and Georgios Papaioannou
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 213
4.2 Color Space Conversion . . . . . . . . . . . . . . . . . . . . . . 214
4.3 Chrominance Multiplexing . . . . . . . . . . . . . . . . . . . . . 215
4.4 Chrominance Reconstruction . . . . . . . . . . . . . . . . . . . 217Contents ix
4.5 Antialiasing . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 221
4.6 Blending . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 222
4.7 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 222
4.8 Conclusion and Discussion . . . . . . . . . . . . . . . . . . . . . 224
4.9 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 225
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 225
## 5 Coherence-Enhancing Filtering on the GPU 227
Jan Eric Kyprianidis and Henry Kang
5.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 227
5.2 Local Orientation Estimation . . . . . . . . . . . . . . . . . . . 229
5.3 Flow-Guided Smoothing . . . . . . . . . . . . . . . . . . . . . . 238
5.4 Shock Filter . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 243
5.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 248
5.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 248
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 248
# IV Shadows 251
Wolfgang Engel
## 1 Real-Time Deep Shadow Maps 253
Ren´e F¨ urst, Oliver Mattausch, and Daniel Scherzer
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 253
1.2 Transmittance Function . . . . . . . . . . . . . . . . . . . . . . 255
1.3 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 255
1.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 262
1.5 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 263
1.6 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 264
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 264
# V Game Engine Design 265
Wessam Bahnassi
## 1 An Aspect-Based Engine Architecture 267
Donald Revie
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 267
1.2 Rationale . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 267
1.3 Engine Core . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 268
1.4 Aspects . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 272
1.5 Common Aspects . . . . . . . . . . . . . . . . . . . . . . . . . . 275x Contents
1.6 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 277
1.7 Aspect Interactions . . . . . . . . . . . . . . . . . . . . . . . . . 278
1.8 Praetorian: The Brief History of Aspects . . . . . . . . . . . . . 281
1.9 Analysis . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 282
1.10 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 283
1.11 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 283
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 284
## 2 Kinect Programming with Direct3D 11 285
Jason Zink
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 285
2.2 Meet the Kinect . . . . . . . . . . . . . . . . . . . . . . . . . . 285
2.3 Mathematics of the Kinect . . . . . . . . . . . . . . . . . . . . . 289
2.4 Programming with the Kinect SDK . . . . . . . . . . . . . . . . 292
2.5 Applications of the Kinect . . . . . . . . . . . . . . . . . . . . . 300
2.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 302
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 302
## 3 A Pipeline for Authored Structural Damage 303
Homam Bahnassi and Wessam Bahnassi
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 303
3.2 The Addressed Problem . . . . . . . . . . . . . . . . . . . . . . 303
3.3 Challenges and Previous Work . . . . . . . . . . . . . . . . . . 304
3.4 Implementation Description and Details . . . . . . . . . . . . . 305
3.5 Level of Detail . . . . . . . . . . . . . . . . . . . . . . . . . . . 313
3.6 Discussion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 314
3.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 314
3.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 314
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 315
# VI GPGPU 317
S´ebastien St-Laurent
## 1 Bit-Trail Traversal for Stackless LBVH on DirectCompute 319
Sergio Murgu´ıa, Francisco Avila, Leo Reyes, and Arturo Garc´ ´ ıa
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 319
1.2 Ray Tracing Rendering . . . . . . . . . . . . . . . . . . . . . . . 320
1.3 Global Illumination . . . . . . . . . . . . . . . . . . . . . . . . . 320
1.4 Stackless LBVH . . . . . . . . . . . . . . . . . . . . . . . . . . . 322
1.5 The SLBVH in Action . . . . . . . . . . . . . . . . . . . . . . . 331
1.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 334
1.7 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 335
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 335Contents xi
## 2 Real-Time JPEG Compression Using DirectCompute 337
Stefan Petersson
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 337
2.2 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 342
2.3 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 352
2.4 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 355
2.5 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 355
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 355
