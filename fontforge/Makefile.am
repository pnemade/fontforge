# Copyright (C) 2000-2012 by George Williams
# Copyright (C) 2012 by Barry Schwartz
#
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions are met:
#
# Redistributions of source code must retain the above copyright notice, this
# list of conditions and the following disclaimer.
#
# Redistributions in binary form must reproduce the above copyright notice,
# this list of conditions and the following disclaimer in the documentation
# and/or other materials provided with the distribution.
#
# The name of the author may not be used to endorse or promote products
# derived from this software without specific prior written permission.
#
# THIS SOFTWARE IS PROVIDED BY THE AUTHOR ``AS IS'' AND ANY EXPRESS OR IMPLIED
# WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
# MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
# EVENT SHALL THE AUTHOR BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
# SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
# PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;
# OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
# WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR
# OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF
# ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

include $(top_srcdir)/mk/layout.am

#--------------------------------------------------------------------------

lib_LTLIBRARIES = libfontforge.la

#--------------------------------------------------------------------------

noinst_HEADERS = \
	asmfpst.h \
	autohint.h \
	autosave.h \
	autotrace.h \
	autowidth.h \
	autowidth2.h \
	bitmapchar.h \
	bitmapcontrol.h \
	bvedit.h \
	clipnoui.h \
	crctab.h \
	cvexport.h \
	cvimages.h \
	dumpbdf.h \
	dumppfa.h \
	effects.h \
	encoding.h \
	featurefile.h \
	fvcomposite.h \
	fvfonts.h \
	fvimportbdf.h \
	ikarus.h\
	langfreq.h\
	macbinary.h\
	macenc.h\
	mathconstants.h\
	namelist.h\
	othersubrs.h \
	palmfonts.h \
	parsepdf.h \
	parsepfa.h \
	parsettfatt.h \
	parsettfbmf.h \
	parsettf.h \
	parsettfvar.h \
	psread.h \
	pua.h \
	savefont.h \
	scstyles.h \
	sfd.h \
	spiro.h \
	splinefill.h \
	splineorder2.h \
	splineoverlap.h \
	splinerefigure.h \
	splinesaveafm.h \
	splinesave.h \
	splinestroke.h \
	splineutil.h \
	splineutil2.h \
	start.h \
	svg.h \
	tottfaat.h \
	tottf.h \
	tottfgpos.h \
	tottfvar.h \
	ttfspecial.h \
	winfonts.h \
	woff.h \
	zapfnomen.h \
	fontforgeui.h \
	cvundoes.h

pkginclude_HEADERS = autowidth2.h fontforge.h		\
	psfont.h stemdb.h autowidth.h delta.h fontforgevw.h	\
	lookups.h savefont.h ttf.h baseviews.h fvmetrics.h mm.h			\
	scriptfuncs.h ttfinstrs.h edgelist2.h namehash.h scripting.h		\
	uiinterface.h bezctx_ff.h edgelist.h groups.h nonlineartrans.h		\
	sd.h unicoderange.h bitmapcontrol.h encoding.h ofl.h search.h		\
	fffreetype.h PfEd.h sfd1.h ffpython.h								\
	sflayoutP.h print.h splinefont.h           \
	flaglist.h \
	glif_name_hash.h \
	glyphcomp.h \
	mem.h \
	views.h

#--------------------------------------------------------------------------

LIBADD = $(top_builddir)/Unicode/libgunicode.la	\
	$(top_builddir)/gutils/libgutils.la

AM_CFLAGS = $(WARN_CFLAGS)

AM_CPPFLAGS = "-I$(top_builddir)/inc" "-I$(top_srcdir)/inc"		\
	"-I$(top_builddir)/lib" "-I$(top_srcdir)/lib"			\
	"-DSHAREDIR=\"${MY_SHAREDIR}\"" "-DDOCDIR=\"${MY_DOCDIR}\""	\
	$(MY_CFLAGS)

#--------------------------------------------------------------------------

libfontforge_la_SOURCES = activeinui.c asmfpst.c autohint.c autosave.c	\
	autotrace.c autowidth.c autowidth2.c bezctx_ff.c bitmapchar.c	\
	bitmapcontrol.c bvedit.c clipnoui.c crctab.c cvexport.c cvimages.c	\
	cvundoes.c dumpbdf.c dumppfa.c effects.c encoding.c		\
	featurefile.c flaglist.c fontviewbase.c freetype.c		\
	fvcomposite.c fvfonts.c fvimportbdf.c fvmetrics.c ftdelta.c	\
	glyphcomp.c groups.c ikarus.c langfreq.c			\
	lookups.c macbinary.c macenc.c mathconstants.c mm.c namelist.c	\
	nonlineartrans.c noprefs.c nouiutil.c nowakowskittfinstr.c	\
	ofl.c othersubrs.c palmfonts.c parsepdf.c parsepfa.c		\
	parsettfatt.c parsettfbmf.c parsettf.c parsettfvar.c    	\
	print.c psread.c pua.c python.c savefont.c	                \
	scripting.c scstyles.c search.c sfd1.c sfd.c sflayout.c		\
	spiro.c splinechar.c splinefill.c splinefont.c				\
	splineorder2.c splineoverlap.c splinesaveafm.c splinesave.c	\
	splinestroke.c splineutil2.c splineutil.c start.c		\
	stemdb.c svg.c tottfaat.c tottfgpos.c tottf.c tottfvar.c	\
	ttfinstrs.c ttfspecial.c ufo.c unicoderange.c winfonts.c woff.c	\
	zapfnomen.c glif_name_hash.c mem.c

EXTRA_libfontforge_la_SOURCES = splinerefigure.c
libfontforge_la_LIBADD =

if FONTFORGE_CAN_USE_WOFF2
CLEANFILES = libfontforge_cxx.la
noinst_LTLIBRARIES = libfontforge_cxx.la
libfontforge_cxx_la_SOURCES = woff2.cc
libfontforge_la_LIBADD += libfontforge_cxx.la -lstdc++
endif

libfontforge_la_CPPFLAGS = $(AM_CPPFLAGS)
libfontforge_la_LIBADD += splinerefigure.lo $(LIBADD)

libfontforge_la_LDFLAGS = $(MY_CFLAGS) -version-info $(LIBFONTFORGE_VERSION) \
	${MY_LIB_LDFLAGS}

if PYTHON_SCRIPTING
if !MACINTOSH
libfontforge_la_LIBADD += $(PYTHON_LIBS)
else
libfontforge_la_LDFLAGS += -undefined dynamic_lookup
endif MACINTOSH
endif PYTHON_SCRIPTING

libfontforge_la_LIBADD += $(MY_LIBS)

#--------------------------------------------------------------------------

GUILIBADD =
if GRAPHICAL_USER_INTERFACE
GUILIBADD += $(top_builddir)/gdraw/libgdraw.la $(XINPUT_LIBS) $(XKB_LIBS)
endif GRAPHICAL_USER_INTERFACE

LDADD = $(LIBADD) $(GUILIBADD)

#--------------------------------------------------------------------------

# In splinerefigure.c, the slight error introduced occasionally by
# optimization turns out to have disastrous effects. Compile it
# without optimization.
splinerefigure.lo: $(srcdir)/splinerefigure.c $(srcdir)/splinefont.h
	$(AM_V_CC)$(LIBTOOL) $(AM_V_lt) \
		--mode=compile $(CC) $(RAW_COMPILE_PLATFORM_CFLAGS) -g -c -o \
		splinerefigure.lo $(AM_CPPFLAGS) $(srcdir)/splinerefigure.c

#--------------------------------------------------------------------------

EXTRA_DIST = generate_codepoint_selector.py

if MACINTOSH
EXTRA_DIST += MacFontForgeApp.zip
MOSTLYCLEANFILES = MacFontForgeApp.zip
endif MACINTOSH

#--------------------------------------------------------------------------

-include $(top_srcdir)/git.mk
