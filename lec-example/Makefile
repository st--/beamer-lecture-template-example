LATEXMKOPTIONS=
PDFLATEXHANDOUT='pdflatex %O -interaction=nonstopmode -synctex=1 "\\PassOptionsToClass{handout}{beamer}\\input{%S}"'
PDFLATEXSLIDES='pdflatex %O -interaction=nonstopmode -synctex=1 %S' 

LATEXMKCLEANEXT=-e '$$clean_ext = "synctex.gz nav snm bbl";'

BASEDIR=$(shell basename $(shell pwd))

slides:
	latexmk -jobname=$(BASEDIR)-slides -pdf -pdflatex=$(PDFLATEXSLIDES) $(LATEXMKOPTIONS) content.tex

handout:
	latexmk -jobname=$(BASEDIR)-handout -pdf -pdflatex=$(PDFLATEXHANDOUT) $(LATEXMKOPTIONS) content.tex

clean:
	latexmk $(LATEXMKCLEANEXT) -c *.pdf


PDF_PREVIEWER=evince
CONTINUOUS_OPTION=-pvc -e '\$$\$$pdf_previewer = \"$(PDF_PREVIEWER) %O %S\";'

continuous:
	make LATEXMKOPTIONS="$(CONTINUOUS_OPTION)" $(TARGET)
