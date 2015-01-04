FILENAME = paper

default: all

all:
	latex ${FILENAME}
	bibtex ${FILENAME}
	latex ${FILENAME}
	latex ${FILENAME}
	dvips -Ppdf -t a4 -o ${FILENAME}.ps ${FILENAME}.dvi
	ps2pdf -dMaxSubsetPct=100 -dCompatibilityLevel=1.2 \
		-dSubsetFonts=true -dEmbedAllFonts=true \
		-sPAPERSIZE=a4 ${FILENAME}.ps ${FILENAME}.pdf


clean:
	rm -f ${FILENAME}.aux \
		${FILENAME}.ps \
		${FILENAME}.log \
		${FILENAME}.dvi \
		${FILENAME}.bbl \
		${FILENAME}.blg
