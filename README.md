# Perl4 resurrected

Perl4 with minimal changes to make it work on modern systems

## Quick start
```
./configure && make && make test
("make install" has not been tested)
```

## About

* Based on the official perl5 git repo from https://github.com/Perl/perl5.
* All tags and branches after perl4 have been deleted.
* patch#36 was released in a corrupt state, leading to many rejects. This has been fixed, using https://www.cpan.org/src/unsupported/4.036/perl-4.036.tar.gz as a reference

## Security

This is historical software. It has many bugs that were fixed in later releases, and should thus not be used outside a disconnected sandbox.

## Changes

Changes to the original source have been kept as minimal as possible.
* build: automatically get include and lib dirs on modern systems
* build: added C flags to set the language standard to ISO C90
* build: set correct sizes for uid and gid
* build: use shared libraries by default
* build: workaround for missing namlen in dirent.h
* build: add "distclean" target to Makefile
* build: makedepend: fix typo, filter out noise made by modern cpp
* build: add "configure" wrapper script for a more standard way to build
* code: renamed "AF\_LOCAL" macro to "AF\_LOCALVAR", to prevent clash with the macro from socket.h
* code: replaced deprecated "setpgrp" with "setpgid"
* code: x2p: fix multiple definitions of "nameary" and "ops" variables
* code: x2p: import "string.h" where needed

Code changes are probably not backwards compatible with historical systems.

Patches are welcome.
