# Generated helper Makefile for building idevicerestore without autotools.
# Usage:
#   make -C build
#   make -C build install

include config.mk

PKGS = libirecovery-1.0 libimobiledevice-1.0 libusbmuxd-2.0 libplist-2.0 libimobiledevice-glue-1.0 libtatsu-1.0 libzip libcurl zlib

CFLAGS ?= -O2 -g
CFLAGS += -DHAVE_CONFIG_H -I. -I$(SRC_DIR) $(shell pkg-config --cflags $(PKGS))
LDFLAGS += $(shell pkg-config --libs $(PKGS))

SOURCES = \
	$(SRC_DIR)/idevicerestore.c \
	$(SRC_DIR)/log.c \
	$(SRC_DIR)/common.c \
	$(SRC_DIR)/fls.c \
	$(SRC_DIR)/mbn.c \
	$(SRC_DIR)/img3.c \
	$(SRC_DIR)/img4.c \
	$(SRC_DIR)/ftab.c \
	$(SRC_DIR)/ipsw.c \
	$(SRC_DIR)/normal.c \
	$(SRC_DIR)/dfu.c \
	$(SRC_DIR)/recovery.c \
	$(SRC_DIR)/restore.c \
	$(SRC_DIR)/asr.c \
	$(SRC_DIR)/fdr.c \
	$(SRC_DIR)/ace3.c \
	$(SRC_DIR)/download.c \
	$(SRC_DIR)/locking.c

TARGET = idevicerestore

all: config.h $(TARGET)

$(TARGET): $(SOURCES)
	$(CC) $(CFLAGS) -o $@ $(SOURCES) $(LDFLAGS)

config.h:
	@printf '%s\n' \
	'#ifndef CONFIG_H' \
	'#define CONFIG_H' \
	'#define PACKAGE "idevicerestore"' \
	'#define PACKAGE_NAME "idevicerestore"' \
	'#define PACKAGE_TARNAME "idevicerestore"' \
	'#define PACKAGE_VERSION "local"' \
	'#define PACKAGE_STRING "idevicerestore local"' \
	'#define PACKAGE_BUGREPORT "https://github.com/libimobiledevice/idevicerestore/issues"' \
	'#define PACKAGE_URL "https://libimobiledevice.org"' \
	'#endif' > $@

install: all
	install -d $(DESTDIR)$(PREFIX)/bin
	install -m 0755 $(TARGET) $(DESTDIR)$(PREFIX)/bin/$(TARGET)

clean:
	rm -f $(TARGET) config.h

.PHONY: all install clean
