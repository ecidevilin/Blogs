# 1 2D GEOMETRY
Useful 2D Geometry 3
Trigonometry Summary 12
Useful Trigonometry 13
Trigonometric Functions at Select Points 18
Triangles 20
Generating Random Points in Triangles (649) 24
Fast Line–Edge Intersections on a Uniform Grid (651) 29GRAPHICS GEMS I Edited by ANDREW S. GLASSNER viii
CONTENTS
Anti-Aliasing Summary 37
Area of Intersection: Circle and a Half-Plane 38
Area of Intersection: Circle and a Thick Line 40
Area of Intersection: Two Circles 43
Vertical Distance from a Point to a Line 47
A Fast 2D Point-on-Line Test (654) 49
Fast Circle–Rectangle Intersection Checking (656) 51
# 2 2D RENDERING
Circles of Integral Radius on Integer Lattices 57
Nice Numbers for Graph Labels (657) 61
Efficient Generation of Sampling Jitter Using Look-up
Tables (660) 64
Scan Conversion Summary 75
Fast Anti-Aliasing Polygon Scan Conversion (662) 76
Generic Convex Polygon Scan Conversion and Clipping (667) 84
ConcavePolygon Scan Conversion (681) 87
Fast Scan Conversion of Arbitrary Polygons 92
Line-Drawing Summary 98
Digital Line Drawing (685) 99
Symmetric Double Step Line Algorithm (686) 101
Rendering Anti-Aliased Lines (690) 105
An Algorithm for Filling in 2D Wide Line Bevel Joints 107
Rendering Fat Lines on a Raster Grid 114GRAPHICS GEMS I Edited by ANDREW S. GLASSNER ix
CONTENTS
Two-Dimensional Clipping: A Vector-Based Approach (694) 121
Periodic Tilings of the Plane on a Raster 129
# 3 IMAGE PROCESSING
Anti-Aliasing Filters Summary 143
Convenient Anti-Aliasing Filters That Minimize
“Bumpy” Sampling 144
Filters for Common Resampling Tasks 147
Smoothing Enlarged Monochrome Images 166
Median Finding on a 3 × 3 Grid (711) 171
Ordered Dithering (713) 176
A Fast Algorithm for General Raster Rotation 179
Useful 1-to-1 Pixel Transforms 196
Alpha Blending 210
# 4 FRAME BUFFER TECHNIQUES
Frame Buffers and Color Maps 215
Reading a Write-Only Write Mask 219
A Digital “Dissolve” Effect (715) 221
Mapping RGB Triples onto Four Bits (718) 233
What Are the Coordinates of a Pixel? 246
Proper Treatment of Pixels as Integers (719) 249
Normal Coding 257
Recording Animation in Binary Order for Progressive
Temporal Refinement (720) 265GRAPHICS GEMS I Edited by ANDREW S. GLASSNER x
CONTENTS
1-to-1 Pixel Transforms Optimized through
Color-Map Manipulation 270
A Seed Fill Algorithm (721) 275
Filling a Region in a Frame Buffer 278
Precalculating Addresses for Fast Fills, Circles,
and Lines 285
A Simple Method for Color Quantization:
Octree Quantization 287
# 5 3D GEOMETRY
Useful 3D Geometry 297
An Efficient Bounding Sphere (723) 301
Intersection of Two Lines in Three-Space 304
Intersection of Three Planes 305
Mapping Summary 306
Digital Cartography for Computer Graphics 307
Albers Equal-Area Conic Map Projection. (726) 321
Boxes and Spheres Summary 326
Spheres-to-Voxels Conversion 327
A Simple Method for Box-Sphere Intersection Testing (730) 335
# 6 3D RENDERING
3D Grid Hashing Function (733) 343
Backface Culling 346GRAPHICS GEMS I Edited by ANDREW S. GLASSNER xi
CONTENTS
Fast Dot Products for Shading 348
Scanline Depth Gradient of a Z-Buffered Triangle 361
Simulating Fog and Haze 364
Interpretation of Texture Map Indices 366
Multidimensional Sum Tables 376
# 7 RAY TRACING
A Simple Ray Rejection Test 385
Ray−Object Intersection Summary 387
Intersection of a Ray with a Sphere 388
An Efficient Ray−Polygon Intersection (735) 390
Fast Ray−Polygon Intersection 394
Fast Ray−Box Intersection (736) 395
Shadow Attenuation for Ray Tracing
Transparent Objects 397
# 8 NUMERICAL AND PROGRAMMING TECHNIQUES
Root Finding Summary 403
Cubic and Quartic Roots (738) 404
A Bézier Curve-Based Root-Finder (787) 408
Using Sturm Sequences to Bracket Real Roots
of Polynomial Equations (743) 416
Distance Measures Summary 423GRAPHICS GEMS I Edited by ANDREW S. GLASSNER xii
CONTENTS
A High-Speed, Low Precision Square Root (756) 424
A Fast Approximation to the Hypotenuse (758) 427
A Fast Approximation to 3D Euclidean Distance 432
Full-Precision Constants 434
Converting between Bits and Digits 435
Storage-free Swapping 436
Generating Random Integers 438
Fast 2D−3D Rotation 440
Bit Patterns for Encoding Angles 442
Bit Interleaving for Quad- or Octrees (759) 443
A Fast HSL-to-RGB Transform (763) 448
# 9 MATRIX TECHNIQUES
Matrix Identities 453
Rotation Matrix Methods Summary 455
Transforming Axes 456
Fast Matrix Multiplication 460
A Virtual Trackball 462
Matrix Orthogonalization (765) 464
Rotation Tools 465
Matrix Inversion (766) 470
Matrices and Transformations 472
Efficient Post-Concatenation of Transformation Matrices (770) 476GRAPHICS GEMS I Edited by ANDREW S. GLASSNER xiii
CONTENTS
# 10 MODELING AND TRANSFORMATIONS
Transformation Identities 485
Fixed-Point Trigonometry with CORDIC Iterations (773) 494
Using Quaternions for Coding 3D Transformations (775) 498
3D Viewing and Rotation Using Orthonormal Bases (778) 516
The Use of Coordinate Frames in Computer Graphics 522
Forms, Vectors, and Transforms (780) 533
Properties of Surface-Normal Transformations 539
Transforming Axis-Aligned Bounding Boxes (785) 548
Constructing Shapes Summary 551
Defining Surfaces from Sampled Data 552
Defining Surfaces from Contour Data 558
Computing Surface Normals for 3D Models 562
Calculation of Reference Frames along a Space Curve 567
# 11 CURVES AND SURFACES
Planar Cubic Curves 575
Explicit Cubic Spline Interpolation Formulas 579
Fast Spline Drawing 585
Some Properties of Bézier Curves 587
Tutorial on Forward Differencing 594
Integration of Bernstein Basis Functions 604GRAPHICS GEMS I Edited by ANDREW S. GLASSNER xiv
CONTENTS
Solving the Nearest-Point-on-Curve Problem (787) 607
An Algorithm for Automatically Fitting Digitized Curves (797) 612
