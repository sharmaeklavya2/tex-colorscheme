# TeX Colorscheme

Almost all TeX documents are created with black text on a white background.
This is fine for printing, but for reading on a screen, other color schemes may be preferable,
like bright text on a dark background.
The file `colorscheme.tex`, along with a few tricks and best practices that I invented,
give a way to create documents with different color schemes,
and seamlessly switch between them whenever you want.
(This is useful if you want to support both a dark version for screen reading
and a light version for printing.)

In `colorscheme.tex`, I first check the value of the macro `\colorscheme` to determine the color scheme.
Then I set the colors `textColor`, `bgColor`, `textRed`, `textBlue`, `textGreen` based on the colorscheme.
I then set the background color to `bgColor` and text color to `textColor`.

In your LaTeX document preamble, add the lines `\usepackage{xcolor}` and `\input{colorscheme.tex}`.
Add `\def\colorscheme{dark}` anywhere in your document before `\input{colorscheme.tex}`
to switch to the `dark` color scheme.
Currently supported color schemes are `dark`, `light`, and `sepia`.
If you don't define `\colorscheme`, the `light` color scheme (black text on white background)
will be used by default.

Instead of adding `\def\colorscheme` to your document, you can also specify it over the command-line.
For example, replace this command

    pdflatex example.tex

by

    pdflatex '\def\colorscheme{dark}\input{example.tex}'

to get a dark color scheme.

This repository includes an example LaTeX document that you can build yourself:
switch to the `example` directory and run `make dark` or `make light` or `make sepia`.

## Tips and Best Practices

If you use [`hyperref`](https://ctan.org/pkg/hyperref?lang=en),
you may want to set colors for hyperlinks like this:

    \hypersetup{colorlinks,linkcolor=textRed,citecolor=textRed,urlcolor=textBlue}

If you use colors in your document, you'll want to use different colors depending on the colorscheme.
There are two ways I recommend:

* Use the pre-defined text colors for coloring text: `textRed`, `textBlue`, `textGreen`.
* Mix fully-saturated colors with `bgColor`.

## Freedom to Use

&copy; 2022 Eklavya Sharma

All code is licensed under the [MIT license](https://choosealicense.com/licenses/mit/).
This roughly means that you are free to use, modify, and distribute this code.
