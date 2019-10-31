# I Geometry Manipulation 1
Carsten Dachsbacher
## 1 Deferred Snow Deformation in Rise of the Tomb Raider 3
Anton Kai Michels and Peter Sikachev
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 3
1.2 Terminology . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 4
1.3 Related Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 5
1.4 Snow Deformation: The Basic Approach . . . . . . . . . . . . . 6
1.5 Deferred Deformation . . . . . . . . . . . . . . . . . . . . . . . 7
1.6 Deformation Heightmap . . . . . . . . . . . . . . . . . . . . . . 11
1.7 Filling the Trail over Time . . . . . . . . . . . . . . . . . . . . . 13
1.8 Hardware Tessellation and Performance . . . . . . . . . . . . . 15
1.9 Future Applications . . . . . . . . . . . . . . . . . . . . . . . . 15
1.10 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 16
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
## 2 Catmull-Clark Subdivision Surfaces 17
Wade Brainerd
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
2.2 The Call of Duty Method . . . . . . . . . . . . . . . . . . . . . 20
2.3 Regular Patches . . . . . . . . . . . . . . . . . . . . . . . . . . 20
2.4 Irregular Patches . . . . . . . . . . . . . . . . . . . . . . . . . . 25
2.5 Filling Cracks . . . . . . . . . . . . . . . . . . . . . . . . . . . . 29
2.6 Going Further . . . . . . . . . . . . . . . . . . . . . . . . . . . . 34
2.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 39
2.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 39
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 39
v
www.allitebooks.comvi Contents
# II Lighting 41
Michal Valient
## 1 Clustered Shading: Assigning Lights Using Conservative
Rasterization in DirectX 12 43
Kevin Ortegren and Emil Persson ¨
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 43
1.2 Conservative Rasterization . . . . . . . . . . . . . . . . . . . . . 44
1.3 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 44
1.4 Shading . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 55
1.5 Results and Analysis . . . . . . . . . . . . . . . . . . . . . . . . 56
1.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 67
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 67
## 2 Fine Pruned Tiled Light Lists 69
Morten S. Mikkelsen
2.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 69
2.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 69
2.3 Our Method . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 71
2.4 Implementation Details . . . . . . . . . . . . . . . . . . . . . . 73
2.5 Engine Integration . . . . . . . . . . . . . . . . . . . . . . . . . 76
2.6 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 78
2.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 79
2.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 80
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 81
## 3 Deferred Attribute Interpolation Shading 83
Christoph Schied and Carsten Dachsbacher
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 83
3.2 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 84
3.3 Implementation . . . . . . . . . . . . . . . . . . . . . . . . . . . 87
3.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 94
3.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 95
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 96
## 4 Real-Time Volumetric Cloudscapes 97
Andrew Schneider
4.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 97
4.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 98
4.3 Cloud Modeling . . . . . . . . . . . . . . . . . . . . . . . . . . . 98
4.4 Cloud Lighting . . . . . . . . . . . . . . . . . . . . . . . . . . . 110
4.5 Cloud Rendering . . . . . . . . . . . . . . . . . . . . . . . . . . 119
www.allitebooks.comContents vii
4.6 Conclusion and Future Work . . . . . . . . . . . . . . . . . . . 125
4.7 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 126
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 126
# III Rendering 129
Christopher Oat
## 1 Adaptive Virtual Textures 131
Ka Chen
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 131
1.2 Procedural Virtual Textures Basics . . . . . . . . . . . . . . . . 131
1.3 Adaptive Virtual Textures . . . . . . . . . . . . . . . . . . . . . 131
1.4 Virtual Texture Best Practices . . . . . . . . . . . . . . . . . . 137
1.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 143
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 144
## 2 Deferred Coarse Pixel Shading 145
Rahul P. Sathe and Tomasz Janczak
2.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 145
2.2 Introduction and Background . . . . . . . . . . . . . . . . . . . 145
2.3 Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 146
2.4 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 151
2.5 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 151
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 153
## 3 Progressive Rendering Using Multi-frame Sampling 155
Daniel Limberger, Karsten Tausche, Johannes Linke, and J¨ urgen D¨ollner
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 155
3.2 Approach . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 156
3.3 Multi-frame Rendering Techniques . . . . . . . . . . . . . . . . 160
3.4 Conclusion and Future Work . . . . . . . . . . . . . . . . . . . 169
3.5 Acknowledgment . . . . . . . . . . . . . . . . . . . . . . . . . . 170
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 170
# IV Mobile Devices 173
Marius Bjørge
## 1 Efficient Soft Shadows Based on Static Local Cubemap 175
Sylwester Bala and Roberto Lopez Mendez
1.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 175
1.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 175
www.allitebooks.comviii Contents
1.3 Algorithm Overview . . . . . . . . . . . . . . . . . . . . . . . . 176
1.4 What Is a Local Cubemap? . . . . . . . . . . . . . . . . . . . . 177
1.5 Creating a Shadow Cubemap . . . . . . . . . . . . . . . . . . . 178
1.6 Applying Shadows . . . . . . . . . . . . . . . . . . . . . . . . . 179
1.7 Smoothness . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 182
1.8 Combining the Shadow Technique with Others . . . . . . . . . 183
1.9 Performance and Quality . . . . . . . . . . . . . . . . . . . . . 184
1.10 Future Work . . . . . . . . . . . . . . . . . . . . . . . . . . . . 185
1.11 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 185
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 186
## 2 Physically Based Deferred Shading on Mobile 187
Ashley Vaughan Smith and Mathieu Einig
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 187
2.2 Physically Based Shading . . . . . . . . . . . . . . . . . . . . . 187
2.3 An Efficient Physically Based Deferred Renderer . . . . . . . . 190
2.4 Experiments . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 195
2.5 Conclusion and Future Work . . . . . . . . . . . . . . . . . . . 195
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 198
# V 3D Engine Design 199
Wessam Bahnassi
## 1 Interactive Cinematic Particles 201
Homam Bahnassi and Wessam Bahnassi
1.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 201
1.2 Background . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 201
1.3 Challenges and Previous Work . . . . . . . . . . . . . . . . . . 202
1.4 Interactive Cinematic Particles (ICP) System Outline . . . . . 204
1.5 Data Authoring Workflow . . . . . . . . . . . . . . . . . . . . . 204
1.6 Offline Build Process . . . . . . . . . . . . . . . . . . . . . . . . 209
1.7 Runtime Execution . . . . . . . . . . . . . . . . . . . . . . . . . 212
1.8 Additional Notes . . . . . . . . . . . . . . . . . . . . . . . . . . 217
1.9 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 217
1.10 Acknowledgment . . . . . . . . . . . . . . . . . . . . . . . . . . 218
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 218
## 2 Real-Time BC6H Compression on GPU 219
Krzysztof Narkowicz
2.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 219
2.2 BC6H Details . . . . . . . . . . . . . . . . . . . . . . . . . . . . 220
2.3 Compression Algorithm . . . . . . . . . . . . . . . . . . . . . . 222
www.allitebooks.comContents ix
2.4 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 225
2.5 Possible Extensions . . . . . . . . . . . . . . . . . . . . . . . . . 227
2.6 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 228
2.7 Acknowledgements . . . . . . . . . . . . . . . . . . . . . . . . . 228
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 228
## 3 A 3D Visualization Tool Used for Test Automation
in the Forza Series 231
Gustavo Bastos Nunes
3.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 231
3.2 Collision Mesh Issues . . . . . . . . . . . . . . . . . . . . . . . . 232
3.3 Detecting the Issues . . . . . . . . . . . . . . . . . . . . . . . . 234
3.4 Visualization . . . . . . . . . . . . . . . . . . . . . . . . . . . . 242
3.5 Navigation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 242
3.6 Workflow . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 243
3.7 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 244
3.8 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 244
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 244
## 4 Semi-static Load Balancing for Low-Latency Ray Tracing
on Heterogeneous Multiple GPUs 245
Takahiro Harada
4.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 245
4.2 Load Balancing Methods . . . . . . . . . . . . . . . . . . . . . . 246
4.3 Semi-static Load Balancing . . . . . . . . . . . . . . . . . . . . 248
4.4 Results and Discussion . . . . . . . . . . . . . . . . . . . . . . . 250
4.5 Acknowledgments . . . . . . . . . . . . . . . . . . . . . . . . . . 253
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 253
# VI Compute 255
Wolfgang Engel
## 1 Octree Mapping from a Depth Camera 257
Dave Kotfis and Patrick Cozzi
1.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 257
1.2 Previous Work and Limitations . . . . . . . . . . . . . . . . . . 260
1.3 Octree Scene Representation . . . . . . . . . . . . . . . . . . . 261
1.4 Rendering Techniques . . . . . . . . . . . . . . . . . . . . . . . 267
1.5 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 270
1.6 Conclusion and Future Work . . . . . . . . . . . . . . . . . . . 271
1.7 Acknowledgment . . . . . . . . . . . . . . . . . . . . . . . . . . 272
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 272
www.allitebooks.comx Contents
## 2 Interactive Sparse Eulerian Fluid 275
Alex Dunn
2.1 Overview . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 275
2.2 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 275
2.3 GPU Eulerian Fluid Simulation . . . . . . . . . . . . . . . . . . 276
2.4 Simulation Stages . . . . . . . . . . . . . . . . . . . . . . . . . . 277
2.5 Problems . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 281
2.6 Latency Resistant Sparse Fluid Simulation . . . . . . . . . . . . 290
2.7 Performance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 291
2.8 Sparse Volume Rendering . . . . . . . . . . . . . . . . . . . . . 293
2.9 Results . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 296
2.10 Conclusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 296
Bibliography . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 298
