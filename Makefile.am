ACLOCAL_AMFLAGS = -I m4
DISTCHECK_CONFIGURE_FLAGS = --enable-gtk-doc

SUBDIRS = doc

pkgconfigdir = $(libdir)/pkgconfig

lib_LTLIBRARIES = libtinynotify-systemwide.la
pkgconfig_DATA = libtinynotify-systemwide.pc
include_HEADERS = lib/tinynotify-systemwide.h

libtinynotify_systemwide_la_LDFLAGS = -version-info 1:0:1
libtinynotify_systemwide_la_CPPFLAGS = $(LIBTINYNOTIFY_CFLAGS) $(PROCPS_CFLAGS)
libtinynotify_systemwide_la_LIBADD = $(LIBTINYNOTIFY_LIBS) $(PROCPS_LIBS)
libtinynotify_systemwide_la_SOURCES = lib/tinynotify-systemwide.c lib/tinynotify-systemwide.h

EXTRA_DIST = NEWS
NEWS: configure.ac Makefile.am
	git for-each-ref refs/tags --sort '-*committerdate' \
		--format '# %(tag) (%(*committerdate:short))%0a%(contents:body)' \
		> NEWS
