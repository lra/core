# Those tests use stub functions interposition which does not work (yet)
# under OS X. Another way of stubbing functions from libpromises is needed.
if !XNU
AM_CFLAGS = $(ENTERPRISE_CFLAGS) \
	-I$(srcdir)/../../libpromises \
	-I$(srcdir)/../../libutils \
	-I$(srcdir)/../../libcfnet \
	-I../../libpromises


EXTRA_DIST = \
	run_db_load.sh \
	run_lastseen_threaded_load.sh

TESTS = \
	run_db_load.sh \
	run_lastseen_threaded_load.sh


check_PROGRAMS = db_load lastseen_load lastseen_threaded_load


db_load_SOURCES = db_load.c
db_load_LDADD = ../unit/libdb.la


lastseen_load_SOURCES = lastseen_load.c \
	$(srcdir)/../../libpromises/lastseen.c \
	$(srcdir)/../../libutils/statistics.c
lastseen_load_LDADD = ../unit/libdb.la ../../libpromises/libpromises.la
endif

lastseen_threaded_load_LDADD = ../unit/libtest.la \
	../../libpromises/libpromises.la
