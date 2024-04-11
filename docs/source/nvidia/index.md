# NVIDIA

## TensorFlow GPU support


:::{note}
This chapter is about using TensorFlow with GPU support on a Windows workstation. Since TensorFlow no longer supports GPU on native Windows, you will need to install TensorFlow on WSL2.  Therefore you need to install NVIDIA Drivers on your Windows host, CUDA Toolbox and cuDNN Library local on your WSL2 host with Linux or the tensorflow[and-cuda] package including CUDA and cuDNN in additional pip packages on WSL2.
:::

<br>

## Install options

<br>

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
<br>

## Installation Tasks

<br>

| Installation Tasks                | Target Platform |
|-----------------------------------|-----------------|
| Install NVIDIA Drivers            | Windows         |
| Install CUDA / cuDNN              | Linux           |
| Info TensorFlow with CUDA package | Python          |
| Config .bashrc                    | Linux           |

<br>
<br>

```{toctree}
nvidia_windows_driver/nvidia_windows_driver
cuda_linux/cuda_linux
cudnn_linux/cudnn_linux
bashrc/bashrc
```
