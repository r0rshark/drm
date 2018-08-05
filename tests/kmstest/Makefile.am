AM_CFLAGS = \
	$(WARN_CFLAGS)\
	-I$(top_srcdir)/include/drm \
	-I$(top_srcdir)/libkms/ \
	-I$(top_srcdir)/tests/ \
	-I$(top_srcdir) \
	-I/usr/include/cairo \
	-I/usr/include/glib-2.0 \
	-I/usr/lib/x86_64-linux-gnu/glib-2.0/include \
	-I/usr/include/pixman-1 \
	-I/usr/include/freetype2 \
	-I/usr/include/libpng12 

if HAVE_INSTALL_TESTS
bin_PROGRAMS = \
	kmstest kmstest_advanced
else
noinst_PROGRAMS = \
	kmstest kmstest_advanced
endif

kmstest_SOURCES = \
	main.c

kmstest_advanced_SOURCES = \
	kmstest_advanced.c

kmstest_LDADD = \
	$(top_builddir)/tests/util/libutil.la \
	$(top_builddir)/libkms/libkms.la \
	$(top_builddir)/libdrm.la

kmstest_advanced_LDADD = \
	$(top_builddir)/tests/util/libutil.la \
	$(top_builddir)/libkms/libkms.la \
	$(top_builddir)/libdrm.la \
	-lcairo


run: kmstest
	./kmstest
