https://www.gnu.org/software/gsrc/package-list.html

# bash
- https://packages.debian.org/bookworm/amd64/bash/filelist
- https://manpages.debian.org/bookworm/bash/index.html
- bash-builtins / bash / bashbug / clear_console / rbash
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
- https://packages.debian.org/bookworm/amd64/coreutils/filelist
- https://manpages.debian.org/bookworm/coreutils/index.html
- arch / b2sum / base32 / base64 / basename / basenc / cat / chcon / chgrp / chmod / chown / chroot / cksum / comm / cp / csplit / cut / date / dd / df / dir / dircolors / dirname / du / echo / env / expand / expr / factor / false / fmt / fold / groups / head / hostid / id / install / join / link / ln / logname / ls / md5sum / md5sum.textutils / mkdir / mkfifo / mknod / mktemp / mv / nice / nl / nohup / nproc / numfmt / od / paste / pathchk / pinky / pr / printenv / printf / ptx / pwd / readlink / realpath / rm / rmdir / runcon / seq / sha1sum / sha224sum / sha256sum / sha384sum / sha512sum / shred / shuf / sleep / sort / split / stat / stdbuf / stty / sum / sync / tac / tail / tee / test / timeout / touch / tr / true / truncate / tsort / tty / uname / unexpand / uniq / unlink / users / vdir / wc / who / whoami / yes
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
- https://packages.debian.org/bookworm/amd64/diffutils/filelist
- https://manpages.debian.org/bookworm/diffutils/index.html
- cmp / diff / diff3 / sdiff
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

# findutils
- https://packages.debian.org/bookworm/amd64/findutils/filelist
- https://manpages.debian.org/bookworm/findutils/index.html
- find / xargs
```          
Package: findutils
Version: 4.10.0-3
Priority: required
Essential: yes
Section: utils
Maintainer: Andreas Metzler <ametzler@debian.org>
Installed-Size: 2,212 kB
Pre-Depends: libc6 (>= 2.38), libselinux1 (>= 3.1~)
Breaks: binstats (<< 1.08-8.1), guilt (<< 0.36-0.2), libpython3.4-minimal (<< 3.4.4-2), libpython3.5-minimal (<< 3.5.1-3), lsat (<< 0.9.7.1-2.1), mc (<< 3:4.8.11-1), switchconf (<< 0.0.9-2.1)
Homepage: https://savannah.gnu.org/projects/findutils/
Tag: implemented-in::c, interface::commandline, role::program,
 scope::utility, suite::gnu, use::searching, works-with::file
Download-Size: 700 kB
APT-Manual-Installed: yes
APT-Sources: http://http.kali.org/kali kali-rolling/main amd64 Packages
Description: utilities for finding files--find, xargs
 GNU findutils provides utilities to find files meeting specified
 criteria and perform various actions on the files which are found.
 This package contains 'find' and 'xargs'; however, 'locate' has
 been split off into a separate package.
```

# gawk
- https://packages.debian.org/bookworm/amd64/gawk/filelist
- https://manpages.debian.org/bookworm/gawk/index.html
- gawk / gawkbug  
```
Package: gawk
Version: 1:5.2.1-2+b1
Priority: optional
Section: interpreters
Source: gawk (1:5.2.1-2)
Maintainer: Adrian Bunk <bunk@debian.org>
Installed-Size: 2,981 kB
Provides: awk
Pre-Depends: libc6 (>= 2.34), libgmp10 (>= 2:6.3.0+dfsg), libmpfr6 (>= 3.1.3), libreadline8t64 (>= 6.0), libsigsegv2 (>= 2.9)
Suggests: gawk-doc
Homepage: http://www.gnu.org/software/gawk/
Tag: devel::interpreter, implemented-in::c, interface::commandline,
 role::program, scope::utility, suite::gnu, use::converting,
 use::filtering, use::scanning, works-with::text
Download-Size: 674 kB
APT-Manual-Installed: no
APT-Sources: http://http.kali.org/kali kali-rolling/main amd64 Packages
Description: GNU awk, a pattern scanning and processing language
 `awk', a program that you can use to select particular records in a
 file and perform operations upon them.
 .
 Gawk is the GNU Project's implementation of the AWK programming language.
 It conforms to the definition of the language in the POSIX 1003.2 Command
 Language And Utilities Standard. This version in turn is based on the
 description in The AWK Programming Language, by Aho, Kernighan, and
 Weinberger, with the additional features defined in the System V Release
 4 version of UNIX awk. Gawk also provides more recent Bell Labs awk
 extensions, and some GNU-specific extensions.
```

# grep
- https://packages.debian.org/bookworm/amd64/grep/filelist
- https://manpages.debian.org/bookworm/grep/index.html
- egrep / fgrep / grep / rgrep
```
Package: grep
Version: 3.11-4
Priority: required
Essential: yes
Section: utils
Maintainer: Anibal Monsalve Salazar <anibal@debian.org>
Installed-Size: 1,296 kB
Provides: rgrep
Pre-Depends: libc6 (>= 2.34), libpcre2-8-0 (>= 10.32)
Conflicts: rgrep
Homepage: https://www.gnu.org/software/grep/
Tag: implemented-in::c, interface::commandline, role::program,
 scope::utility, suite::gnu, use::filtering, use::searching,
 works-with::file, works-with::text
Download-Size: 431 kB
APT-Manual-Installed: yes
APT-Sources: http://http.kali.org/kali kali-rolling/main amd64 Packages
Description: GNU grep, egrep and fgrep
 'grep' is a utility to search for text in files; it can be used from the
 command line or in scripts.  Even if you don't want to use it, other packages
 on your system probably will.
 .
 The GNU family of grep utilities may be the "fastest grep in the west".
 GNU grep is based on a fast lazy-state deterministic matcher (about
 twice as fast as stock Unix egrep) hybridized with a Boyer-Moore-Gosper
 search for a fixed string that eliminates impossible text from being
 considered by the full regexp matcher without necessarily having to
 look at every character. The result is typically many times faster
 than Unix grep or egrep. (Regular expressions containing backreferencing
 will run more slowly, however.)
```
# curl
- https://packages.debian.org/bookworm/amd64/curl/filelist
- https://manpages.debian.org/bookworm/curl/index.html
- curl
```
Package: curl
Version: 8.13.0-1
Priority: optional
Section: web
Maintainer: Debian Curl Maintainers <team+curl@tracker.debian.org>
Installed-Size: 509 kB
Depends: libc6 (>= 2.34), libcurl3t64-gnutls (= 8.13.0-1), zlib1g (>= 1:1.1.4)
Homepage: https://curl.se/
Tag: implemented-in::c, interface::commandline, network::client,
 protocol::ftp, protocol::gopher, protocol::http, protocol::imap,
 protocol::ipv6, protocol::kerberos, protocol::ldap, protocol::pop3,
 protocol::sftp, protocol::smtp, protocol::ssh, protocol::ssl,
 protocol::telnet, protocol::tftp, role::program, scope::utility,
 use::downloading, use::synchronizing, use::transmission,
 works-with::file, works-with::mail
Download-Size: 269 kB
APT-Manual-Installed: no
APT-Sources: http://http.kali.org/kali kali-rolling/main amd64 Packages
Description: command line tool for transferring data with URL syntax
 curl is a command line tool for transferring data with URL syntax, supporting
 DICT, FILE, FTP, FTPS, GOPHER, HTTP, HTTPS, IMAP, IMAPS, LDAP, LDAPS, POP3,
 POP3S, RTMP, RTSP, SCP, SFTP, SMTP, SMTPS, TELNET and TFTP.
 .
 curl supports SSL certificates, HTTP POST, HTTP PUT, FTP uploading, HTTP form
 based upload, proxies, cookies, user+password authentication (Basic, Digest,
 NTLM, Negotiate, kerberos...), file transfer resume, proxy tunneling and a
 busload of other useful tricks.
```
