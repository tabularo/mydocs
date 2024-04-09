# CUDA @ WSL2 Ubuntu

This guide is for setting up the CUDA Toolkit and cuDNN on WSL2 Ubuntu. WSL or Windows Subsystem for Linux is a Windows feature that enables users to run native Linux applications, containers and command-line tools directly on Windows 11 and later OS builds.

:::{Warning}
**If you need CUDA for TensorFlow, think twice if you really want and need to install CUDA locally.**

Before proceeding with a local CUDA setup, consider your specific needs. If your intent is to use CUDA with TensorFlow, [TensorFlow.org](https://www.tensorflow.org/install/pip) provides a pip installer that includes the necessary CUDA packages within your environment. This avoids the complexity and potential compatibility issues of a local CUDA installation. 

Unless there are specific reasons to have a local CUDA setup, using the pip installation from [TensorFlow.org](https://www.tensorflow.org/install/pip) can be a more straightforward and efficient approach. Issues with TensorFlow are unlikely to be fixed by a local CUDA setup, and it might be worth investigating those problems within the context of TensorFlow instead. 
:::

## Installing CUDA Toolkit 11.8

The following steps guide you through the installation of the CUDA Toolkit 11.8:

### 1. Download the CUDA repository package:
 ```{code-block} bash
   :caption: Terminal    
    
   wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-wsl-ubuntu.pin
```

### 2. Move the downloaded file to /etc/apt/preferences.d/ directory

 ```{code-block} bash
   :caption: Terminal    
    
   sudo mv cuda-wsl-ubuntu.pin /etc/apt/preferences.d/cuda-repository-pin-600 
```

### 3. Download CUDA 11.8 installation package:

 ```{code-block} bash
   :caption: Terminal    
    
   wget https://developer.download.nvidia.com/compute/cuda/11.8.0/local_installers/cuda-repo-wsl-ubuntu-11-8-local_11.8.0-1_amd64.deb 
```

### 4. Install the downloaded CUDA package:

 ```{code-block} bash
   :caption: Terminal    
    
   sudo dpkg -i cuda-repo-wsl-ubuntu-11-8-local_11.8.0-1_amd64.deb 
```

### 5. Copy the keyring file to the appropriate directory:

 ```{code-block} bash
   :caption: Terminal    
    
   sudo cp /var/cuda-repo-wsll-ubuntu-11-8-local/cuda-*-keyring.gpg /usr/share/keyrings/    
```

### 6. Update your repository information:

 ```{code-block} bash
   :caption: Terminal    
    
   sudo apt-get update  
```

That's it! You've installed CUDA Toolkit 11.8 on your machine.

## Adding CUDA to System Paths

### Step 1: Open .bashrc
Open the `.bashrc` file in your home directory using a text editor. In this case, Nano is used.

 ```{code-block} bash
   :caption: Terminal
 
   nano ~/.bashrc
 ```

### Step 2: Insert Conda Configuration
At the end of the file, insert the following Conda configuration:

 ```{code-block} bash
   :caption: Terminal
   
   echo 'export PATH=/usr/local/cuda-12.2/bin${PATH:+:${PATH}}' >> ~/.bashrc
   echo 'export LD_LIBRARY_PATH=/usr/local/cuda-12.2/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}' >> ~/.bashrc
```

By adding these lines to your `.bashrc` file, you ensure that every time a new bash session starts

### Step 3: Save and Exit Nano
While in Nano editor, you can save your changes and exit by using the following shortcuts:

 ```{code-block} bash
   :caption: Terminal    
    `Ctrl + O`           # to save the file.
    
    `Ctrl + X`           # to exit the nano editor.
```

## Verify CUDA version

After installing your CUDA version, verify the installation using the following command:

 ```{code-block} bash
   :caption: Terminal    
    
   nvcc --version    
```

## Removing the CUDA Toolkit
If you need to uninstall the CUDA Toolkit, refer to the official [CUDA Documentation](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/) for instructions. Here's the main command to do so:

```{code-block} bash
   :caption: Terminal   
    
    sudo apt-get --purge remove "*cuda*" "*cublas*" "*cufft*" "*cufile*" "*curand*" "*cusolver*" "*cusparse*" "*npp*" "*nvjpeg*" "*nvvm*"
```

---

## NVIDIA.com Links

| Title   | Description                                                                   |
|--------------------------------------------------------------|-------------------------------------------------------------------------------|
| [CUDA on WSL User Guide ](https://docs.nvidia.com/cuda/wsl-user-guide/index.html#cuda-support-for-wsl-2) | Detailed guide for using NVIDIA CUDA on Windows Subsystem for Linux           |
| [CUDA Toolkit Archive](https://developer.nvidia.com/cuda-toolkit-archive) | Comprehensive archive of latest and archived versions of NVIDIA CUDA toolkit. |