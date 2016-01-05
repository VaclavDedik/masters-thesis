.PHONY: all thesis-text clean

all: thesis-text

thesis-text:
	pdflatex --shell-escape -interaction=nonstopmode -synctex=1 thesis.tex
	bibtex thesis.aux
	pdflatex --shell-escape -interaction=nonstopmode -synctex=1 thesis.tex > /dev/null
	pdflatex --shell-escape -interaction=nonstopmode -synctex=1 thesis.tex > /dev/null

fast:
	pdflatex --shell-escape --interaction=nonstopmode -synctex=1 thesis.tex

printable: thesis-text
	pdftk A=thesis.pdf B=bureaucracy/description.pdf C=bureaucracy/declaration.pdf cat A1-2 B1 A4 C1 A6-end output thesis-printable.pdf

clean:
	rm -rf *.{log,out,pdf,aux,tfm,600pk,514pk,fls,toc,bbl,blg,fdb_latexmk,synctex.gz,tdo}
