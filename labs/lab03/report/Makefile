export PATH := $(PATH)
%.docx: %.md
	pandoc $< --filter /usr/local/bin/pandoc-crossref -o $@
FILES = $(patsubst %.md, %.docx, $(wildcard *.md))
FILES += $(patsubst %.md, %.pdf, $(wildcard *.md))

LATEX_FORMAT =

FILTER = --filter pandoc-crossref

%.docx: %.md
	-pandoc "$<" $(FILTER) -o "$@"
%.pdf: %.md
	-pandoc "$<" $(LATEX_FORMAT) $(FILTER) -o "$@"
all: $(FILES)
	@echo $(FILES)
clean:
	-rm $(FILES) *~


