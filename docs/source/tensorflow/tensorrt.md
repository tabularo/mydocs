# TensorRT

## Install

### Software Installation Dependency Chart

:::{mermaid}
graph LR
    A(TensorFlow) --> B(setuptools) 
    subgraph TensorFlowRT
        B(setuptools) --> C(nvidia-pyindex) 
        C --> D(nvidia-tensorrt)
    end
    style A fill:#808080,stroke:#333,stroke-width:1px,color:#fff;
:::

### Packages installation

#### 1. setuptools

Update setuptools, to assure `nvidia-pyindex` installation. Run the following command in your terminal:

 ```{code-block} bash
   :caption: Terminal (WSL2 guest)

    python3 -m pip install --upgrade setuptools pip
 ```

#### 2. nvidia-pyindex

Install nvidia-pyindex. Run the following command in your terminal:

 ```{code-block} bash
   :caption: Terminal (WSL2 guest)

    python3 -m pip install nvidia-pyindex
 ```

#### 3. nvidia-tensorrt

Upgrade nvidia-tensorrt. This will also pull CUDA libraries and cuDNN because of dependencies. Run the following command in your terminal:

 ```{code-block} bash
   :caption: Terminal (WSL2 guest)

    python3 -m pip install --upgrade nvidia-tensorrt
 ```

### Verify installation

 ```{code-block} bash
   :caption: Terminal (WSL2 guest)

    python3 -c "import tensorrt; print('TensorRT version:', tensorrt.__version__); assert tensorrt.Builder(tensorrt.Logger()); print('TensorRT Builder was successfully initialized')"
 ```