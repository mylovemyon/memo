## Usage
```
Usage: nice [OPTION] [COMMAND [ARG]...]
Run COMMAND with an adjusted niceness, which affects process scheduling.
With no COMMAND, print the current niceness.  Niceness values range from
-20 (most favorable to the process) to 19 (least favorable to the process).

Mandatory arguments to long options are mandatory for short options too.
  -n, --adjustment=N   add integer N to the niceness (default 10)
      --help        display this help and exit
      --version     output version information and exit

Your shell may have its own version of nice, which usually supersedes
the version described here.  Please refer to your shell's documentation
for details about the options it supports.

Exit status:
  125  if the nice command itself fails
  126  if COMMAND is found but cannot be invoked
  127  if COMMAND cannot be found
  -    the exit status of COMMAND otherwise

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Full documentation <https://www.gnu.org/software/coreutils/nice>
or available locally via: info '(coreutils) nice invocation'
```

## man 1
```
NICE(1)                                                                                                        User Commands                                                                                                        NICE(1)

NAME
       nice - run a program with modified scheduling priority

SYNOPSIS
       nice [OPTION] [COMMAND [ARG]...]

DESCRIPTION
       Run COMMAND with an adjusted niceness, which affects process scheduling.  With no COMMAND, print the current niceness.  Niceness values range from -20 (most favorable to the process) to 19 (least favorable to the process).

       Mandatory arguments to long options are mandatory for short options too.

       -n, --adjustment=N
              add integer N to the niceness (default 10)

       --help display this help and exit

       --version
              output version information and exit

       Your shell may have its own version of nice, which usually supersedes the version described here.  Please refer to your shell's documentation for details about the options it supports.

   Exit status:
       125    if the nice command itself fails

       126    if COMMAND is found but cannot be invoked

       127    if COMMAND cannot be found

       -      the exit status of COMMAND otherwise

AUTHOR
       Written by David MacKenzie.

REPORTING BUGS
       GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
       Report any translation bugs to <https://translationproject.org/team/>

COPYRIGHT
       Copyright © 2024 Free Software Foundation, Inc.  License GPLv3+: GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
       This is free software: you are free to change and redistribute it.  There is NO WARRANTY, to the extent permitted by law.

SEE ALSO
       nice(2), renice(1)

       Full documentation <https://www.gnu.org/software/coreutils/nice>
       or available locally via: info '(coreutils) nice invocation'

GNU coreutils 9.5                                                                                               October 2024                                                                                                        NICE(1)
```

## man 2
```
nice(2)                                                                                                     System Calls Manual                                                                                                     nice(2)

NAME
       nice - change process priority

LIBRARY
       Standard C library (libc, -lc)

SYNOPSIS
       #include <unistd.h>

       int nice(int inc);

   Feature Test Macro Requirements for glibc (see feature_test_macros(7)):

       nice():
           _XOPEN_SOURCE
               || /* Since glibc 2.19: */ _DEFAULT_SOURCE
               || /* glibc <= 2.19: */ _BSD_SOURCE || _SVID_SOURCE

DESCRIPTION
       nice() adds inc to the nice value for the calling thread.  (A higher nice value means a lower priority.)

       The range of the nice value is +19 (low priority) to -20 (high priority).  Attempts to set a nice value outside the range are clamped to the range.

       Traditionally,  only  a  privileged  process  could  lower  the  nice value (i.e., set a higher priority).  However, since Linux 2.6.12, an unprivileged process can decrease the nice value of a target process that has a suitable
       RLIMIT_NICE soft limit; see getrlimit(2) for details.

RETURN VALUE
       On success, the new nice value is returned (but see NOTES below).  On error, -1 is returned, and errno is set to indicate the error.

       A successful call can legitimately return -1.  To detect an error, set errno to 0 before the call, and check whether it is nonzero after nice() returns -1.

ERRORS
       EPERM  The calling process attempted to increase its priority by supplying a negative inc but has insufficient privileges.  Under Linux, the CAP_SYS_NICE capability is required.  (But see the discussion of  the  RLIMIT_NICE  re‐
              source limit in setrlimit(2).)

VERSIONS
   C library/kernel differences
       POSIX.1 specifies that nice() should return the new nice value.  However, the raw Linux system call returns 0 on success.  Likewise, the nice() wrapper function provided in glibc 2.2.3 and earlier returns 0 on success.

       Since glibc 2.2.4, the nice() wrapper function provided by glibc provides conformance to POSIX.1 by calling getpriority(2) to obtain the new nice value, which is then returned to the caller.

STANDARDS
       POSIX.1-2008.

HISTORY
       POSIX.1-2001, SVr4, 4.3BSD.

NOTES
       For further details on the nice value, see sched(7).

       Note: the addition of the "autogroup" feature in Linux 2.6.38 means that the nice value no longer has its traditional effect in many circumstances.  For details, see sched(7).

SEE ALSO
       nice(1), renice(1), fork(2), getpriority(2), getrlimit(2), setpriority(2), capabilities(7), sched(7)

Linux man-pages 6.9.1                                                                                            2024-05-02                                                                                                         nice(2)
```
