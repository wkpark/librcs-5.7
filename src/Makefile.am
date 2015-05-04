#
#
bin_PROGRAMS = ci co ident merge rlog rcs rcsclean rcsdiff rcsmerge

ci_SOURCES = ci.c rcslex.c rcssyn.c rcsgen.c rcsedit.c rcskeys.c rcsmap.c \
        rcsrev.c rcsutil.c rcsfnms.c maketime.c partime.c rcstime.c rcskeep.c \
        rcsfcmp.c version.c
co_SOURCES = co.c rcslex.c rcssyn.c rcsgen.c rcsedit.c rcskeys.c rcsmap.c \
        rcsrev.c rcsutil.c rcsfnms.c maketime.c partime.c rcstime.c rcskeep.c \
        version.c

ident_SOURCES = ident.c rcsmap.c version.c

merge_SOURCES = merge.c merger.c rcsfnms.c rcslex.c \
        rcsmap.c rcsrev.c rcssyn.c rcsutil.c \
        rcskeep.c rcskeys.c maketime.c partime.c rcstime.c version.c

rlog_SOURCES = rlog.c rcslex.c rcsmap.c rcssyn.c rcsrev.c rcsutil.c \
        maketime.c partime.c rcstime.c rcsfnms.c rcskeep.c rcskeys.c \
        version.c

rcs_SOURCES = rcs.c rcslex.c rcssyn.c rcsrev.c rcsutil.c rcsgen.c \
        rcsedit.c rcskeys.c rcsmap.c rcsfnms.c rcskeep.c \
        maketime.c partime.c rcstime.c version.c
rcsclean_SOURCES = rcsclean.c rcsedit.c rcsfcmp.c rcsfnms.c rcsgen.c rcskeys.c \
        rcslex.c rcsmap.c rcsrev.c rcssyn.c rcsutil.c rcskeep.c \
        maketime.c partime.c rcstime.c version.c
rcsdiff_SOURCES = rcsdiff.c rcsutil.c rcsfnms.c rcsmap.c rcsrev.c rcssyn.c \
        rcslex.c maketime.c partime.c rcstime.c rcskeep.c rcskeys.c \
        version.c
rcsmerge_SOURCES = rcsmerge.c merger.c rcsutil.c rcsfnms.c rcsmap.c rcsrev.c \
        rcssyn.c rcslex.c rcskeep.c rcskeys.c \
        maketime.c partime.c rcstime.c version.c

lib_LTLIBRARIES = librcs.la
librcs_la_SOURCES = ci.c co.c ident.c maketime.c merge.c merger.c partime.c rcs.c \
	rcsclean.c rcsdiff.c rcsedit.c rcsfcmp.c rcsfnms.c rcsgen.c \
	rcskeep.c rcskeys.c rcslex.c rcsmap.c rcsmerge.c rcsrev.c rcssyn.c \
	rcstime.c rcsutil.c rlog.c version.c

librcs_la_LDFLAGS = -version-info 0:0:0
librcs_la_CFLAGS = -DPHP -DRCS_lib
#librcs_la_LIBADD = @LIBOBJS@
librcs_la_DEPENDENCIES = $(librcs_la_LIBADD)

MAINTAINERCLEANFILES = $(srcdir)/version.c

$(srcdir)/version.c: $(top_srcdir)/configure.in
	(echo '#include <config.h>' && \
	 echo 'char const RCS_version_string[] = "$(VERSION)";') \
		>$@
