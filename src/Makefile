# Makefile for thesis

TARGET  = thesis

# List of source files
SOURCES = thesis.tex \
      jUtils.sty \
      alg_set_shard.tex

DVILOG = dvi.log
PDFLOG = pdf.log

.PHONY: default bib view dvi pdf ps index twoside all clean realclean

default: thesis

all:     thesis twoside

thesis:  thesis.pdf

pdf:     thesis.pdf

thesis.pdf: ${SOURCES}
	@echo " "
	@echo "--------------------MAKING  PDF--------------------"
	@echo " "
	pdflatex thesis
	#bibtex thesis   > ${PDFLOG}
	#makeindex thesis >> ${PDFLOG}
	#pdflatex thesis >> ${PDFLOG}
	pdflatex thesis

twoside: thesis.ps
	@echo "---psnup run---"
	psnup -pa4 -2 thesis.ps thesis-twoside.ps

clean:
	@echo "Removing auxiliary files:"
	rm -f *.aux *.bbl *.blg *.glg *.glo *.gls *.idx *.ilg *.ind *.loa *.lof *.log *.lot *.out *.toc *.brf *.log

realclean: clean
	@echo "Removing backup files:"
	rm -f *~ *.bak
	@echo "Removing document files:"
	@echo "-" *.dvi
	@echo "-" *.ps
	@echo "-" *.pdf
	rm -f *.dvi *.ps *.pdf

