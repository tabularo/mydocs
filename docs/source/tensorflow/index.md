# TensorFlow GPU

This chapter is about installing **TensorFlow** with and without CUDA packages as well as **TensorRT**.

:::{important}
 TensorFlow 2.10 was the last TensorFlow release that supported GPU on native-Windows. Starting with TensorFlow 2.11, you will need to install TensorFlow in WSL2.
:::

## Installation on Windows via WSL2

Installing TensorFlow within WSL2 is an efficient approach as it allows you to leverage the performance benefits of the Linux kernel while working in a Windows environment. The setup process includes installing a Linux distribution on Windows using WSL2, configuring a Python environment, preferably using Anaconda, and then installing TensorFlow into this environment.

:::{mermaid}
graph TB;
    classDef green fill:#9f6,stroke:#333,stroke-width:2px;
    subgraph "Windows_host"
        subgraph "WSL2_guest"
            A[Anaconda]
        end
    end
    class WSL2_guest green
:::

<br>

:::{warning}

Installing `TensorFlow with GPU support` can be a nightmare - **expect challenges**. 

If the installation didn't work, starting a trial-and-error process can exacerbate the problems and mess everything up.

I highly recommend you carefully consider whether you choose option 1 or option 2. I recommend you favor Option 2 and only choose Option 1 if it is absolutely necessary and you are sure you can handle it. Option 1 is much more complex in terms of installation and maintenance.


see also, [CUDA Installation](http://localhost:63342/mydocs/docs/build/html/nvidia/cuda_linux/cuda_linux.html)
:::

<br>

## Install options

:::{mermaid}

graph TB;
    classDef red fill:#f96,stroke:#AAA,stroke-width:0.5px;
    classDef green fill:#90EE90,stroke:#AAA,stroke-width:0.5px;

    subgraph "    Host    "
        A[Host: Windows] 
        A --> B[NVIDIA Driver];
    end

    subgraph "Option 1        "
        B --> C[Guest: WSL2];
        C --> D[CUDA Toolkit + cuDNN Libraries];
        D --> E["TensorFlow package"];
    end

    subgraph "Option 2        "
        B --> F[Guest: WSL2];
        F --> G["TensorFlow[and-cuda] package"];
    end

    class B,D red;
    class A,C,F green;
:::

<br>

## Software Installation Dependency Chart

:::{mermaid}
graph LR
    A[TensorFlow] -->|Option 1| B[Setuptools]
    C["TensorFlow[and Cuda]"] -->|Option 2| B
    subgraph TensorFlowRT
        B --> D[Nvidia-pyindex]
        D --> E[Nvidia-TensorRT]
    end
:::

<br>
<br>


## Table of content
```{toctree}
tensorflow
tensorrt
pythonpattern
```