# Basic Installation
<br>

***

## Prerequisites

[The Sphinx ecosystem](http://www.sphinx-doc.org/), if not already installed.

:::{tip} 

recommended location: create `docs` folder at your project directory and install *sphinx* there.

```bash
mkdir docs
```

:::

Start installation with:

```{code-block}
:caption: sphinx install

sphinx-quickstart
```

<br>

At path `docs` run

```{code-block}
:caption: build documentation

    make html
```

This will build the folder, file structure at `/docs/build` folder, e.g. `/docs/build/html/index.html`. Run `index.html` in brower to see if the installation was successful.

<br>

You could remove the build with

```{code-block}
:caption: build documentation

    make clean
```

<br>

:::{tip} 

Keep the commands `make clean` and `make html` in mind, you'll use them frequently.

:::



