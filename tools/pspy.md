https://github.com/DominicBreuker/pspy
## Usage
```
pspy - version: v1.2.1 - Commit SHA: f9e6a1590a4312b9faa093d8dc84e19567977a6d


     ██▓███    ██████  ██▓███ ▓██   ██▓
    ▓██░  ██▒▒██    ▒ ▓██░  ██▒▒██  ██▒
    ▓██░ ██▓▒░ ▓██▄   ▓██░ ██▓▒ ▒██ ██░
    ▒██▄█▓▒ ▒  ▒   ██▒▒██▄█▓▒ ▒ ░ ▐██▓░
    ▒██▒ ░  ░▒██████▒▒▒██▒ ░  ░ ░ ██▒▓░
    ▒▓▒░ ░  ░▒ ▒▓▒ ▒ ░▒▓▒░ ░  ░  ██▒▒▒ 
    ░▒ ░     ░ ░▒  ░ ░░▒ ░     ▓██ ░▒░ 
    ░░       ░  ░  ░  ░░       ▒ ▒ ░░  
                   ░           ░ ░     
                               ░ ░

Usage:
  pspy [flags]

Flags:
  -c, --color                        color the printed events (default true)
      --debug                        print detailed error messages
  -d, --dirs stringArray             watch these dirs
  -f, --fsevents                     print file system events to stdout
  -h, --help                         help for pspy
  -i, --interval int                 scan every 'interval' milliseconds for new processes (default 100)
      --ppid                         record process ppids
  -p, --procevents                   print new processes to stdout (default true)
  -r, --recursive_dirs stringArray   watch these dirs recursively (default [/usr,/tmp,/etc,/home,/var,/opt])
  -t, --truncate int                 truncate process cmds longer than this (default 2048)
```
