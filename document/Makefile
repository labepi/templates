ARQNAME = document
CONTENT = content

default: all

all:
	latex ${ARQNAME}
	makeindex ${ARQNAME}
	bibtex ${ARQNAME}
	latex ${ARQNAME}
	latex ${ARQNAME}
	latex ${ARQNAME}
	dvips -Ppdf -t a4 -o ${ARQNAME}.ps ${ARQNAME}.dvi
	ps2pdf -dMaxSubsetPct=100 -dCompatibilityLevel=1.2 -dSubsetFonts=true -dEmbedAllFonts=true -sPAPERSIZE=a4 ${ARQNAME}.ps ${ARQNAME}.pdf

clean:
	rm -f ${ARQNAME}.aux\
		${ARQNAME}.ind\
		${ARQNAME}.ilg\
		${ARQNAME}.toc\
		${ARQNAME}.bbl\
		${ARQNAME}.blg\
		${ARQNAME}.brf\
		${ARQNAME}.out\
		${ARQNAME}.idx\
		${ARQNAME}.lo*\
		${ARQNAME}.ps\
		${ARQNAME}.dvi
	cd ${CONTENT}; rm -f *.aux
	cd ${CONTENT}/chapter; for i in `ls`; do rm -f $$i/*.aux; done
	cd ${CONTENT}/appendix; for i in `ls`; do rm -f $$i/*.aux; done
