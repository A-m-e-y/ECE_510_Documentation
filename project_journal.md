# Project Journal

This section tracks the progress of my course project, week-by-week.

## Project Overview

| Task | Success? | Comments |
|:------|:----------:|:----------|
| Cocotb Sim     |  ✅ Yes        |  Complete H/W <> S/W co-simulation is working |
| OpenLane-2 Synthesis | ❌ No        | OpenLane-2 doesn't support SystemVerilog constructs |
|  |         | Please check here for further details - [Link]() |
| Synopsys Design Compiler Synthesis | ✅ Yes        | Synthesis is successful with all the important metrics |
|  |     | Check here for all the details of Synthesis - [Link]() |
| Vivado Synthesis | ✅ Yes        | Synthesis is successful with all the important metrics |
|  |     | Check here for all the details of Synthesis - [Link]() |

## Synthesis Results

| Metric | Result | Comments |
|:------|:----------:|:----------:|
| Area | 0 | 0 |
| Transistor Count | 0 | 0 |
| Power | 0 | 0 |
| Timing | 0 | 0 |

**Table of Contents**
- [Week 1](#week-1--)
- [Week 2](#week-2--)
- [Week 3](#week-3--)
- [Week 4](#week-4--)
- [Week 5](#week-5--)
- [Week 6](#week-6--)
- [Week 7](#week-7--)
- [Week 8](#week-8--)
- [Week 9](#week-9--)


---

## Week 1 -
- This week didn't really involve any direct project work, instead I focused on completing the weekly challenge and getting familiar with profiling python code using `cProfile` and `snakeviz`.
- I completed both weekly challenges, [W01_C04_SNN](https://github.com/A-m-e-y/W01_C04_SNN) and [W01_C05_PyBytecode](https://github.com/A-m-e-y/W01_C05_PyBytecode).
- This gave me clear understanding of how to profile python code and how to use `cProfile` and `snakeviz` to visualize the profiling results.
- I also learnt about vibe-coding, prompt-engineering and how to use LLMs to generate the code we want.

---

## Week 2 -
- This week, during codefest, we were asked to choose a project topic and start coding and benchmarking the software version. 
- The goal was to find a software workload bottleneck which can be accelerated using hardware implementation.
- I initially wanted to choose the topic "LSTM Audio to Text Conversion Using LSTM Layers", so I started working on it.
- Even though later I ended up changing the topic, I created following GitHub repo for this project -
- 🔗 GitHub Repo - [LSTM_audio_to_text_SW](https://github.com/A-m-e-y/LSTM_audio_to_text_SW)
- While working on this project, I realized following complexities -
    - The Python code for LSTM is quite complex and requires a lot of understanding of the underlying algorithms.
    - The code is implemented entirely using TensorFlow, which makes it difficult to profile.
    - Since Tenserflow is a high-level library, it abstracts away a lot of the low-level details, making it difficult to understand the performance bottlenecks.
    - I learnt that TensorFlow bypasses the Python interpreter and uses advance C kernels for performance, which makes it difficult to profile using `cProfile`.
    - I also tried to bypass TensorFlow and use pure Python code for LSTM, but it was too complex and time-consuming.
    - The initial audio processing itself is very library heavy, I was using libraries like `librosa` and `pydub`.
    - Also, I later realized that someone else had taken a similar topic for the project, so I decided to pivot and change my topic.
    - Hence, I decided to change my project topic to "CNN Digit Recognizor for 240x240 Images".

---

## Week 3 -
- This week, I started working on the new project topic "CNN Digit Recognizor for 240x240 Images".
- I started by creating a new GitHub repo for this project -
- 🔗 GitHub Repo - [CNN_TF_hand_written_digit](https://github.com/A-m-e-y/CNN_TF_hand_written_digit)
- I started by implementing the CNN model using TensorFlow and Keras first with MNIST dataset which is for 28x28 images.
- Here I faced similar challenges for profiling the code as I did in the previous week.
- I also tried to use `cProfile` and `snakeviz` to profile the code, but it didn't work as expected.
- I even tried to create a custom CNN TF class `custom_conv2D.py`, but I was still unable to profile the code and pinpoint the bottlenecks.
- I also tried to use TensorFlow's built-in profiling tool, called `TensorBoard`, but I was not able to make it work till the end.
- So I decided to implement the CNN model using pure Python code without using TensorFlow or PyTorch.
- I created a new GitHub repo for this project -
- 🔗 GitHub Repo - [CNN_hand_written_digit](https://github.com/A-m-e-y/CNN_hand_written_digit)
- I started by implementing the CNN model using pure Python code and NumPy.
- I was able to make it work for MNIST dataset, but I faced some challenges while trying to scale it up for 240x240 images.
- However, I was able to profile the code using `cProfile` and `snakeviz` and pinpoint the bottlenecks.
- I found that the bottleneck was in the convolution operation, which is a 2D matrix multiplication, which was taking a lot of time to compute.
- But this was all for 28x28 images, since I want to do this for 240x240 images, I needed to change my training dataset from MNIST to a different one which has 240x240 images.
- I tried to find this dataset online, but I couldn't find anything other than 28x28 images.
- At the end of the project, I realized why people don't do 240x240 image recognition. And because of that, we don't have a dataset for it easily available online. 😅
- So I decided to create my own dataset for 240x240 images.
- I tried to scale up the MNIST dataset from 28x28 to 240x240 images, but it didn't work at all.

---

## Week 4 -
- This week, I focused on creating my own dataset for 240x240 images.
- I asked Professor in the class about this and he suggested me to create my own images for this and tamper with the created image to get more images.
- So, I got an idea to use ChatGPT itself to generate handwritten digit images.
- My thought process was that if it can generate Studio Ghibli style images, it shouldn't be hard for it to generate handwritten digit images.
- I used the following prompt to generate the images -
  ```
    Can you generate a set of 240x240 images for me. Images should have a plain white canvas and number "0" hand-written on it.
    Remember, the number should look like it is "hand-written" by a person.
  ```
- I generated the images from 0-9 one by one and downloaded them.
- Then I created a script to tamper with the images and create more images. Below is the GitHub repo for this script -
- 🔗 GitHub Repo - [Generate_Modified_Images](https://github.com/A-m-e-y/Generate_Modified_Images)
- This script uses OpenCV, numpy and PIL to manipulate the images using following functions -
```
    add_noise, rotate_image, add_lines, add_dots, deform_image
```
- This script can generate given number of images for each digit from 0-9.
- This gave me a dataset of 240x240 images for each digit from 0-9.
- I then used this dataset to train the CNN model using pure Python code and NumPy.

---

## Week 5 -
- This week, I continued to profile the CNN model for 240x240 images.
- I was able to profile the code using `cProfile` and `snakeviz` and pinpoint the bottlenecks.
- I profiled the code for various image sizes from 28x28 to 240x240 and consistently found that the bottleneck was in the convolution operation, which is a 2D matrix multiplication.
- Profiling results are available in the GitHub repo at this location -
- 🔗 GitHub Repo - [CNN_hand_written_digit](https://github.com/A-m-e-y/CNN_hand_written_digit)
- Now that I know the bottleneck, I can now start working on the hardware implementation of the CNN model.
- I realized that I need a Floating Point MAC using of some sort to implement the hardware accelerator.
- So I focused on learning about the Floating Point MAC and how to implement it in hardware.
- I started by creating a MAC unit which can perform following operation on individual Floating Point number -
```
    output = a + b * c
```
- I created a new GitHub repo for this project -
- 🔗 GitHub Repo - [Floating_Point_MAC_HW_Accelerator](https://github.com/A-m-e-y/Floating_Point_MAC_HW_Accelerator)
- Detailed documentation for this project is available in the README.md file of this GitHub repo.
- I struggled a lot with the verilog code for this MAC unit, I tried multiple LLMs to vibe-code this MAC unit, but it was failing miserably to do so.
- So with lot of trial and error, and taking inspiration from GitHub repos, I was able to implement the MAC unit in pure Synthesizable Verilog in the end.
- I took heavy inspiration from the work of hankshyu's GitHub repo - [Link](https://github.com/hankshyu/RISC-V_MAC.git).
- I also implemented the testbench for this MAC unit using Verilog and extensively tested it.
- Then I created a Python script to test the MAC unit using `cocotb` and `iverilog`.
- I tested this MAC unit with cocotb extensively to gain some confidence that it works as expected.
- So basically, I was able to implement a fully functional IEEE-754 compliant 32-bit Floating Point MAC unit written in pure Synthesizable Verilog, with a fully automated testbench and software verification pipeline.

---

## Week 6 -
- After successfully implementing the Floating Point MAC unit last week, I started working on taking this MAC unit further.
- I started implementing an FSM which can take a 1D vector of Floating Point numbers and perform the MAC operation on it.
- I created a new GitHub repo for this project -
- 🔗 GitHub Repo - [Dot_Prod_HW_Accelerator](https://github.com/A-m-e-y/Dot_Prod_HW_Accelerator)
- Detailed documentation for this project is available in the README.md file of this GitHub repo.
- This Dot Product HW Accelerator can take 2 1D vectors of Floating Point numbers (called Patch and Filter) and perform the dot product operation on it.
- The exact operation it performs is -
```
    result = ∑ patch[i] * filter[i]
```
- I implemented the testbench for this Dot Product HW Accelerator using Verilog and extensively tested it.
- Then I created a Python script to test the Dot Product HW Accelerator using `cocotb` and `iverilog`.
- Tetsing involved generating random 1D vectors of Floating Point numbers and passing them to the Dot Product HW Accelerator. The output is then compared with the expected output calculated using NumPy in Software and output returned by the Hardware.
- I tested this Dot Product HW Accelerator with cocotb extensively to gain some confidence that it works as expected.

---

## Week 7 -
- After successfully implementing the Dot Product HW Accelerator last week, I started working on taking this further.
- Since my goal is to multiply 2 2D matrices, I started to write an FSM which can take a 2D matrix of Floating Point numbers and perform the dot product operation on it.
- I created a new GitHub repo for this project -
- 🔗 GitHub Repo - [Matrix_Dot_Product_HW_Accelerator](https://github.com/A-m-e-y/Matrix_Dot_Product_HW_Accelerator)
- Detailed documentation for this project is available in the README.md file of this GitHub repo.
- This Matrix Dot Product HW Accelerator can take 2 2D matrices of Floating Point numbers (called Patch and Filter) and perform the dot product operation on it.
- Here, my goal was to write working Verilog code, so I developed the RTL and verilog testbench to extensively test it.
- To verify the generated results, I created a Python script `test_matrix_mul.py` to test the produced output with Software Multiplication using NumPy.
- I struggled a lot with the FSM design and the Verilog code, I tried multiple LLMs to vibe-code this FSM, but it was failing miserably to do so.
- After extensive waveform analysis and debugging, I was able to implement the Matrix Dot Product engine in the end.

---

## Week 8 -
- After successfully implementing the Matrix Dot Product HW Accelerator last week, I started working on taking this further.
- I tried t integrate `cocotb` with the Matrix Dot Product HW Accelerator.
- I created a new GitHub repo for this project -
- 🔗 GitHub Repo - [MatrixMul_cocotb](https://github.com/A-m-e-y/MatrixMul_cocotb)
- Detailed documentation for this project is available in the README.md file of this GitHub repo.
- This currently doesn't use any communication bus to transfer the matrices to dut. The matrix inputs are directly exposed as top level ports to the testbench.
- Currently, this is not linked to the CNN model as well. My plan was to gain full confidence on the functionality of Matrix Multiplication happening in this engine.
- After extensively testing this Matrix Dot Product HW Accelerator with cocotb, I was able to gain some confidence that it works as expected.
- I tried adding some sort of communication bus to transfer the matrices to dut, so I created a new GitHub repo for this project -
- 🔗 GitHub Repo - [Simple_UART_Setup_v1](https://github.com/A-m-e-y/Simple_UART_Setup_v1)
- Since I wanted to take this project to FPGA, I wanted to use a simple UART setup to transfer the matrices to the dut.
- My thought process was that since our LAB already has a UART setup, I can use that to transfer the matrices to the dut on FPGA.
- But after talking with Professor, I realized that this is not the end goal of the project.
- The end goal is to take the HW Accelerator though OpenLane-2 flow and generate the GDS file and not to run this on an FPGA.
- Also, professor suggested to use `SPI` for the communication bus in the weekly codefest.
- So I decided to pivot and change my approach to use `SPI` for the communication bus.
- I created a new GitHub repo for this project -
- 🔗 GitHub Repo - [W08_C25_SPI_for_CNN](https://github.com/A-m-e-y/W08_C25_SPI_for_CNN)
- This repo contains the SPI implementation for sending 32 bit hex data to the dut.
- The testing script can test full SPI roundtrip by sending 32 bit hex data and receiving 32 bit hex data from the dut. Then it cross-verifies the received data with the expected data.
- This repo also has the `cocotb` implementation for the SPI communication, where I have moved the master to `cocotb` and kept slave in `verilog`.
- I tested this SPI implementation with cocotb extensively to gain some confidence that it works as expected.

---

## Week 9 -
- After successfully implementing the SPI communication last week, I started to integrate the SPI communication with the Matrix Dot Product HW Accelerator.
- I created a new GitHub repo for this project -
- 🔗 GitHub Repo - [W09_C27_Project_Testing](https://github.com/A-m-e-y/W09_C27_Project_Testing)
- Here, I faced some challenges while integrating the SPI communication with the Matrix Dot Product HW Accelerator.
- Somehow, I faced an issue in the SPI loader module, where it as not passing correct data to the dut.
- Somehow, it was missing the first bit of the data and sending the rest of the bits correctly. However, it was not quite clear that this was the issue as all the symptoms were pointing to the fact that MatrixMulEngine was producing wrong multiplication results.
- Vibe-coding didn't help me much here, so I had to debug the code manually. All the LLMs were halucinating and not able to help me with the issue.
- I had to get my hands dirty and debug the code manually by exporting the waveforms and carefully inspecting each and every step.
- After extensive debugging, I was able to fix the issue and get the SPI communication working with the Matrix Dot Product HW Accelerator.
- I tested this SPI communication with cocotb extensively to gain some confidence that it works as expected.
- After this I was able to seemlessly integrate this with my CNN model.
- I created a new GitHub repo for this project -
- 🔗 GitHub Repo - [W09_C28_CNN_HW_Accelerator](https://github.com/A-m-e-y/W09_C28_CNN_HW_Accelerator)
- This repo contains the CNN HW Accelerator which can take 240x240 images and perform the CNN operation on it.
- When I tried to run the CNN model on the 240x240 images, I faced some challenges with the image size.
- The matrix size was too large, size of matrix A was 57600 x 288 and B was 288 x 64.
- The details of the CNN model with each image size is available in the README.md file of this GitHub repo.
- So, I scaled down the image size to 28x28 and tried to run the CNN model on it.
- I was able to run the CNN model on the 28x28 images and get the results with `cocotb`.
- I tested this CNN HW Accelerator with cocotb extensively to gain some confidence that it works as expected and produces correct output.
- Then I tried to synthesize the design using OpenLane-2 flow.
- Here as well, the matrix size for 240x240 images was too large and it was not able to synthesize the design.
- So, I scaled down the image size to 28x28 and tried to synthesize the design.
- But I faced the next issue here, which is that my RTL is in SystemVerilog and OpenLane-2 flow doesn't support SystemVerilog.
- So, I get ann error at the yosys step that it doesn't support my SystemVerilog constructs in the RTL.
- For details of the error, please refer to this section in the README.md file of this GitHub repo - [Link] ().
- I searched online for the solution, but I couldn't find anything useful.
- There is no getting around the fact that OpenLane-2 is a community driven project and it doesn't support SystemVerilog.
- I tried to make chatGPT to convert my SystemVerilog code to Verilog, but it was not able to do so.
- Translating SystemVerilog to Verilog is a very complex task and it is not possible to do it within the timeline of this project.
- So, I decided to use Synopsys Design Compiler to synthesize the design.
- For details of the synthesis flow, please refer to this section in the README.md file of this GitHub repo - [Link] ().
- I was able to synthesize the design using Synopsys Design Compiler and get the gate-level netlist with all the important metrics like *Area, Power, Timing and transistor count*.
