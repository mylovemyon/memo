```sh
*Evil-WinRM* PS C:\Users\FSmith\Desktop> .\winPEASx86.exe -h
  [*] WinPEAS is a binary to enumerate possible paths to escalate privileges locally. By default it'll run all the following checks unless otherwise specified, but you could also indicate as arguments the names of the checks to run if you only want to run a few of them.                                                                                                                                                                                                          
        domain               Enumerate domain information
        systeminfo           Search system information
        eventsinfo           Display interesting events information
        userinfo             Search user information
        processinfo          Search processes information
        servicesinfo         Search services information
        applicationsinfo     Search installed applications information
        networkinfo          Search network information
        cloudinfo            Enumerate cloud information
        windowscreds         Search windows credentials
        browserinfo          Search browser information
        filesinfo            Search generic files that can contains credentials
        fileanalysis         [NOT RUN BY DEFAULT] Search specific files that can contains credentials and for regexes inside files. Might take several minutes.
        all                  Run all checks the previous check including fileanalysis.

        quiet                Do not print banner
        notcolor             Don't use ansi colors (all white)
        searchpf             Search credentials via regex also in Program Files folders
        wait                 Wait for user input between checks
        debug                Display debugging information - memory usage, method execution time
        dont-check-hostname  Don't check the hostname externally
        log[=logfile]        Log all output to file defined as logfile, or to "out.txt" if not specified
        max-regex-file-size=1000000        Max file size (in Bytes) to search regex in. Default: 1000000B

        Additional checks (slower):
        -lolbas              Run additional LOLBAS check                                                                                                                                                                                    
        -linpeas=[url]       Run additional linpeas.sh check for default WSL distribution, optionally provide custom linpeas.sh URL
                             (default: https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh)                                                                                                                         
        -network|-ports      Run additional network scanning - find network interfaces, hosts and scan nmap top 1000 TCP ports for each host found
                             -network="auto"                          -    find interfaces/hosts automatically                                                                                                                              
                             -network="10.10.10.10,10.10.10.20"       -    scan only selected ip address(es)
                             -network="10.10.10.10/24"                -    scan host based on ip address/netmask
                             -ports="80,443,8080"                     -    If a list of ports is provided, use this list instead of the nmap top 1000 TCP
```
