# Admonitions

:::{note}
This page contains only excerpts from my frequently used syntax. For the full documentation, please see [{book}theme](https://sphinx-book-theme.readthedocs.io/en/latest/tutorials/get-started.html).
:::

<br>

***

## Admonition types

### Topics

:::{admonition} custom title
Let's give readers a helpful hint!
:::

:::{tip}
Let's give readers a helpful hint!
:::

:::{attention}
Let's give readers a helpful hint!
:::

:::{caution}
Let's give readers a helpful hint!
:::

:::{danger}
Let's give readers a helpful hint!
:::

:::{error}
Let's give readers a helpful hint!
:::

:::{hint}
Let's give readers a helpful hint!
:::

:::{important}
Let's give readers a helpful hint!
:::

:::{note}
Let's give readers a helpful hint!
:::

:::{seealso}
Let's give readers a helpful hint!
:::

:::{warning}
Let's give readers a helpful hint!
:::


```{code-block}
:caption: Admotion Syntax

    :::{tip}
        your_text
    :::
```

***

### Container

Sphinx also adds a number of additional admonition types, for denoting changes to the documentation, or to the codebase:

:::{versionadded} 1.2.3
Explanation of the new feature.
:::

:::{versionchanged} 1.2.3
Explanation of the change.
:::

:::{deprecated} 1.2.3
Explanation of the deprecation.
:::


```{code-block}
:caption: Admotion Syntax

    :::{versionadded} 1.2.3
    new: versionadded
    changed: versionchanged
    deprecated: deprecated
    :::
```

***



## Other Containers

### Card

Card

:::{card} Card Title
Header
^^^
Card content
+++
Footer
:::


```{code-block}
:caption: Admotion Syntax

    :::{card} Card Title
    Header
    ^^^
    Card content
    +++
    Footer
    :::
```

<br>

### Tab-Set

Tab-Set

::::{tab-set}

:::{tab-item} Label1
Content 1
:::

:::{tab-item} Label2
Content 2
:::

::::


```{code-block}
:caption: Admotion Syntax

    ::::{tab-set}
    
    :::{tab-item} Label1
    Content 1
    :::
    
    :::{tab-item} Label2
    Content 2
    :::
    
    ::::
```
