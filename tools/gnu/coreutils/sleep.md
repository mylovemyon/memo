## Usage
```
Usage: sleep NUMBER[SUFFIX]...
  or:  sleep OPTION
Pause for NUMBER seconds.  SUFFIX may be 's' for seconds (the default),
'm' for minutes, 'h' for hours or 'd' for days.  NUMBER need not be an
integer.  Given two or more arguments, pause for the amount of time
specified by the sum of their values.

      --help        display this help and exit
      --version     output version information and exit

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Full documentation <https://www.gnu.org/software/coreutils/sleep>
or available locally via: info '(coreutils) sleep invocation'
```

## man 1
```
SLEEP(1)                                                                                                       User Commands                                                                                                       SLEEP(1)

NAME
       sleep - delay for a specified amount of time

SYNOPSIS
       sleep NUMBER[SUFFIX]...
       sleep OPTION

DESCRIPTION
       Pause  for NUMBER seconds.  SUFFIX may be 's' for seconds (the default), 'm' for minutes, 'h' for hours or 'd' for days.  NUMBER need not be an integer.  Given two or more arguments, pause for the amount of time specified by the
       sum of their values.

       --help display this help and exit

       --version
              output version information and exit

AUTHOR
       Written by Jim Meyering and Paul Eggert.

REPORTING BUGS
       GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
       Report any translation bugs to <https://translationproject.org/team/>

COPYRIGHT
       Copyright © 2024 Free Software Foundation, Inc.  License GPLv3+: GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
       This is free software: you are free to change and redistribute it.  There is NO WARRANTY, to the extent permitted by law.

SEE ALSO
       sleep(3)

       Full documentation <https://www.gnu.org/software/coreutils/sleep>
       or available locally via: info '(coreutils) sleep invocation'

GNU coreutils 9.5                                                                                               October 2024                                                                                                       SLEEP(1)

```

## man 2
```
sleep(3)                                                                                                  Library Functions Manual                                                                                                 sleep(3)

NAME
       sleep - sleep for a specified number of seconds

LIBRARY
       Standard C library (libc, -lc)

SYNOPSIS
       #include <unistd.h>

       unsigned int sleep(unsigned int seconds);

DESCRIPTION
       sleep() causes the calling thread to sleep either until the number of real-time seconds specified in seconds have elapsed or until a signal arrives which is not ignored.

RETURN VALUE
       Zero if the requested time has elapsed, or the number of seconds left to sleep, if the call was interrupted by a signal handler.

ATTRIBUTES
       For an explanation of the terms used in this section, see attributes(7).
       ┌────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┬───────────────┬─────────────────────────────┐
       │ Interface                                                                                                                                                                          │ Attribute     │ Value                       │
       ├────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┼───────────────┼─────────────────────────────┤
       │ sleep()                                                                                                                                                                            │ Thread safety │ MT-Unsafe sig:SIGCHLD/linux │
       └────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┴───────────────┴─────────────────────────────┘

VERSIONS
       On Linux, sleep() is implemented via nanosleep(2).  See the nanosleep(2) man page for a discussion of the clock used.

       On some systems, sleep() may be implemented using alarm(2) and SIGALRM (POSIX.1 permits this); mixing calls to alarm(2) and sleep() is a bad idea.

STANDARDS
       POSIX.1-2008.

HISTORY
       POSIX.1-2001.

CAVEATS
       Using longjmp(3) from a signal handler or modifying the handling of SIGALRM while sleeping will cause undefined results.

SEE ALSO
       sleep(1), alarm(2), nanosleep(2), signal(2), signal(7)

Linux man-pages 6.9.1                                                                                            2024-05-02                                                                                                        sleep(3)
```
