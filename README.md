# Image Processing on FPGA using Verilog

Implementation of basic image processing operations on an FPGA using Verilog HDL. The system reads BMP image data stored in hex format, applies processing operations, and writes the output back. Developed and simulated using Xilinx ISE.

\---

## Tools and Platform

* **HDL:** Verilog
* **Tool:** Xilinx ISE
* **Target:** FPGA
* **Support Scripts:** MATLAB (for BMP to hex conversion)

\---

## Project Structure

```
Image-Processing-FPGA-Verilog/
├── Verilog\_Image\_Processing/
│   ├── image\_read.v          # Reads BMP image data from hex file
│   ├── image\_write.v         # Writes processed data to output BMP
│   ├── parameter.v           # Global parameters (image dimensions etc.)
│   ├── tb\_simulation.v       # Testbench for simulation
│   ├── car.bmp               # Input test image 1
│   ├── parrot.bmp            # Input test image 2
│   └── output.bmp            # Processed output image
├── html/
│   └── matlab.html           # MATLAB script output
├── carbmp.hex                # Car image in hex format
├── input.hex                 # Primary input hex file
├── input2.hex                # Secondary input hex file
├── parrotinvert.hex          # Parrot image inverted hex data
├── matlab.m                  # MATLAB script for BMP to hex conversion
├── Steps.txt                 # Implementation workflow notes
└── Report - Verilog\_Image\_Processing.pdf
```

\---

## How It Works

BMP images cannot be directly fed into FPGA memory. The workflow is:

1. Convert BMP image to hex format using the MATLAB script
2. Store hex data in FPGA memory (ROM/RAM)
3. `image\_read.v` reads pixel data from memory sequentially
4. Processing operations are applied pixel by pixel
5. `image\_write.v` writes the output back to a BMP file
6. Testbench simulates the full pipeline and verifies output

\---

## Operations Implemented

* **Grayscale conversion** — RGB to grayscale using standard luminance weights
* **Image inversion** — bitwise NOT on pixel values

\---

## Sample Output

Input and output BMP files are included in the `Verilog\_Image\_Processing` folder. The parrot image was used to demonstrate the inversion operation.

\---

## About

This project was completed in the 6th semester of B.E. ECE at SDM College of Engineering and Technology, Dharwad (Feb to May 2024).

**Author:** Sumanth Y Kargar
**Contact:** sumanthk0403@gmail.com
**LinkedIn:** *www.linkedin.com/in/sumanth-y-kargar-984b7a268*

