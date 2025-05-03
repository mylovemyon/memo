## Usage
```
Usage:
 script [options] [file]

Make a typescript of a terminal session.

Options:
 -I, --log-in <file>           log stdin to file
 -O, --log-out <file>          log stdout to file (default)
 -B, --log-io <file>           log stdin and stdout to file

 -T, --log-timing <file>       log timing information to file
 -t[<file>], --timing[=<file>] deprecated alias to -T (default file is stderr)
 -m, --logging-format <name>   force to 'classic' or 'advanced' format

 -a, --append                  append to the log file
 -c, --command <command>       run command rather than interactive shell
 -e, --return                  return exit code of the child process
 -f, --flush                   run flush after each write
     --force                   use output file even when it is a link
 -E, --echo <when>             echo input in session (auto, always or never)
 -o, --output-limit <size>     terminate if output files exceed size
 -q, --quiet                   be quiet

 -h, --help                    display this help
 -V, --version                 display version

For more details see script(1).
```
