# Building the reviewed configuration

`configs/2022.05.config` is the byte-for-byte configuration found in all three
reviewed payloads. It has no embedded keys or environment-specific toolchain
paths. The original build used native compilers for each target architecture;
cross compilation requires a matching target sysroot and development libraries.

For a native Linux build, provide GNU make, GCC/binutils, flex, bison,
pkg-config, and development headers/libraries for libcurl, libconfig,
libarchive, zlib and ZeroMQ. Then, from the repository root:

```sh
cp olive/configs/2022.05.config .config
make olddefconfig
make -j2
```

For a cross build, also set `CROSS_COMPILE` and `CONFIG_SYSROOT` as appropriate
for the target development environment; do not reuse host library paths.
Consult the original `doc/source/` documentation and `Makefile` for supported
options.

## Validation on 2026-11-24

An isolated native x86_64 build completed using GCC 10.2.1. Running
`make olddefconfig` preserved the supplied configuration byte-for-byte.
SWUpdate and its client, IPC and progress utilities all passed help-command
smoke checks. The build required no changes to the released C sources.

Generated binaries are not included in this publication. This native check
does not establish byte-identical reproduction of the shipped ARM binaries.
Detailed build-validation results are retained in the publication audit.
