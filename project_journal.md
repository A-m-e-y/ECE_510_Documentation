# Project Journal

This section tracks the progress of my course project, week-by-week.

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
- I also implemented the testbench for this MAC unit using Verilog and extensively tested it.
- Then I created a Python script to test the MAC unit using `cocotb` and `iverilog`.
- I tested this MAC unit with cocotb extensively to gain some confidence that it works as expected.
-- So basically, I was able to implement a fully functional IEEE-754 compliant 32-bit Floating Point MAC unit written in pure Synthesizable Verilog, with a fully automated testbench and software verification pipeline.

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

## Week 7 -
