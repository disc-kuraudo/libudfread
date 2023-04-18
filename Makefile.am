ACLOCAL_AMFLAGS = -I m4

SET_FEATURES = -D_ISOC99_SOURCE -D_POSIX_C_SOURCE=200809L -D_REENTRANT
SET_INCLUDES = -I$(top_srcdir) -I$(top_srcdir)/src -Isrc

AM_CFLAGS = $(SET_FEATURES) $(SET_INCLUDES)

lib_LTLIBRARIES = libudfread-dk.la

libudfread_dk_la_SOURCES = \
	src/default_blockinput.h \
	src/default_blockinput.c \
	src/ecma167.h \
	src/ecma167.c \
	src/udfread.c \
	src/udfread-version.c

libudfread_dk_la_LDFLAGS = -version-info $(UDFREAD_LTVERSION) -export-symbols-regex "(^udfread_.*)"

pkgincludedir = $(includedir)/udfread
pkginclude_HEADERS = \
	src/udfread.h \
	src/udfread-version.h \
	src/blockinput.h

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = src/libudfread-dk.pc

noinst_PROGRAMS = \
	udfls \
	udfcat

udfls_SOURCES = examples/udfls.c
udfls_LDADD = libudfread-dk.la

udfcat_SOURCES = examples/udfcat.c
udfcat_LDADD = libudfread-dk.la
