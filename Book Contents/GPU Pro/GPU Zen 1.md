# I Geometry Manipulation 1
Christopher Oat, editor
## 1 Attributed Vertex Clouds 3
Willy Scheibel, Stefan Buschmann, Matthias Trapp, and Jurgen D ¨ ollner ¨
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 3
1.2 Concept . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 4
1.3 Applications for Attributed Vertex Clouds . . . . . . . . . . . . 5
1.4 Evaluation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 18
1.5 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 20
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
## 2 Rendering Convex Occluders with Inner Conservative
Rasterization 23
Marcus Svensson and Emil Persson
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 23
2.2 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 24
2.3 Conclusions and Future Work . . . . . . . . . . . . . . . . . . . 29
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 29
# II Lighting 31
Carsten Dachsbacher, editor
## 1 Stable Indirect Illumination 33
Holger Gruen and Louis Bavoil
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 33
1.2 Deinterleaved Texturing for RSM Sampling . . . . . . . . . . . 34
1.3 Adding Sub-image Blurs . . . . . . . . . . . . . . . . . . . . . . 38
vvi Contents
1.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 41
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 42
## 2 Participating Media Using Extruded Light Volumes 45
Nathan Hoobler, Andrei Tatarinov, and Alex Dunn
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 45
2.2 Background . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 46
2.3 Directional Lights . . . . . . . . . . . . . . . . . . . . . . . . . 51
2.4 Local Lights . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 57
2.5 Additional Optimizations . . . . . . . . . . . . . . . . . . . . . 67
2.6 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 68
2.7 Summary . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 72
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 73
# III Rendering 75
Mark Chatfield, editor
## 1 Deferred+ 77
Hawar Doghramachi and Jean-Normand Bucci
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 77
1.2 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 77
1.3 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 79
1.4 Comparison with Hierarchical
Depth Buffer-based Culling . . . . . . . . . . . . . . . . . . . . 96
1.5 Pros and Cons . . . . . . . . . . . . . . . . . . . . . . . . . . . 98
1.6 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 100
1.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 102
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 103
## 2 Programmable Per-pixel Sample Placement with
Conservative Rasterizer 105
Rahul P. Sathe
2.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 105
2.2 Background . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 105
2.3 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 106
2.4 Demo . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 114
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 114
## 3 Mobile Toon Shading 115
Felipe Lira, Felipe Chaves, Flavio Villalva, Jesus Sosa, ´
Kleverson Paix ´ ao and Te ˜ ofilo Dutra ´
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 115Contents vii
3.2 Technique Overview . . . . . . . . . . . . . . . . . . . . . . . . 116
3.3 Flat Shading . . . . . . . . . . . . . . . . . . . . . . . . . . . . 117
3.4 Soft Light Blending . . . . . . . . . . . . . . . . . . . . . . . . . 117
3.5 Halftone-based Shadows . . . . . . . . . . . . . . . . . . . . . . 118
3.6 Threshold-based Inverted Hull Outline . . . . . . . . . . . . . . 119
3.7 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 120
3.8 Final Considerations . . . . . . . . . . . . . . . . . . . . . . . . 121
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 121
## 4 High Quality GPU-efficient Image Detail Manipulation 123
Kin-Ming Wong and Tien-Tsin Wong
4.1 Image Detail Manipulation Pipeline . . . . . . . . . . . . . . . 124
4.2 Decomposition . . . . . . . . . . . . . . . . . . . . . . . . . . . 126
4.3 GLSL Compute Shader-based Implementation . . . . . . . . . . 129
4.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 133
4.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 133
4.6 Acknowledgement . . . . . . . . . . . . . . . . . . . . . . . . . . 136
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 136
## 5 Linear-Light Shading with Linearly Transformed Cosines 137
Eric Heitz and Stephen Hill
5.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 137
5.2 The Linear-Light Shading Model . . . . . . . . . . . . . . . . . 140
5.3 Line-integral of a Diffuse Material . . . . . . . . . . . . . . . . 147
5.4 Line-Integral of a Glossy Material with LTCs . . . . . . . . . . 150
5.5 Adding the End Caps . . . . . . . . . . . . . . . . . . . . . . . 154
5.6 Rectangle-Like Linear Lights . . . . . . . . . . . . . . . . . . . 157
5.7 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 160
5.8 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 160
5.9 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 160
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 160
## 6 Profiling and Optimizing WebGL Applications Using Google
Chrome 163
Gareth Morgan
6.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 163
6.2 Browser Profiling Tools . . . . . . . . . . . . . . . . . . . . . . 167
6.3 Case Studies . . . . . . . . . . . . . . . . . . . . . . . . . . . . 174
6.4 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 180
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 180viii Contents
# IV Screen Space 181
Wessam Bahnassi, editor
## 1 Scalable Adaptive SSAO 183
Filip Strugar
1.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 183
1.2 Problem Statement . . . . . . . . . . . . . . . . . . . . . . . . . 183
1.3 ASSAO|A High-level Overview . . . . . . . . . . . . . . . . . 184
1.4 SSAO|A Quick Refresh . . . . . . . . . . . . . . . . . . . . . . 185
1.5 Scaling the SSAO . . . . . . . . . . . . . . . . . . . . . . . . . . 186
1.6 Sampling Kernel . . . . . . . . . . . . . . . . . . . . . . . . . . 197
1.7 Adaptive SSAO . . . . . . . . . . . . . . . . . . . . . . . . . . . 197
1.8 Putting It All Together . . . . . . . . . . . . . . . . . . . . . . 199
1.9 Future Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 200
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 200
## 2 Robust Screen Space Ambient Occlusion 203
Wojciech Sterna
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 203
2.2 Problem Formulation . . . . . . . . . . . . . . . . . . . . . . . . 203
2.3 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 205
2.4 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 209
2.5 Possible Improvements . . . . . . . . . . . . . . . . . . . . . . . 213
2.6 Demo Application . . . . . . . . . . . . . . . . . . . . . . . . . 214
2.7 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 215
2.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 215
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 216
## 3 Practical Gather-based Bokeh Depth of Field 217
Wojciech Sterna
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 217
3.2 Problem Formulation . . . . . . . . . . . . . . . . . . . . . . . . 217
3.3 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 221
3.4 Implementation Details . . . . . . . . . . . . . . . . . . . . . . 227
3.5 Per-pixel Kernel Scale . . . . . . . . . . . . . . . . . . . . . . . 235
3.6 Demo Application . . . . . . . . . . . . . . . . . . . . . . . . . 236
3.7 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 237
3.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 237
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 237Contents ix
# V Virtual Reality 239
Eric Haines, editor
## 1 Efficient Stereo and VR Rendering 241
´Inigo Qu ˜ ´ılez
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 241
1.2 Engine Design . . . . . . . . . . . . . . . . . . . . . . . . . . . . 241
1.3 Stereo Rendering . . . . . . . . . . . . . . . . . . . . . . . . . . 247
1.4 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 251
## 2 Understanding, Measuring, and Analyzing VR
Graphics Performance 253
James Hughes, Reza Nourai, and Ed Hutchins
2.1 VR Graphics Overview . . . . . . . . . . . . . . . . . . . . . . . 253
2.2 Trace Collection . . . . . . . . . . . . . . . . . . . . . . . . . . 259
2.3 Analyzing Traces . . . . . . . . . . . . . . . . . . . . . . . . . . 263
2.4 The Big Picture . . . . . . . . . . . . . . . . . . . . . . . . . . . 274
VI Compute 275
Wolfgang Engel, editor
## 1 Optimizing the Graphics Pipeline with Compute 277
Graham Wihlidal
1.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 277
1.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 278
1.3 Motivation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 280
1.4 Draw Association . . . . . . . . . . . . . . . . . . . . . . . . . . 283
1.5 Draw Compaction . . . . . . . . . . . . . . . . . . . . . . . . . 287
1.6 Cluster Culling . . . . . . . . . . . . . . . . . . . . . . . . . . . 291
1.7 Triangle Culling . . . . . . . . . . . . . . . . . . . . . . . . . . . 293
1.8 Batch Scheduling . . . . . . . . . . . . . . . . . . . . . . . . . . 308
1.9 De-interleaved Vertex Buffers . . . . . . . . . . . . . . . . . . . 310
1.10 Hardware Tessellation . . . . . . . . . . . . . . . . . . . . . . . 311
1.11 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 315
1.12 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 317
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 319
## 2 Real Time Markov Decision Processes for Crowd Simulation 321
Sergio Ruiz and Benjam´ın Hernandez ´
2.1 Modeling Agent Navigation using a
Markov Decision Process . . . . . . . . . . . . . . . . . . . . . . 321
2.2 Crowd Rendering . . . . . . . . . . . . . . . . . . . . . . . . . . 332x Contents
2.3 Coupling the MDP Solver with Crowd
Rendering . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 333
2.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 335
2.5 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 338
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 338
