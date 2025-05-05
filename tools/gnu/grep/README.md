https://manpages.debian.org/bookworm/grep/index.html
## apt
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
