
dist_man_MANS = ci.1 co.1 ident.1 merge.1 rcs.1 rcsclean.1 \
	rcsdiff.1 rcsfile.5 rcsmerge.1 rlog.1

## Is this correct?
dist_noinst_MANS = rcsfreeze.1

BUILT_SOURCES = REL $(dist_noinst_MANS)

soelim = $(SOELIM) -I. -I'$(srcdir)'
nolf = sed '/^\.lf /d'

# We do the sanity (test -s) check at generation time since
# it is a maintainer concern not a user (make check) concern.

.5in.5:
	$(PIC) $(PICFLAGS) $< | $(nolf) > $@
	test -s $@

$(dist_man_MANS) $(dist_noinst_MANS): REL $(bits)

REL: $(top_srcdir)/configure
	@{ echo '.ds Rv $(PACKAGE_VERSION)' ;		\
	  date -u +'.ds Dt %Y-%m-%d'			\
		-r $(top_srcdir)/configure ; } > $@t ;	\
	if [ -f $@ ] && cmp -s $@t $@ ;			\
	  then rm -f $@t ;				\
	  else mv $@t $@ ; echo Created $@ ;		\
	fi

MAINTAINERCLEANFILES = $(dist_man_MANS) REL

# Makefile.am ends
