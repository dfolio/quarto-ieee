# IEEE Transaction Quarto journal template

## Overview

`quarto-ieee` provide a `IEEEtran` template for [journal format](https://quarto.org/docs/journals/formats.html) with your [quarto](https://quarto.org/) documents.
`quarto-ieee` use the `IEEEtran.cls` document class that is used for most IEEE transaction articles.
It supports both `PDF` and `HTML` output.

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


## Options

Most basic `IEEEtran.cls` command are supported.
There are some (few) limitations for the `HTML` output.

For the  `HTML` output, `quarto-ieee` tries to mimic as closely as possible the layout seen on IEEEXplore^®^.

## Example

The source code for a minimal sample document is given in [template.qmd](template.qmd).

[IEEEtran.cls]: https://ctan.org/pkg/ieeetran "Document class for IEEE Transactions journals and conferences"


You can view a preview of the rendered basic template at [template.pdf](template.pdf) or  [template.html](template.html).

## Unsuported feature

- Several authors with same affiliation. 
  In such case use `note` and `tex-author-no-affiliation: true`
- For `HTML` output
  - The default Quarto toc is used, so the display is not the same as on IEEEXplore^®^.
  - Footnote are put at the end of document, while on IEEEXplore^®^ there are placed in the accordion.
  - Figures are not placed in the accordion.
  - IEEEXplore^®^ specifics (e.g. citation metrics)
  
