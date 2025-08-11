# FPGA Rasterizer Implementation Overview
Welcome to the FPGA Rasterizer project! Inspired by my interest in computer graphics and digital design, this project aims to design and implement a simple graphics card on an FPGA using VHDL.
## Overview 
This project involves creating a hardware-based rasterizer on an FPGA, focusing on the graphics pipeline and rendering techniques. The rasterizer processes geometric data to produce pixel data for display, interacting with frame buffers to store rendered images.

## Rasterizer Components

### Vertex Processing
The vertex processing unit is responsible for transforming vertex data from object space to screen space. It applies transformations such as translation, rotation, and scaling, and outputs the transformed vertices to the next stage of the pipeline.

### Triangle Setup
The triangle setup unit takes transformed vertices and calculates edge equations for each triangle. This information is used to determine which pixels fall within the triangle's boundaries during rasterization.

### Rasterization
The rasterization unit scans through the pixel grid and determines which pixels are covered by triangles. It uses edge equations from the triangle setup to efficiently fill triangles and outputs pixel coordinates and attributes.

### Fragment Shader
The fragment shader processes each pixel covered by a triangle, applying shading techniques to determine the final color. This can include operations like texture mapping, lighting calculations, and color blending.

### Frame Buffer
The frame buffer stores the final pixel data produced by the rasterizer. It acts as a temporary storage for rendered images before they are sent to the display. The frame buffer is typically implemented as a block RAM on the FPGA.

### Control Unit
The control unit orchestrates the rasterization process, managing the flow of data between units and ensuring synchronization. It handles input commands and control signals to coordinate rendering tasks.


## Software Implementation
The goal is to take geometric data and rendering commands from a software application and convert them into a format suitable for the FPGA rasterizer to process. This involves generating vertex data and rendering instructions that the hardware can interpret.

```C
// Example pseudo-code for generating vertex data
void generateTriangleData() {
    Vertex v1 = {0.0, 0.5, 0.0};
    Vertex v2 = {-0.5, -0.5, 0.0};
    Vertex v3 = {0.5, -0.5, 0.0};

    sendToRasterizer(v1, v2, v3);
}
```

## Differences between Rasterization and Ray Tracing

---

Please go into each subproject folder to see more in detail.

