#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

# Copyright (C) 2021 by Joe Da Silva

AC_PREREQ(2.61)

m4_define([xinv3d_version], [1.4.0])
AC_INIT([xinv3d],[xinv3d_version],[packages@qa.debian.org],
	[xinv3d],[https://packages.debian.org/sid/xinv3d])
AM_INIT_AUTOMAKE([foreign -Wall])
AC_CANONICAL_BUILD
AC_CANONICAL_HOST
AC_USE_SYSTEM_EXTENSIONS
AC_DEFINE(MOTIF, HAVE_MOTIF)
AC_SUBST([XINV3D_VERSION],[xinv3d_version])
AC_PROG_CC
AC_PROG_RANLIB
AC_PROG_INSTALL

case $host in
   *-freebsd* | *-openbsd*)
	AC_DEFINE([GAME_LINUX_X11],1,[Build for X11])
	;;
   *-apple-darwin*)
	AC_DEFINE([GAME_LINUX_X11],1,[Build for X11])
	;;
   *mingw*)
	AC_DEFINE([GAME_WIN32],1,[Build for WIN_32])
	;;
   *cygwin*)
	AC_DEFINE([GAME_DOS_DJGPP],1,[Build for DOS])
	;;
   *) AC_DEFINE([GAME_LINUX_X11],1,[Build for X11])
esac

# Required development include files (and associated libraries)
AC_MSG_CHECKING([Check for X11 and required developer header files])
AC_CHECK_HEADER([X11/Xlib.h],[],[AC_MSG_FAILURE([ERROR: Missing X11/Xlib.h, Please install Developer version of libx11-devel or lib64x11-devel],[1])])

AC_CONFIG_FILES([Makefile xinv3d.pc desktop/Makefile])
AC_OUTPUT
AC_MSG_NOTICE([

Configuration:

  Source code location	${srcdir}
  Build code location	${builddir}
  Destination prefix	${prefix}
  Host Operating System	${host}
  Compiler		${CC}
  Config CFLAGS		"${CFLAGS}"

])
