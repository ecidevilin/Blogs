# Part I Geometry Manipulation
## 1.1 Scalar to Polygonal: Extracting Isosurfaces Using Geometry Shaders
Scalar Fields Versus Polygonal Representation
Isosurface Extraction Using Marching Methods
Hybrid Cubes/Tetrahedra Extraction
Isosurface Extraction Results and Analysis
## 1.2 Fast High-Quality Rendering with Real-Time Tessellation on GPUs
GPU Tessellation Pipeline
Programming for GPU Tessellation
Continuous Tessellation Mode
Adaptive Tessellation Mode
Rendering Characters with Tessellation
Designing a Vertex Evaluation Shader for GPU Tessellation
Accessing Per-Vertex Data Beyond Input Structure Declaration
Tessellation API in Direct3D 10
Lighting with Tessellation and Displacement Mapping
Rendering Animated, Tessellated Characters
Displacement Map Tips and Reducing Surface Cracks
## 1.3 Dynamic Terrain Rendering on GPUs Using Real-Time Tessellation
Programming for Adaptive GPU Tessellation
Transforming Mesh Using R2VB
Computing Per-Edge Tessellation Factors
Rendering Tessellated Mesh with Per-Edge Tessellation Factors
Shading Tessellated Displaced Surfaces
Performance Analysis
## 1.4 Adaptive Re-Meshing for Displacement Mapping
Introduction
Displacement Map
Adaptive Re-Meshing for Displacement Mapping
LOD
Results
Implementation
Demo
Conclusion
Endnotes
## 1.5 Fast Tessellation of Quadrilateral Patches for Dynamic Levels of Detail
Introduction
The Method
How Many Strips Will Be Needed?
Where Will Each Strip Be Located?
How Do We Tessellate Each Strip?
A 3D Interpolation to Place Triangle Strips
A 2D Interpolation to Tessellate Strips
Results
Discussion
# Part II Rendering Techniques
## 2.1 Quick Noise for GPUs
Introduction
Background
Math to the Rescue
Applying It in the Real World
And Now the Bad News
Implementation, the Sequel
Results
Future Work
## 2.2 Efficient Soft Particles
Introduction
Hard Particles vs. Soft ParticlesImplementing Soft Particles the Standard Way
Optimizing Soft Particles
Results
Conclusion
## 2.3 Simplified High-Quality Anti-Aliased Lines
Abstract
Introduction
Method
Texture Creation
Vertex Setup
Variations on the Theme
Conclusion
Appendix A: The Shader Code
## 2.4 Fast Skin Shading
Introduction
Background and Existing Art
Specular and Diffuse
Data Preparation
Conclusion
## 2.5 An Efficient and Physically Plausible Real-Time Shading Model
Introduction
Review: Blinn-Phong and Cook-Torrance
Some Physics of Light-Surface Interaction
Toward an Improved Shading Model
Mathematical Formulation
Appendix
## 2.6 Graphics Techniques in Crackdown
Introduction
Sky
Implementation Notes
Clutter
Outlines
Deferred Rendering
Vehicle Reflections
Implementation Notes
Texture Map Setup
Conclusion
Endnotes
## 2.7 Deferred Rendering Transparency
Introduction
Transparency
Overview
Rendering
Results Discussion
Summary and Future Work
## 2.8 Deferred Shading with Multisampling Anti-Aliasing in DirectX 10
Introduction
Deferred Shading Principles
MSAA Requirements for Deferred Shading
Implementation
Assessment of Alternative Implementation
Conclusion
## 2.9 Light-Indexed Deferred Rendering
Introduction
Rendering Concept
Light-Indexed Deferred Rendering
Combining with Other Rendering Techniques
Multi-Sample Anti-Aliasing
Transparency
Shadows
Constraining Lights to Surfaces
Multi-Light Type Support
Lighting Technique Comparison
Future Work
Conclusion# Part III Image Space
## 3.1 Efficient Post-Processing with Importance Sampling
Introduction
Problem Statement
The Approach of Importance Sampling
Tone Mapping with Glow
Depth of Field
Comparisons to Uniform Sampling
Conclusion
## 3.2 Efficient Real-Time Motion Blur for Multiple Rigid Objects
Introduction
Overview
CPU-Side Work
GPU-Side Work
Blurring and Halo Fixing
Integration with a Post-Processing Pipeline
Coping with Hardware Limitations
Conclusion
## 3.3 Real-Time Image Abstraction by Directed Filtering
Introduction
Color Space Conversion
Flow Field Construction
Orientation-Aligned Bilateral Filter
Separable Flow-Based Difference-of-Gaussians
Color Quantization
Conclusions
# Part IV Shadows
## 4.1 Practical Cascaded Shadow Maps
Introduction
Flickering of Shadow Quality
Exact Solution
Approximated Solution
Storage Strategy
Non-Optimized Split Selection
Correct Computation of Texture Coordinates
Filtering Across Splits
Method Used in PSVSMs
Analytic Method
Conclusion
## 4.2 A Hybrid Method for Interactive Shadows in Homogeneous Media
Introduction
Participating Media Review
Hybrid Approach
Adding Textured Light Sources
Implementation Details
Results
Conclusions
## 4.3 Real-Time Dynamic Shadows for Image-Based Lighting
Introduction
Related Work
Algorithm Overview
Environment Map Importance Sampling
Visibility Map Generation
Rendering Shadows on Diffuse Surfaces
Rendering Shadows on Glossy Surfaces
Results
Conclusion
Endnotes
## 4.4 Facetted Shadow Mapping for Large Dynamic Game Environments
Introduction
The Challenges
Existing Shadow Map Approaches
Facetted Shadow Map ApproachCreating and Using Facetted Shadow Maps
Results
Conclusion
# Part V Environmental Effects
## 5.1 Dynamic Weather Effects
Introduction
Particle Simulation and Rendering
Rendering Motion-Blurred Particles
Occlusion
Dynamic, Artist-Controlled Weather
Additional Effects
Conclusion
## 5.2 Interactive Hydraulic Erosion on the GPU
Introduction
Data Structures
Water Movement
Erosion
Boundaries
Rendering
Results and Conclusion
## 5.3 Advanced Geometry for Complex Sky Representation
Introduction
Geometry Generation
Conclusion
# Part VI Global Illumination Effects
## 6.1 Screen-Space Ambient Occlusion
Introduction
The Problems
Previous Work
Overview of the Approach
Implementation
Future Improvements
Results and Conclusion
## 6.2 Image-Space Horizon-Based Ambient Occlusion
Introduction
Input Buffers for Image Space Ambient Occlusion
Image Space Ambient Occlusion with Ray Marching
Our Algorithm
Reformulating the Ambient Occlusion Integral
Implementation Considerations
Results
## 6.3 Deferred Occlusion from Analytic Surfaces
Introduction
Method
Analytic Occlusion from other Surfaces
Optimization
Conclusion
## 6.4 Fast Fake Global Illumination
Introduction
Ambient Occlusion Probes
Screen-Space Ambient Occlusion
Screen-Space Radiosity
Fake Radiosity
Conclusion
## 6.5 Real-Time Subsurface Scattering Using Shadow Maps
Introduction
Related Work
Theory
Algorithm
Results
Conclusion## 6.6 Instant Radiosity with GPU Photon Tracing and Approximate Indirect Shadows
Introduction
Techniques We Build On
Algorithm Overview
Scene Representation for Ray Tracing
Ray-Triangle Intersection
BIH Traversal
Light Source Sampling
Photon Shooting
VPL Management
Rendering the Distance Impostor Cube Map
Rendering Deferring Textures
Building Pyramidal Occlusion Maps
Lighting
Adaptive Geometry-Sensitive Box Filtering
Performance
Conclusion
## 6.7 Variance Methods for Screen-Space Ambient Occlusion
Ambient Lighting
Ambient Occlusion
## 6.8 Per-Pixel Ambient Occlusion Using Geometry Shaders
Introduction
Background
Our Approach
Results
Conclusion
# Part VII Handheld Devices
## 7.1 Optimizing Your First OpenGL ES Application
Introduction
Mobile Development
Graphics Development Guidelines
A Developer’s Experience: Insight from Jadestone into KODO Evolved 539 Conclusion
## 7.2 Optimized Shaders for Advanced Graphical User Interfaces
Introduction
Handheld GUI Requirements
Optimizing for Power Consumption
Optimizing Blurs
Optimizing Other Popular Effects
Background and Post-Processing
Transitions
Conclusion
## 7.3 Facial Animation for Mobile GPUs
Introduction
Facial Animation Components
Current Approaches and Efficiency
Mobile Approach: Maximal Efficiency Is Critical
Conclusion
## 7.4 Augmented Reality on Mobile Phones
Introduction
Developing Augmented Reality Applications
Platform Considerations
Application Initialization
Graphics API Abstraction
Hardware vs. Software Rendering
Scene-Graph Rendering
Video and Image Processing
Fixed Point vs. Floating Point
Conclusion
# Part VIII 3D Engine Design Overview
## 8.1 Cross-Platform Rendering Thread: Design and Implementation
Motivation
Overview
ImplementationResults
Going Further: Add-Ons and Features
Conclusion
## 8.2 Advanced GUI System for Games
Introduction
Architecture
Rendering
Conclusion
## 8.3 Automatic Load-Balancing Shader Framework
Introduction
The Problems
User Inconvenience
Performance
The Approach
Workflow
Discussion of Results
GPU Requirements
Conclusion
## 8.4 Game-Engine-Friendly Occlusion Culling
Introduction
Coherent Hierarchical Culling
Reducing State Changes
Game Engine Integration
Skipping Tests for Visible Nodes
Further Optimizations
Multiqueries
Putting It All Together
Conclusion
## 8.5 Designing a Renderer for Multiple Lights: The Light Pre-Pass Renderer
Z Pre-Pass Renderer
Deferred Renderer
Light Pre-Pass Renderer
Storing an Additional Diffuse Term
Converting the Diffuse Term to Luminance
Bending the Specular Reflection Rules
Comparison and Conclusion
Appendix: Applying Different Materials with a Light Pre-Pass Renderer
## 8.6 Light Pre-Pass Renderer: Using the CIE Luv Color Space
Introduction
Why CIE Luv?
Working with Luv Colors
Luv Light Buffer Format
Grouping and Rendering Lights
Integrating Luv into Light Accumulation
Conclusion
## 8.7 Elemental Engine II
# Part IX Beyond Pixels and Triangles
## 9.1 Sliced Grid: A Memory and Computationally Efficient Data Structure for ParticleBased Simulation on the GPU
Introduction
Sliced Grid
Implementing a Sliced Grid on the GPU
Results
Conclusion
## 9.2 Free-Viewpoint Video on the GPU
Introduction
Background Subtraction
Shape from Silhouette
Surface Extraction
Texture Mapping
Conclusion
## 9.3 A Volume Shader for Quantum Voronoi Diagrams Inside the 3D Bloch BallIntroduction and Preliminaries
Von Neumann Quantum Entropy and Its Relative Entropy Divergence
Quantum Voronoi Diagrams
Quantum Voronoi Diagrams for Pure States
Quantum Voronoi Diagrams for Mixed States
Quantum Channel and Holevo’s Capacity
Concluding Remarks
## 9.4 Packing Arbitrary Bit Fields into 16-Bit Floating-Point Render Targets in DirectX 10
Introduction
16-Bit and 32-Bit Floating-Point Formats
Writing a Valid 32-Bit Floating-Point Output
Converting Between Single- and Half-Precision
Packing and Unpacking Code
Performance Considerations
Conclusion
## 9.5 Interactive Image Morphing Using Thin-Plate Spline
Introduction
Thin-Plate Spline-Based Warping
GPU Implementation of TPS Warping
Interactive Image Morphing
Conclusion
