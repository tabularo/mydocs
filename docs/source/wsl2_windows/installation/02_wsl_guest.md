# WSL2 @ guest

````{sidebar} **Terminal @ guest** 
```{code-block} shell
<your command at Terminal>
```
````

The following `commands` needs to be executetd in Terminal at `WSL2 guest`

<br>

---

## Post-Installation Setup

:::{tip}
Not only after new installation, it's good practice for system maintenance to frequently check if the system is up to date or what could/should be updated. Remember, staying updated not only gives you the latest features but also ensures you have the most recent security patches.
:::

| Command                    | Description |
|----------------------------|-------------|
| `sudo apt update`          | Run regularly to synchronize package index files, informing the system about available software updates. |
| `sudo apt upgrade`         | Used less frequently than 'update'; it installs the latest versions of installed packages based on the updated index. |
| `sudo apt autoremove`      | Removes unneeded packages that were installed as dependencies but are no longer necessary. |
| `lsb_release -a`           | Displays version information about the installed Linux distribution; used infrequently unless information about system is needed. |
