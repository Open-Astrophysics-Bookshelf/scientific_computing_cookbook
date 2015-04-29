EPStoPDF = epstopdf

ALL: SciComputing.pdf

DIRS := UNIX

TEXS := $(foreach dir, $(DIRS), $(wildcard $(dir)/*.tex))
EPSS := $(foreach dir, $(DIRS), $(wildcard $(dir)/*.eps))

#TEXS += git_info.tex

#git_info.tex:


SciComputing.pdf: SciComputing.tex symbols.tex $(TEXS) $(EPSS) #refs.bib
	git rev-parse --short=12 HEAD > git_info.tex
	pdflatex SciComputing  < /dev/null
#	bibtex SciComputing.aux
	pdflatex SciComputing  < /dev/null
	pdflatex SciComputing  < /dev/null
	$(RM) git_info.tex


clean:
	$(RM) *.aux *.log *.dvi *.bbl *.blg *.lof *.toc *.exc *.out
	$(RM) *~

realclean: clean
	$(RM) SciComputing.pdf

.PHONY: clean
