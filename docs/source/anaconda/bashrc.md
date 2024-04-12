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

### Set default conde environment
At the end of the file, insert the following Conda configuration:

 ```{code-block} bash
   :caption: nano
   
    # Set default 'conda environment'
    ## Deactivate the current conda environment (if any)
    conda deactivate
    ## Activate 'baseclone' as the default conda environment for new sessions
    conda activate baseclone
```

