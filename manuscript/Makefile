
NAME1= bmc_article
PDFLATEX=	pdflatex
BIBTEX=		bibtex
XELATEX=	xelatex
LATEX=		latex
BIBLATEX=	$(PDFLATEX)
BIBTEX=		bibtex -min-crossref=1000
RM=		rm -f
MV=		mv
CP=		cp -p

all: bmcpdf

bmcpdf: $(NAME1).tex
	rm $(NAME1).pdf && $(PDFLATEX) $<

clean:
	$(RM) ${BUILTPDFFIGURES} $(NAME1).aux $(NAME1).dvi \
	    $(NAME1).log $(NAME1).blg $(NAME1).bbl $(NAME1).out \
	    $(NAME1).toc $(NAME1).lof $(NAME1).lot $(NAME1).brf \
            *.aux

watch:
	@echo Watching for changes...
	@fswatch -0 -e ".*" -i "\\.tex$$" . | xargs -0 -n 1 -I {} sh -c 'make; ./buildFinished.sh'
