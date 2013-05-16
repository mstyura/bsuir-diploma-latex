SHELL=%WINDIR%/cmd.exe
PDFLATEX = pdflatex
BIBTEX = bibtex
PDFNAME = diploma_report
RM = rm -f
GREP = grep

all: $(PDFNAME).pdf

$(PDFNAME).pdf: *.tex
	$(PDFLATEX) $(PDFNAME)
	$(BIBTEX) $(PDFNAME).aux
	$(PDFLATEX) $(PDFNAME)
	$(PDFLATEX) $(PDFNAME)
	cp $(PDFNAME).pdf ../example.pdf

cleanall: clean
	$(RM) *.bbl *.pdf *.gz *.gz(busy) *.blg

.PHONY: clean
clean:
	$(RM) *.aux *.log *.out *.toc $(PDFNAME).pdf

