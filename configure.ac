AC_PREREQ([2.69])
AC_INIT([ldid], m4_esyscmd([git rev-list --count HEAD | tr -d '\n']), [saurik@saurik.com])

AC_CANONICAL_SYSTEM
AC_CANONICAL_HOST
AM_PROG_LIBTOOL

AM_INIT_AUTOMAKE
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_MACRO_DIRS([m4])

# Checks for programs.
AC_PROG_CXX
AC_PROG_CC

CXXFLAGS+=" -std=c++11"
CFLAGS+=" -std=c11"

# Check for operating system
AC_MSG_CHECKING([whether we need platform-specific build settings])
case $host_os in
  *mingw32*|*cygwin*)
  AC_MSG_RESULT([${host_os}])
  win32=true
  LDFLAGS+=" -lmman"
      ;;
esac


# Checks for libraries.
PKG_CHECK_MODULES(libplist, libplist-2.0 >= 2.3.0)
PKG_CHECK_MODULES(openssl, openssl >= 0.9.8)
PKG_CHECK_MODULES(libpcreposix, libpcreposix >= 8.0, have_pcre=yes, have_pcre=no)


# Checks for header files.
AC_CHECK_HEADERS([regex.h])

AC_CONFIG_FILES([ Makefile ])

AC_OUTPUT

echo "
Configuration for $PACKAGE-$VERSION:
-------------------------------------------

  have pcre ...............: $have_pcre
  install prefix ..........: $prefix"

echo "  compiler ................: ${CC}

  Now type 'make' to build $PACKAGE-$VERSION,
  and then 'make install' for installation.
"
