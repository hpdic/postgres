#-------------------------------------------------------------------------
#
# Makefile--
#    Makefile for src/backend/replication
#
# IDENTIFICATION
#    src/backend/replication/Makefile
#
#-------------------------------------------------------------------------

subdir = src/backend/replication
top_builddir = ../../..
include $(top_builddir)/src/Makefile.global

override CPPFLAGS := -I. -I$(srcdir) $(CPPFLAGS)

OBJS = \
	backup_manifest.o \
	basebackup.o \
	basebackup_copy.o \
	basebackup_progress.o \
	basebackup_sink.o \
	basebackup_throttle.o \
	repl_gram.o \
	slot.o \
	slotfuncs.o \
	syncrep.o \
	syncrep_gram.o \
	walreceiver.o \
	walreceiverfuncs.o \
	walsender.o

SUBDIRS = logical

include $(top_srcdir)/src/backend/common.mk

# repl_scanner is compiled as part of repl_gram
repl_gram.o: repl_scanner.c

# syncrep_scanner is compiled as part of syncrep_gram
syncrep_gram.o: syncrep_scanner.c

# repl_gram.c, repl_scanner.c, syncrep_gram.c and syncrep_scanner.c
# are in the distribution tarball, so they are not cleaned here.
# (Our parent Makefile takes care of them during maintainer-clean.)
