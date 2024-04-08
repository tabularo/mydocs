# Typography

:::{note}
This page contains only excerpts from my frequently used syntax. For the full documentation, please see [{book}theme](https://sphinx-book-theme.readthedocs.io/en/latest/tutorials/get-started.html).
:::

<br>

***

## Paragraph heading

> {.bg-primary}
> ### Paragraph heading


# Paragraphs

{.bg-primary}
Here is a paragraph with a class to control its formatting.



# Inline Text Formating

**strong**, _emphasis_, `literal text`, \*escaped symbols\*

~~strikethrough with *emphasis*~~

A paragraph with a span of [text with attributes]{.bg-warning}


# Quotations

> We know what we are, but know not what we may be.

{attribution="Hamlet act 4, Scene 5"}
> We know what we are, but know not what we may be.

{.glossary}
my term
: Definition of the term


{term}`my term`

# Field lists

:param arg1: A description of arg1
:param arg2: A longer description,
    with multiple lines.

    - And bullet points
:return: A description of the return value

# Comments

\% my comment

# Footnotes

- This is a manually-numbered footnote reference.[^3]
- This is an auto-numbered footnote reference.[^myref]

[^myref]: This is an auto-numbered footnote definition.
[^3]: This is a manually-numbered footnote definition.



<div style="width: 1200px">&nbsp;</div>