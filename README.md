# IEEE Transaction (IEEE)

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
  quarto-ieee-pdf: default
```

## Options

Most basic `IEEEtran.cls` command are supported.

## Example

Here is the source code for a minimal sample document: [template.qmd](template.qmd).
