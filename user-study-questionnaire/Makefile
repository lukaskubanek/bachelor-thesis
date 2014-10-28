# Makefile

FILE=user-study-questionnaire

PDFLATEX=pdflatex $(1)

COMPILE = \
	$(call PDFLATEX,$(1));
	
all: pdf clean

pdf:
	$(call COMPILE,$(FILE))

clean:
	rm -f $(FILE).{aux,out,dvi,bbl,blg,toc,lof}
	rm -f *.log
