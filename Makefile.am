AUTOMAKE_OPTIONS = foreign
ACLOCAL_AMFLAGS = -I m4

AM_CFLAGS = $(GLOBAL_CFLAGS) $(libplist_CFLAGS) $(openssl_CFLAGS) $(libpcreposix_CFLAGS)
AM_CXXFLAGS = $(GLOBAL_CXXFLAGS) $(AM_CFLAGS)
AM_LDFLAGS = $(GLOBAL_LDFLAGS) $(libplist_LIBS) $(openssl_LIBS) $(libpcreposix_LIBS)

bin_PROGRAMS = ldid

ldid_CFLAGS = $(AM_CFLAGS)
ldid_CXXFLAGS = $(AM_CXXFLAGS)
ldid_LDFLAGS = $(AM_LDFLAGS)
ldid_SOURCES = 	ldid.cpp
