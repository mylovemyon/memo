https://manpages.debian.org/bookworm/coreutils/index.html
## apt
```
└─$ apt show coreutils       
Package: coreutils
Version: 9.5-1+b1
Priority: required
Essential: yes
Section: utils
Source: coreutils (9.5-1)
Maintainer: Michael Stone <mstone@debian.org>
Installed-Size: 18.4 MB
Pre-Depends: libacl1 (>= 2.2.23), libattr1 (>= 1:2.4.48), libc6 (>= 2.38), libgmp10 (>= 2:6.3.0+dfsg), libselinux1 (>= 3.1~), libssl3t64 (>= 3.0.0)
Breaks: usrmerge (<< 39)
Homepage: http://gnu.org/software/coreutils
Tag: admin::configuring, implemented-in::c, interface::commandline,
 role::program, scope::utility, suite::gnu, works-with::file
Download-Size: 2,922 kB
APT-Manual-Installed: yes
APT-Sources: http://http.kali.org/kali kali-rolling/main amd64 Packages
Description: GNU core utilities
 This package contains the basic file, shell and text manipulation
 utilities which are expected to exist on every operating system.
 .
 Specifically, this package includes:
 arch base64 basename cat chcon chgrp chmod chown chroot cksum comm cp
 csplit cut date dd df dir dircolors dirname du echo env expand expr
 factor false flock fmt fold groups head hostid id install join link ln
 logname ls md5sum mkdir mkfifo mknod mktemp mv nice nl nohup nproc numfmt
 od paste pathchk pinky pr printenv printf ptx pwd readlink realpath rm
 rmdir runcon sha*sum seq shred sleep sort split stat stty sum sync tac
 tail tee test timeout touch tr true truncate tsort tty uname unexpand
 uniq unlink users vdir wc who whoami yes
```
