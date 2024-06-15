# dbt

## Installation on WSL2


```{code-block} shell
:caption: Terminal

pip install dbt-snowflake==1.7.1

conda install -c conda-forge dbt-snowflake==1.7.1

```

## .bashrc

Create alias to your desktop on WSL2 **host**

Open .bashrc file on WSL2 guest

```{code-block} shell
:caption: Terminal

nano ~/.bashrc

```

Config .bashrc file on WSL2 guest

```{code-block} shell
:caption: Terminal

# dbt
alias winhome='cd /mnt/c/Users/user/Desktop'

```
run `source ~/.bashrc`

Create folder on WSL2 **host**