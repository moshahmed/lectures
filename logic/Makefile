# MIKTEX=/c/miktex/miktex/bin/x64/
# PATH:=$(MIKTEX):$(PATH)
TEXLIVE=/c/texlive/2019/bin/win32
PATH:=$(TEXLIVE):$(PATH)

help:: ; make -qps | grep -Pi "^\w+:"

thesis::
	for i in *.mf ;do \
	   mf $$i ;\
	done
	for i in *.*gf ;do\
	  gftopk $$i $${i%gf}pk ;\
	  gftodvi $$i ;\
	done
	latex $@.tex
	dvips $@.dvi
	ps2pdf $@.ps
	sumatra-pdf $@.pdf

clean::
	# rm -fv *.toc *.lot *.aux *.tfm
	rm -fv *.log *.lot *.lof *.*pk *.*gf *.dvi *.ps *.pdf
