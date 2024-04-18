# Installation @Ubuntu

## Download Installer
   | Description                    | Link |
   |--------------------------------| -----|
   | Anaconda installer             | [Click here](https://www.anaconda.com/download#linux) |
   | Anaconda installer file hashes | [Click here](https://docs.anaconda.com/anaconda/install/hashes/) |

## Make Installer Executable
   | Command | Description | Expected Output |
   |---------|-------------|-----------------|
   | `ls -l` | Check permissions | Outputs `-rw-r--r-- 1 user user ... your_Anaconda_filename.sh` |
   | `chmod +x your_Anaconda_filename.sh` | Modify permission |  |
   | `ls -l` | Verify permission modification | Outputs `-rwxr-xr-x 1 user user ... your_Anaconda_filename.sh` |

## Run Installer
| Command | Description |
|---------|-------------|
| `bash your_Anaconda_filename.sh` | This will run the installer |

<br>

   During the installation process, you'll be prompted with the question:
```
   Do you wish the installer to initialize Anaconda3
   by running conda init? [yes|no]
   [no] >>> yes
```
   Type `yes` and press Enter to continue.

<br>

## Post-Installation Steps

:::{hint}
To maintain a clean setup, clone the base environment right after installation and create a separate environment, `conda create --name <myenv> --clone base`. This practice helps to avoid any modifications or conflicts in the *base* environment. To make it foolproof, adjust your .bashrc configuration as described in the steps below.
:::

   | Command                                    | Description |
   |--------------------------------------------|-------------|
   | `conda --version`                          | Check current Anaconda version |
   | `conda update conda`                       | Update Conda to the latest version |
   | `conda create --name <myenv> --clone base` | Clone the base environment |
   | `conda list`                               | Verify installation by showing a list of installed packages |
   
Remember, you should restart the terminal after installing Anaconda. In some cases, changes might not take effect until the system is restarted.

<br>

## Configuring the .bashrc File
After setting up a working Anaconda environment, it's is also recommended to configure the `.bashrc` file for Conda.

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
   
   # <<< conda initialize <<<
   
   # Conda config
   conda deactivate
   conda activate baseclone
```

By adding these lines to your `.bashrc` file, you ensure that every time a new bash session starts, it will initialize Conda and activate the `<myenv>` environment.

### Step 3: Save and Exit Nano
While in Nano editor, you can save your changes and exit by using the following shortcuts:

 ```{code-block} bash
   :caption: Terminal    
    `Ctrl + O`           # to save the file.
    
    `Ctrl + X`           # to exit the nano editor.
```


After saving the changes and closing the `.bashrc` file, you may need to restart your terminal for the changes to take effect.

<br>
