SHELL=%WINDIR%/cmd.exe
PDFLATEX = pdflatex
PDFNAME = diploma_report
RM = rm -f
GREP = grep

all: $(PDFNAME).pdf

$(PDFNAME).pdf: *.tex
	$(PDFLATEX) $(PDFNAME)
	while $(GREP) 'Label(s) may have changed' $(PDFNAME).log > NUL 2>&1 ; do \
		$(PDFLATEX) $(PDFNAME) ; \
	done

cleanall: clean
	$(RM) *.bbl *.pdf *.gz *.gz(busy) *.blg

.PHONY: clean
clean:
	$(RM) *.aux *.log *.out *.toc $(PDFNAME).pdf

