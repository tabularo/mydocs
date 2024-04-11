# .bashrc

## Editing .bashrc

### Step 1: Open .bashrc
Open the `.bashrc` file in your home directory using a text editor. In this case, Nano is used.

 ```{code-block} bash
   :caption: Terminal
 
   nano ~/.bashrc
 ```

### Step 2: Save and Exit Nano
While in Nano editor, you can save your changes and exit by using the following shortcuts:

 ```{code-block} bash
   :caption: Terminal    
    `Ctrl + O`           # to save the file.
    
    `Ctrl + X`           # to exit the nano editor.
```

---

## .bashrc Configurations

### Adding CUDA to System Paths
At the end of the file, insert the following Conda configuration:

 ```{code-block} bash
   :caption: nano
   
   # Adding CUDA to System Paths
   'export PATH=/usr/local/cuda-12.2/bin${PATH:+:${PATH}}'
   'export LD_LIBRARY_PATH=/usr/local/cuda-12.2/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}'
```

:::{note}
After adding these export statements, ensure they are available in your current session by executing the command `source ~/.bashrc`. Next, update the system's dynamic linker run-time bindings with the command `sudo ldconfig`.
    
    source ~/.bashrc && sudo ldconfig
:::

### Adding cuDNN to System Paths
At the end of the file, insert the following Conda configuration:

 ```{code-block} bash
   :caption: nano
   
   # Adding cuDNN to System Paths
   echo ‘export LD_LIBRARY_PATH=/usr/lib/wsl/lib:$LD_LIBRARY_PATH’ 
```

:::{note}
After adding these export statements, ensure they are available in your current session by executing the command `source ~/.bashrc`. Next, update the system's dynamic linker run-time bindings with the command `sudo ldconfig`.
    
    source ~/.bashrc && sudo ldconfig
:::

<br>