# MarchingCubes

## Introduction

Within the scope of this project, the focus was on developing the "marching cubes" algorithm in the Unity environment, along with implementing the visualization of the results. The marching cubes algorithm is used to generate 3D models from given data, in this case, Perlin noise as a density function. The goal was to create a system that enables precise visualization of complex 3D structures from provided data.

--- 

## Running Instructions

To run this project, first ensure that you have Unity3D development environment installed on your computer. After that, download the project file and unpack it to the desired location. Then, start Unity3D, choose the "Open Project" option, and navigate to the main project directory.

The second scene, named "MarchingCubes," contains an exemplary implementation of the marching cubes algorithm. Open this scene to explore the generation of 3D models using this algorithm. You can observe the results and adjust parameters to obtain different shapes and structures.

---

## Settings

### Basic

- **Material:** Defines the material for visualizing the generated mesh.
- **Body Size:** Sets the uniform size of the body, with default values set to 1.
- **Density Threshold:** Determines the density threshold that distinguishes the interior and exterior of the body (values from 0 to 1).
- **Mesh Resolution:** Sets the resolution of the generated mesh.

### Perlin Noise Settings (Generating Functions)

- **Octaves:** Defines the number of octaves in the Perlin noise.
- **Lacunarity:** Sets the lacunarity parameter of the Perlin noise.
- **Frequency:** Determines the frequency of the Perlin noise.
- **Offset:** Adjusts the offset parameter of the Perlin noise.

### Animation Settings

- **Frequency Speed:** Controls the speed of frequency function changes.
- **Offset Speed:** Influences the speed of offset function changes.
- **Lacunarity Speed:** Regulates the speed of lacunarity parameter changes.

---

## Implementation

The project relies on several dependencies and components to achieve its functionality. Below are the key elements involved in the implementation:

### Dependencies

1. **FastNoiseLite:** A robust HLSL noise library utilized for generating procedural noise in the project.

2. **MarchingTable:** This component is employed to store all possible configurations of a mesh contained inside a cube chunk. It plays a crucial role in the mesh generation process.

### Scripts

1. **StableCubeMarcher.cs:** This C# script serves as a bridge between the CPU and GPU. It is responsible for communicating with the GPU, sending parameters, and visualizing the generated mesh. The script facilitates the coordination of operations between the CPU and GPU components.

2. **StableMarchShader.shader:** This script is designed to render the mesh properly using vertex and pixel shaders. It ensures the correct visualization of the generated mesh on the GPU side.

3. **StableCubeMarcher.compute:** The bulk of operations occurs in this compute shader. Here, noise is sampled, the mesh is constructed, and buffers are updated. It serves as the computational core where the intricate calculations take place.
   
All three files must effectively communicate as they share the same data for the entire system to function seamlessly.
