# WSL2 @ Windows

This chapter is about installing and maintaining a **WSL2 guest** like `ubuntu 22.04` on a `Windows machine` which we will call **WSL2 host** in this documentation.

:::{mermaid}
graph TB;
    classDef green fill:#9f6,stroke:#333,stroke-width:2px;
    subgraph "WSL2_host"
        Host[Win11]
        subgraph "WSL2_guest"
            Guest[ubuntu 22.04]
        end
    end
    class Host,Guest green
:::

<br>
<br>

```{toctree}
installation/01_wsl_host
installation/02_wsl_guest
```