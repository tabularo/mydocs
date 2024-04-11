# TensorFlow

This chapter is about installing **TensorFlow** with and without CUDA packages as well as **TensorRT**.

:::{warning}

Installing `TensorFlow with GPU support` can be a nightmare - **expect challenges**. 

If the installation didn't work, starting a trial-and-error process can exacerbate the problems and mess everything up.

I highly recommend you carefully consider whether you choose option 1 or option 2. I recommend you favor Option 2 and only choose Option 1 if it is absolutely necessary and you are sure you can handle it. Option 1 is much more complex in terms of installation and maintenance.


see also, [CUDA Installation](http://localhost:63342/mydocs/docs/build/html/nvidia/cuda_linux/cuda_linux.html)
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
```