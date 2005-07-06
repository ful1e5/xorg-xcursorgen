# $XdotOrg: $

AC_PREREQ([2.57])
AC_INIT(xcursorgen, [7.0], [xorg@freedesktop.org], xcursorgen)
AM_INIT_AUTOMAKE([dist-bzip2])
AM_MAINTAINER_MODE

AM_CONFIG_HEADER(config.h)

AC_PROG_CC
AC_PROG_INSTALL

AC_TYPE_SIGNAL

# Checks for pkg-config packages
PKG_CHECK_MODULES(XCURSORGEN, x11 xcursor libpng12)
AC_SUBST(XCURSOR_CFLAGS)
AC_SUBST(XCURSOR_LIBS)

AC_OUTPUT([Makefile])
