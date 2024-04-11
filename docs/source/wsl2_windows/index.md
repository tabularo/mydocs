# WSL2 @ Windows

## Installation
| Command | Description |
|---------|-------------|
| `wsl --list --online` | List available Linux distributions for WSL |
| `wsl --install -d NAME` | Install a specific Linux distribution (replace NAME with the distribution name, e.g., 'Ubuntu-22.04') |


> During the installation process, you might be prompted to set a new `user name` and `password` for the Linux distribution. 
> After setup, you may also need to `reboot` your system to complete the installation.

<br>

## Post-Installation Setup
| Command            | Description |
|--------------------|-------------|
| `sudo apt update`  | Update the APT package index files from their sources |
| `sudo apt upgrade` | Update the APT package index files from their sources |
| `lsb_release -a`   | Show the installed Linux distribution version |

<br>

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