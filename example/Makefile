TEX_OPTIONS = -cnf-line "max_print_line = 10000" -halt-on-error
light:
	pdflatex $(TEX_OPTIONS) example.tex
	bibtex example.aux
	pdflatex $(TEX_OPTIONS) example.tex
	pdflatex $(TEX_OPTIONS) example.tex
dark:
	pdflatex $(TEX_OPTIONS) '\def\colorscheme{dark}\input{example.tex}'
	bibtex example.aux
	pdflatex $(TEX_OPTIONS) '\def\colorscheme{dark}\input{example.tex}'
	pdflatex $(TEX_OPTIONS) '\def\colorscheme{dark}\input{example.tex}'
sepia:
	pdflatex $(TEX_OPTIONS) '\def\colorscheme{sepia}\input{example.tex}'
	bibtex example.aux
	pdflatex $(TEX_OPTIONS) '\def\colorscheme{sepia}\input{example.tex}'
	pdflatex $(TEX_OPTIONS) '\def\colorscheme{sepia}\input{example.tex}'
clean:
	rm -f *.{aux,bbl,blg,log,out,toc}
