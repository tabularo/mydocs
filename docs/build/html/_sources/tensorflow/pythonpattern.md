# Jupyter Setup Blocks

## Import Libraries

```{code-block} python
    :caption: import libraries
    :linenos:
    :emphasize-lines: 3
import sys
import tensorrt as trt
import tensorflow as tf
```

Output:
<p style="color: red;">
2024-04-12 07:06:13.429787: I tensorflow/core/platform/cpu_feature_guard.cc:182] This TensorFlow binary is optimized to use available CPU instructions in performance-critical operations.<br/>
To enable the following instructions: AVX2 AVX512F AVX512_VNNI AVX512_BF16 FMA, in other operations, rebuild TensorFlow with the appropriate compiler flags.
</p>

---
Responsible for the out put is line 3.

The TensorFlow informational message (even though it's displayed in red) is neither an error nor a warning, but simply informational. The red output might seem alarming, but it's just TensorFlow's way of sharing significant system information. The message states that the TensorFlow binary you're using has been optimized to leverage specific CPU instructions in performance-driven operations. However, certain available CPU instructions - namely AVX2, AVX512F, AVX512_VNNI, AVX512_BF16, and FMA - aren't being utilized in other operations. If you wish to utilize these for potential performance enhancements, you would need to rebuild TensorFlow from the source with the appropriate compiler flags. It's crucial to remember, though, that while these specific instruction sets can add considerable value, rebuilding TensorFlow to include them may result in only slight performance improvements for most users.

<br>

## Checking Python and TensorFlow Configuration

```{code-block} python
    :caption: import libraries
    :linenos:
    :emphasize-lines: 11, 18
    
print("\n")
print("Python Interpreter")
print("==================")
print("Python version", sys.version)

print("\n")
print("Python Packages")
print("===============")
print('tensorflowRT Version: ', trt.__version__)
print("TensorFlow version:", tf.__version__)
print("CUDA is available: ", tf.test.is_built_with_cuda())
print("CUDA version:", tf.sysconfig.get_build_info()["cuda_version"])
print("cuDNN version:", tf.sysconfig.get_build_info()["cudnn_version"])

print("\n")
print("GPU Support")
print("===========")
print("Is GPU available:", tf.config.list_physical_devices('GPU'))
```

Output:

    Python Interpreter  
    ==================  
    Python version 3.11.5 (main, Sep 11 2023, 13:54:46) [GCC 11.2.0]  
    
    
    Python Packages  
    ===============
    tensorflowRT Version:  8.6.1  
    TensorFlow version: 2.13.0  
    CUDA is available:  True  
    CUDA version: 11.8  
    cuDNN version: 8  
    
    
    GPU Support  
    ===========
    Is GPU available: [PhysicalDevice(name='/physical_device:GPU:0', device_type='GPU')]  
    
<p style="color: red;">
2024-04-12 07:19:51.782689: I tensorflow/compiler/xla/stream_executor/cuda/cuda_gpu_executor.cc:981] could not open file to read NUMA node: /sys/bus/pci/devices/0000:01:00.0/numa_node
Your kernel may have been built without NUMA support. <br>
2024-04-12 07:19:51.864908: I tensorflow/compiler/xla/stream_executor/cuda/cuda_gpu_executor.cc:981] could not open file to read NUMA node: /sys/bus/pci/devices/0000:01:00.0/numa_node
Your kernel may have been built without NUMA support. <br>
2024-04-12 07:19:51.865059: I tensorflow/compiler/xla/stream_executor/cuda/cuda_gpu_executor.cc:981] could not open file to read NUMA node: /sys/bus/pci/devices/0000:01:00.0/numa_node
Your kernel may have been built without NUMA support. <br>
</p>

---

Responsible for the output are lines 11, 18.

The output in red might appear alarming; however, this message is neither a warning nor an error. In fact, it's an informational message produced by TensorFlow, as indicated by the leading 'I'.

It indicates that TensorFlow tried to check for Non-Uniform Memory Access (NUMA) support by looking at the numa_node file for your GPU device and could not find it. This suggests that your Linux kernel may not have been built with support for NUMA.

However, lack of NUMA support is not typically an issue for most TensorFlow workflows unless you are working in a high performance computing environment with very specific requirements. Your TensorFlow operations should still work as expected.


<br>

## CUDA version and path

```{attention}
When querying the CUDA version within a Python environment, the result might not always be what you expect. The version returned could be that of the CUDA toolkit installed on the system, or it could be tied to a specific Python package like PyCUDA or TensorFlow. The reported version could also depend on your PATH and environment variables. Therefore, be mindful about which CUDA version is being referred to in different contexts within Python.
```


```{code-block} python
    :caption: Get CUDA version and path

import subprocess


def get_cuda_version_and_path():
    try:
        nvcc_path = subprocess.check_output(['which', 'nvcc']).decode('utf-8').strip()
        output = subprocess.check_output(["nvcc", "--version"]).decode("utf-8")
        version_line = [line for line in output.split("\n") if "release" in line][0]
        version = version_line.split("release ")[-1].split(",")[0]
        return version, nvcc_path
    except Exception as e:
        print(f"Could not retrieve CUDA version or path: {str(e)}")
        return None


version, path = get_cuda_version_and_path()
print(f"CUDA version: {version}")
print(f"NVCC path: {path}")
```
Output:

    CUDA version: 11.5  
    NVCC path: /usr/bin/nvcc

<br>

## Setting CUDA path in environment

```{code-block} python
    :caption: Change CUDA path
import os

 os.environ['PATH'] = '/usr/local/cuda/bin:' + os.environ['PATH']
```

