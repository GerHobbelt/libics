#
# libics: Image Cytometry Standard file reading and writing.
#
# Copyright (C) 2000-2013, 2016 Cris Luengo and others
# Copyright 2015, 2016:
#   Scientific Volume Imaging Holding B.V.
#   Hilversum, The Netherlands.
#   https://www.svi.nl
#
# Script for automake and autoconfig.
# Written by Peter Verveer, Cris Luengo

ACLOCAL_AMFLAGS = -I m4
AUTOMAKE_OPTIONS = foreign

lib_LTLIBRARIES = libics.la
libics_la_LDFLAGS = -version-info $(ICS_LT_VERSION) -no-undefined

# list all sources and include files that are not installed, but are
# distributed, except for libics_conf.h, which is generated from
# libics_conf.h.in:
libics_la_SOURCES = libics_binary.c \
                    libics_compress.c \
                    libics_data.c \
                    libics_gzip.c \
                    libics_history.c \
                    libics_preview.c \
                    libics_read.c \
                    libics_sensor.c \
                    libics_test.c \
                    libics_top.c \
                    libics_util.c \
                    libics_write.c \
                    libics_intern.h

# list all include files that must be installed and distributed:
include_HEADERS = libics.h \
                  libics_ll.h \
                  libics_sensor.h \
                  libics_test.h

# list all test programs
check_PROGRAMS = test_ics1 \
                 test_ics2a \
                 test_ics2b \
                 test_compress \
                 test_gzip \
                 test_strides \
                 test_strides2 \
                 test_strides3 \
                 test_metadata \
                 test_history

test_ics1_SOURCES = test_ics1.c
test_ics2a_SOURCES = test_ics2a.c
test_ics2b_SOURCES = test_ics2b.c
test_compress_SOURCES = test_compress.c
test_gzip_SOURCES = test_gzip.c
test_strides_SOURCES = test_strides.c
test_strides2_SOURCES = test_strides2.c
test_strides3_SOURCES = test_strides3.c
test_metadata_SOURCES = test_metadata.c
test_history_SOURCES = test_history.c

test_ics1_LDADD = libics.la
test_ics2a_LDADD = libics.la
test_ics2b_LDADD = libics.la
test_compress_LDADD = libics.la
test_gzip_LDADD = libics.la
test_strides_LDADD = libics.la
test_strides2_LDADD = libics.la
test_strides3_LDADD = libics.la
test_metadata_LDADD = libics.la
test_history_LDADD = libics.la

TESTS1 = test_ics1.sh \
        test_ics2a.sh \
        test_ics2b.sh \
        test_strides.sh \
        test_strides2.sh \
        test_strides3.sh \
        test_metadata1.sh \
        test_history.sh

if ICS_ZLIB
TESTS2 = test_gzip.sh test_metadata2.sh
else
TESTS2 =
endif

if ICS_DO_GZEXT
TESTS3 = test_compress.sh
else
TESTS3 =
endif

TESTS = $(TESTS1) $(TESTS2) $(TESTS3)

# list other files that must go into the distribution:
EXTRA_DIST = INSTALL \
             GNU_LICENSE \
             README \
             bootstrap.sh \
             Makefile.bcc \
             Makefile.vc6 \
             Makefile.vc9 \
             docs/index.html \
             docs/Credits.html \
             docs/Documentation.html \
             docs/Enums.html \
             docs/Ics_DataRepresentation.html \
             docs/Ics_Error.html \
             docs/Ics_Header.html \
             docs/Ics_ImelRepresentation.html \
             docs/LowLevelFunctions.html \
             docs/TopLevelFunctions.html \
             docs/Usage.html \
             docs/libics.css \
             docs/iexplorefix.css \
             support/icsviewer/README \
             support/icsviewer/icsviewer.dsp \
             support/icsviewer/icsviewer.dsw \
             support/icsviewer/readics.c \
             support/icsviewer/resource.h \
             support/icsviewer/viewer.c \
             support/icsviewer/viewer.ico \
             support/icsviewer/viewer.rc \
             support/icsviewer/writedib.c \
             support/matlab/README \
             support/matlab/icsread.c \
             support/matlab/icswrite.c \
             support/matlab/makefile \
             test/testim.ics \
             test/testim.ids \
             test/testim_c.ics \
             test/testim_c.ids.Z \
             $(TESTS)

# list other files that should be cleaned
#MOSTLYCLEANFILES = result_v1.ics result_v1.ids  result_v2a.ics result_v2b.ics
mostlyclean-local:
	-rm -f result*

