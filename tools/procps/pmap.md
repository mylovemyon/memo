## Usage
```
Usage:
 pmap [options] PID [PID ...]

Options:
 -x, --extended              show details
 -X                          show even more details
            WARNING: format changes according to /proc/PID/smaps
 -XX                         show everything the kernel provides
 -c, --read-rc               read the default rc
 -C, --read-rc-from=<file>   read the rc from file
 -n, --create-rc             create new default rc
 -N, --create-rc-to=<file>   create new rc to file
            NOTE: pid arguments are not allowed with -n, -N
 -d, --device                show the device format
 -q, --quiet                 do not display header and footer
 -p, --show-path             show path in the mapping
 -A, --range=<low>[,<high>]  limit results to the given range

 -h, --help     display this help and exit
 -V, --version  output version information and exit

For more details see pmap(1).
```

## man
```
PMAP(1)                                                                                                        User Commands                                                                                                        PMAP(1)

NAME
       pmap - report memory map of a process

SYNOPSIS
       pmap [options] pid [...]

DESCRIPTION
       The pmap command reports the memory map of a process or processes.

OPTIONS
       -x, --extended
              Show the extended format.

       -d, --device
              Show the device format.

       -q, --quiet
              Do not display some header or footer lines.

       -A, --range low,high
              Limit results to the given range to low and high address range.  Notice that the low and high arguments are single string separated with comma.

       -X     Show even more details than the -x option. WARNING: format changes according to /proc/PID/smaps

       -XX    Show everything the kernel provides

       -p, --show-path
              Show full path to files in the mapping column

       -c, --read-rc
              Read the default configuration

       -C, --read-rc-from file
              Read the configuration from file

       -n, --create-rc
              Create new default configuration

       -N, --create-rc-to file
              Create new configuration to file

       -h, --help
              Display help text and exit.

       -V, --version
              Display version information and exit.

EXIT STATUS
              0      Success.
              1      Failure.
              42     Did not find all processes asked for.

SEE ALSO
       ps(1), pgrep(1)

STANDARDS
       No standards apply, but pmap looks an awful lot like a SunOS command.

REPORTING BUGS
       Please send bug reports to procps@freelists.org

procps-ng                                                                                                        2020-06-04                                                                                                         PMAP(1)
```
