SRC=01_wstep.tex 02_regresja_liniowa.tex 03_regularyzacja.tex 04_klasyfikacja.tex 05_nn.tex
NOTES_SRC=$(shell grep -l '\\note' $(SRC))

PDF=$(SRC:%.tex=%.pdf) $(NOTES_SRC:%.tex=%_notes.pdf) cwiczenia_odp.pdf

all: $(PDF)

$(PDF): sa.cls beamercolorthemePUT.sty beamerthemePUT.sty

%.pdf: %.tex
	pdflatex $^
	pdflatex $^

%_notes.pdf: %.tex
	pdflatex -jobname $(<:%.tex=%_notes) "\\def\\notatki{}\\input{$<}"
	pdflatex -jobname $(<:%.tex=%_notes) "\\def\\notatki{}\\input{$<}"

.PHONY: all clean publish
