# Weekly Challenges and Codefest

- Here is the Quick Summary and GitHub repo links for the weekly challenges and codefests.
- Detailed documentation for each challenge is available in the respective README.md file in the GitHub repositories.

---

## 1. Week 1

### Challenge #1 - Beyond CMOS 2023
#### Objective
- Go to the IEEE International Roadmap for Devices and Systems (IRDS) website (https://irds.ieee.org) and browse through the “Beyond CMOS” 2023 update roadmap to get a sense of the variety of devices that are being considered for beyond Moore technologies: https://irds.ieee.org/images/files/pdf/2023/2023IRDS_BC.pdf
#### Learnings
<details>
      <summary>Click to expand</summary>
      
- Below are some key takeaways from the 2023 “Beyond CMOS” roadmap (IRDS), highlighting the breadth of technologies being explored beyond traditional Moore-scaling:
- **Beyond Moore Focus**  
  - Exploring alternatives to CMOS scaling using new device physics, materials, and architectures.

- **Emerging Memory Technologies**  
  - **STT-MRAM**, **ReRAM**, **FeFET**, and **FTJ** are leading non-volatile memory candidates.  
  - Also includes Mott-transition and polymer-based memory concepts.

- **New Logic Devices**  
  - Spintronics, straintronics, and magnetics offer potential for energy-efficient logic.  
  - Focus on non-charge-based switching mechanisms.

- **Architectural Co-Design**  
  - Devices designed in parallel with systems for neuromorphic and in-memory computing.  
  - Supports unconventional, brain-inspired architectures.

- **Alternative Computing Models**  
  - Emphasis on analog, neural, and non-Von Neumann paradigms for better parallelism and efficiency.

- **Advanced Materials Integration**  
  - Use of TMDCs, high-k dielectrics, and 3D stacking to support new device designs.

- **Benchmarking and Readiness**  
  - Each tech is evaluated for energy, performance, scalability, and manufacturability.

- **Heterogeneous Integration**  
  - Combining CMOS with new devices to enhance system capabilities (More-than-Moore).

- **Manufacturing Challenges**  
  - Focused on sub-2 nm scaling, new metrology tools, and reliable fabrication processes.
</details>

---

### Challenge #4 - Replicate the Johns Hopkins paper of a Spiking Neuron Array
#### GitHub Repository
- 🔗 GitHub Repo - [W01_C04_SNN](https://github.com/A-m-e-y/W01_C04_SNN)
#### Quick Overview
- This project replicates the Johns Hopkins paper: "Designing Silicon Brains using LLM: Leveraging ChatGPT for Automated Description of a Spiking Neuron Array".
- The goal is to implement a synthesizable SystemVerilog code for a programmable Spiking Neuron Array ASIC.
- Instead of using `ChatGPT4`, this project uses `Claude 3.5 Sonnet`.
- Instead of writing the code in `Verilog`, this project uses `SystemVerilog`.

### Challenge #5 - Python Bytecode Analysis and Profiling
#### GitHub Repository
- 🔗 GitHub Repo - [W01_C05_PyBytecode](https://github.com/A-m-e-y/W01_C05_PyBytecode)
#### Quick Overview
- This project's goal is to identify the most commonly used bytecode instructions across a variety of Python scripts and gain insights into their performance characteristics.
- Chosen workloads are:
  - QuickSort
  - 2 Layer Perceptron
  - Matrix Multiplication

---

## 2. Week 2

### Challenge #6 - Perceptron Logic Gate Visualizations
#### GitHub Repository
- 🔗 GitHub Repo - [W02_C06_Perceptron](https://github.com/A-m-e-y/W02_C06_Perceptron)
#### Quick Overview
- This project demonstrates the implementation of a perceptron to learn basic logic gates (AND, OR, NAND, NOR).
- Each gate has its own Python script, `Simple_Perceptron_<gate_name>.py`.

### Challenge #7
#### GitHub Repository
- 🔗 GitHub Repo - [W02_C07_Perceptron](https://github.com/A-m-e-y/W02_C06_Perceptron)
#### Quick Overview
- This project visualizes the learning process of a perceptron.
- Each gate has its own Python script, `visualize_<gate_name>.py`.
- Visualization is done using `matplotlib` to plot the decision boundary and the data points.
- *GIF animation* of the learning process can be seen in the README.md file of the repository.
- Created a Single Layer Perceptron for XOR gate in the script `Simple_Perceptron_XOR.py` and `Visualize_XOR.py` which visually demonstrates the problem - Why XOR is not linearly separable?
- This helps answer the question - Why at least Two Layers Are Needed for XOR and XNOR Gates.

### Challenge #8
#### GitHub Repository
- 🔗 GitHub Repo - [W02_C08_Perceptron](https://github.com/A-m-e-y/W02_C06_Perceptron)
#### Quick Overview
- This project demonstrates the implementation of a multi-layered perceptron to learn XOR and XNOR logic gates.
- Each gate has its own Python script, `Multi_Layer_Perceptron_XOR.py`.
- Visualization of the learning process is done using `visualize_multi_XOR.py`.

#### Extra Challenges from SLACK Channel
- Creating a single perceptron network with multiple outputs:
  - Single Layer - Multiple Outputs Perceptron is implemented in the script `Simple_Perceptron_Multi_Gates.py`
  - Multi Layer - Multiple Outputs Perceptron is implemented in the script `Multi_Layer_Perceptron_All_Gates.py`

### Challenge #9
#### Quick Overview
- Chose the topic for Final Project - "CNN Digit Recognizor for 240x240 Images"
- Answered the Helmier's questions in the given word doc.
- Started to implement the pure software implementation of the project.
- For detailed journal of the project, please refer to the [Project Journal](project_journal.md).

---

## 3. Week 3

### Challenge #10 - Identify computational bottlenecks in Frozen Lake Problem
#### GitHub Repository
- 🔗 GitHub Repo - [W03_C10_Frozen_Lake](https://github.com/A-m-e-y/W03_C10_Frozen_Lake)
#### Quick Overview
- This project identifies computational bottlenecks in the Frozen Lake problem and proposes a hardware acceleration solution.
- The project uses the `Frozen Lake` environment from Gymnasium library and implements a Q-learning algorithm to solve the problem.
- It clearly demonstrates that the bottleneck is the `Q-table update` step, which is implemented using `update_q_value()` function.
- Performance comparison is shown here: [Link](https://github.com/A-m-e-y/W03_C10_Frozen_Lake?tab=readme-ov-file#performance-comparison)

#### Hardware Acceleration Solution
- I have implemented a hardware acceleration solution in the following GitHub repository:
  - 🔗 GitHub Repo - [Frozen_Lake_HW_Accelerator](https://github.com/A-m-e-y/Frozen_Lake_HW_Accelerator)
- The project includes:
  - A Python-based Q-learning implementation for the Frozen Lake environment.
  - A hardware implementation of the Q-value update formula in Verilog.
  - H/W <> S/W co-simulation using `cocotb` framework.
  - A comparison framework to validate and benchmark the hardware implementation against the software implementation.

### Challenge #11 - Implementing GPU acceleration for Frozen Lake Problem
#### GitHub Repository
- 🔗 GitHub Repo - [W03_C11_Frozen_Lake](https://github.com/A-m-e-y/W03_C10_Frozen_Lake)
#### Quick Overview
- This project implements GPU acceleration for the Frozen Lake problem using CuPy.
- The goal is to offload the Q-table update step to the GPU to improve performance.
- The project uses the `CuPy` library to leverage GPU available on My Laptop `Nvidia RTX 3050`.
- Detailed performance comparison is shown here: [Link](https://github.com/A-m-e-y/W03_C10_Frozen_Lake?tab=readme-ov-file#performance-comparison)

### Challenge #12
#### Quick Overview
- Started to implement the pure software implementation of the project.
- I studied and chose `cocotb` as the testbench framework for the project.
- For detailed journal of the project, please refer to the [Project Journal](https://a-m-e-y.github.io/ECE_510_Documentation/project_journal.html).

---

## 4. Week 4

### Challenge #13 - Benchmarking different SAXPY problem sizes
#### GitHub Repository
- 🔗 GitHub Repo - [W04_C13_SAXPY](https://github.com/A-m-e-y/W04_C13_SAXPY)
#### Quick Overview
- This experiment explores the performance characteristics of executing the SAXPY (Single-Precision A * X Plus Y) operation on both CPU and GPU, using an NVIDIA RTX-3050 4GB VRAM GPU and i5-12450H CPU.
- This experiment clearly demonstrates that raw GPU power is not enough — understanding the memory bottlenecks and execution model is essential when designing GPU-accelerated workloads.
- GPU acceleration only delivers real benefits when you:
  - Minimize transfers
  - Increase arithmetic intensity
  - Optimize for data locality
- This benchmark serves as a cautionary tale: More threads ≠ more speed, unless you architect your program to take full advantage of GPU design.
- All the interesting results are shown in the README.md file of the repository.
- Performance comparison is present at this location in README.md file: [Link](https://github.com/A-m-e-y/W04_C13_SAXPY#-visualization-1-cpu-vs-gpu-total-time-log-scale)

### Challenge #14 - Fibonacci sequence in CUDA
#### GitHub Repository
- 🔗 GitHub Repo - [W04_C14_Fibonacci](https://github.com/A-m-e-y/W04_C14_Fibonacci)
#### Quick Overview
- This project implements the Fibonacci sequence calculation using CUDA.
- The goal is to compare the performance of the CUDA implementation with a CPU-based implementation.
- The data clearly demonstrates that, even though the GPU kernel execution is significantly faster than the CPU, the total GPU execution time is more than 2x slower due to massive overhead from memory transfers and allocations.
- Benchmarking data clearly shows that the GPU spends less than 1/3 of its time doing useful computation. The rest is lost to cudaMalloc, cudaMemcpy, and cudaFree.
- All the interesting data and visualizations are shown at this location in README.md file: [Link](https://github.com/A-m-e-y/W04_C14_Fibonacci#-full-metrics-breakdown)

---

## 5. Week 5

### Challenge #16 - Benchmarking SAXPY with PyTorch
#### GitHub Repository
- 🔗 GitHub Repo - [W05_C16_feedforward_NN](https://github.com/A-m-e-y/W05_C16_feedforward_NN)
#### Quick Overview
- This project aims to:
  - Benchmark a simple fully connected neural network (FCNN) with increasing number of hidden layers (1 to 10).
  - Compare execution time across:
    - CUDA (custom kernel)
    - PyTorch GPU
    - PyTorch CPU
  - Ensure fair benchmarking by including all overheads: memory allocation, H2D/D2H copies, and kernel launch.
  - Produce plot-ready CSV files and detailed performance comparison visuals.
- All the interesting data and visualizations are shown at this location in README.md file: [Link](https://github.com/A-m-e-y/W05_C16_feedforward_NN#collected-results)

### Challenge #17 - Sorting on a systolic array
#### GitHub Repository
- 🔗 GitHub Repo - [W05_C17_BubbleSort_Systolic_Array](https://github.com/A-m-e-y/W05_C17_BubbleSort_Systolic_Array)
#### Quick Overview
- This project implements a bubble sorting algorithm on a systolic array.
- The goals of the project are:
  - Implement Bubble Sort using a standard CPU approach (pure Python).
  - Design and simulate a systolic array version of Bubble Sort using NumPy.
  - Benchmark both implementations over different input sizes.
  - Visualize and analyze performance using a log-scaled bar chart.
- Generated animation of the systolic array sorting process is available at this location in the README.md file: [Link](https://github.com/A-m-e-y/W05_C17_BubbleSort_Systolic_Array#visualization-of-a-systolic-array)

---

## 6. Week 6

### Challenge #19: Implement a binary LIF neuron
#### GitHub Repository
- 🔗 GitHub Repo - [W06_C19_Binary_LIF_Neuron](https://github.com/A-m-e-y/W06_C19_Binary_LIF_Neuron)
#### Quick Overview
- This project implements a binary leaky integrate-and-fire (LIF) neuron model in Verilog.
- The goals of the project are:
  - Implement the binary LIF neuron model in Verilog.
  - Simulate the neuron's response to various input stimuli.
  - Analyze the neuron's behavior and performance characteristics.

---

## 7. Week 7

### Challenge #22: Broadening your horizon about neuromorphic computing
#### GitHub Repository
- 🔗 GitHub Repo - [W07_C22_Neuromorphic_Computing](https://github.com/A-m-e-y/W07_C22_Neuromorphic_Computing)
#### Quick Overview
- This project explores the principles and applications of neuromorphic computing.
- The goals of the project are:
  - Understand the key concepts of neuromorphic computing.
  - Read the paper Kudithipudi, D., Schuman, C., Vineyard, C.M. et al. Neuromorphic computing at scale. Nature 637, 801–812 (2025).
  - Write a “blog” post which answers the following questions:
    - The authors discuss several key features necessary for neuromorphic systems at scale (distributed hierarchy, sparsity, neuronal scalability, etc.). Which of these features do you believe presents the most significant research challenge, and why? How might overcoming this challenge transform the field?
    - The article compares neuromorphic computing's development to the evolution of deep learning, suggesting it awaits its own "AlexNet moment." What specific technological or algorithmic breakthrough might trigger such a moment for neuromorphic computing? What applications would become feasible with such a breakthrough?
    - The authors highlight the gap between hardware implementation and software frameworks in neuromorphic computing compared to traditional deep learning. Develop a proposal for addressing this gap, specifically focusing on how to create interoperability between different neuromorphic platforms.
    - The review emphasizes the importance of benchmarks for neuromorphic systems. What unique metrics would you propose for evaluating neuromorphic systems that go beyond traditional performance measures like accuracy or throughput? How would you standardize these across diverse neuromorphic architectures?
    - How might the convergence of emerging memory technologies (like memristors or phase-change memory) with neuromorphic principles lead to new computational capabilities not possible with traditional von Neumann architectures? What specific research directions seem most promising?.

---

## 8. Week 8

### Challenge #25: Building and co-simulating an SPI interface in Python and Verilog
#### GitHub Repository
- 🔗 GitHub Repo - [W08_C25_SPI_for_CNN](https://github.com/A-m-e-y/W08_C25_SPI_for_CNN)
#### Quick Overview
- This project aims to build and co-simulate an SPI interface in Python and Verilog.
- The goals of the project are:
  - Understand the SPI protocol and its requirements.
  - Implement the SPI interface in Verilog.
  - Create a Python script to run the SPI master in cocotb.
  - Co-simulate the Verilog and Python components in cocotb to verify the functionality.
  - Benchmark the SPI interface performance to use the numbers in Project.

---

## 9. Week 9

### Challenge #26: BrainChip’s IP for Targeting AI Applications at the Edge
#### GitHub Repository
- 🔗 GitHub Repo - [W09_C26_BrainChip_Podcast](https://github.com/A-m-e-y/W09_C26_BrainChip_Podcast)
#### Quick Overview
- This task focuses on Listening to the EETimes BrainChip podcast.
- The goals of the project are:
  - Listen and understand the capabilities of BrainChip’s Akida architecture.
  - Do a short write-up which compares the BrainChip approach to GPUs and other neuromorphic chips that we have seen in class.

---

## 10. Week 10

### Challenge #28: Model and simulate a memristor
#### GitHub Repository
- 🔗 GitHub Repo - [W10_C28_Memristor](https://github.com/A-m-e-y/W10_C28_Memristor)
#### Quick Overview
- This task focuses on learning how to model and simulate a memristor in Python.
- The goals of the project are:
  - Understand the underlying principles of memristors and their behavior.
  - Plot the I-V characteristics of a memristor.
  - Implement a memristor model in Python and simulate its response to various frequencies.
