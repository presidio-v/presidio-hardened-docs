# Regenerate the SDLC report PDF from the Markdown source.
#   make         build sdlc-report.pdf
#   make clean   remove the built PDF
#
# Requires pandoc + a pdflatex TeX distribution (TeX Live). House style and
# unicode glyph maps live in house-style.tex; pandoc default template supplies
# the table/list/link machinery. Version and date are read from the front matter.

PANDOC ?= pandoc
SRC    := sdlc-report.md
PDF    := sdlc-report.pdf

VERSION := $(shell sed -n 's/^version:[[:space:]]*//p' $(SRC) | head -1)
DATE    := $(shell sed -n 's/^date:[[:space:]]*//p' $(SRC) | head -1)

$(PDF): $(SRC) house-style.tex
	$(PANDOC) $(SRC) -o $(PDF) \
	  --pdf-engine=pdflatex \
	  -V documentclass=article -V classoption=11pt \
	  -V papersize=a4 -V geometry:margin=2.5cm \
	  -V fontfamily=lmodern \
	  -V date="$(DATE) — Version $(VERSION)" \
	  -H house-style.tex

.PHONY: clean
clean:
	rm -f $(PDF)
