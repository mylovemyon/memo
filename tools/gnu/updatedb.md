## Usage
```
Usage: updatedb [OPTION]...
Update a plocate database.

  -f, --add-prunefs FS           omit also FS (space-separated)
  -n, --add-prunenames NAMES     omit also NAMES (space-separated)
  -e, --add-prunepaths PATHS     omit also PATHS (space-separated)
      --add-single-prunepath PATH  omit also PATH
  -U, --database-root PATH       the subtree to store in database (default "/")
  -h, --help                     print this help
  -o, --output FILE              database to update (default
                                 `/var/lib/plocate/plocate.db')
  -b, --block-size SIZE          number of filenames to store
                                 in each block (default 32)
      --prune-bind-mounts FLAG   omit bind mounts (default "no")
      --prunefs FS               filesystems to omit from database
      --prunenames NAMES         directory names to omit from database
      --prunepaths PATHS         paths to omit from database
  -l, --require-visibility FLAG  check visibility before reporting files
                                 (default "yes")
  -v, --verbose                  print paths of files as they are found
  -V, --version                  print version information

The configuration defaults to values read from
`/etc/updatedb.conf'.

Report bugs to steinar+plocate@gunderson.no.
```
