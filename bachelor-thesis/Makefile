# Makefile

FILE=bachelor-thesis
PRINTFILE=$(FILE)-print

PDFLATEX=pdflatex $(1)
BIBTEX=bibtex $(1) || true

COMPILE = \
	$(call PDFLATEX,$(1)); \
	$(call BIBTEX,$(1)); \
	$(call PDFLATEX,$(1)); \
	$(call PDFLATEX,$(1));

# The compress command is taken from http://tex.stackexchange.com/a/19047
COMPRESS = \
	gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dNOPAUSE -dQUIET -dBATCH -sOutputFile=$(1)-temp.pdf $(1).pdf; \
	rm -f $(1).pdf; \
	mv $(1)-temp.pdf $(1).pdf;
	
all: pdf clean
print: pdf-print clean

pdf:
	$(call COMPILE,$(FILE))
	$(call COMPRESS,$(FILE))
	
pdf-print:
	$(call COMPILE,$(PRINTFILE))

clean:
	rm -f $(FILE).{aux,out,dvi,bbl,blg,toc,lof}
	rm -f $(PRINTFILE).{aux,out,dvi,bbl,blg,toc,lof}
	rm -f *.log
