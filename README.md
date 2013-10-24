Dolt
----

Dolt provides a drop-in replacement for libtool that significantly decreases
compile times on the platforms it supports. Rather than the libtool approach
of running a large script for every compile that repeatedly figures out how
to build libraries on the platform, dolt figures out those details at
configure time and writes out a minimal doltcompile script containing only the
commands needed to build a library on the current platform.


Usage
-----

If you use automake, autoconf, and libtool, then using dolt just requires two
steps:

- add DOLT after the call to LT_INIT, AC_PATH_LIBTOOL, or AM_PATH_LIBTOOL in
  your configure.ac or configure.in script
- append dolt.m4 to your project's acinclude.m4
- Add DISTCLEANFILES = @DOLT_CLEANFILES@ to your Makefile.am
For any platform Dolt does not support, it will transparently fall back to
libtool.

Additional features
-------------------

- Experimental yasm support.
