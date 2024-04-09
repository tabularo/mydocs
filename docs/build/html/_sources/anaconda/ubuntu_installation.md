# Anaconda@Ubuntu Installation

## download installer

| Description                    | Link |
|--------------------------------| -----|
| Anaconda installer             | [click here](https://www.anaconda.com/download#downloads) |
| Anaconda installer file hashes | [click here](https://docs.anaconda.com/free/anaconda/hashes/index.html) |

<br>

## make installer executable

| Command                              | Description                  | Expected Output                                                                                       |
|--------------------------------------|------------------------------|-------------------------------------------------------------------------------------------------------|
| `ls -l`                              | check permissions            | rw-r--r-- 1 user user 1153404010 Sep 29 17:47 your_Anaconda_filename.sh |
| `chmod +x your_Anaconda_filename.sh` | modify permission            |                                                                                                       |
| `ls -l`                              | check if permissions modified| -rwxr-xr-x 1 user user 1153404010 Sep 29 17:47 your_Anaconda_filename.sh |


## run installer, update & clone base env

| Command                              | Expected Output       |
|--------------------------------------|-----------------------|
| `bash your_Anaconda_filename.sh`     | run installer         |   
| `conda --version`                     | check current version |
| 



