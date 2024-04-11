# TensorFlow

This guide is for installing TensorFlow with GPU support on Windows WSL2.

## Option 1: TensorFlow *package*

### Prerequisites

Verify that `NVIDIA GPU Driver` is installed

- Verify, see [Verfiy NIDIA Driver `nvidia-smi`](http://localhost:63342/mydocs/docs/build/html/nvidia/nvidia_windows_driver/nvidia_windows_driver.html)
- In this documentation called "option 1", you need to install CUDA local on your WSL2 guest, see [NVIDIA](http://localhost:63342/mydocs/docs/build/html/nvidia/index.html)

### Installation

Installation is straightforward

    pip install --upgrade pip
    pip install tensorflow==2.13


## Option 2: TensorFlow[and-cuda] *package*

### Prerequisites

No prerequisites, except installing NVIDIA Graphics driver on your windows machine, do nothing ;-)

### Installation

Installation is straightforward

    pip install --upgrade pip
    pip install tensorflow[and-cuda]




## Verify Installation

 ```{code-block} bash
   :caption: Terminal (WSL2 guest)

    python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
 ```

:::{note}
You could expect some error messages, that doesn't mean TensorFlow didn't work properly. For me, April 2024, tensorflow v2.13, still works best.

From my side you could ignore, error/warings, like:

> I tensorflow/core/platform/cpu_feature_guard.cc:182] This TensorFlow binary is optimized to use available CPU instructions in performance-critical operations.
To enable the following instructions: AVX2 AVX512F AVX512_VNNI AVX512_BF16 FMA, in other operations, rebuild TensorFlow with the appropriate compiler flags.

> Your kernel may have been built without NUMA support.

This is the important part:

> [PhysicalDevice(name='/physical_device:GPU:0', device_type='GPU')]

That means GPU is available.

:::


