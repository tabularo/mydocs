# Special Content blocks

:::{note}
This page contains only excerpts from my frequently used syntax. For the full documentation, please see [{book}theme](https://sphinx-book-theme.readthedocs.io/en/latest/tutorials/get-started.html).
:::

<br>

***

## Quotations and epigraphs

<br>

```{margin} **margin note content**
On wider screens, this content will pop out to the side!
```

### Default markdown quotes

> Here's my quote, it's pretty neat.
> I wonder how many lines I can create with
> a single stream-of-consciousness quote.
> I could try to add a list of ideas to talk about.
> I suppose I could just keep going on forever,
> but I'll stop here.

<br>

```{code-block}
:caption: markdown

    ```{margin} **margin note content**
    your margin content
    ```
    
    Default markdown quotes
    
    > your quotes
    > your quotes
    > your quotes
```

<br>

---

### Epigraph with attribution

```{epigraph}
Here's my quote, it's pretty neat.
I wonder how many lines I can create with
a single stream-of-consciousness quote.
I could try to add a list of ideas to talk about.
I suppose I could just keep going on forever,
but I'll stop here.

-- Jo the Jovyan, *[the jupyter book docs](https://jupyterbook.org)*
```

<br>

```{code-block}
:caption: markdown

    ```{epigraph}
    Here's my quote, it's pretty neat.
    I wonder how many lines I can create with
    a single stream-of-consciousness quote.
    I could try to add a list of ideas to talk about.
    I suppose I could just keep going on forever,
    but I'll stop here.
    
    -- Jo the Jovyan, *[the jupyter book docs](https://jupyterbook.org)*
    ```
```

<br>

---

### Text with footnote on side

Lorem ipsum dolor sit amet, consetetur sadipscing [^sn2] elitr, sed diam nonumy eirmod tempor invidunt ut labore et 
dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet 
clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur 
sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. 
At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem 
ipsum dolor sit amet.

[^sn2]: And here's my sidenote content.

<br>

```{code-block}
:caption: markdown

    Lorem ipsum dolor sit amet, consetetur sadipscing [^sn2] elitr.
    
    [^sn2]: And here's my sidenote content.
```

<br>

---

# CSS classes for custom margin content

<br>

## Margin Note

:::{note}
:class: margin
This note will be in the margin!
:::

This works for most elements on the page, but in general this works best for “parent containers” that are the 
top-most element of a bundle of content. For example, you can also put the whole figure in the margin if you like. 
Here is a figure with a caption below. We’ll add a note below to create some vertical space to see better.


<br>

```{code-block}
:caption: markdown

    :::{note}
    :class: margin
    This note will be in the margin!
    :::
    
    Lorem ipsum dolor sit amet, consetetur sadipscing And here’s my sidenote content. elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. 

```

<br>

---

## Content examples in the margin

Margin content can include all kinds of things, such as code blocks:

````{margin} Code blocks in margins
```python
print("here is some python")
```
`````

Lorem ipsum dolor sit amet, consetetur 
sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. 
At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem 
ipsum dolor sit amet.

<br>

```{code-block}
:caption: markdown

    ````{margin} Code blocks in margins
    ```python
    print("here is some python")
    ```
    `````
    
    Lorem ipsum dolor sit amet, consetetur 
```

<br>

---

## Full-width content

Full-width content extends into the right margin, making it stand out against
the rest of your book's content. To add full-width content to your page, add the
class `full-width` to any of the elements in your documentation. For example, you can
add a `full-width` tag to a note element like this:

```{note}
:class: full-width
This content will be full-width
```

<br>

```{code-block}
:caption: markdown

    ```{note}
    :class: full-width
    This content will be full-width
    ```
```

<br>

---

## Sidebars



````{sidebar} **My sidebar title** 
```{note}
Here is my sidebar content, it is pretty cool!
```
<!--
![](../images/G-Icon_002_230.png) TODO Image not rendered during build
-->
````

Lorem ipsum dolor sit amet, consetetur 
sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. 
At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem 
ipsum dolor sit amet.

<br>

```{code-block}
:caption: markdown

    ````{sidebar} **My sidebar title** 
    ```{note}
    Here is my sidebar content, it is pretty cool!
    ```
    <!--
    ![](../images/G-Icon_002_230.png) TODO Image not rendered during build
    -->
    ````
```

<br>
<br>
<br>
<br>
<br>

***

# Data Elements

## Code blocks

```{code-block} python
:caption: python code highlighting

print("A code block with a caption.")
```

<br>

```{code-block} sql
:caption: SQL code highlighting

SELECT *
FROM AnyTable
```
<br>

<br>

```{code-block}
:caption: markdown

    ```{code-block} sql
    :caption: SQL
    
    {code-block} python
    {code-block}
    ```
```
