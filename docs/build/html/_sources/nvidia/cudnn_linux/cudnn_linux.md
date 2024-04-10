# cuDNN @ WSL2 Ubuntu

This guide is for setting up the CUDA Toolkit and cuDNN on WSL2 Ubuntu. WSL or Windows Subsystem for Linux is a Windows feature that enables users to run native Linux applications, containers and command-line tools directly on Windows 11 and later OS builds.

:::{Warning}
**If you need CUDA for TensorFlow, think twice if you really want and need to install CUDA locally.**

Before proceeding with a local CUDA setup, consider your specific needs. If your intent is to use CUDA with TensorFlow, [TensorFlow.org](https://www.tensorflow.org/install/pip) provides a pip installer that includes the necessary CUDA packages within your environment. This avoids the complexity and potential compatibility issues of a local CUDA installation. 

Unless there are specific reasons to have a local CUDA setup, using the pip installation from [TensorFlow.org](https://www.tensorflow.org/install/pip) can be a more straightforward and efficient approach. Issues with TensorFlow are unlikely to be fixed by a local CUDA setup, and it might be worth investigating those problems within the context of TensorFlow instead. 
:::

## Installing cuDNN 8.6.0

The following steps guide you through the installation of NVIDIA CUDA® Deep Neural Network library (cuDNN)

### Download cuDNN 8.6.0

> [download from here](https://developer.nvidia.com/compute/cudnn/secure/8.6.0/local_installers/11.8/cudnn-linux-x86_64-8.6.0.163_cuda11-archive.tar.xz)

:::{admonition} Other versions of cuDNN
[redist/cudnn](https://developer.nvidia.com/compute/cudnn/)
:::

### 1. Install the zlib1g package:
Install the zlib1g library as superuser.

 ```{code-block} bash
   :caption: Terminal
 
   sudo apt-get install zlib1g
 ```

### 2. Extract the downloaded tar.xz file:
Extract the downloaded cuDNN tar.xz file:

 ```{code-block} bash
   :caption: Terminal
 
   tar -xvf cudnn-linux-x86_64-8.6.0.163_cuda11-archive.tar.xz
 ```

### 3. Copy the extracted  files to the CUDA include directory:
Copy the header files from the 'include' directory in the extracted folder to the CUDA 'include' directory.

 ```{code-block} bash
   :caption: Terminal
 
   sudo cp cudnn-*-archive/include/cudnn*.h /usr/local/cuda/include 
 ```

### 4. Copy the files to the CUDA lib64 directory:
Copy the library files from the 'lib' directory in the extracted folder to the 'lib64' directory in the CUDA folder.

 ```{code-block} bash
   :caption: Terminal
 
   sudo cp -P cudnn-*-archive/lib/libcudnn* /usr/local/cuda/lib64 
 ```
### 5. Modify the permission:
Change the permission of the copied files to provide read access to all users.

 ```{code-block} bash
   :caption: Terminal
 
   sudo chmod a+r /usr/local/cuda/include/cudnn*.h /usr/local/cuda/lib64/libcudnn*
 ```

That's it! You've installed the cuDNN Library for Linux on your machine.

:::{note}
Please be aware that all commands should be executed in a Linux terminal. The provided code has been tested on an Ubuntu 22.04 system with CuDNN 8.6. Therefore, ensure to replace specific version identifiers like `8.6.0.163_cuda11` in the given examples with the actual versions in use on your system.
:::

## NVIDIA.com Links

| Title   | Description                                                                   |
|--------------------------------------------------------------|-------------------------------------------------------------------------------|


