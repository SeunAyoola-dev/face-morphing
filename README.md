# Face Morphing with Dlib, OpenCV, and Delaunay Triangulation
This project performs face morphing between two input images using facial landmark detection, Delaunay triangulation, affine transformations, and frame interpolation. The final result is a smooth transition video illustrating the morph from one face to another.

# Features
- Detects facial landmarks using dlib's pretrained face detector and shape predictor
- Computers Delauney triangulation over facial features to ensure consistent mesh mapping
- Interpolates landmark positions based on an alpha value from 0 -> 1
- Applies custom affine transformations and bilinear interpolation to warp triangular regions
- Generates a sequence of intermediate frames
- Compiles frames into a final morphing video using OpenCV

# Landmark Detection
Extracts facial landmarks for both input images using a mouse click callback and dlib's detector 

# Triangulation 
Performs Delaunay triangulation on the landmark points of the first image
Saves triangle vertex indices for consistent gemotery mapping 

# Coordinate Interpolation 
Interpolates between triangle coordinates using: 
((trig2 - trig1) * alpha) + trig1

# Affine Warping & Pixel Mapping
- Custom affine transformation logic
- Manual bilinear interpolation
- Logic for checking whether a pixel lies inside a triangle
- Mapping triangles to generate morphed frames

# Frame Generation
Generates 50 intermediate images blending the two faces
