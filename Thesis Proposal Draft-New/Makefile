# Makefile for the Mateti's LaTeX Thesis Example Files

THISDIR=AmritaThesisDraft
FILES= thesis.bib thesis.tex AmritaU/abstract.tex			\
	AmritaU/acknowledgements.tex AmritaU/amrita.tex			\
	AmritaU/amrita.tex.bak AmritaU/approvalPage.tex			\
	AmritaU/avvp_logo.png AmritaU/bkabstract			\
	AmritaU/titlePage.tex WSU/abstract.tex WSU/approvalPage.tex	\
	WSU/titlePage.tex LaTeX/acmtrans.bst Chapters/english.tex	\
	Chapters/intro.tex Chapters/latexStyle.tex Chapters/learn.tex	\
	Chapters/pmthesis.tex Chapters/techReport.tex			\
	Chapters/tools.tex Chapters/typeWriting.tex			\
	Tables/metrictab.tex Figures/tiger.eps Figures/trie.tex

%.src: %.c
	indent -kr -i2 --no-tabs  $<
	echo \\singleSpacing \\begin\{verbatim\} > $@
	cat $<  >> $@
	echo \\end\{verbatim\}\\doubleSpacing  >> $@

pdf thesis.pdf: ${FILES} thesis.bbl
	pdflatex thesis
	if ( fgrep 'Rerun to get cross-references right' thesis.log ) ; then \
		pdflatex thesis; \
	fi

all:	thesis.pdf archive
	pdflatex thesis

thesis.bbl: ${FILES}
	pdflatex thesis
	bibtex thesis

tar archive: clean
	(cd ..; tar -cjf thesis`date '+%G%m%d%H%M'`.tbz $(THISDIR))

clean:
	rm -f *~ *.dvi *.aux *.log *.lot *.lof *.toc *.out \
	*.bbl *.blg *.gz *.pdf *.ps \
	Chapters/*~ Figures/*~ Tables/*~ WSU/*~ LaTeX/*~



