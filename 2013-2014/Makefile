
all:: report

report:: logo
	pandoc parts/*.md summaries/*.md -o report.pdf \
	  --template=template.tex \
	  && make upload

logo::
	if ! [ -e 'logo_gconfs.png' ]; then \
	  wget 'http://gconfs.fr/tmp/logo_gconfs.png'; \
	fi

upload::
	cp report.pdf /srv/
