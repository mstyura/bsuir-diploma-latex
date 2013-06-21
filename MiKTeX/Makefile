SHELL=%WINDIR%/cmd.exe
PDFLATEX = pdflatex
DIPLOMA_REPORT_PDF = diploma_report
PRACTICE_REPORT_PDF = practice_report
TITLE_PDF = diploma_title_only
TASK_PDF = diploma_task_only
BIBTEX = bibtex
RM = rm -f
GREP = grep
DROPBOX_PUBLIC=$(USERPROFILE)/Dropbox/Public

all: $(DIPLOMA_REPORT_PDF).pdf $(PRACTICE_REPORT_PDF).pdf $(TITLE_PDF).pdf $(TASK_PDF).pdf

$(DIPLOMA_REPORT_PDF).pdf: *.tex
	$(PDFLATEX) $(DIPLOMA_REPORT_PDF)
	$(BIBTEX) $(DIPLOMA_REPORT_PDF).aux
	$(PDFLATEX) $(DIPLOMA_REPORT_PDF)
	$(PDFLATEX) $(DIPLOMA_REPORT_PDF)
	cp $(DIPLOMA_REPORT_PDF).pdf ../example_diploma.pdf
	cp $(DIPLOMA_REPORT_PDF).pdf $(DROPBOX_PUBLIC)/$(DIPLOMA_REPORT_PDF).pdf


$(PRACTICE_REPORT_PDF).pdf: *.tex
	$(PDFLATEX) $(PRACTICE_REPORT_PDF)
	$(BIBTEX) $(PRACTICE_REPORT_PDF).aux
	$(PDFLATEX) $(PRACTICE_REPORT_PDF)
	$(PDFLATEX) $(PRACTICE_REPORT_PDF)
	cp $(PRACTICE_REPORT_PDF).pdf ../example_practice.pdf
	cp $(PRACTICE_REPORT_PDF).pdf $(DROPBOX_PUBLIC)/$(PRACTICE_REPORT_PDF).pdf


$(TITLE_PDF).pdf: *.tex
	$(PDFLATEX) $(TITLE_PDF)
	$(BIBTEX) $(TITLE_PDF).aux
	$(PDFLATEX) $(TITLE_PDF)
	$(PDFLATEX) $(TITLE_PDF)


$(TASK_PDF).pdf: *.tex
	$(PDFLATEX) $(TASK_PDF)
	$(BIBTEX) $(TASK_PDF).aux
	$(PDFLATEX) $(TASK_PDF)
	$(PDFLATEX) $(TASK_PDF)


cleanall: clean
	$(RM)  *.pdf

.PHONY: clean
clean:
	$(RM) *.aux *.log *.out *.toc *.gz *.gz(busy) *.blg *.bbl $(DIPLOMA_REPORT_PDF).pdf $(TASK_PDF).pdf $(TITLE_PDF).pdf $(PRACTICE_REPORT_PDF).pdf

