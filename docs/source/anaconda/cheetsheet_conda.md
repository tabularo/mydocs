# MyConda Cheet Sheet

## Managing Environments
| Action                        | Command                                      |
| ------------------------------ | -------------------------------------------- |
| Show environments              | `conda env list`                             |
| Create environment             | `conda create --name <myenv>`                |
| Activate environment           | `conda activate <myenv>`                     |
| Deactivate environment         | `conda deactivate`                           |
| Clone base environment         | `conda create --name <myenv> --clone base`   |
| Delete environment             | `conda env remove --name <myenv>`            |

## Managing Packages
| Action                                      | Command                                           |
| -------------------------------------------- | ------------------------------------------------- |
| List installed packages                     | `conda list`                                      |
| Install package(s)                          | `conda install <package>`                         |
| Install multiple packages                   | `conda install <package1> <package2>`             |
| Install package from specified channel      | `conda install -c conda-forge <package>`          |
| Uninstall package                           | `conda remove --name <myenv> <package>`           |
| Update package                              | `conda update --name <myenv> <package>`           |
| Update all packages in an environment       | `conda update --all --name <myenv>`               |
| Search for a package across all channels    | `conda search <package>`                          |

## Maintenance
| Action                        | Command                                      |
| ------------------------------ | -------------------------------------------- |
| Update conda                   | `conda update conda`                         |
| Clean unused packages and caches| `conda clean --all`                         |

## PIP Commands
| Action                        | Command                                      |
| ------------------------------ | -------------------------------------------- |
| Install package               | `pip install package_name`                   |
| Uninstall package             | `pip uninstall package_name`                 |
| Upgrade pip                   | `pip install --upgrade pip`                  |
| List installed packages       | `pip list`                                   |
| Show package info             | `pip show package_name`                      |
| Check for outdated packages   | `pip list --outdated`                        |
| Upgrade all outdated packages | `pip install --upgrade -r requirements.txt`  |
