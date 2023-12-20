# IEEE Transaction Quarto journal template

![Tested on Quarto-1.3](https://img.shields.io/badge/quarto-1.3-blue?label=quarto)
![Tested on Quarto-1.4](https://img.shields.io/badge/quarto-1.4-blue?label=quarto)

## Overview

`quarto-ieee` provide a [`IEEEtran`][`IEEEtran.cls`] template for [journal format](https://quarto.org/docs/journals/formats.html) with your [Quarto](https://quarto.org/) documents.
`quarto-ieee` use the [`IEEEtran.cls`] document class that is used for most IEEE transaction articles.
It supports both `PDF` and `HTML` output.

[`IEEEtran.cls`]: https://ctan.org/pkg/ieeetran "Document class for IEEE Transactions journals and conferences"

## Creating a New Article

To create a new article using this format:

``` bash
quarto use template dfolio/quarto-ieee
```

This will create a new directory with an example document that uses this format.

## Using with an Existing Document

To add this format to an existing document:

``` bash
quarto add dfolio/quarto-ieee
```

Then, add the format to your document options:

``` yaml
format:
  ieee-pdf: default
```

## Usage

Most basic [`IEEEtran.cls`] command are supported.
For  these commands, there are some (few) limitations[^HTML-limit] for the `HTML` output.
For `PDF` output, using the LaTeX command is often the solution.
\
Additionally, `quarto-ieee` template also supports the [`mhchem`](https://ctan.org/pkg/mhchem) (for chemical equation) 
and [`physics`](https://ctan.org/pkg/physics) (for flexible macros for typesetting equations) LaTeX packages 
and [Mathjax(v3) extensions](https://docs.mathjax.org/en/latest/input/tex/extensions/index.html).

[^HTML-limit]: If there are some [`IEEEtran.cls`] command that are not supported in `HTML` output, you may raise an issue about it.

For the  `HTML` output, `quarto-ieee` tries to mimic as closely as possible the layout seen on [IEEEXplore<sup>®</sup>].

### Front Matter

Most [Quarto](https://quarto.org)'s [authors and affiliations scheme](https://quarto.org/docs/journals/authors.html) are supported.
When provided, `note` is used as `\thanks{}` in `PDF` output (ignored in `HTML` output).
Additionally, `photo` with `bio` allows generating a `IEEEbiography`, while a sole `bio` generates a `IEEEbiographynophoto` (this is used both in `PDF` and `HTML` outputs).
\
The following front matter entries are also supported:

- `funding` (see <https://quarto.org/docs/authoring/front-matter.html>)
- `citation` (see <https://quarto.org/docs/authoring/create-citeable-articles.html>)

Similarly, you can manage the page header from the front matter:

```yaml
pageheader:
  left: Journal XXX, Month Year
  right: 'First Author et al.: Short title'
```

### Examples

The source code for a minimal sample document is given in [template.qmd](template.qmd).
You have a preview of the rendering of this basic template at [template.pdf](https://github.com/dfolio/quarto-ieee/blob/main/template.pdf) or  [template.html](https://htmlpreview.github.io/?https://github.com/dfolio/quarto-ieee/blob/master/template.html). \
Incomplete articles (i.e. more advanced examples) are available in the `examples` folder.

### Unsuported features and limitations

- If you are using [Quarto](https://quarto.org), it is strongly recommended to use TexLive from the LaTeX distribution instead of the one provided by your Linux distribution.
  Otherwise, you may encounter a missing package problem.
- Several authors with same affiliation. 
  In such case use `note` and `tex-author-no-affiliation: true`.
- For `PDF` output
  - `quarto-ieee` use a hack to handle the `longtable` issue with  2-column LaTeX documents[^longtable].
    In some cases, a page overflow may occur.
- For `HTML` output
  - The default Quarto toc is used, so the display is not the same as on [IEEEXplore<sup>®</sup>].
  - Footnote are put at the end of document, while on [IEEEXplore<sup>®</sup>] there are placed in the accordion.
  - Figures are not placed in the accordion.
  - [IEEEXplore<sup>®</sup>] specifics (e.g. citation metrics, etc.)
  - The `HTML` output is a  [Quarto citeable article](https://quarto.org/docs/authoring/create-citeable-articles.html), so a citation appendix is automatically added to the article end.

[^longtable]: "_[longtable not compatible with 2-column LaTeX documents](https://github.com/jgm/pandoc/issues/1023>)_", see this issue <https://github.com/jgm/pandoc/issues/1023>
  
> [!IMPORTANT]
> The `quarto-ieee` template are intended to **only approximate the final look and page length of the articles/papers** either in `PDF` output or `HTML` output. 
> **They are NOT intended to be the final produced work that is displayed in print or on [IEEEXplore<sup>®</sup>]**.
> They will help to give the authors an approximation of the number of pages and layout that will be in the final version. 

### Contributing

If you want to improve the `quarto-ieee` template or need some specific features do not hesitate to submit Pull Request (PR) (it is considered good practice to open an issue for discussion before working on a pull request for a new feature).

[IEEEXplore<sup>®</sup>]: <https://ieeexplore.ieee.org/>
