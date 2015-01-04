# Generic make file for LaTeX: requires GNU make

TEXFILE	= presentation.tex

.PHONY: dvi ps pdf clean

pdf:	$(TEXFILE:.tex=.pdf)
ps:	$(TEXFILE:.tex=.ps)
dvi:	$(TEXFILE:.tex=.dvi)

%.dvi: %.tex
	( \
	latex $<; \
	latex $<; \
	)

%.ps: %.dvi
	dvips -q $< -o $(<:.dvi=.ps)

%.pdf: %.ps
	ps2pdf -dPDFSETTINGS=/prepress -dAutoRotatePages=/All $<

clean:
	@rm -f \
	$(TEXFILE:.tex=.aux) \
	$(TEXFILE:.tex=.nav) \
	$(TEXFILE:.tex=.snm) \
	$(TEXFILE:.tex=.vrb) \
	$(TEXFILE:.tex=.toc) \
	$(TEXFILE:.tex=.bbl) \
	$(TEXFILE:.tex=.blg) \
	$(TEXFILE:.tex=.log) \
	$(TEXFILE:.tex=.out) \
	$(TEXFILE:.tex=.dvi) \
	$(TEXFILE:.tex=.ps)
