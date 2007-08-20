bin_PROGRAMS = xcursorgen

xcursorgen_SOURCES = xcursorgen.c

AM_CFLAGS = @XCURSORGEN_CFLAGS@

xcursorgen_LDADD = @XCURSORGEN_LIBS@

appmandir = $(APP_MAN_DIR)

appman_PRE = xcursorgen.man
appman_DATA = $(appman_PRE:man=@APP_MAN_SUFFIX@)

EXTRA_DIST = $(appman_PRE) ChangeLog autogen.sh
CLEANFILES = $(appman_DATA)
MAINTAINERCLEANFILES = ChangeLog

.PHONY: ChangeLog

ChangeLog:
	(GIT_DIR=$(top_srcdir)/.git git-log > .changelog.tmp && mv .changelog.tmp ChangeLog; rm -f .changelog.tmp) || (touch ChangeLog; echo 'git directory not found: installing possibly empty changelog.' >&2)

dist-hook: ChangeLog

MAN_SUBSTS = -e 's|__vendorversion__|"$(XORGRELSTRING)" "$(XORGMANNAME)"|' 

SUFFIXES = .$(APP_MAN_SUFFIX) .man

.man.$(APP_MAN_SUFFIX):
	sed $(MAN_SUBSTS) < $< > $@
