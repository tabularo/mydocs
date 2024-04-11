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
   :caption: Terminal (WSL2 guest)
 
   sudo apt-get install zlib1g
 ```

### 2. Extract the downloaded tar.xz file:
Extract the downloaded cuDNN tar.xz file:

 ```{code-block} bash
   :caption: Terminal (WSL2 guest)
 
   tar -xvf cudnn-linux-x86_64-8.6.0.163_cuda11-archive.tar.xz
 ```

### 3. Copy the extracted  files to the CUDA include directory:
Copy the header files from the 'include' directory in the extracted folder to the CUDA 'include' directory.

 ```{code-block} bash
   :caption: Terminal (WSL2 guest)
 
   sudo cp cudnn-*-archive/include/cudnn*.h /usr/local/cuda/include 
 ```

### 4. Copy the files to the CUDA lib64 directory:
Copy the library files from the 'lib' directory in the extracted folder to the 'lib64' directory in the CUDA folder.

 ```{code-block} bash
   :caption: Terminal (WSL2 guest)
 
   sudo cp -P cudnn-*-archive/lib/libcudnn* /usr/local/cuda/lib64 
 ```
### 5. Modify the permission:
Change the permission of the copied files to provide read access to all users.

 ```{code-block} bash
   :caption: Terminal (WSL2 guest)
 
   sudo chmod a+r /usr/local/cuda/include/cudnn*.h /usr/local/cuda/lib64/libcudnn*
 ```

That's it! You've installed the cuDNN Library for Linux on your machine.

:::{note}
Please be aware that all commands should be executed in a Linux terminal. The provided code has been tested on an Ubuntu 22.04 system with CuDNN 8.6. Therefore, ensure to replace specific version identifiers like `8.6.0.163_cuda11` in the given examples with the actual versions in use on your system.
:::

<br>

## Updating CUDA Library Links

**Updating CUDA Library Symbolic Links @ Windows (WSL2 host)**

:::{hint}
Modifications we do here, these files are created by [NVIDIA Installer](../nvidia_windows_driver/nvidia_windows_driver.md). Also keep in mind if you reinstall the `NVIDIA Driver` this modifications will be overwritten.
:::

### 1. Open Powershell *as admin* 

> Run the commands below in Windows `Command Prompt` or `Powershell` **as admin** (thanks to Roy Shilkrot) and restart your WSL2.

### 2. Change directory

Navigate you into the \Windows\System32\lxss\lib directory

 ```{code-block} bash
   :caption: Powershell (WSL2 host)
 
   cd \Windows\System32\lxss\lib
 ```

### 3. Delete existing files

 ```{code-block} bash
   :caption: Powershell (WSL2 host)
 
   del libcuda.so && del libcuda.so.1
 ```

### 3. Create Symlinks

 ```{code-block} bash
   :caption: Powershell (WSL2 host)
 
   mklink libcuda.so libcuda.so.1.1 && mklink libcuda.so.1 libcuda.so.1.1 
 ```

### 4. Restart WS

 ```{code-block} bash
   :caption: Powershell (WSL2 host)
   # shuts down all running WSL2 instances
   wsl --shutdown
   
   # Starting a new WSL instance which restarts the service automatically
   wsl
 ```


### 5. Adding cuDNN to System Paths

> see [.bashrc configurations > adding cuDNN to system path](../bashrc/bashrc.md)

## Uninstall / Update cuDNN

### 1. Identify the Files to be Removed

In the default installation, cudnn files are located at:

- path: `/usr/local/cuda/include/` - file names: `cudnn*.h`
- path: `/usr/local/cuda/lib64/` - file names: `libcudnn*`


These are the files that were copied during the cudnn installation.

### 2. Remove CUDAnn Library Files

To uninstall CUDAnn, these files need to be removed, open the terminal and execute the following commands:

 ```{code-block} bash
   :caption: Terminal (WSL2 guest)

    sudo rm /usr/local/cuda/include/cudnn*.h /usr/local/cuda/lib64/libcudnn*
 ```

After executing these commands, the CUDAnn library will be uninstalled from your system.

Please note:
- If your setup differs from the default paths mentioned, replace the <path/to/> part with the actual directory paths.
- Always double-check before running these commands to prevent the removal of unintended files.
- Make sure you have sudo privileges to perform these operations.
Be aware that these steps only remove the CUDAnn library files. Therefore, if you have installed other software that depends on this library, double-check as they might not work properly after the removal.

<br>

## NVIDIA.com Links

| Title   | Description                                                                    |
|--------------------------------------------------------------|--------------------------------------------------------------------------------|
| [cuDNN Driver Archive](https://developer.nvidia.com/rdp/cudnn-archive) | Comprehensive archive of latest and archived versions of NVIDIA cuDNN library. |

<br>
<br>

