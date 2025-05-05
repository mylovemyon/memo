https://manpages.debian.org/bookworm/sysvinit-utils/index.html
## apt
```
Package: sysvinit-utils
Version: 3.14-4
Priority: required
Essential: yes
Section: admin
Source: sysvinit
Maintainer: Debian sysvinit maintainers <debian-init-diversity@chiark.greenend.org.uk>
Installed-Size: 106 kB
Provides: lsb-base (= 11.1.0)
Depends: libc6 (>= 2.38)
Conflicts: lsb-base (<< 11.3~)
Replaces: lsb-base
Homepage: https://github.com/slicer69/sysvinit
Tag: implemented-in::c, interface::commandline, role::program,
 scope::utility, use::analysing, use::checking, use::monitor,
 works-with::software:running
Download-Size: 34.1 kB
APT-Manual-Installed: yes
APT-Sources: http://http.kali.org/kali kali-rolling/main amd64 Packages
Description: System-V-like utilities
 This package contains the important System-V-like utilities.
 .
 Specifically, this package includes:
 init-d-script, fstab-decode, killall5, pidof
 .
 It also contains the library scripts sourced by init-d-script and other
 initscripts that were formerly in lsb-base.
```
