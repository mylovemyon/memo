## USAGE
```
rustscan 2.4.1
Fast Port Scanner built in Rust. WARNING Do not use this program against sensitive infrastructure since the specified
server may not be able to handle this many socket connections at once. - Discord  <http://discord.skerritt.blog> -
GitHub <https://github.com/RustScan/RustScan>

USAGE:
    rustscan [OPTIONS] [-- <COMMAND>...]

OPTIONS:
  -a, --addresses <ADDRESSES>                  A comma-delimited list or newline-delimited file of separated CIDRs, IPs,
                                               or hosts to be scanned
  -p, --ports <PORTS>                          A list of comma separated ports to be scanned. Example: 80,443,8080
  -r, --range <RANGE>                          A range of ports with format start-end. Example: 1-1000
  -n, --no-config                              Whether to ignore the configuration file or not
      --no-banner                              Hide the banner
  -c, --config-path <CONFIG_PATH>              Custom path to config file
  -g, --greppable                              Greppable mode. Only output the ports. No Nmap. Useful for grep or
                                               outputting to a file
      --accessible                             Accessible mode. Turns off features which negatively affect screen
                                               readers
      --resolver <RESOLVER>                    A comma-delimited list or file of DNS resolvers
  -b, --batch-size <BATCH_SIZE>                The batch size for port scanning, it increases or slows the speed of
                                               scanning. Depends on the open file limit of your OS.  If you do 65535 it
                                               will do every port at the same time. Although, your OS may not support
                                               this [default: 4500]
  -t, --timeout <TIMEOUT>                      The timeout in milliseconds before a port is assumed to be closed
                                               [default: 1500]
      --tries <TRIES>                          The number of tries before a port is assumed to be closed. If set to 0,
                                               rustscan will correct it to 1 [default: 1]
  -u, --ulimit <ULIMIT>                        Automatically ups the ULIMIT with the value you provided
      --scan-order <SCAN_ORDER>                The order of scanning to be performed. The "serial" option will scan
                                               ports in ascending order while the "random" option will scan ports
                                               randomly [default: serial] [possible values: serial, random]
      --scripts <SCRIPTS>                      Level of scripting required for the run [default: default] [possible
                                               values: none, default, custom]
      --top                                    Use the top 1000 ports
  -e, --exclude-ports <EXCLUDE_PORTS>          A list of comma separated ports to be excluded from scanning. Example:
                                               80,443,8080
  -x, --exclude-addresses <EXCLUDE_ADDRESSES>  A list of comma separated CIDRs, IPs, or hosts to be excluded from
                                               scanning
      --udp                                    UDP scanning mode, finds UDP ports that send back responses
  -h, --help                                   Print help
  -V, --version                                Print version
```
