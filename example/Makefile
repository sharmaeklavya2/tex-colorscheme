light:
	pdflatex example.tex
	bibtex example.aux
	pdflatex example.tex
	pdflatex example.tex
dark:
	pdflatex '\def\colorscheme{dark}\input{example.tex}'
	bibtex example.aux
	pdflatex '\def\colorscheme{dark}\input{example.tex}'
	pdflatex '\def\colorscheme{dark}\input{example.tex}'
sepia:
	pdflatex '\def\colorscheme{sepia}\input{example.tex}'
	bibtex example.aux
	pdflatex '\def\colorscheme{sepia}\input{example.tex}'
	pdflatex '\def\colorscheme{sepia}\input{example.tex}'
clean:
	rm -f *.{aux,bbl,blg,log,out,toc}
