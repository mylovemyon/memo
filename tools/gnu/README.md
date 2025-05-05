https://www.gnu.org/software/gsrc/package-list.html

# bash
https://manpages.debian.org/bookworm/bash/index.html  
https://packages.debian.org/bookworm/amd64/bash/filelist
### file
bash-builtins / bash / bashbug / clear_console / rbash
### apt
```
Package: bash
Version: 5.2.37-2
Priority: required
Essential: yes
Section: shells
Maintainer: Matthias Klose <doko@debian.org>
Installed-Size: 7,368 kB
Pre-Depends: libc6 (>= 2.38), libtinfo6 (>= 6)
Depends: base-files (>= 2.1.12), debianutils (>= 5.6-0.1)
Recommends: bash-completion
Suggests: bash-doc
Homepage: http://tiswww.case.edu/php/chet/bash/bashtop.html
Tag: admin::TODO, devel::TODO, devel::interpreter, implemented-in::c,
 interface::shell, interface::text-mode, role::program,
 scope::application, suite::gnu, uitoolkit::ncurses
Download-Size: 1,500 kB
APT-Manual-Installed: yes
APT-Sources: http://http.kali.org/kali kali-rolling/main amd64 Packages
Description: GNU Bourne Again SHell
 Bash is an sh-compatible command language interpreter that executes
 commands read from the standard input or from a file.  Bash also
 incorporates useful features from the Korn and C shells (ksh and csh).
 .
 Bash is ultimately intended to be a conformant implementation of the
 IEEE POSIX Shell and Tools specification (IEEE Working Group 1003.2).
 .
 The Programmable Completion Code, by Ian Macdonald, is now found in
 the bash-completion package.
```

# coreutils
https://manpages.debian.org/bookworm/coreutils/index.html  
https://packages.debian.org/bookworm/amd64/coreutils/filelist
### file
arch / b2sum / base32 / base64 / basename / basenc / cat / chcon / chgrp / chmod / chown / chroot / cksum / comm / cp / csplit / cut / date / dd / df / dir / dircolors / dirname / du / echo / env / expand / expr / factor / false / fmt / fold / groups / head / hostid / id / install / join / link / ln / logname / ls / md5sum / md5sum.textutils / mkdir / mkfifo / mknod / mktemp / mv / nice / nl / nohup / nproc / numfmt / od / paste / pathchk / pinky / pr / printenv / printf / ptx / pwd / readlink / realpath / rm / rmdir / runcon / seq / sha1sum / sha224sum / sha256sum / sha384sum / sha512sum / shred / shuf / sleep / sort / split / stat / stdbuf / stty / sum / sync / tac / tail / tee / test / timeout / touch / tr / true / truncate / tsort / tty / uname / unexpand / uniq / unlink / users / vdir / wc / who / whoami / yes
### apt
```
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

# diffutils
https://packages.debian.org/bookworm/amd64/diffutils/filelist
### apt
```
Package: diffutils
Version: 1:3.10-3
Priority: required
Essential: yes
Section: utils
Maintainer: Santiago Vila <sanvila@debian.org>
Installed-Size: 1,810 kB
Pre-Depends: libc6 (>= 2.38)
Suggests: diffutils-doc, wdiff
Replaces: diff
Homepage: https://www.gnu.org/software/diffutils/
Tag: devel::rcs, implemented-in::c, interface::commandline, role::program,
 scope::utility, suite::gnu, use::comparing, use::editing,
 use::synchronizing, works-with-format::diff,
 works-with-format::plaintext, works-with::file,
 works-with::software:source, works-with::text
Download-Size: 385 kB
APT-Manual-Installed: yes
APT-Sources: http://http.kali.org/kali kali-rolling/main amd64 Packages
Description: File comparison utilities
 The diffutils package provides the diff, diff3, sdiff, and cmp programs.
 .
 `diff' shows differences between two files, or each corresponding file
 in two directories.  `cmp' shows the offsets and line numbers where
 two files differ.  `cmp' can also show all the characters that
 differ between the two files, side by side.  `diff3' shows differences
 among three files.  `sdiff' merges two files interactively.
 .
 The set of differences produced by `diff' can be used to distribute
 updates to text files (such as program source code) to other people.
 This method is especially useful when the differences are small compared
 to the complete files.  Given `diff' output, the `patch' program can
 update, or "patch", a copy of the file.
```
