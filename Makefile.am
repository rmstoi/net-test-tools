
ACLOCAL_AMFLAGS = -I m4

AM_CFLAGS = @deps_CFLAGS@
LDADD = @deps_LIBS@

libslip_sources = libslip.c libslip.h libslip_types.h

libslipcat_sources = libslipcat.c libslipcat.h

lib_LTLIBRARIES = libslip.la libslipcat.la
libslip_la_SOURCES = $(libslip_sources)
libslipcat_la_SOURCES = $(libslipcat_sources)

noinst_PROGRAMS = slipcat

check_PROGRAMS = libslip-test queue-test libslipcat-test

libslip_test_SOURCES = libslip-test.c $(libslip_sources)
libslip_test_CFLAGS = $(AM_CFLAGS)

queue_test_SOURCES = queue-test.c queue.h

slipcat_sources = slipcat.c slipcat.h $(libslip_sources)

slipcat_SOURCES = $(slipcat_sources) $(libslipcat_sources)
slipcat_CFLAGS = $(AM_CFLAGS)

libslipcat_test_SOURCES = libslipcat-test.c $(libslipcat_sources)
libslipcat_test_CFLAGS = $(AM_CFLAGS)

TESTS = \
	tests/slip-01.txt \
	tests/slip-02.txt \
	tests/slip-03.txt \
	tests/queue-01.txt \
	tests/queue-02.txt \
	tests/queue-03.txt \
	tests/queue-04.txt \
	tests/queue-05.txt \
	tests/queue-06.txt \
	tests/queue-07.txt \
	tests/queue-08.txt \
	tests/queue-09.txt \
	tests/queue-10.txt \
	tests/queue-11.txt \
	tests/queue-12.txt \
	tests/queue-13.txt \
	tests/libslipcat-01.txt \
	tests/libslipcat-02.txt \
	tests/libslipcat-03.txt

LOG_COMPILER = $(srcdir)/tests/test-wrapper.sh

dist_check_SCRIPTS = \
	$(LOG_COMPILER) \
	$(TESTS)

MAINTAINERCLEANFILES = Makefile.in \
	aclocal.m4 compile configure config.guess config.sub depcomp missing \
	install-sh ltmain.sh test-driver cscope.out *~ .*~ core

maintainer-clean-local:
	-rm -rf m4
