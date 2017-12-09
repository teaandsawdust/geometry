# abspath to work around the screwball stuff that happens on Mac with inkscape.
#
# http://wiki.inkscape.org/wiki/index.php/Mac_OS_X#Inkscape_command_line
#
# TL;DR: inkscape changes directory to somewhere other than where make is
# invoked from.
SVGS := $(abspath $(shell find . -type f -name "*.svg"))
PDFS := $(SVGS:.svg=.pdf)

.PHONY: all
all: $(PDFS)

foo:
	echo $(SVGS)
	echo $(PDFS)

%.pdf: %.svg
	inkscape $< --export-pdf=$@

.PHONY: clean
clean:
	-rm *.pdf
