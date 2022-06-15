# Cross-Compiling C++ for different architectures

## Introduction

When writing my program clcalc, I wanted it to be available for both x86 and arm64 architectures. To do this, I'd run both my Raspberry Pi and my Windows PC to compile the binaries needed for each architecture. This was a bit annoying, as I had to swap around monitors while programming, just to test if the program worked on both machines. 
That's the main reason for me to use a cross compiler that targets the arm64 architecture.

## Prerequisites 

Make sure that `aarch64-linux-gnu-g++` is installed and working.

To install it, run:

```bash
sudo apt-get install g++-aarch64-linux-gnu
```

## Command

```bash
aarch64-linux-gnu-g++ -o main main.cpp
```

By using this special compiler instead of your standard compiler (I use g++), you can create a binary that can be executed by systems that have the arm64 architecture.