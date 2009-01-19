# $XdotOrg: app/xcursorgen/configure.ac,v 1.7 2005/12/15 00:24:05 kem Exp $

AC_PREREQ([2.57])
AC_INIT(xcursorgen, [1.0.2], [https://bugs.freedesktop.org/enter_bug.cgi?product=xorg], xcursorgen)
AM_INIT_AUTOMAKE([dist-bzip2])
AM_MAINTAINER_MODE

# Require xorg-macros: XORG_CWARNFLAGS, XORG_CHANGELOG
m4_ifndef([XORG_MACROS_VERSION], [AC_FATAL([must install xorg-macros 1.2 or later before running autoconf/autogen])])
XORG_MACROS_VERSION(1.2)
AM_CONFIG_HEADER(config.h)

AC_PROG_CC
AC_PROG_INSTALL
XORG_CWARNFLAGS

# Checks for pkg-config packages
PKG_CHECK_MODULES(XCURSORGEN, x11 xcursor libpng12)
XCURSORGEN_CFLAGS="$CWARNFLAGS $XCURSORGEN_CFLAGS"
AC_SUBST(XCURSORGEN_CFLAGS)
AC_SUBST(XCURSORGEN_LIBS)

XORG_MANPAGE_SECTIONS
XORG_RELEASE_VERSION
XORG_CHANGELOG

AC_OUTPUT([Makefile])
