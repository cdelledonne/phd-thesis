# Carlo Delle Donne's PhD Thesis

Dissertation, propositions, and cover image of Carlo Delle Donne's PhD thesis.
The LaTeX template was taken from
https://github.com/Inventitech/phd-thesis-template.

## Dissertation

To generate a PDF of the dissertation, compile the LaTeX document
`dissertation.tex`. Remember to use the class option `print` when generating a
PDF intended to be submitted for printing.

## Propositions

To generate a PDF of the propositions, compile the LaTeX document
`propositions.tex`.

## Cover

Requirements:

- Inkscape (https://inkscape.org/)
- ... (), only needed to generate separate front and back sides of the cover

To generate a PDF of the Inkscape SVG cover, which includes back side, front
side, spine, bookmark, and bleed margin of 2mm, run:

```sh
inkscape --export-type=pdf --export-margin=2 --export-filename=cover.pdf cover.svg
```

To generate a PDF of the front side of the Inkscape SVG cover, run:

```sh
cat cover.svg |
    sed '0,/viewBox.*/s//viewBox="180 0 170 240"/' |
    sed '0,/width.*/s//width="170mm"/' |
    inkscape --pipe --export-type=pdf --export-filename=cover-front.pdf
```

To generate a PDF of the back side of the Inkscape SVG cover, run:

```sh
cat cover.svg |
    sed '0,/viewBox.*/s//viewBox="0 0 170 240"/' |
    sed '0,/width.*/s//width="170mm"/' |
    inkscape --pipe --export-type=pdf --export-filename=cover-back.pdf
```
