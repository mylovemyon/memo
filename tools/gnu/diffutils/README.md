https://packages.debian.org/bookworm/amd64/diffutils/filelist
## apt
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
