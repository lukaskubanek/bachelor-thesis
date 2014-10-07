# Makefile

FILE=bachelor-thesis
PRINTFILE=$(FILE)-print

PDFLATEX=pdflatex $(1)
BIBTEX=bibtex $(1) || true

define COMPILE
	$(call PDFLATEX, $(1))
	$(call BIBTEX, $(1))
	$(call PDFLATEX, $(1))
	$(call PDFLATEX, $(1))
endef

all: pdf clean
print: pdf-print clean

pdf:
	$(call COMPILE, $(FILE))
	
pdf-print:
	$(call COMPILE, $(PRINTFILE))

clean:
	rm -f $(FILE).{aux,out,dvi,bbl,blg,toc,lof}
	rm -f $(PRINTFILE).{aux,out,dvi,bbl,blg,toc,lof}
	rm -f *.log
