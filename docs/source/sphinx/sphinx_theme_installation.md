# Sphinx Thema Installation

:::{important} 

This is a setup guide for **sphinx-book-theme**, with several additional packages:
- MyST
- Sphinx Desing
- Mermaid Diagramming
- Sphinx Copybutton

*The additional packages are necessary for this setup.*

:::

<br>

Install ``sphinx-book-theme`` with ``conda``:

```{code-block}
:caption: conda install

    conda install -c conda-forge sphinx-book-theme
```

[![icon](https://anaconda.org/conda-forge/sphinx-book-theme/badges/version.svg)](https://anaconda.org/conda-forge/sphinx-book-theme)
[![icon](https://anaconda.org/conda-forge/sphinx-book-theme/badges/latest_release_date.svg)](https://anaconda.org/conda-forge/sphinx-book-theme)


<br>

Theme configuration at ``conf.py``:

```{code-block}
:caption: theme configuration

        html_theme = "sphinx_book_theme"
        html_logo = "path/to/myimage.png" # (create folder, e.g. theme_custom)
        html_title = "My site title"
```



```{code-block}
    :caption: theme configuration

        # -- adds source repository button on theme
        # -- current NOT Used

        html_theme_options = {
            ...
            "repository_url": "https://github.com/{your-docs-url}",
            "use_repository_button": True,
            ...
        }
```

:::{seealso}
Package configuration details, see [{book}theme](https://sphinx-book-theme.readthedocs.io/en/latest/tutorials/get-started.html).
:::

***

## MyST

*Markedly Structured Text - Parser*


<br>

Install ``myst-parser`` with ``conda``:

:::{tip}
:class: margin
Add margin content
:::

```{code-block}
   :caption: conda install

        conda install -c conda-forge myst-parser
```

[![icon](https://anaconda.org/conda-forge/myst-parser/badges/version.svg)](https://anaconda.org/conda-forge/myst-parser)
[![icon](https://anaconda.org/conda-forge/myst-parser/badges/latest_release_date.svg)](https://anaconda.org/conda-forge/myst-parser)

<br>

Theme configuration at ``conf.py``:

```{code-block}
    :caption: theme configuration

        extensions = [
        ..
        'myst_parser',
        ..
        ]

        myst_enable_extensions = [
            'colon_fence',
            'attrs_block'
        ]
```

'attrs_block' enable parsing of block attributes before certain block syntaxes

:::{note}
Package configuration details, see [{MyST}theme](https://myst-parser.readthedocs.io/en/latest/intro.html).
:::


***

<br>


## Sphinx-Design

<br>

Install ``sphinx-design`` with ``conda``:

:::{tip}
:class: margin
Add margin content
:::

```{code-block}
   :caption: conda install

        conda install -c conda-forge sphinx-design
```

[![icon](https://anaconda.org/conda-forge/sphinx-design/badges/version.svg)](https://anaconda.org/conda-forge/sphinx-design)
[![icon](https://anaconda.org/conda-forge/sphinx-design/badges/latest_release_date.svg)](https://anaconda.org/conda-forge/sphinx-design)


<br>

Theme configuration at ``conf.py``:

```{code-block}
    :caption: theme configuration

        extensions = [
        ..
        'sphinx_design',
        ..
        ]
```

:::{seealso}
Package configuration details, see [{MyST}theme](https://myst-parser.readthedocs.io/en/latest/intro.html>)
:::

<br>

***

<br>

## Mermaid Diagramming


Install ``sphinxcontrib-mermaid`` with ``conda``:

```{code-block}
   :caption: conda install

        conda install -c conda-forge sphinxcontrib-mermaid
```

[![icon](https://anaconda.org/conda-forge/sphinxcontrib-mermaid/badges/version.svg)](https://anaconda.org/conda-forge/sphinxcontrib-mermaid)
[![icon](https://anaconda.org/conda-forge/sphinxcontrib-mermaid/badges/latest_release_date.svg)](https://anaconda.org/conda-forge/sphinxcontrib-mermaid)

<br>

Theme configuration at ``conf.py``:

```{code-block}
    :caption: theme configuration

    extensions = [
    ..
    'sphinxcontrib.mermaid',
    ..
    ]
    
<br>
    
```

<br>

***

<br>

## Sphinx Copybutton


Install ``sphinx-copybutton`` with ``conda``:

```{code-block}
   :caption: conda install

        conda install -c conda-forge sphinx-copybutton
```

[![icon](https://anaconda.org/conda-forge/sphinx-copybutton/badges/version.svg)](https://anaconda.org/conda-forge/sphinx-copybutton)
[![icon](https://anaconda.org/conda-forge/sphinx-copybutton/badges/latest_release_date.svg)](https://anaconda.org/conda-forge/sphinx-copybutton)

<br>

Theme configuration at ``conf.py``:

```{code-block}
    :caption: theme configuration

    extensions = [
    ..
    'sphinx_copybutton',
    ..
    ]
```

<br>

***

<br>

## Warnings

*Human error possibilities*

:::{warning}

    Order of extensions is relevant !

    .. code-block::

        extensions = [
        'myst_parser',
        'sphinx_design',
        'sphinxcontrib.mermaid',
        ]
:::

<br>

