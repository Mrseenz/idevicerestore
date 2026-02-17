# Local configured build directory

This directory contains a generated standalone `Makefile` so you can build the executable directly without running autotools.

## Build

```bash
make -C build
```

## Install

```bash
make -C build install PREFIX=/usr/local
```

The build requires the same pkg-config dependencies as the autotools build:

- libirecovery-1.0
- libimobiledevice-1.0
- libusbmuxd-2.0
- libplist-2.0
- libimobiledevice-glue-1.0
- libtatsu-1.0
- libzip
- libcurl
- zlib
