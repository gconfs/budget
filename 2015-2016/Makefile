#! /usr/bin/env make

PROJECT		= demande-budget_2015-2016
TEAM		= gconfs
HIERARCHY	= gconfs/
SOURCES		= src/header.md src/content.md
OUTPUT		= ${TEAM}_${PROJECT}.pdf
TEMPLATE	= src/template.tex
FONTSIZE	= 12pt
IMAGES		=

all:: report

report:: logos
	pandoc ${SOURCES} \
	  --variable fontsize=${FONTSIZE} \
	  --template=${TEMPLATE} \
	  -o ${OUTPUT}

logos: logo_epita.png logo_gconfs.png logo_epitech.png

images: ${IMAGES}

logo_%.png:
	@if ! [ -d 'images/' ]; then mkdir 'images'; fi
	@if ! [ -e 'images/$@' ]; then \
	  wget 'http://horgix.fr/epita/logos/$@'; \
	  mv $@ images/; \
	fi
	@if ! [ -e 'images/EPITA.png' ]; then \
	  wget 'http://misc.poussif.eu/EPITA.png'; \
	  mv 'EPITA.png' images/; \
	fi

%.png:
	@if ! [ -d 'images/' ]; then mkdir 'images'; fi
	@if ! [ -e 'images/$@' ]; then \
	  wget 'http://horgix.fr/epita/${PROJECT}/images/$@'; \
	  mv $@ images/; \
	fi

upload::
	scp ${OUTPUT} horgix@horgix.fr:/www/http/${HIERARCHY}
