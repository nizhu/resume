ProbablyOutOfDate Resume
========================
This is resume, trying to familiarise myself for the possibility of Hons in the future.

With help from:  
http://www.ctan.org/tex-archive/macros/latex/contrib/moderncv/  
http://levelbossmike.github.io/blog/2011/09/19/using-social-media-icons-in-a-latex-document/

generate-resume.sh
==================
Terrible way of doing configuration  
TODO: http://tex.stackexchange.com/questions/35854/creating-a-common-settings-file  
OR  
TODO: remove phone number so this won't be required at all  
Is there a point of a resume without a phone number?  

	#!/usr/bin/env sh
	TEXFILE='/tmp/resume.tex'
	FNAME='Nick'
	LNAME='Zhu'
	CITY='Sydney'
	COUNTRY='Australia'
	PHONE=
	EMAIL=
	GITHUB='github.com\/nizhu'

	rm $TEXFILE 2> /dev/null
	cp resume.tex.template $TEXFILE
	sed -i "s/%fname/$FNAME/" $TEXFILE
	sed -i "s/%lname/$LNAME/" $TEXFILE
	sed -i "s/%city/$CITY/" $TEXFILE
	sed -i "s/%country/$COUNTRY/" $TEXFILE
	sed -i "s/%phone/$PHONE/" $TEXFILE
	sed -i "s/%email/$EMAIL/" $TEXFILE
	sed -i "s/%github/$GITHUB/" $TEXFILE
	sed -i "s/%homepage/$HOMEPAGE/" $TEXFILE
	pdflatex $TEXFILE
