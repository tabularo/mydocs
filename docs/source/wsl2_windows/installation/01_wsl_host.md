# WSL2 @ host

````{sidebar} **PowerShell @ host** 
```{code-block} shell
<your command at PowerShell>
```
````

The following `commands` needs to be executetd in PowerShell at `WSL2 host`

<br>

---

## Installation
| Command | Description |
|---------|-------------|
| `wsl --list --online` | List available Linux distributions for WSL |
| `wsl --install -d NAME` | Install a specific Linux distribution (replace NAME with the distribution name, e.g., 'Ubuntu-22.04') |


> During the installation process, you might be prompted to set a new `user name` and `password` for the Linux distribution. 
> After setup, you may also need to `reboot` your system to complete the installation.


## Maintenance and Verification
| Command | Description |
|---------|-------------|
| `wsl --list --verbose` | List all running WSL virtual machines |

<br>

## Uninstallation
Use the name of the distribution (NAME) similar to installation.
| Command | Description |
|---------|-------------|
| `wsl --unregister NAME` | Uninstall a specific Linux distribution (replace NAME with the distribution name, e.g., 'Ubuntu-22.04') |

<br>


