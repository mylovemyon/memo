## Usage
```
Usage:
 slabtop [options]

Options:
 -d, --delay <secs>  delay updates
 -o, --once          only display once, then exit
 -s, --sort <char>   specify sort criteria by character (see below)

 -h, --help     display this help and exit
 -V, --version  output version information and exit

The following are valid sort criteria:
 a: sort by number of active objects
 b: sort by objects per slab
 c: sort by cache size
 l: sort by number of slabs
 v: sort by (non display) number of active slabs
 n: sort by name
 o: sort by number of objects (the default)
 p: sort by (non display) pages per slab
 s: sort by object size
 u: sort by cache utilization

For more details see slabtop(1).
```

## man
```
SLABTOP(1)                                                                                                     User Commands                                                                                                     SLABTOP(1)

NAME
       slabtop - display kernel slab cache information in real time

SYNOPSIS
       slabtop [options]

DESCRIPTION
       slabtop displays detailed kernel slab cache information in real time.  It displays a listing of the top caches sorted by one of the listed sort criteria.  It also displays a statistics header filled with slab layer information.

OPTIONS
       Normal invocation of slabtop does not require any options.  The behavior, however, can be fine-tuned by specifying one or more of the following flags:

       -d, --delay=N
              Refresh the display every n in seconds.  By default, slabtop refreshes the display every three seconds.  To exit the program, hit q.  This cannot be combined with the -o option.

       -s, --sort=S
              Sort by S, where S is one of the sort criteria.

       -o, --once
              Display the output once and then exit.

       -V, --version
              Display version information and exit.

       -h, --help
              Display usage information and exit.

SORT CRITERIA
       The following are valid sort criteria used to sort the individual slab caches and thereby determine what are the "top" slab caches to display.  The default sort criteria is to sort by the number of objects ("o").

       The sort criteria can also be changed while slabtop is running by pressing the associated character.
       character   description                header
       a           number of active objects   ACTIVE
       b           objects per slab           OBJ/SLAB
       c           cache size                 CACHE SIZE
       l           number of slabs            SLABS
       v           number of active slabs     N/A
       n           name                       NAME
       o           number of objects          OBJS
       p           pages per slab             N/A
       s           object size                OBJ SIZE
       u           cache utilization          USE

COMMANDS
       slabtop accepts keyboard commands from the user during use.  The following are supported.  In the case of letters, both cases are accepted.

       Each of the valid sort characters are also accepted, to change the sort routine. See the section SORT CRITERIA.

       <SPACEBAR>
              Refresh the screen.

       Q      Quit the program.

FILES
       /proc/slabinfo
              slab information

SEE ALSO
       free(1), ps(1), top(1), vmstat(8)

NOTES
       Currently, slabtop requires a 2.4 or later kernel (specifically, a version 1.1 or later /proc/slabinfo).  Kernel 2.2 should be supported in the future.

       The slabtop statistic header is tracking how many bytes of slabs are being used and is not a measure of physical memory.  The 'Slab' field in the /proc/meminfo file is tracking information about used slab physical memory.

       The  CACHE  SIZE column is not accurate, it's the upper limit of memory used by specific slab. When system using slub (most common case) is under high memory pressure, there are slab order fallbacks, which means "pages per slab"
       is not constant and may decrease.

AUTHORS
       Written by Chris Rivera and Robert Love.

       slabtop was inspired by Martin Bligh's perl script, vmtop.

REPORTING BUGS
       Please send bug reports to procps@freelists.org

procps-ng                                                                                                        2021-03-11                                                                                                      SLABTOP(1)
```
