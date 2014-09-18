
all:: report

report:: logo
	pandoc parts/*.md -o report.pdf \
	  --template=template.tex \

logo::
	if ! [ -e 'logo_gconfs.png' ]; then \
	  wget 'http://gconfs.fr/tmp/logo_gconfs.png'; \
	fi
