## Usage
```
Usage: mktemp [OPTION]... [TEMPLATE]
Create a temporary file or directory, safely, and print its name.
TEMPLATE must contain at least 3 consecutive 'X's in last component.
If TEMPLATE is not specified, use tmp.XXXXXXXXXX, and --tmpdir is implied.
Files are created u+rw, and directories u+rwx, minus umask restrictions.

  -d, --directory     create a directory, not a file
  -u, --dry-run       do not create anything; merely print a name (unsafe)
  -q, --quiet         suppress diagnostics about file/dir-creation failure
      --suffix=SUFF   append SUFF to TEMPLATE; SUFF must not contain a slash.
                        This option is implied if TEMPLATE does not end in X
  -p DIR, --tmpdir[=DIR]  interpret TEMPLATE relative to DIR; if DIR is not
                        specified, use $TMPDIR if set, else /tmp.  With
                        this option, TEMPLATE must not be an absolute name;
                        unlike with -t, TEMPLATE may contain slashes, but
                        mktemp creates only the final component
  -t                  interpret TEMPLATE as a single file name component,
                        relative to a directory: $TMPDIR, if set; else the
                        directory specified via -p; else /tmp [deprecated]
      --help        display this help and exit
      --version     output version information and exit

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Full documentation <https://www.gnu.org/software/coreutils/mktemp>
or available locally via: info '(coreutils) mktemp invocation'
```

## man 1
```
MKTEMP(1)                                                                                                      User Commands                                                                                                      MKTEMP(1)

NAME
       mktemp - create a temporary file or directory

SYNOPSIS
       mktemp [OPTION]... [TEMPLATE]

DESCRIPTION
       Create  a temporary file or directory, safely, and print its name.  TEMPLATE must contain at least 3 consecutive 'X's in last component.  If TEMPLATE is not specified, use tmp.XXXXXXXXXX, and --tmpdir is implied.  Files are cre‐
       ated u+rw, and directories u+rwx, minus umask restrictions.

       -d, --directory
              create a directory, not a file

       -u, --dry-run
              do not create anything; merely print a name (unsafe)

       -q, --quiet
              suppress diagnostics about file/dir-creation failure

       --suffix=SUFF
              append SUFF to TEMPLATE; SUFF must not contain a slash.  This option is implied if TEMPLATE does not end in X

       -p DIR, --tmpdir[=DIR]
              interpret TEMPLATE relative to DIR; if DIR is not specified, use $TMPDIR if set, else /tmp.  With this option, TEMPLATE must not be an absolute name; unlike with -t, TEMPLATE may contain slashes, but mktemp  creates  only
              the final component

       -t     interpret TEMPLATE as a single file name component, relative to a directory: $TMPDIR, if set; else the directory specified via -p; else /tmp [deprecated]

       --help display this help and exit

       --version
              output version information and exit

AUTHOR
       Written by Jim Meyering and Eric Blake.

REPORTING BUGS
       GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
       Report any translation bugs to <https://translationproject.org/team/>

COPYRIGHT
       Copyright © 2024 Free Software Foundation, Inc.  License GPLv3+: GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
       This is free software: you are free to change and redistribute it.  There is NO WARRANTY, to the extent permitted by law.

SEE ALSO
       mkstemp(3), mkdtemp(3), mktemp(3)

       Full documentation <https://www.gnu.org/software/coreutils/mktemp>
       or available locally via: info '(coreutils) mktemp invocation'

GNU coreutils 9.5                                                                                               October 2024                                                                                                      MKTEMP(1)
```

## man 2
```
mktemp(3)                                                                                                 Library Functions Manual                                                                                                mktemp(3)

NAME
       mktemp - make a unique temporary filename

LIBRARY
       Standard C library (libc, -lc)

SYNOPSIS
       #include <stdlib.h>

       char *mktemp(char *template);

   Feature Test Macro Requirements for glibc (see feature_test_macros(7)):

       mktemp():
           Since glibc 2.12:
               (_XOPEN_SOURCE >= 500) && ! (_POSIX_C_SOURCE >= 200112L)
                   || /* glibc >= 2.19: */ _DEFAULT_SOURCE
                   || /* glibc <= 2.19: */ _SVID_SOURCE || _BSD_SOURCE
           Before glibc 2.12:
               _BSD_SOURCE || _SVID_SOURCE || _XOPEN_SOURCE >= 500

DESCRIPTION
       Never use this function; see BUGS.

       The mktemp() function generates a unique temporary filename from template.  The last six characters of template must be XXXXXX and these are replaced with a string that makes the filename unique.  Since it will be modified, tem‐
       plate must not be a string constant, but should be declared as a character array.

RETURN VALUE
       The mktemp() function always returns template.  If a unique name was created, the last six bytes of template will have been modified in such a way that the resulting name is unique (i.e., does not exist already) If a unique name
       could not be created, template is made an empty string, and errno is set to indicate the error.

ERRORS
       EINVAL The last six characters of template were not XXXXXX.

ATTRIBUTES
       For an explanation of the terms used in this section, see attributes(7).
       ┌────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┬───────────────┬─────────┐
       │ Interface                                                                                                                                                                                              │ Attribute     │ Value   │
       ├────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┼───────────────┼─────────┤
       │ mktemp()                                                                                                                                                                                               │ Thread safety │ MT-Safe │
       └────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┴───────────────┴─────────┘

STANDARDS
       None.

HISTORY
       4.3BSD, POSIX.1-2001.  Removed in POSIX.1-2008.

BUGS
       Never  use  mktemp().   Some implementations follow 4.3BSD and replace XXXXXX by the current process ID and a single letter, so that at most 26 different names can be returned.  Since on the one hand the names are easy to guess,
       and on the other hand there is a race between testing whether the name exists and opening the file, every use of mktemp() is a security risk.  The race is avoided by mkstemp(3) and mkdtemp(3).

SEE ALSO
       mktemp(1), mkdtemp(3), mkstemp(3), tempnam(3), tmpfile(3), tmpnam(3)

Linux man-pages 6.9.1                                                                                            2024-05-02                                                                                                       mktemp(3)
```
