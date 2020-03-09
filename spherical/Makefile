.PHONY: all, img/drawio
SHELL := /bin/bash

all: build/main.pdf

build/main.pdf: main.tex
	latexmk -pdf -output-directory=build

img/drawio: img/drawio/main.pdf
	pdftk $< cat 1-1 output $@/frames.pdf
	pdftk $< cat 2-2 output $@/flow.pdf
	pdftk $< cat 3-3 output $@/choice-1.pdf
	pdftk $< cat 4-4 output $@/choice-2.pdf
	pdftk $< cat 5-5 output $@/choice-3.pdf
	pdftk $< cat 6-6 output $@/interpolation-1.pdf
	pdftk $< cat 7-7 output $@/interpolation-2.pdf
	pdftk $< cat 8-8 output $@/interpolation-3.pdf
	pdftk $< cat 9-9 output $@/preloading-1.pdf
	pdftk $< cat 10-10 output $@/preloading-2.pdf
	pdftk $< cat 11-11 output $@/preloading-3.pdf
	pdftk $< cat 12-12 output $@/preloading-4.pdf
	pdftk $< cat 13-13 output $@/preloading-5.pdf
	pdftk $< cat 14-14 output $@/preloading-6.pdf
	pdftk $< cat 15-15 output $@/preloading-7.pdf
	pdfcrop $@/flow.pdf $@/flow.pdf

check:
	languagetool \
		-l en-US \
		--disablecategories TYPOGRAPHY,PUNCTUATION,CASING \
		<(detex main.tex)

clean:
	latexmk -C -pdf -output-directory=build
