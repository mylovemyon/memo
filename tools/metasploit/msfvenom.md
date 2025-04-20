## Usage
```
Usage: /usr/bin/msfvenom [options] <var=val>
Example: /usr/bin/msfvenom -p windows/meterpreter/reverse_tcp LHOST=<IP> -f exe -o payload.exe

Options:
    -l, --list            <type>     List all modules for [type]. Types are: payloads, encoders, nops, platforms, archs, encrypt, formats, all
    -p, --payload         <payload>  Payload to use (--list payloads to list, --list-options for arguments). Specify '-' or STDIN for custom
        --list-options               List --payload <value>'s standard, advanced and evasion options
    -f, --format          <format>   Output format (use --list formats to list)
    -e, --encoder         <encoder>  The encoder to use (use --list encoders to list)
        --service-name    <value>    The service name to use when generating a service binary
        --sec-name        <value>    The new section name to use when generating large Windows binaries. Default: random 4-character alpha string
        --smallest                   Generate the smallest possible payload using all available encoders
        --encrypt         <value>    The type of encryption or encoding to apply to the shellcode (use --list encrypt to list)
        --encrypt-key     <value>    A key to be used for --encrypt
        --encrypt-iv      <value>    An initialization vector for --encrypt
    -a, --arch            <arch>     The architecture to use for --payload and --encoders (use --list archs to list)
        --platform        <platform> The platform for --payload (use --list platforms to list)
    -o, --out             <path>     Save the payload to a file
    -b, --bad-chars       <list>     Characters to avoid example: '\x00\xff'
    -n, --nopsled         <length>   Prepend a nopsled of [length] size on to the payload
        --pad-nops                   Use nopsled size specified by -n <length> as the total payload size, auto-prepending a nopsled of quantity (nops minus payload length)
    -s, --space           <length>   The maximum size of the resulting payload
        --encoder-space   <length>   The maximum size of the encoded payload (defaults to the -s value)
    -i, --iterations      <count>    The number of times to encode the payload
    -c, --add-code        <path>     Specify an additional win32 shellcode file to include
    -x, --template        <path>     Specify a custom executable file to use as a template
    -k, --keep                       Preserve the --template behaviour and inject the payload as a new thread
    -v, --var-name        <value>    Specify a custom variable name to use for certain output formats
    -t, --timeout         <second>   The number of seconds to wait when reading the payload from STDIN (default 30, 0 to disable)
    -h, --help                       Show this message
```


## payload
```
Framework Payloads (1616 total) [--payload <value>]
===================================================

    Name                                                               Description
    ----                                                               -----------
    aix/ppc/shell_bind_tcp                                             Listen for a connection and spawn a command shell
    aix/ppc/shell_find_port                                            Spawn a shell on an established connection
    aix/ppc/shell_interact                                             Simply execve /bin/sh (for inetd programs)
    aix/ppc/shell_reverse_tcp                                          Connect back to attacker and spawn a command shell
    android/meterpreter/reverse_http                                   Run a meterpreter server in Android. Tunnel communication over HTTP
    android/meterpreter/reverse_https                                  Run a meterpreter server in Android. Tunnel communication over HTTPS
    android/meterpreter/reverse_tcp                                    Run a meterpreter server in Android. Connect back stager
    android/meterpreter_reverse_http                                   Connect back to attacker and spawn a Meterpreter shell
    android/meterpreter_reverse_https                                  Connect back to attacker and spawn a Meterpreter shell
    android/meterpreter_reverse_tcp                                    Connect back to the attacker and spawn a Meterpreter shell
    android/shell/reverse_http                                         Spawn a piped command shell (sh). Tunnel communication over HTTP
    android/shell/reverse_https                                        Spawn a piped command shell (sh). Tunnel communication over HTTPS
    android/shell/reverse_tcp                                          Spawn a piped command shell (sh). Connect back stager
    apple_ios/aarch64/meterpreter_reverse_http                         Run the Meterpreter / Mettle server payload (stageless)
    apple_ios/aarch64/meterpreter_reverse_https                        Run the Meterpreter / Mettle server payload (stageless)
    apple_ios/aarch64/meterpreter_reverse_tcp                          Run the Meterpreter / Mettle server payload (stageless)
    apple_ios/aarch64/shell_reverse_tcp                                Connect back to attacker and spawn a command shell
    apple_ios/armle/meterpreter_reverse_http                           Run the Meterpreter / Mettle server payload (stageless)
    apple_ios/armle/meterpreter_reverse_https                          Run the Meterpreter / Mettle server payload (stageless)
    apple_ios/armle/meterpreter_reverse_tcp                            Run the Meterpreter / Mettle server payload (stageless)
    bsd/sparc/shell_bind_tcp                                           Listen for a connection and spawn a command shell
    bsd/sparc/shell_reverse_tcp                                        Connect back to attacker and spawn a command shell
    bsd/vax/shell_reverse_tcp                                          Connect back to attacker and spawn a command shell
    bsd/x64/exec                                                       Execute an arbitrary command
    bsd/x64/shell_bind_ipv6_tcp                                        Listen for a connection and spawn a command shell over IPv6
    bsd/x64/shell_bind_tcp                                             Bind an arbitrary command to an arbitrary port
    bsd/x64/shell_bind_tcp_small                                       Listen for a connection and spawn a command shell
    bsd/x64/shell_reverse_ipv6_tcp                                     Connect back to attacker and spawn a command shell over IPv6
    bsd/x64/shell_reverse_tcp                                          Connect back to attacker and spawn a command shell
    bsd/x64/shell_reverse_tcp_small                                    Connect back to attacker and spawn a command shell
    bsd/x86/exec                                                       Execute an arbitrary command
    bsd/x86/metsvc_bind_tcp                                            Stub payload for interacting with a Meterpreter Service
    bsd/x86/metsvc_reverse_tcp                                         Stub payload for interacting with a Meterpreter Service
    bsd/x86/shell/bind_ipv6_tcp                                        Spawn a command shell (staged). Listen for a connection over IPv6
    bsd/x86/shell/bind_tcp                                             Spawn a command shell (staged). Listen for a connection
    bsd/x86/shell/find_tag                                             Spawn a command shell (staged). Use an established connection
    bsd/x86/shell/reverse_ipv6_tcp                                     Spawn a command shell (staged). Connect back to the attacker over IPv6
    bsd/x86/shell/reverse_tcp                                          Spawn a command shell (staged). Connect back to the attacker
    bsd/x86/shell_bind_tcp                                             Listen for a connection and spawn a command shell
    bsd/x86/shell_bind_tcp_ipv6                                        Listen for a connection and spawn a command shell over IPv6
    bsd/x86/shell_find_port                                            Spawn a shell on an established connection
    bsd/x86/shell_find_tag                                             Spawn a shell on an established connection (proxy/nat safe)
    bsd/x86/shell_reverse_tcp                                          Connect back to attacker and spawn a command shell
    bsd/x86/shell_reverse_tcp_ipv6                                     Connect back to attacker and spawn a command shell over IPv6
    bsdi/x86/shell/bind_tcp                                            Spawn a command shell (staged). Listen for a connection
    bsdi/x86/shell/reverse_tcp                                         Spawn a command shell (staged). Connect back to the attacker
    bsdi/x86/shell_bind_tcp                                            Listen for a connection and spawn a command shell
    bsdi/x86/shell_find_port                                           Spawn a shell on an established connection
    bsdi/x86/shell_reverse_tcp                                         Connect back to attacker and spawn a command shell
    cmd/linux/http/aarch64/meterpreter/reverse_tcp                     Fetch and execute an AARCH64 payload from an HTTP server. Connect back to the attacker
    cmd/linux/http/aarch64/meterpreter_reverse_http                    Fetch and execute an AARCH64 payload from an HTTP server.
    cmd/linux/http/aarch64/meterpreter_reverse_https                   Fetch and execute an AARCH64 payload from an HTTP server.
    cmd/linux/http/aarch64/meterpreter_reverse_tcp                     Fetch and execute an AARCH64 payload from an HTTP server.
    cmd/linux/http/aarch64/shell/reverse_tcp                           Fetch and execute an AARCH64 payload from an HTTP server. dup2 socket in x12, then execve. Connect back to the attacker
    cmd/linux/http/aarch64/shell_reverse_tcp                           Fetch and execute an AARCH64 payload from an HTTP server. Connect back to attacker and spawn a command shell
    cmd/linux/http/armbe/meterpreter_reverse_http                      Fetch and execute an ARMBE payload from an HTTP server.
    cmd/linux/http/armbe/meterpreter_reverse_https                     Fetch and execute an ARMBE payload from an HTTP server.
    cmd/linux/http/armbe/meterpreter_reverse_tcp                       Fetch and execute an ARMBE payload from an HTTP server.
    cmd/linux/http/armbe/shell_bind_tcp                                Fetch and execute an ARMBE payload from an HTTP server. Listen for a connection and spawn a command shell
    cmd/linux/http/armle/adduser                                       Fetch and execute an ARMLE payload from an HTTP server. Create a new user with UID 0
    cmd/linux/http/armle/exec                                          Fetch and execute an ARMLE payload from an HTTP server. Execute an arbitrary command
    cmd/linux/http/armle/meterpreter/bind_tcp                          Fetch and execute an ARMLE payload from an HTTP server. Listen for a connection
    cmd/linux/http/armle/meterpreter/reverse_tcp                       Fetch and execute an ARMLE payload from an HTTP server. Connect back to the attacker
    cmd/linux/http/armle/meterpreter_reverse_http                      Fetch and execute an ARMLE payload from an HTTP server.
    cmd/linux/http/armle/meterpreter_reverse_https                     Fetch and execute an ARMLE payload from an HTTP server.
    cmd/linux/http/armle/meterpreter_reverse_tcp                       Fetch and execute an ARMLE payload from an HTTP server.
    cmd/linux/http/armle/shell/bind_tcp                                Fetch and execute an ARMLE payload from an HTTP server. dup2 socket in r12, then execve. Listen for a connection
    cmd/linux/http/armle/shell/reverse_tcp                             Fetch and execute an ARMLE payload from an HTTP server. dup2 socket in r12, then execve. Connect back to the attacker
    cmd/linux/http/armle/shell_bind_tcp                                Fetch and execute an ARMLE payload from an HTTP server. Connect to target and spawn a command shell
    cmd/linux/http/armle/shell_reverse_tcp                             Fetch and execute an ARMLE payload from an HTTP server. Connect back to attacker and spawn a command shell
    cmd/linux/http/mips64/meterpreter_reverse_http                     Fetch and execute a MIPS64 payload from an HTTP server.
    cmd/linux/http/mips64/meterpreter_reverse_https                    Fetch and execute a MIPS64 payload from an HTTP server.
    cmd/linux/http/mips64/meterpreter_reverse_tcp                      Fetch and execute a MIPS64 payload from an HTTP server.
    cmd/linux/http/mipsbe/exec                                         Fetch and execute an MIPSBE payload from an HTTP server. A very small shellcode for executing commands. This module is sometimes helpful for testing purposes.
    cmd/linux/http/mipsbe/meterpreter/reverse_tcp                      Fetch and execute an MIPSBE payload from an HTTP server. Connect back to the attacker
    cmd/linux/http/mipsbe/meterpreter_reverse_http                     Fetch and execute an MIPSBE payload from an HTTP server.
    cmd/linux/http/mipsbe/meterpreter_reverse_https                    Fetch and execute an MIPSBE payload from an HTTP server.
    cmd/linux/http/mipsbe/meterpreter_reverse_tcp                      Fetch and execute an MIPSBE payload from an HTTP server.
    cmd/linux/http/mipsbe/reboot                                       Fetch and execute an MIPSBE payload from an HTTP server. A very small shellcode for rebooting the system. This payload is sometimes helpful for testing purposes or
                                                                        executing other payloads that rely on initial startup procedures.
    cmd/linux/http/mipsbe/shell/reverse_tcp                            Fetch and execute an MIPSBE payload from an HTTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/http/mipsbe/shell_bind_tcp                               Fetch and execute an MIPSBE payload from an HTTP server. Listen for a connection and spawn a command shell
    cmd/linux/http/mipsbe/shell_reverse_tcp                            Fetch and execute an MIPSBE payload from an HTTP server. Connect back to attacker and spawn a command shell
    cmd/linux/http/mipsle/exec                                         Fetch and execute an MIPSLE payload from an HTTP server. A very small shellcode for executing commands. This module is sometimes helpful for testing purposes as we
                                                                       ll as on targets with extremely limited buffer space.
    cmd/linux/http/mipsle/meterpreter/reverse_tcp                      Fetch and execute an MIPSLE payload from an HTTP server. Connect back to the attacker
    cmd/linux/http/mipsle/meterpreter_reverse_http                     Fetch and execute an MIPSLE payload from an HTTP server.
    cmd/linux/http/mipsle/meterpreter_reverse_https                    Fetch and execute an MIPSLE payload from an HTTP server.
    cmd/linux/http/mipsle/meterpreter_reverse_tcp                      Fetch and execute an MIPSLE payload from an HTTP server.
    cmd/linux/http/mipsle/reboot                                       Fetch and execute an MIPSLE payload from an HTTP server. A very small shellcode for rebooting the system. This payload is sometimes helpful for testing purposes.
    cmd/linux/http/mipsle/shell/reverse_tcp                            Fetch and execute an MIPSLE payload from an HTTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/http/mipsle/shell_bind_tcp                               Fetch and execute an MIPSLE payload from an HTTP server. Listen for a connection and spawn a command shell
    cmd/linux/http/mipsle/shell_reverse_tcp                            Fetch and execute an MIPSLE payload from an HTTP server. Connect back to attacker and spawn a command shell
    cmd/linux/http/ppc/meterpreter_reverse_http                        Fetch and execute an PPC payload from an HTTP server.
    cmd/linux/http/ppc/meterpreter_reverse_https                       Fetch and execute an PPC payload from an HTTP server.
    cmd/linux/http/ppc/meterpreter_reverse_tcp                         Fetch and execute an PPC payload from an HTTP server.
    cmd/linux/http/ppc64/shell_bind_tcp                                Fetch and execute an PPC64 payload from an HTTP server. Listen for a connection and spawn a command shell
    cmd/linux/http/ppc64/shell_find_port                               Fetch and execute an PPC64 payload from an HTTP server. Spawn a shell on an established connection
    cmd/linux/http/ppc64/shell_reverse_tcp                             Fetch and execute an PPC64 payload from an HTTP server. Connect back to attacker and spawn a command shell
    cmd/linux/http/ppc64le/meterpreter_reverse_http                    Fetch and execute a PPC64LE payload from an HTTP server.
    cmd/linux/http/ppc64le/meterpreter_reverse_https                   Fetch and execute a PPC64LE payload from an HTTP server.
    cmd/linux/http/ppc64le/meterpreter_reverse_tcp                     Fetch and execute a PPC64LE payload from an HTTP server.
    cmd/linux/http/x64/exec                                            Fetch and execute an x64 payload from an HTTP server. Execute an arbitrary command or just a /bin/sh shell
    cmd/linux/http/x64/meterpreter/bind_tcp                            Fetch and execute an x64 payload from an HTTP server. Listen for a connection
    cmd/linux/http/x64/meterpreter/reverse_sctp                        Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker
    cmd/linux/http/x64/meterpreter/reverse_tcp                         Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker
    cmd/linux/http/x64/meterpreter_reverse_http                        Fetch and execute an x64 payload from an HTTP server.
    cmd/linux/http/x64/meterpreter_reverse_https                       Fetch and execute an x64 payload from an HTTP server.
    cmd/linux/http/x64/meterpreter_reverse_tcp                         Fetch and execute an x64 payload from an HTTP server.
    cmd/linux/http/x64/pingback_bind_tcp                               Fetch and execute an x64 payload from an HTTP server. Accept a connection from attacker and report UUID (Linux x64)
    cmd/linux/http/x64/pingback_reverse_tcp                            Fetch and execute an x64 payload from an HTTP server. Connect back to attacker and report UUID (Linux x64)
    cmd/linux/http/x64/shell/bind_tcp                                  Fetch and execute an x64 payload from an HTTP server. Spawn a command shell (staged). Listen for a connection
    cmd/linux/http/x64/shell/reverse_sctp                              Fetch and execute an x64 payload from an HTTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/http/x64/shell/reverse_tcp                               Fetch and execute an x64 payload from an HTTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/http/x64/shell_bind_ipv6_tcp                             Fetch and execute an x64 payload from an HTTP server. Listen for an IPv6 connection and spawn a command shell
    cmd/linux/http/x64/shell_bind_tcp                                  Fetch and execute an x64 payload from an HTTP server. Listen for a connection and spawn a command shell
    cmd/linux/http/x64/shell_bind_tcp_random_port                      Fetch and execute an x64 payload from an HTTP server. Listen for a connection in a random port and spawn a command shell. Use nmap to discover the open port: 'nmap
                                                                        -sS target -p-'.
    cmd/linux/http/x64/shell_find_port                                 Fetch and execute an x64 payload from an HTTP server. Spawn a shell on an established connection
    cmd/linux/http/x64/shell_reverse_ipv6_tcp                          Fetch and execute an x64 payload from an HTTP server. Connect back to attacker and spawn a command shell over IPv6
    cmd/linux/http/x64/shell_reverse_tcp                               Fetch and execute an x64 payload from an HTTP server. Connect back to attacker and spawn a command shell
    cmd/linux/http/x86/adduser                                         Fetch and execute a x86 payload from an HTTP server. Create a new user with UID 0
    cmd/linux/http/x86/chmod                                           Fetch and execute a x86 payload from an HTTP server. Runs chmod on specified file with specified mode
    cmd/linux/http/x86/exec                                            Fetch and execute a x86 payload from an HTTP server. Execute an arbitrary command or just a /bin/sh shell
    cmd/linux/http/x86/generic/debug_trap                              Fetch and execute a x86 payload from an HTTP server. Generate a debug trap in the target process
    cmd/linux/http/x86/generic/tight_loop                              Fetch and execute a x86 payload from an HTTP server. Generate a tight loop in the target process
    cmd/linux/http/x86/meterpreter/bind_ipv6_tcp                       Fetch and execute a x86 payload from an HTTP server. Listen for an IPv6 connection (Linux x86)
    cmd/linux/http/x86/meterpreter/bind_ipv6_tcp_uuid                  Fetch and execute a x86 payload from an HTTP server. Listen for an IPv6 connection with UUID Support (Linux x86)
    cmd/linux/http/x86/meterpreter/bind_nonx_tcp                       Fetch and execute a x86 payload from an HTTP server. Listen for a connection
    cmd/linux/http/x86/meterpreter/bind_tcp                            Fetch and execute a x86 payload from an HTTP server. Listen for a connection (Linux x86)
    cmd/linux/http/x86/meterpreter/bind_tcp_uuid                       Fetch and execute a x86 payload from an HTTP server. Listen for a connection with UUID Support (Linux x86)
    cmd/linux/http/x86/meterpreter/find_tag                            Fetch and execute a x86 payload from an HTTP server. Use an established connection
    cmd/linux/http/x86/meterpreter/reverse_ipv6_tcp                    Fetch and execute a x86 payload from an HTTP server. Connect back to attacker over IPv6
    cmd/linux/http/x86/meterpreter/reverse_nonx_tcp                    Fetch and execute a x86 payload from an HTTP server. Connect back to the attacker
    cmd/linux/http/x86/meterpreter/reverse_tcp                         Fetch and execute a x86 payload from an HTTP server. Connect back to the attacker
    cmd/linux/http/x86/meterpreter/reverse_tcp_uuid                    Fetch and execute a x86 payload from an HTTP server. Connect back to the attacker
    cmd/linux/http/x86/meterpreter_reverse_http                        Fetch and execute a x86 payload from an HTTP server.
    cmd/linux/http/x86/meterpreter_reverse_https                       Fetch and execute a x86 payload from an HTTP server.
    cmd/linux/http/x86/meterpreter_reverse_tcp                         Fetch and execute a x86 payload from an HTTP server.
    cmd/linux/http/x86/metsvc_bind_tcp                                 Fetch and execute a x86 payload from an HTTP server. Stub payload for interacting with a Meterpreter Service
    cmd/linux/http/x86/metsvc_reverse_tcp                              Fetch and execute a x86 payload from an HTTP server. Stub payload for interacting with a Meterpreter Service
    cmd/linux/http/x86/read_file                                       Fetch and execute a x86 payload from an HTTP server. Read up to 4096 bytes from the local file system and write it back out to the specified file descriptor
    cmd/linux/http/x86/shell/bind_ipv6_tcp                             Fetch and execute a x86 payload from an HTTP server. Spawn a command shell (staged). Listen for an IPv6 connection (Linux x86)
    cmd/linux/http/x86/shell/bind_ipv6_tcp_uuid                        Fetch and execute a x86 payload from an HTTP server. Spawn a command shell (staged). Listen for an IPv6 connection with UUID Support (Linux x86)
    cmd/linux/http/x86/shell/bind_nonx_tcp                             Fetch and execute a x86 payload from an HTTP server. Spawn a command shell (staged). Listen for a connection
    cmd/linux/http/x86/shell/bind_tcp                                  Fetch and execute a x86 payload from an HTTP server. Spawn a command shell (staged). Listen for a connection (Linux x86)
    cmd/linux/http/x86/shell/bind_tcp_uuid                             Fetch and execute a x86 payload from an HTTP server. Spawn a command shell (staged). Listen for a connection with UUID Support (Linux x86)
    cmd/linux/http/x86/shell/find_tag                                  Fetch and execute a x86 payload from an HTTP server. Spawn a command shell (staged). Use an established connection
    cmd/linux/http/x86/shell/reverse_ipv6_tcp                          Fetch and execute a x86 payload from an HTTP server. Spawn a command shell (staged). Connect back to attacker over IPv6
    cmd/linux/http/x86/shell/reverse_nonx_tcp                          Fetch and execute a x86 payload from an HTTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/http/x86/shell/reverse_tcp                               Fetch and execute a x86 payload from an HTTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/http/x86/shell/reverse_tcp_uuid                          Fetch and execute a x86 payload from an HTTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/http/x86/shell_bind_ipv6_tcp                             Fetch and execute a x86 payload from an HTTP server. Listen for a connection over IPv6 and spawn a command shell
    cmd/linux/http/x86/shell_bind_tcp                                  Fetch and execute a x86 payload from an HTTP server. Listen for a connection and spawn a command shell
    cmd/linux/http/x86/shell_bind_tcp_random_port                      Fetch and execute a x86 payload from an HTTP server. Listen for a connection in a random port and spawn a command shell. Use nmap to discover the open port: 'nmap
                                                                       -sS target -p-'.
    cmd/linux/http/x86/shell_find_port                                 Fetch and execute a x86 payload from an HTTP server. Spawn a shell on an established connection
    cmd/linux/http/x86/shell_find_tag                                  Fetch and execute a x86 payload from an HTTP server. Spawn a shell on an established connection (proxy/nat safe)
    cmd/linux/http/x86/shell_reverse_tcp                               Fetch and execute a x86 payload from an HTTP server. Connect back to attacker and spawn a command shell
    cmd/linux/http/x86/shell_reverse_tcp_ipv6                          Fetch and execute a x86 payload from an HTTP server. Connect back to attacker and spawn a command shell over IPv6
    cmd/linux/https/aarch64/meterpreter/reverse_tcp                    Fetch and execute an AARCH64 payload from an HTTPS server. Connect back to the attacker
    cmd/linux/https/aarch64/meterpreter_reverse_http                   Fetch and execute an AARCH64 payload from an HTTPS server.
    cmd/linux/https/aarch64/meterpreter_reverse_https                  Fetch and execute an AARCH64 payload from an HTTPS server.
    cmd/linux/https/aarch64/meterpreter_reverse_tcp                    Fetch and execute an AARCH64 payload from an HTTPS server.
    cmd/linux/https/aarch64/shell/reverse_tcp                          Fetch and execute an AARCH64 payload from an HTTPS server. dup2 socket in x12, then execve. Connect back to the attacker
    cmd/linux/https/aarch64/shell_reverse_tcp                          Fetch and execute an AARCH64 payload from an HTTPS server. Connect back to attacker and spawn a command shell
    cmd/linux/https/armbe/meterpreter_reverse_http                     Fetch and execute an ARMBE payload from an HTTPS server.
    cmd/linux/https/armbe/meterpreter_reverse_https                    Fetch and execute an ARMBE payload from an HTTPS server.
    cmd/linux/https/armbe/meterpreter_reverse_tcp                      Fetch and execute an ARMBE payload from an HTTPS server.
    cmd/linux/https/armbe/shell_bind_tcp                               Fetch and execute an ARMBE payload from an HTTPS server. Listen for a connection and spawn a command shell
    cmd/linux/https/armle/adduser                                      Fetch and execute an ARMLE payload from an HTTPS server. Create a new user with UID 0
    cmd/linux/https/armle/exec                                         Fetch and execute an ARMLE payload from an HTTPS server. Execute an arbitrary command
    cmd/linux/https/armle/meterpreter/bind_tcp                         Fetch and execute an ARMLE payload from an HTTPS server. Listen for a connection
    cmd/linux/https/armle/meterpreter/reverse_tcp                      Fetch and execute an ARMLE payload from an HTTPS server. Connect back to the attacker
    cmd/linux/https/armle/meterpreter_reverse_http                     Fetch and execute an ARMLE payload from an HTTPS server.
    cmd/linux/https/armle/meterpreter_reverse_https                    Fetch and execute an ARMLE payload from an HTTPS server.
    cmd/linux/https/armle/meterpreter_reverse_tcp                      Fetch and execute an ARMLE payload from an HTTPS server.
    cmd/linux/https/armle/shell/bind_tcp                               Fetch and execute an ARMLE payload from an HTTPS server. dup2 socket in r12, then execve. Listen for a connection
    cmd/linux/https/armle/shell/reverse_tcp                            Fetch and execute an ARMLE payload from an HTTPS server. dup2 socket in r12, then execve. Connect back to the attacker
    cmd/linux/https/armle/shell_bind_tcp                               Fetch and execute an ARMLE payload from an HTTPS server. Connect to target and spawn a command shell
    cmd/linux/https/armle/shell_reverse_tcp                            Fetch and execute an ARMLE payload from an HTTPS server. Connect back to attacker and spawn a command shell
    cmd/linux/https/mips64/meterpreter_reverse_http                    Fetch and execute an MIPS64 payload from an HTTPS server.
    cmd/linux/https/mips64/meterpreter_reverse_https                   Fetch and execute an MIPS64 payload from an HTTPS server.
    cmd/linux/https/mips64/meterpreter_reverse_tcp                     Fetch and execute an MIPS64 payload from an HTTPS server.
    cmd/linux/https/mipsbe/exec                                        Fetch and execute an MIPSBE payload from an HTTPS server. A very small shellcode for executing commands. This module is sometimes helpful for testing purposes.
    cmd/linux/https/mipsbe/meterpreter/reverse_tcp                     Fetch and execute an MIPSBE payload from an HTTPS server. Connect back to the attacker
    cmd/linux/https/mipsbe/meterpreter_reverse_http                    Fetch and execute an MIPSBE payload from an HTTPS server.
    cmd/linux/https/mipsbe/meterpreter_reverse_https                   Fetch and execute an MIPSBE payload from an HTTPS server.
    cmd/linux/https/mipsbe/meterpreter_reverse_tcp                     Fetch and execute an MIPSBE payload from an HTTPS server.
    cmd/linux/https/mipsbe/reboot                                      Fetch and execute an MIPSBE payload from an HTTPS server. A very small shellcode for rebooting the system. This payload is sometimes helpful for testing purposes o
                                                                       r executing other payloads that rely on initial startup procedures.
    cmd/linux/https/mipsbe/shell/reverse_tcp                           Fetch and execute an MIPSBE payload from an HTTPS server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/https/mipsbe/shell_bind_tcp                              Fetch and execute an MIPSBE payload from an HTTPS server. Listen for a connection and spawn a command shell
    cmd/linux/https/mipsbe/shell_reverse_tcp                           Fetch and execute an MIPSBE payload from an HTTPS server. Connect back to attacker and spawn a command shell
    cmd/linux/https/mipsle/exec                                        Fetch and execute an MIPSLE payload from an HTTPS server. A very small shellcode for executing commands. This module is sometimes helpful for testing purposes as w
                                                                       ell as on targets with extremely limited buffer space.
    cmd/linux/https/mipsle/meterpreter/reverse_tcp                     Fetch and execute an MIPSLE payload from an HTTPS server. Connect back to the attacker
    cmd/linux/https/mipsle/meterpreter_reverse_http                    Fetch and execute an MIPSLE payload from an HTTPS server.
    cmd/linux/https/mipsle/meterpreter_reverse_https                   Fetch and execute an MIPSLE payload from an HTTPS server.
    cmd/linux/https/mipsle/meterpreter_reverse_tcp                     Fetch and execute an MIPSLE payload from an HTTPS server.
    cmd/linux/https/mipsle/reboot                                      Fetch and execute an MIPSLE payload from an HTTPS server. A very small shellcode for rebooting the system. This payload is sometimes helpful for testing purposes.
    cmd/linux/https/mipsle/shell/reverse_tcp                           Fetch and execute an MIPSLE payload from an HTTPS server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/https/mipsle/shell_bind_tcp                              Fetch and execute an MIPSLE payload from an HTTPS server. Listen for a connection and spawn a command shell
    cmd/linux/https/mipsle/shell_reverse_tcp                           Fetch and execute an MIPSLE payload from an HTTPS server. Connect back to attacker and spawn a command shell
    cmd/linux/https/ppc/meterpreter_reverse_http                       Fetch and execute an MIPSLE payload from an HTTPS server.
    cmd/linux/https/ppc/meterpreter_reverse_https                      Fetch and execute an MIPSLE payload from an HTTPS server.
    cmd/linux/https/ppc/meterpreter_reverse_tcp                        Fetch and execute an MIPSLE payload from an HTTPS server.
    cmd/linux/https/ppc64/shell_bind_tcp                               Fetch and execute an PPC64 payload from an HTTPS server. Listen for a connection and spawn a command shell
    cmd/linux/https/ppc64/shell_find_port                              Fetch and execute an PPC64 payload from an HTTPS server. Spawn a shell on an established connection
    cmd/linux/https/ppc64/shell_reverse_tcp                            Fetch and execute an PPC64 payload from an HTTPS server. Connect back to attacker and spawn a command shell
    cmd/linux/https/ppc64le/meterpreter_reverse_http                   Fetch and execute a PPC64LE payload from an HTTPS server.
    cmd/linux/https/ppc64le/meterpreter_reverse_https                  Fetch and execute a PPC64LE payload from an HTTPS server.
    cmd/linux/https/ppc64le/meterpreter_reverse_tcp                    Fetch and execute a PPC64LE payload from an HTTPS server.
    cmd/linux/https/x64/exec                                           Fetch and execute an x64 payload from an HTTPS server. Execute an arbitrary command or just a /bin/sh shell
    cmd/linux/https/x64/meterpreter/bind_tcp                           Fetch and execute an x64 payload from an HTTPS server. Listen for a connection
    cmd/linux/https/x64/meterpreter/reverse_sctp                       Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker
    cmd/linux/https/x64/meterpreter/reverse_tcp                        Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker
    cmd/linux/https/x64/meterpreter_reverse_http                       Fetch and execute an x64 payload from an HTTPS server.
    cmd/linux/https/x64/meterpreter_reverse_https                      Fetch and execute an x64 payload from an HTTPS server.
    cmd/linux/https/x64/meterpreter_reverse_tcp                        Fetch and execute an x64 payload from an HTTPS server.
    cmd/linux/https/x64/pingback_bind_tcp                              Fetch and execute an x64 payload from an HTTPS server. Accept a connection from attacker and report UUID (Linux x64)
    cmd/linux/https/x64/pingback_reverse_tcp                           Fetch and execute an x64 payload from an HTTPS server. Connect back to attacker and report UUID (Linux x64)
    cmd/linux/https/x64/shell/bind_tcp                                 Fetch and execute an x64 payload from an HTTPS server. Spawn a command shell (staged). Listen for a connection
    cmd/linux/https/x64/shell/reverse_sctp                             Fetch and execute an x64 payload from an HTTPS server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/https/x64/shell/reverse_tcp                              Fetch and execute an x64 payload from an HTTPS server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/https/x64/shell_bind_ipv6_tcp                            Fetch and execute an x64 payload from an HTTPS server. Listen for an IPv6 connection and spawn a command shell
    cmd/linux/https/x64/shell_bind_tcp                                 Fetch and execute an x64 payload from an HTTPS server. Listen for a connection and spawn a command shell
    cmd/linux/https/x64/shell_bind_tcp_random_port                     Fetch and execute an x64 payload from an HTTPS server. Listen for a connection in a random port and spawn a command shell. Use nmap to discover the open port: 'nma
                                                                       p -sS target -p-'.
    cmd/linux/https/x64/shell_find_port                                Fetch and execute an x64 payload from an HTTPS server. Spawn a shell on an established connection
    cmd/linux/https/x64/shell_reverse_ipv6_tcp                         Fetch and execute an x64 payload from an HTTPS server. Connect back to attacker and spawn a command shell over IPv6
    cmd/linux/https/x64/shell_reverse_tcp                              Fetch and execute an x64 payload from an HTTPS server. Connect back to attacker and spawn a command shell
    cmd/linux/https/x86/adduser                                        Fetch and execute an x86 payload from an HTTPS server. Create a new user with UID 0
    cmd/linux/https/x86/chmod                                          Fetch and execute an x86 payload from an HTTPS server. Runs chmod on specified file with specified mode
    cmd/linux/https/x86/exec                                           Fetch and execute an x86 payload from an HTTPS server. Execute an arbitrary command or just a /bin/sh shell
    cmd/linux/https/x86/generic/debug_trap                             Fetch and execute an x86 payload from an HTTPS server. Generate a debug trap in the target process
    cmd/linux/https/x86/generic/tight_loop                             Fetch and execute an x86 payload from an HTTPS server. Generate a tight loop in the target process
    cmd/linux/https/x86/meterpreter/bind_ipv6_tcp                      Fetch and execute an x86 payload from an HTTPS server. Listen for an IPv6 connection (Linux x86)
    cmd/linux/https/x86/meterpreter/bind_ipv6_tcp_uuid                 Fetch and execute an x86 payload from an HTTPS server. Listen for an IPv6 connection with UUID Support (Linux x86)
    cmd/linux/https/x86/meterpreter/bind_nonx_tcp                      Fetch and execute an x86 payload from an HTTPS server. Listen for a connection
    cmd/linux/https/x86/meterpreter/bind_tcp                           Fetch and execute an x86 payload from an HTTPS server. Listen for a connection (Linux x86)
    cmd/linux/https/x86/meterpreter/bind_tcp_uuid                      Fetch and execute an x86 payload from an HTTPS server. Listen for a connection with UUID Support (Linux x86)
    cmd/linux/https/x86/meterpreter/find_tag                           Fetch and execute an x86 payload from an HTTPS server. Use an established connection
    cmd/linux/https/x86/meterpreter/reverse_ipv6_tcp                   Fetch and execute an x86 payload from an HTTPS server. Connect back to attacker over IPv6
    cmd/linux/https/x86/meterpreter/reverse_nonx_tcp                   Fetch and execute an x86 payload from an HTTPS server. Connect back to the attacker
    cmd/linux/https/x86/meterpreter/reverse_tcp                        Fetch and execute an x86 payload from an HTTPS server. Connect back to the attacker
    cmd/linux/https/x86/meterpreter/reverse_tcp_uuid                   Fetch and execute an x86 payload from an HTTPS server. Connect back to the attacker
    cmd/linux/https/x86/meterpreter_reverse_http                       Fetch and execute an x86 payload from an HTTPS server.
    cmd/linux/https/x86/meterpreter_reverse_https                      Fetch and execute an x86 payload from an HTTPS server.
    cmd/linux/https/x86/meterpreter_reverse_tcp                        Fetch and execute an x86 payload from an HTTPS server.
    cmd/linux/https/x86/metsvc_bind_tcp                                Fetch and execute an x86 payload from an HTTPS server. Stub payload for interacting with a Meterpreter Service
    cmd/linux/https/x86/metsvc_reverse_tcp                             Fetch and execute an x86 payload from an HTTPS server. Stub payload for interacting with a Meterpreter Service
    cmd/linux/https/x86/read_file                                      Fetch and execute an x86 payload from an HTTPS server. Read up to 4096 bytes from the local file system and write it back out to the specified file descriptor
    cmd/linux/https/x86/shell/bind_ipv6_tcp                            Fetch and execute an x86 payload from an HTTPS server. Spawn a command shell (staged). Listen for an IPv6 connection (Linux x86)
    cmd/linux/https/x86/shell/bind_ipv6_tcp_uuid                       Fetch and execute an x86 payload from an HTTPS server. Spawn a command shell (staged). Listen for an IPv6 connection with UUID Support (Linux x86)
    cmd/linux/https/x86/shell/bind_nonx_tcp                            Fetch and execute an x86 payload from an HTTPS server. Spawn a command shell (staged). Listen for a connection
    cmd/linux/https/x86/shell/bind_tcp                                 Fetch and execute an x86 payload from an HTTPS server. Spawn a command shell (staged). Listen for a connection (Linux x86)
    cmd/linux/https/x86/shell/bind_tcp_uuid                            Fetch and execute an x86 payload from an HTTPS server. Spawn a command shell (staged). Listen for a connection with UUID Support (Linux x86)
    cmd/linux/https/x86/shell/find_tag                                 Fetch and execute an x86 payload from an HTTPS server. Spawn a command shell (staged). Use an established connection
    cmd/linux/https/x86/shell/reverse_ipv6_tcp                         Fetch and execute an x86 payload from an HTTPS server. Spawn a command shell (staged). Connect back to attacker over IPv6
    cmd/linux/https/x86/shell/reverse_nonx_tcp                         Fetch and execute an x86 payload from an HTTPS server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/https/x86/shell/reverse_tcp                              Fetch and execute an x86 payload from an HTTPS server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/https/x86/shell/reverse_tcp_uuid                         Fetch and execute an x86 payload from an HTTPS server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/https/x86/shell_bind_ipv6_tcp                            Fetch and execute an x86 payload from an HTTPS server. Listen for a connection over IPv6 and spawn a command shell
    cmd/linux/https/x86/shell_bind_tcp                                 Fetch and execute an x86 payload from an HTTPS server. Listen for a connection and spawn a command shell
    cmd/linux/https/x86/shell_bind_tcp_random_port                     Fetch and execute an x86 payload from an HTTPS server. Listen for a connection in a random port and spawn a command shell. Use nmap to discover the open port: 'nma
                                                                       p -sS target -p-'.
    cmd/linux/https/x86/shell_find_port                                Fetch and execute an x86 payload from an HTTPS server. Spawn a shell on an established connection
    cmd/linux/https/x86/shell_find_tag                                 Fetch and execute an x86 payload from an HTTPS server. Spawn a shell on an established connection (proxy/nat safe)
    cmd/linux/https/x86/shell_reverse_tcp                              Fetch and execute an x86 payload from an HTTPS server. Connect back to attacker and spawn a command shell
    cmd/linux/https/x86/shell_reverse_tcp_ipv6                         Fetch and execute an x86 payload from an HTTPS server. Connect back to attacker and spawn a command shell over IPv6
    cmd/linux/tftp/aarch64/meterpreter/reverse_tcp                     Fetch and execute an AARCH64 payload from a TFTP server. Connect back to the attacker
    cmd/linux/tftp/aarch64/meterpreter_reverse_http                    Fetch and execute an AARCH64 payload from a TFTP server.
    cmd/linux/tftp/aarch64/meterpreter_reverse_https                   Fetch and execute an AARCH64 payload from a TFTP server.
    cmd/linux/tftp/aarch64/meterpreter_reverse_tcp                     Fetch and execute an AARCH64 payload from a TFTP server.
    cmd/linux/tftp/aarch64/shell/reverse_tcp                           Fetch and execute an AARCH64 payload from a TFTP server. dup2 socket in x12, then execve. Connect back to the attacker
    cmd/linux/tftp/aarch64/shell_reverse_tcp                           Fetch and execute an AARCH64 payload from a TFTP server. Connect back to attacker and spawn a command shell
    cmd/linux/tftp/armbe/meterpreter_reverse_http                      Fetch and execute an ARMBE payload from a TFTP server.
    cmd/linux/tftp/armbe/meterpreter_reverse_https                     Fetch and execute an ARMBE payload from a TFTP server.
    cmd/linux/tftp/armbe/meterpreter_reverse_tcp                       Fetch and execute an ARMBE payload from a TFTP server.
    cmd/linux/tftp/armbe/shell_bind_tcp                                Fetch and execute an ARMBE payload from a TFTP server. Listen for a connection and spawn a command shell
    cmd/linux/tftp/armle/adduser                                       Fetch and execute an ARMLE payload from a TFTP server. Create a new user with UID 0
    cmd/linux/tftp/armle/exec                                          Fetch and execute an ARMLE payload from a TFTP server. Execute an arbitrary command
    cmd/linux/tftp/armle/meterpreter/bind_tcp                          Fetch and execute an ARMLE payload from a TFTP server. Listen for a connection
    cmd/linux/tftp/armle/meterpreter/reverse_tcp                       Fetch and execute an ARMLE payload from a TFTP server. Connect back to the attacker
    cmd/linux/tftp/armle/meterpreter_reverse_http                      Fetch and execute an ARMLE payload from a TFTP server.
    cmd/linux/tftp/armle/meterpreter_reverse_https                     Fetch and execute an ARMLE payload from a TFTP server.
    cmd/linux/tftp/armle/meterpreter_reverse_tcp                       Fetch and execute an ARMLE payload from a TFTP server.
    cmd/linux/tftp/armle/shell/bind_tcp                                Fetch and execute an ARMLE payload from a TFTP server. dup2 socket in r12, then execve. Listen for a connection
    cmd/linux/tftp/armle/shell/reverse_tcp                             Fetch and execute an ARMLE payload from a TFTP server. dup2 socket in r12, then execve. Connect back to the attacker
    cmd/linux/tftp/armle/shell_bind_tcp                                Fetch and execute an ARMLE payload from a TFTP server. Connect to target and spawn a command shell
    cmd/linux/tftp/armle/shell_reverse_tcp                             Fetch and execute an ARMLE payload from a TFTP server. Connect back to attacker and spawn a command shell
    cmd/linux/tftp/mips64/meterpreter_reverse_http                     Fetch and execute a MIPS64 payload from a TFTP server.
    cmd/linux/tftp/mips64/meterpreter_reverse_https                    Fetch and execute a MIPS64 payload from a TFTP server.
    cmd/linux/tftp/mips64/meterpreter_reverse_tcp                      Fetch and execute a MIPS64 payload from a TFTP server.
    cmd/linux/tftp/mipsbe/exec                                         Fetch and execute an MIPSBE payload from a TFTP server. A very small shellcode for executing commands. This module is sometimes helpful for testing purposes.
    cmd/linux/tftp/mipsbe/meterpreter/reverse_tcp                      Fetch and execute an MIPSBE payload from a TFTP server. Connect back to the attacker
    cmd/linux/tftp/mipsbe/meterpreter_reverse_http                     Fetch and execute an MIPSBE payload from a TFTP server.
    cmd/linux/tftp/mipsbe/meterpreter_reverse_https                    Fetch and execute an MIPSBE payload from a TFTP server.
    cmd/linux/tftp/mipsbe/meterpreter_reverse_tcp                      Fetch and execute an MIPSBE payload from a TFTP server.
    cmd/linux/tftp/mipsbe/reboot                                       Fetch and execute an MIPSBE payload from a TFTP server. A very small shellcode for rebooting the system. This payload is sometimes helpful for testing purposes or
                                                                       executing other payloads that rely on initial startup procedures.
    cmd/linux/tftp/mipsbe/shell/reverse_tcp                            Fetch and execute an MIPSBE payload from a TFTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/tftp/mipsbe/shell_bind_tcp                               Fetch and execute an MIPSBE payload from a TFTP server. Listen for a connection and spawn a command shell
    cmd/linux/tftp/mipsbe/shell_reverse_tcp                            Fetch and execute an MIPSBE payload from a TFTP server. Connect back to attacker and spawn a command shell
    cmd/linux/tftp/mipsle/exec                                         Fetch and execute an MIPSLE payload from a TFTP server. A very small shellcode for executing commands. This module is sometimes helpful for testing purposes as wel
                                                                       l as on targets with extremely limited buffer space.
    cmd/linux/tftp/mipsle/meterpreter/reverse_tcp                      Fetch and execute an MIPSLE payload from a TFTP server. Connect back to the attacker
    cmd/linux/tftp/mipsle/meterpreter_reverse_http                     Fetch and execute an MIPSLE payload from a TFTP server.
    cmd/linux/tftp/mipsle/meterpreter_reverse_https                    Fetch and execute an MIPSLE payload from a TFTP server.
    cmd/linux/tftp/mipsle/meterpreter_reverse_tcp                      Fetch and execute an MIPSLE payload from a TFTP server.
    cmd/linux/tftp/mipsle/reboot                                       Fetch and execute an MIPSLE payload from a TFTP server. A very small shellcode for rebooting the system. This payload is sometimes helpful for testing purposes.
    cmd/linux/tftp/mipsle/shell/reverse_tcp                            Fetch and execute an MIPSLE payload from a TFTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/tftp/mipsle/shell_bind_tcp                               Fetch and execute an MIPSLE payload from a TFTP server. Listen for a connection and spawn a command shell
    cmd/linux/tftp/mipsle/shell_reverse_tcp                            Fetch and execute an MIPSLE payload from a TFTP server. Connect back to attacker and spawn a command shell
    cmd/linux/tftp/ppc/meterpreter_reverse_http                        Fetch and execute an PPC payload from an TFTP server.
    cmd/linux/tftp/ppc/meterpreter_reverse_https                       Fetch and execute an PPC payload from an TFTP server.
    cmd/linux/tftp/ppc/meterpreter_reverse_tcp                         Fetch and execute an PPC payload from an TFTP server.
    cmd/linux/tftp/ppc64/shell_bind_tcp                                Fetch and execute an PPC64 payload from a TFTP server. Listen for a connection and spawn a command shell
    cmd/linux/tftp/ppc64/shell_find_port                               Fetch and execute an PPC64 payload from a TFTP server. Spawn a shell on an established connection
    cmd/linux/tftp/ppc64/shell_reverse_tcp                             Fetch and execute an PPC64 payload from a TFTP server. Connect back to attacker and spawn a command shell
    cmd/linux/tftp/ppc64le/meterpreter_reverse_http                    Fetch and execute a PPC64LE payload from a TFTP server.
    cmd/linux/tftp/ppc64le/meterpreter_reverse_https                   Fetch and execute a PPC64LE payload from a TFTP server.
    cmd/linux/tftp/ppc64le/meterpreter_reverse_tcp                     Fetch and execute a PPC64LE payload from a TFTP server.
    cmd/linux/tftp/x64/exec                                            Fetch and execute an x64 payload from a TFTP server. Execute an arbitrary command or just a /bin/sh shell
    cmd/linux/tftp/x64/meterpreter/bind_tcp                            Fetch and execute an x64 payload from a TFTP server. Listen for a connection
    cmd/linux/tftp/x64/meterpreter/reverse_sctp                        Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker
    cmd/linux/tftp/x64/meterpreter/reverse_tcp                         Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker
    cmd/linux/tftp/x64/meterpreter_reverse_http                        Fetch and execute an x64 payload from a TFTP server.
    cmd/linux/tftp/x64/meterpreter_reverse_https                       Fetch and execute an x64 payload from a TFTP server.
    cmd/linux/tftp/x64/meterpreter_reverse_tcp                         Fetch and execute an x64 payload from a TFTP server.
    cmd/linux/tftp/x64/pingback_bind_tcp                               Fetch and execute an x64 payload from a TFTP server. Accept a connection from attacker and report UUID (Linux x64)
    cmd/linux/tftp/x64/pingback_reverse_tcp                            Fetch and execute an x64 payload from a TFTP server. Connect back to attacker and report UUID (Linux x64)
    cmd/linux/tftp/x64/shell/bind_tcp                                  Fetch and execute an x64 payload from a TFTP server. Spawn a command shell (staged). Listen for a connection
    cmd/linux/tftp/x64/shell/reverse_sctp                              Fetch and execute an x64 payload from a TFTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/tftp/x64/shell/reverse_tcp                               Fetch and execute an x64 payload from a TFTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/tftp/x64/shell_bind_ipv6_tcp                             Fetch and execute an x64 payload from a TFTP server. Listen for an IPv6 connection and spawn a command shell
    cmd/linux/tftp/x64/shell_bind_tcp                                  Fetch and execute an x64 payload from a TFTP server. Listen for a connection and spawn a command shell
    cmd/linux/tftp/x64/shell_bind_tcp_random_port                      Fetch and execute an x64 payload from a TFTP server. Listen for a connection in a random port and spawn a command shell. Use nmap to discover the open port: 'nmap
                                                                       -sS target -p-'.
    cmd/linux/tftp/x64/shell_find_port                                 Fetch and execute an x64 payload from a TFTP server. Spawn a shell on an established connection
    cmd/linux/tftp/x64/shell_reverse_ipv6_tcp                          Fetch and execute an x64 payload from a TFTP server. Connect back to attacker and spawn a command shell over IPv6
    cmd/linux/tftp/x64/shell_reverse_tcp                               Fetch and execute an x64 payload from a TFTP server. Connect back to attacker and spawn a command shell
    cmd/linux/tftp/x86/adduser                                         Fetch and execute a x86 payload from a TFTP server. Create a new user with UID 0
    cmd/linux/tftp/x86/chmod                                           Fetch and execute a x86 payload from a TFTP server. Runs chmod on specified file with specified mode
    cmd/linux/tftp/x86/exec                                            Fetch and execute a x86 payload from a TFTP server. Execute an arbitrary command or just a /bin/sh shell
    cmd/linux/tftp/x86/generic/debug_trap                              Fetch and execute a x86 payload from a TFTP server. Generate a debug trap in the target process
    cmd/linux/tftp/x86/generic/tight_loop                              Fetch and execute a x86 payload from a TFTP server. Generate a tight loop in the target process
    cmd/linux/tftp/x86/meterpreter/bind_ipv6_tcp                       Fetch and execute a x86 payload from a TFTP server. Listen for an IPv6 connection (Linux x86)
    cmd/linux/tftp/x86/meterpreter/bind_ipv6_tcp_uuid                  Fetch and execute a x86 payload from a TFTP server. Listen for an IPv6 connection with UUID Support (Linux x86)
    cmd/linux/tftp/x86/meterpreter/bind_nonx_tcp                       Fetch and execute a x86 payload from a TFTP server. Listen for a connection
    cmd/linux/tftp/x86/meterpreter/bind_tcp                            Fetch and execute a x86 payload from a TFTP server. Listen for a connection (Linux x86)
    cmd/linux/tftp/x86/meterpreter/bind_tcp_uuid                       Fetch and execute a x86 payload from a TFTP server. Listen for a connection with UUID Support (Linux x86)
    cmd/linux/tftp/x86/meterpreter/find_tag                            Fetch and execute a x86 payload from a TFTP server. Use an established connection
    cmd/linux/tftp/x86/meterpreter/reverse_ipv6_tcp                    Fetch and execute a x86 payload from a TFTP server. Connect back to attacker over IPv6
    cmd/linux/tftp/x86/meterpreter/reverse_nonx_tcp                    Fetch and execute a x86 payload from a TFTP server. Connect back to the attacker
    cmd/linux/tftp/x86/meterpreter/reverse_tcp                         Fetch and execute a x86 payload from a TFTP server. Connect back to the attacker
    cmd/linux/tftp/x86/meterpreter/reverse_tcp_uuid                    Fetch and execute a x86 payload from a TFTP server. Connect back to the attacker
    cmd/linux/tftp/x86/meterpreter_reverse_http                        Fetch and execute a x86 payload from a TFTP server.
    cmd/linux/tftp/x86/meterpreter_reverse_https                       Fetch and execute a x86 payload from a TFTP server.
    cmd/linux/tftp/x86/meterpreter_reverse_tcp                         Fetch and execute a x86 payload from a TFTP server.
    cmd/linux/tftp/x86/metsvc_bind_tcp                                 Fetch and execute a x86 payload from a TFTP server. Stub payload for interacting with a Meterpreter Service
    cmd/linux/tftp/x86/metsvc_reverse_tcp                              Fetch and execute a x86 payload from a TFTP server. Stub payload for interacting with a Meterpreter Service
    cmd/linux/tftp/x86/read_file                                       Fetch and execute a x86 payload from a TFTP server. Read up to 4096 bytes from the local file system and write it back out to the specified file descriptor
    cmd/linux/tftp/x86/shell/bind_ipv6_tcp                             Fetch and execute a x86 payload from a TFTP server. Spawn a command shell (staged). Listen for an IPv6 connection (Linux x86)
    cmd/linux/tftp/x86/shell/bind_ipv6_tcp_uuid                        Fetch and execute a x86 payload from a TFTP server. Spawn a command shell (staged). Listen for an IPv6 connection with UUID Support (Linux x86)
    cmd/linux/tftp/x86/shell/bind_nonx_tcp                             Fetch and execute a x86 payload from a TFTP server. Spawn a command shell (staged). Listen for a connection
    cmd/linux/tftp/x86/shell/bind_tcp                                  Fetch and execute a x86 payload from a TFTP server. Spawn a command shell (staged). Listen for a connection (Linux x86)
    cmd/linux/tftp/x86/shell/bind_tcp_uuid                             Fetch and execute a x86 payload from a TFTP server. Spawn a command shell (staged). Listen for a connection with UUID Support (Linux x86)
    cmd/linux/tftp/x86/shell/find_tag                                  Fetch and execute a x86 payload from a TFTP server. Spawn a command shell (staged). Use an established connection
    cmd/linux/tftp/x86/shell/reverse_ipv6_tcp                          Fetch and execute a x86 payload from a TFTP server. Spawn a command shell (staged). Connect back to attacker over IPv6
    cmd/linux/tftp/x86/shell/reverse_nonx_tcp                          Fetch and execute a x86 payload from a TFTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/tftp/x86/shell/reverse_tcp                               Fetch and execute a x86 payload from a TFTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/tftp/x86/shell/reverse_tcp_uuid                          Fetch and execute a x86 payload from a TFTP server. Spawn a command shell (staged). Connect back to the attacker
    cmd/linux/tftp/x86/shell_bind_ipv6_tcp                             Fetch and execute a x86 payload from a TFTP server. Listen for a connection over IPv6 and spawn a command shell
    cmd/linux/tftp/x86/shell_bind_tcp                                  Fetch and execute a x86 payload from a TFTP server. Listen for a connection and spawn a command shell
    cmd/linux/tftp/x86/shell_bind_tcp_random_port                      Fetch and execute a x86 payload from a TFTP server. Listen for a connection in a random port and spawn a command shell. Use nmap to discover the open port: 'nmap -
                                                                       sS target -p-'.
    cmd/linux/tftp/x86/shell_find_port                                 Fetch and execute a x86 payload from a TFTP server. Spawn a shell on an established connection
    cmd/linux/tftp/x86/shell_find_tag                                  Fetch and execute a x86 payload from a TFTP server. Spawn a shell on an established connection (proxy/nat safe)
    cmd/linux/tftp/x86/shell_reverse_tcp                               Fetch and execute a x86 payload from a TFTP server. Connect back to attacker and spawn a command shell
    cmd/linux/tftp/x86/shell_reverse_tcp_ipv6                          Fetch and execute a x86 payload from a TFTP server. Connect back to attacker and spawn a command shell over IPv6
    cmd/mainframe/apf_privesc_jcl                                      (Elevate privileges for user. Adds SYSTEM SPECIAL and BPX.SUPERUSER to user profile. Does this by using an unsecured/updateable APF authorized library (APFLIB) and
                                                                        updating the user's ACEE using this program/library. Note: This privesc only works with z/OS systems using RACF, no other ESM is supported.)
    cmd/mainframe/bind_shell_jcl                                       Provide JCL which creates a bind shell This implementation does not include ebcdic character translation, so a client with translation capabilities is required. MS
                                                                       F handles this automatically.
    cmd/mainframe/generic_jcl                                          Provide JCL which can be used to submit a job to JES2 on z/OS which will exit and return 0. This can be used as a template for other JCL based payloads
    cmd/mainframe/reverse_shell_jcl                                    Provide JCL which creates a reverse shell This implementation does not include ebcdic character translation, so a client with translation capabilities is required.
                                                                        MSF handles this automatically.
    cmd/unix/adduser                                                   Creates a new user. By default the new user is set with sudo but other options exist to make the new user automatically root but this is not automatically set sinc
                                                                       e the new user will be treated as root (and login may be difficult). The new user can also be set as just a standard user if desired.
    cmd/unix/bind_awk                                                  Listen for a connection and spawn a command shell via GNU AWK
    cmd/unix/bind_aws_instance_connect                                 Creates an SSH shell using AWS Instance Connect
    cmd/unix/bind_busybox_telnetd                                      Listen for a connection and spawn a command shell via BusyBox telnetd
    cmd/unix/bind_inetd                                                Listen for a connection and spawn a command shell (persistent)
    cmd/unix/bind_jjs                                                  Listen for a connection and spawn a command shell via jjs
    cmd/unix/bind_lua                                                  Listen for a connection and spawn a command shell via Lua
    cmd/unix/bind_netcat                                               Listen for a connection and spawn a command shell via netcat
    cmd/unix/bind_netcat_gaping                                        Listen for a connection and spawn a command shell via netcat
    cmd/unix/bind_netcat_gaping_ipv6                                   Listen for a connection and spawn a command shell via netcat
    cmd/unix/bind_nodejs                                               Continually listen for a connection and spawn a command shell via nodejs
    cmd/unix/bind_perl                                                 Listen for a connection and spawn a command shell via perl
    cmd/unix/bind_perl_ipv6                                            Listen for a connection and spawn a command shell via perl
    cmd/unix/bind_r                                                    Continually listen for a connection and spawn a command shell via R
    cmd/unix/bind_ruby                                                 Continually listen for a connection and spawn a command shell via Ruby
    cmd/unix/bind_ruby_ipv6                                            Continually listen for a connection and spawn a command shell via Ruby
    cmd/unix/bind_socat_sctp                                           Creates an interactive shell via socat
    cmd/unix/bind_socat_udp                                            Creates an interactive shell via socat
    cmd/unix/bind_stub                                                 Listen for a connection and spawn a command shell (stub only, no payload)
    cmd/unix/bind_zsh                                                  Listen for a connection and spawn a command shell via Zsh. Note: Although Zsh is often available, please be aware it isn't usually installed by default.
    cmd/unix/generic                                                   Executes the supplied command
    cmd/unix/interact                                                  Interacts with a shell on an established socket connection
    cmd/unix/pingback_bind                                             Accept a connection, send a UUID, then exit
    cmd/unix/pingback_reverse                                          Creates a socket, send a UUID, then exit
    cmd/unix/python/exec                                               Execute a Python payload from a command. Execute an arbitrary OS command. Compatible with Python 2.7 and 3.4+.
    cmd/unix/python/meterpreter/bind_tcp                               Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Listen for a connection
    cmd/unix/python/meterpreter/bind_tcp_uuid                          Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Listen for a connection with UUID Support
    cmd/unix/python/meterpreter/reverse_http                           Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Tunnel communication over HTTP
    cmd/unix/python/meterpreter/reverse_https                          Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Tunnel communication over HTTP using SSL
    cmd/unix/python/meterpreter/reverse_tcp                            Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Connect back to the attacker
    cmd/unix/python/meterpreter/reverse_tcp_ssl                        Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Reverse Python connect back stager using SSL
    cmd/unix/python/meterpreter/reverse_tcp_uuid                       Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Connect back to the attacker with UUID Support
    cmd/unix/python/meterpreter_bind_tcp                               Execute a Python payload from a command. Connect to the victim and spawn a Meterpreter shell
    cmd/unix/python/meterpreter_reverse_http                           Execute a Python payload from a command. Connect back to the attacker and spawn a Meterpreter shell
    cmd/unix/python/meterpreter_reverse_https                          Execute a Python payload from a command. Connect back to the attacker and spawn a Meterpreter shell
    cmd/unix/python/meterpreter_reverse_tcp                            Execute a Python payload from a command. Connect back to the attacker and spawn a Meterpreter shell
    cmd/unix/python/pingback_bind_tcp                                  Execute a Python payload from a command. Listens for a connection from the attacker, sends a UUID, then terminates
    cmd/unix/python/pingback_reverse_tcp                               Execute a Python payload from a command. Connects back to the attacker, sends a UUID, then terminates
    cmd/unix/python/shell_bind_tcp                                     Execute a Python payload from a command. Creates an interactive shell via Python, encodes with base64 by design. Compatible with Python 2.4-2.7 and 3.4+.
    cmd/unix/python/shell_reverse_sctp                                 Execute a Python payload from a command. Creates an interactive shell via Python, encodes with base64 by design. Compatible with Python 2.6-2.7 and 3.4+.
    cmd/unix/python/shell_reverse_tcp                                  Execute a Python payload from a command. Creates an interactive shell via Python, encodes with base64 by design. Compatible with Python 2.4-2.7 and 3.4+.
    cmd/unix/python/shell_reverse_tcp_ssl                              Execute a Python payload from a command. Creates an interactive shell via Python, uses SSL, encodes with base64 by design. Compatible with Python 2.6-2.7 and 3.4+.
    cmd/unix/python/shell_reverse_udp                                  Execute a Python payload from a command. Creates an interactive shell via Python, encodes with base64 by design. Compatible with Python 2.6-2.7 and 3.4+.
    cmd/unix/reverse                                                   Creates an interactive shell through two inbound connections
    cmd/unix/reverse_awk                                               Creates an interactive shell via GNU AWK
    cmd/unix/reverse_bash                                              Creates an interactive shell via bash's builtin /dev/tcp. This will not work on circa 2009 and older Debian-based Linux distributions (including Ubuntu) because th
                                                                       ey compile bash without the /dev/tcp feature.
    cmd/unix/reverse_bash_telnet_ssl                                   Creates an interactive shell via mkfifo and telnet. This method works on Debian and other systems compiled without /dev/tcp support. This module uses the '-z' opti
                                                                       on included on some systems to encrypt using SSL.
    cmd/unix/reverse_bash_udp                                          Creates an interactive shell via bash's builtin /dev/udp. This will not work on circa 2009 and older Debian-based Linux distributions (including Ubuntu) because th
                                                                       ey compile bash without the /dev/udp feature.
    cmd/unix/reverse_jjs                                               Connect back and create a command shell via jjs
    cmd/unix/reverse_ksh                                               Connect back and create a command shell via Ksh. Note: Although Ksh is often available, please be aware it isn't usually installed by default.
    cmd/unix/reverse_lua                                               Creates an interactive shell via Lua
    cmd/unix/reverse_ncat_ssl                                          Creates an interactive shell via ncat, utilizing ssl mode
    cmd/unix/reverse_netcat                                            Creates an interactive shell via netcat
    cmd/unix/reverse_netcat_gaping                                     Creates an interactive shell via netcat
    cmd/unix/reverse_nodejs                                            Continually listen for a connection and spawn a command shell via nodejs
    cmd/unix/reverse_openssl                                           Creates an interactive shell through two inbound connections
    cmd/unix/reverse_perl                                              Creates an interactive shell via perl
    cmd/unix/reverse_perl_ssl                                          Creates an interactive shell via perl, uses SSL
    cmd/unix/reverse_php_ssl                                           Creates an interactive shell via php, uses SSL
    cmd/unix/reverse_python                                            Connect back and create a command shell via Python
    cmd/unix/reverse_python_ssl                                        Creates an interactive shell via python, uses SSL, encodes with base64 by design.
    cmd/unix/reverse_r                                                 Connect back and create a command shell via R
    cmd/unix/reverse_ruby                                              Connect back and create a command shell via Ruby
    cmd/unix/reverse_ruby_ssl                                          Connect back and create a command shell via Ruby, uses SSL
    cmd/unix/reverse_socat_sctp                                        Creates an interactive shell via socat
    cmd/unix/reverse_socat_tcp                                         Creates an interactive shell via socat
    cmd/unix/reverse_socat_udp                                         Creates an interactive shell via socat
    cmd/unix/reverse_ssh                                               Connect back and create a command shell via SSH
    cmd/unix/reverse_ssl_double_telnet                                 Creates an interactive shell through two inbound connections, encrypts using SSL via "-z" option
    cmd/unix/reverse_stub                                              Creates an interactive shell through an inbound connection (stub only, no payload)
    cmd/unix/reverse_tclsh                                             Creates an interactive shell via Tclsh
    cmd/unix/reverse_zsh                                               Connect back and create a command shell via Zsh. Note: Although Zsh is often available, please be aware it isn't usually installed by default.
    cmd/windows/adduser                                                Create a new user and add them to local administration group. Note: The specified password is checked for common complexity requirements to prevent the target mach
                                                                       ine rejecting the user for failing to meet policy requirements. Complexity check: 8-14 chars (1 UPPER, 1 lower, 1 digit/special)
    cmd/windows/bind_lua                                               Listen for a connection and spawn a command shell via Lua
    cmd/windows/bind_perl                                              Listen for a connection and spawn a command shell via perl (persistent)
    cmd/windows/bind_perl_ipv6                                         Listen for a connection and spawn a command shell via perl (persistent)
    cmd/windows/bind_ruby                                              Continually listen for a connection and spawn a command shell via Ruby
    cmd/windows/download_eval_vbs                                      Downloads a file from an HTTP(S) URL and executes it as a vbs script. Use it to stage a vbs encoded payload from a short command line.
    cmd/windows/download_exec_vbs                                      Download an EXE from an HTTP(S) URL and execute it
    cmd/windows/generic                                                Executes the supplied command
    cmd/windows/http/x64/custom/bind_ipv6_tcp                          Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Listen for an IPv6 connection (Windows x64)
    cmd/windows/http/x64/custom/bind_ipv6_tcp_uuid                     Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/http/x64/custom/bind_named_pipe                        Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Listen for a pipe connection (Windows x64)
    cmd/windows/http/x64/custom/bind_tcp                               Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Listen for a connection (Windows x64)
    cmd/windows/http/x64/custom/bind_tcp_rc4                           Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Connect back to the attacker
    cmd/windows/http/x64/custom/bind_tcp_uuid                          Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/http/x64/custom/reverse_http                           Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/http/x64/custom/reverse_https                          Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/http/x64/custom/reverse_named_pipe                     Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Connect back to the attacker via a named pipe pivot
    cmd/windows/http/x64/custom/reverse_tcp                            Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Connect back to the attacker (Windows x64)
    cmd/windows/http/x64/custom/reverse_tcp_rc4                        Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Connect back to the attacker
    cmd/windows/http/x64/custom/reverse_tcp_uuid                       Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/http/x64/custom/reverse_winhttp                        Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/http/x64/custom/reverse_winhttps                       Fetch and execute an x64 payload from an HTTP server. Custom shellcode stage. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/http/x64/encrypted_shell/reverse_tcp                   Fetch and execute an x64 payload from an HTTP server. Spawn a piped command shell (staged). Connect to MSF and read in stage
    cmd/windows/http/x64/encrypted_shell_reverse_tcp                   Fetch and execute an x64 payload from an HTTP server. Connect back to attacker and spawn an encrypted command shell
    cmd/windows/http/x64/exec                                          Fetch and execute an x64 payload from an HTTP server. Execute an arbitrary command (Windows x64)
    cmd/windows/http/x64/loadlibrary                                   Fetch and execute an x64 payload from an HTTP server. Load an arbitrary x64 library path
    cmd/windows/http/x64/messagebox                                    Fetch and execute an x64 payload from an HTTP server. Spawn a dialog via MessageBox using a customizable title, text & icon
    cmd/windows/http/x64/meterpreter/bind_ipv6_tcp                     Fetch and execute an x64 payload from an HTTP server. Listen for an IPv6 connection (Windows x64)
    cmd/windows/http/x64/meterpreter/bind_ipv6_tcp_uuid                Fetch and execute an x64 payload from an HTTP server. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/http/x64/meterpreter/bind_named_pipe                   Fetch and execute an x64 payload from an HTTP server. Listen for a pipe connection (Windows x64)
    cmd/windows/http/x64/meterpreter/bind_tcp                          Fetch and execute an x64 payload from an HTTP server. Listen for a connection (Windows x64)
    cmd/windows/http/x64/meterpreter/bind_tcp_rc4                      Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker
    cmd/windows/http/x64/meterpreter/bind_tcp_uuid                     Fetch and execute an x64 payload from an HTTP server. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/http/x64/meterpreter/reverse_http                      Fetch and execute an x64 payload from an HTTP server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/http/x64/meterpreter/reverse_https                     Fetch and execute an x64 payload from an HTTP server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/http/x64/meterpreter/reverse_named_pipe                Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker via a named pipe pivot
    cmd/windows/http/x64/meterpreter/reverse_tcp                       Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker (Windows x64)
    cmd/windows/http/x64/meterpreter/reverse_tcp_rc4                   Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker
    cmd/windows/http/x64/meterpreter/reverse_tcp_uuid                  Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/http/x64/meterpreter/reverse_winhttp                   Fetch and execute an x64 payload from an HTTP server. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/http/x64/meterpreter/reverse_winhttps                  Fetch and execute an x64 payload from an HTTP server. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/http/x64/meterpreter_bind_named_pipe                   Fetch and execute an x64 payload from an HTTP server. Connect to victim and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/http/x64/meterpreter_bind_tcp                          Fetch and execute an x64 payload from an HTTP server. Connect to victim and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/http/x64/meterpreter_reverse_http                      Fetch and execute an x64 payload from an HTTP server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/http/x64/meterpreter_reverse_https                     Fetch and execute an x64 payload from an HTTP server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/http/x64/meterpreter_reverse_ipv6_tcp                  Fetch and execute an x64 payload from an HTTP server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/http/x64/meterpreter_reverse_tcp                       Fetch and execute an x64 payload from an HTTP server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/http/x64/peinject/bind_ipv6_tcp                        Fetch and execute an x64 payload from an HTTP server. Listen for an IPv6 connection (Windows x64)
    cmd/windows/http/x64/peinject/bind_ipv6_tcp_uuid                   Fetch and execute an x64 payload from an HTTP server. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/http/x64/peinject/bind_named_pipe                      Fetch and execute an x64 payload from an HTTP server. Listen for a pipe connection (Windows x64)
    cmd/windows/http/x64/peinject/bind_tcp                             Fetch and execute an x64 payload from an HTTP server. Listen for a connection (Windows x64)
    cmd/windows/http/x64/peinject/bind_tcp_rc4                         Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker
    cmd/windows/http/x64/peinject/bind_tcp_uuid                        Fetch and execute an x64 payload from an HTTP server. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/http/x64/peinject/reverse_named_pipe                   Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker via a named pipe pivot
    cmd/windows/http/x64/peinject/reverse_tcp                          Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker (Windows x64)
    cmd/windows/http/x64/peinject/reverse_tcp_rc4                      Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker
    cmd/windows/http/x64/peinject/reverse_tcp_uuid                     Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/http/x64/pingback_reverse_tcp                          Fetch and execute an x64 payload from an HTTP server. Connect back to attacker and report UUID (Windows x64)
    cmd/windows/http/x64/powershell_bind_tcp                           Fetch and execute an x64 payload from an HTTP server.
    cmd/windows/http/x64/powershell_reverse_tcp                        Fetch and execute an x64 payload from an HTTP server.
    cmd/windows/http/x64/powershell_reverse_tcp_ssl                    Fetch and execute an x64 payload from an HTTP server.
    cmd/windows/http/x64/shell/bind_ipv6_tcp                           Fetch and execute an x64 payload from an HTTP server. Spawn a piped command shell (Windows x64) (staged). Listen for an IPv6 connection (Windows x64)
    cmd/windows/http/x64/shell/bind_ipv6_tcp_uuid                      Fetch and execute an x64 payload from an HTTP server. Spawn a piped command shell (Windows x64) (staged). Listen for an IPv6 connection with UUID Support (Windows
                                                                       x64)
    cmd/windows/http/x64/shell/bind_named_pipe                         Fetch and execute an x64 payload from an HTTP server. Spawn a piped command shell (Windows x64) (staged). Listen for a pipe connection (Windows x64)
    cmd/windows/http/x64/shell/bind_tcp                                Fetch and execute an x64 payload from an HTTP server. Spawn a piped command shell (Windows x64) (staged). Listen for a connection (Windows x64)
    cmd/windows/http/x64/shell/bind_tcp_rc4                            Fetch and execute an x64 payload from an HTTP server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker
    cmd/windows/http/x64/shell/bind_tcp_uuid                           Fetch and execute an x64 payload from an HTTP server. Spawn a piped command shell (Windows x64) (staged). Listen for a connection with UUID Support (Windows x64)
    cmd/windows/http/x64/shell/reverse_tcp                             Fetch and execute an x64 payload from an HTTP server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker (Windows x64)
    cmd/windows/http/x64/shell/reverse_tcp_rc4                         Fetch and execute an x64 payload from an HTTP server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker
    cmd/windows/http/x64/shell/reverse_tcp_uuid                        Fetch and execute an x64 payload from an HTTP server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker with UUID Support (Windows x
                                                                       64)
    cmd/windows/http/x64/shell_bind_tcp                                Fetch and execute an x64 payload from an HTTP server. Listen for a connection and spawn a command shell (Windows x64)
    cmd/windows/http/x64/shell_reverse_tcp                             Fetch and execute an x64 payload from an HTTP server. Connect back to attacker and spawn a command shell (Windows x64)
    cmd/windows/http/x64/vncinject/bind_ipv6_tcp                       Fetch and execute an x64 payload from an HTTP server. Listen for an IPv6 connection (Windows x64)
    cmd/windows/http/x64/vncinject/bind_ipv6_tcp_uuid                  Fetch and execute an x64 payload from an HTTP server. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/http/x64/vncinject/bind_named_pipe                     Fetch and execute an x64 payload from an HTTP server. Listen for a pipe connection (Windows x64)
    cmd/windows/http/x64/vncinject/bind_tcp                            Fetch and execute an x64 payload from an HTTP server. Listen for a connection (Windows x64)
    cmd/windows/http/x64/vncinject/bind_tcp_rc4                        Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker
    cmd/windows/http/x64/vncinject/bind_tcp_uuid                       Fetch and execute an x64 payload from an HTTP server. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/http/x64/vncinject/reverse_http                        Fetch and execute an x64 payload from an HTTP server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/http/x64/vncinject/reverse_https                       Fetch and execute an x64 payload from an HTTP server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/http/x64/vncinject/reverse_tcp                         Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker (Windows x64)
    cmd/windows/http/x64/vncinject/reverse_tcp_rc4                     Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker
    cmd/windows/http/x64/vncinject/reverse_tcp_uuid                    Fetch and execute an x64 payload from an HTTP server. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/http/x64/vncinject/reverse_winhttp                     Fetch and execute an x64 payload from an HTTP server. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/http/x64/vncinject/reverse_winhttps                    Fetch and execute an x64 payload from an HTTP server. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/https/x64/custom/bind_ipv6_tcp                         Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Listen for an IPv6 connection (Windows x64)
    cmd/windows/https/x64/custom/bind_ipv6_tcp_uuid                    Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/https/x64/custom/bind_named_pipe                       Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Listen for a pipe connection (Windows x64)
    cmd/windows/https/x64/custom/bind_tcp                              Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Listen for a connection (Windows x64)
    cmd/windows/https/x64/custom/bind_tcp_rc4                          Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Connect back to the attacker
    cmd/windows/https/x64/custom/bind_tcp_uuid                         Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/https/x64/custom/reverse_http                          Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/https/x64/custom/reverse_https                         Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/https/x64/custom/reverse_named_pipe                    Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Connect back to the attacker via a named pipe pivot
    cmd/windows/https/x64/custom/reverse_tcp                           Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Connect back to the attacker (Windows x64)
    cmd/windows/https/x64/custom/reverse_tcp_rc4                       Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Connect back to the attacker
    cmd/windows/https/x64/custom/reverse_tcp_uuid                      Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/https/x64/custom/reverse_winhttp                       Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/https/x64/custom/reverse_winhttps                      Fetch and execute an x64 payload from an HTTPS server. Custom shellcode stage. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/https/x64/encrypted_shell/reverse_tcp                  Fetch and execute an x64 payload from an HTTPS server. Spawn a piped command shell (staged). Connect to MSF and read in stage
    cmd/windows/https/x64/encrypted_shell_reverse_tcp                  Fetch and execute an x64 payload from an HTTPS server. Connect back to attacker and spawn an encrypted command shell
    cmd/windows/https/x64/exec                                         Fetch and execute an x64 payload from an HTTPS server. Execute an arbitrary command (Windows x64)
    cmd/windows/https/x64/loadlibrary                                  Fetch and execute an x64 payload from an HTTPS server. Load an arbitrary x64 library path
    cmd/windows/https/x64/messagebox                                   Fetch and execute an x64 payload from an HTTPS server. Spawn a dialog via MessageBox using a customizable title, text & icon
    cmd/windows/https/x64/meterpreter/bind_ipv6_tcp                    Fetch and execute an x64 payload from an HTTPS server. Listen for an IPv6 connection (Windows x64)
    cmd/windows/https/x64/meterpreter/bind_ipv6_tcp_uuid               Fetch and execute an x64 payload from an HTTPS server. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/https/x64/meterpreter/bind_named_pipe                  Fetch and execute an x64 payload from an HTTPS server. Listen for a pipe connection (Windows x64)
    cmd/windows/https/x64/meterpreter/bind_tcp                         Fetch and execute an x64 payload from an HTTPS server. Listen for a connection (Windows x64)
    cmd/windows/https/x64/meterpreter/bind_tcp_rc4                     Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker
    cmd/windows/https/x64/meterpreter/bind_tcp_uuid                    Fetch and execute an x64 payload from an HTTPS server. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/https/x64/meterpreter/reverse_http                     Fetch and execute an x64 payload from an HTTPS server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/https/x64/meterpreter/reverse_https                    Fetch and execute an x64 payload from an HTTPS server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/https/x64/meterpreter/reverse_named_pipe               Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker via a named pipe pivot
    cmd/windows/https/x64/meterpreter/reverse_tcp                      Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker (Windows x64)
    cmd/windows/https/x64/meterpreter/reverse_tcp_rc4                  Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker
    cmd/windows/https/x64/meterpreter/reverse_tcp_uuid                 Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/https/x64/meterpreter/reverse_winhttp                  Fetch and execute an x64 payload from an HTTPS server. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/https/x64/meterpreter/reverse_winhttps                 Fetch and execute an x64 payload from an HTTPS server. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/https/x64/meterpreter_bind_named_pipe                  Fetch and execute an x64 payload from an HTTPS server. Connect to victim and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/https/x64/meterpreter_bind_tcp                         Fetch and execute an x64 payload from an HTTPS server. Connect to victim and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/https/x64/meterpreter_reverse_http                     Fetch and execute an x64 payload from an HTTPS server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/https/x64/meterpreter_reverse_https                    Fetch and execute an x64 payload from an HTTPS server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/https/x64/meterpreter_reverse_ipv6_tcp                 Fetch and execute an x64 payload from an HTTPS server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/https/x64/meterpreter_reverse_tcp                      Fetch and execute an x64 payload from an HTTPS server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/https/x64/peinject/bind_ipv6_tcp                       Fetch and execute an x64 payload from an HTTPS server. Listen for an IPv6 connection (Windows x64)
    cmd/windows/https/x64/peinject/bind_ipv6_tcp_uuid                  Fetch and execute an x64 payload from an HTTPS server. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/https/x64/peinject/bind_named_pipe                     Fetch and execute an x64 payload from an HTTPS server. Listen for a pipe connection (Windows x64)
    cmd/windows/https/x64/peinject/bind_tcp                            Fetch and execute an x64 payload from an HTTPS server. Listen for a connection (Windows x64)
    cmd/windows/https/x64/peinject/bind_tcp_rc4                        Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker
    cmd/windows/https/x64/peinject/bind_tcp_uuid                       Fetch and execute an x64 payload from an HTTPS server. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/https/x64/peinject/reverse_named_pipe                  Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker via a named pipe pivot
    cmd/windows/https/x64/peinject/reverse_tcp                         Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker (Windows x64)
    cmd/windows/https/x64/peinject/reverse_tcp_rc4                     Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker
    cmd/windows/https/x64/peinject/reverse_tcp_uuid                    Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/https/x64/pingback_reverse_tcp                         Fetch and execute an x64 payload from an HTTPS server. Connect back to attacker and report UUID (Windows x64)
    cmd/windows/https/x64/powershell_bind_tcp                          Fetch and execute an x64 payload from an HTTPS server.
    cmd/windows/https/x64/powershell_reverse_tcp                       Fetch and execute an x64 payload from an HTTPS server.
    cmd/windows/https/x64/powershell_reverse_tcp_ssl                   Fetch and execute an x64 payload from an HTTPS server.
    cmd/windows/https/x64/shell/bind_ipv6_tcp                          Fetch and execute an x64 payload from an HTTPS server. Spawn a piped command shell (Windows x64) (staged). Listen for an IPv6 connection (Windows x64)
    cmd/windows/https/x64/shell/bind_ipv6_tcp_uuid                     Fetch and execute an x64 payload from an HTTPS server. Spawn a piped command shell (Windows x64) (staged). Listen for an IPv6 connection with UUID Support (Windows
                                                                        x64)
    cmd/windows/https/x64/shell/bind_named_pipe                        Fetch and execute an x64 payload from an HTTPS server. Spawn a piped command shell (Windows x64) (staged). Listen for a pipe connection (Windows x64)
    cmd/windows/https/x64/shell/bind_tcp                               Fetch and execute an x64 payload from an HTTPS server. Spawn a piped command shell (Windows x64) (staged). Listen for a connection (Windows x64)
    cmd/windows/https/x64/shell/bind_tcp_rc4                           Fetch and execute an x64 payload from an HTTPS server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker
    cmd/windows/https/x64/shell/bind_tcp_uuid                          Fetch and execute an x64 payload from an HTTPS server. Spawn a piped command shell (Windows x64) (staged). Listen for a connection with UUID Support (Windows x64)
    cmd/windows/https/x64/shell/reverse_tcp                            Fetch and execute an x64 payload from an HTTPS server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker (Windows x64)
    cmd/windows/https/x64/shell/reverse_tcp_rc4                        Fetch and execute an x64 payload from an HTTPS server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker
    cmd/windows/https/x64/shell/reverse_tcp_uuid                       Fetch and execute an x64 payload from an HTTPS server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker with UUID Support (Windows
                                                                       x64)
    cmd/windows/https/x64/shell_bind_tcp                               Fetch and execute an x64 payload from an HTTPS server. Listen for a connection and spawn a command shell (Windows x64)
    cmd/windows/https/x64/shell_reverse_tcp                            Fetch and execute an x64 payload from an HTTPS server. Connect back to attacker and spawn a command shell (Windows x64)
    cmd/windows/https/x64/vncinject/bind_ipv6_tcp                      Fetch and execute an x64 payload from an HTTPS server. Listen for an IPv6 connection (Windows x64)
    cmd/windows/https/x64/vncinject/bind_ipv6_tcp_uuid                 Fetch and execute an x64 payload from an HTTPS server. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/https/x64/vncinject/bind_named_pipe                    Fetch and execute an x64 payload from an HTTPS server. Listen for a pipe connection (Windows x64)
    cmd/windows/https/x64/vncinject/bind_tcp                           Fetch and execute an x64 payload from an HTTPS server. Listen for a connection (Windows x64)
    cmd/windows/https/x64/vncinject/bind_tcp_rc4                       Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker
    cmd/windows/https/x64/vncinject/bind_tcp_uuid                      Fetch and execute an x64 payload from an HTTPS server. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/https/x64/vncinject/reverse_http                       Fetch and execute an x64 payload from an HTTPS server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/https/x64/vncinject/reverse_https                      Fetch and execute an x64 payload from an HTTPS server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/https/x64/vncinject/reverse_tcp                        Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker (Windows x64)
    cmd/windows/https/x64/vncinject/reverse_tcp_rc4                    Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker
    cmd/windows/https/x64/vncinject/reverse_tcp_uuid                   Fetch and execute an x64 payload from an HTTPS server. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/https/x64/vncinject/reverse_winhttp                    Fetch and execute an x64 payload from an HTTPS server. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/https/x64/vncinject/reverse_winhttps                   Fetch and execute an x64 payload from an HTTPS server. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/jjs_reverse_tcp                                        Connect back and create a command shell via jjs
    cmd/windows/powershell/adduser                                     Execute an x86 payload from a command via PowerShell
    cmd/windows/powershell/custom/bind_hidden_ipknock_tcp              Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Listen for a connection. First, the port will need to be knocked from the IP defined
                                                                       in KHOST. This IP will work as an authentication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket w
                                                                       ill appear as "closed," thus helping to hide the shellcode
    cmd/windows/powershell/custom/bind_hidden_tcp                      Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Listen for a connection from a hidden port and spawn a command shell to the allowed h
                                                                       ost.
    cmd/windows/powershell/custom/bind_ipv6_tcp                        Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Listen for an IPv6 connection (Windows x86)
    cmd/windows/powershell/custom/bind_ipv6_tcp_uuid                   Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Listen for an IPv6 connection with UUID Support (Windows x86)
    cmd/windows/powershell/custom/bind_named_pipe                      Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Listen for a pipe connection (Windows x86)
    cmd/windows/powershell/custom/bind_nonx_tcp                        Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Listen for a connection (No NX)
    cmd/windows/powershell/custom/bind_tcp                             Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Listen for a connection (Windows x86)
    cmd/windows/powershell/custom/bind_tcp_rc4                         Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Listen for a connection
    cmd/windows/powershell/custom/bind_tcp_uuid                        Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Listen for a connection with UUID Support (Windows x86)
    cmd/windows/powershell/custom/find_tag                             Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Use an established connection
    cmd/windows/powershell/custom/reverse_http                         Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Tunnel communication over HTTP (Windows wininet)
    cmd/windows/powershell/custom/reverse_http_proxy_pstore            Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Tunnel communication over HTTP
    cmd/windows/powershell/custom/reverse_https                        Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Tunnel communication over HTTPS (Windows wininet)
    cmd/windows/powershell/custom/reverse_ipv6_tcp                     Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker over IPv6
    cmd/windows/powershell/custom/reverse_named_pipe                   Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker via a named pipe pivot
    cmd/windows/powershell/custom/reverse_nonx_tcp                     Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker (No NX)
    cmd/windows/powershell/custom/reverse_ord_tcp                      Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker
    cmd/windows/powershell/custom/reverse_tcp                          Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker
    cmd/windows/powershell/custom/reverse_tcp_allports                 Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    cmd/windows/powershell/custom/reverse_tcp_dns                      Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker
    cmd/windows/powershell/custom/reverse_tcp_rc4                      Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker
    cmd/windows/powershell/custom/reverse_tcp_rc4_dns                  Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker
    cmd/windows/powershell/custom/reverse_tcp_uuid                     Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker with UUID Support
    cmd/windows/powershell/custom/reverse_udp                          Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker with UUID Support
    cmd/windows/powershell/custom/reverse_winhttp                      Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Tunnel communication over HTTP (Windows winhttp)
    cmd/windows/powershell/custom/reverse_winhttps                     Execute an x86 payload from a command via PowerShell. Custom shellcode stage. Tunnel communication over HTTPS (Windows winhttp)
    cmd/windows/powershell/dllinject/bind_hidden_ipknock_tcp           Execute an x86 payload from a command via PowerShell. Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will w
                                                                       ork as an authentication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed,"
                                                                       thus helping to hide the shellcode
    cmd/windows/powershell/dllinject/bind_hidden_tcp                   Execute an x86 payload from a command via PowerShell. Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    cmd/windows/powershell/dllinject/bind_ipv6_tcp                     Execute an x86 payload from a command via PowerShell. Listen for an IPv6 connection (Windows x86)
    cmd/windows/powershell/dllinject/bind_ipv6_tcp_uuid                Execute an x86 payload from a command via PowerShell. Listen for an IPv6 connection with UUID Support (Windows x86)
    cmd/windows/powershell/dllinject/bind_named_pipe                   Execute an x86 payload from a command via PowerShell. Listen for a pipe connection (Windows x86)
    cmd/windows/powershell/dllinject/bind_nonx_tcp                     Execute an x86 payload from a command via PowerShell. Listen for a connection (No NX)
    cmd/windows/powershell/dllinject/bind_tcp                          Execute an x86 payload from a command via PowerShell. Listen for a connection (Windows x86)
    cmd/windows/powershell/dllinject/bind_tcp_rc4                      Execute an x86 payload from a command via PowerShell. Listen for a connection
    cmd/windows/powershell/dllinject/bind_tcp_uuid                     Execute an x86 payload from a command via PowerShell. Listen for a connection with UUID Support (Windows x86)
    cmd/windows/powershell/dllinject/find_tag                          Execute an x86 payload from a command via PowerShell. Use an established connection
    cmd/windows/powershell/dllinject/reverse_http                      Execute an x86 payload from a command via PowerShell. Tunnel communication over HTTP (Windows wininet)
    cmd/windows/powershell/dllinject/reverse_http_proxy_pstore         Execute an x86 payload from a command via PowerShell. Tunnel communication over HTTP
    cmd/windows/powershell/dllinject/reverse_ipv6_tcp                  Execute an x86 payload from a command via PowerShell. Connect back to the attacker over IPv6
    cmd/windows/powershell/dllinject/reverse_nonx_tcp                  Execute an x86 payload from a command via PowerShell. Connect back to the attacker (No NX)
    cmd/windows/powershell/dllinject/reverse_ord_tcp                   Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/dllinject/reverse_tcp                       Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/dllinject/reverse_tcp_allports              Execute an x86 payload from a command via PowerShell. Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    cmd/windows/powershell/dllinject/reverse_tcp_dns                   Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/dllinject/reverse_tcp_rc4                   Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/dllinject/reverse_tcp_rc4_dns               Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/dllinject/reverse_tcp_uuid                  Execute an x86 payload from a command via PowerShell. Connect back to the attacker with UUID Support
    cmd/windows/powershell/dllinject/reverse_winhttp                   Execute an x86 payload from a command via PowerShell. Tunnel communication over HTTP (Windows winhttp)
    cmd/windows/powershell/dns_txt_query_exec                          Execute an x86 payload from a command via PowerShell. Performs a TXT query against a series of DNS record(s) and executes the returned x86 shellcode. The DNSZONE o
                                                                       ption is used as the base name to iterate over. The payload will first request the TXT contents of the a hostname, followed by b, then c, etc. until there are no m
                                                                       ore records. For each record that is returned, exactly 255 bytes from it are copied into a buffer that is eventually executed. This buffer should be encoded using
                                                                       x86/alpha_mixed with the BufferRegister option set to EDI.
    cmd/windows/powershell/download_exec                               Execute an x86 payload from a command via PowerShell. Download an EXE from an HTTP(S)/FTP URL and execute it
    cmd/windows/powershell/encrypted_shell/reverse_tcp                 Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Connect to MSF and read in stage
    cmd/windows/powershell/exec                                        Execute an x86 payload from a command via PowerShell
    cmd/windows/powershell/format_all_drives                           Execute an x86 payload from a command via PowerShell
    cmd/windows/powershell/generic/debug_trap                          Execute an x86 payload from a command via PowerShell. Generate a debug trap in the target process
    cmd/windows/powershell/generic/tight_loop                          Execute an x86 payload from a command via PowerShell. Generate a tight loop in the target process
    cmd/windows/powershell/loadlibrary                                 Execute an x86 payload from a command via PowerShell
    cmd/windows/powershell/messagebox                                  Execute an x86 payload from a command via PowerShell. Spawns a dialog via MessageBox using a customizable title, text & icon
    cmd/windows/powershell/meterpreter/bind_hidden_ipknock_tcp         Execute an x86 payload from a command via PowerShell. Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will w
                                                                       ork as an authentication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed,"
                                                                       thus helping to hide the shellcode
    cmd/windows/powershell/meterpreter/bind_hidden_tcp                 Execute an x86 payload from a command via PowerShell. Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    cmd/windows/powershell/meterpreter/bind_ipv6_tcp                   Execute an x86 payload from a command via PowerShell. Listen for an IPv6 connection (Windows x86)
    cmd/windows/powershell/meterpreter/bind_ipv6_tcp_uuid              Execute an x86 payload from a command via PowerShell. Listen for an IPv6 connection with UUID Support (Windows x86)
    cmd/windows/powershell/meterpreter/bind_named_pipe                 Execute an x86 payload from a command via PowerShell. Listen for a pipe connection (Windows x86)
    cmd/windows/powershell/meterpreter/bind_nonx_tcp                   Execute an x86 payload from a command via PowerShell. Listen for a connection (No NX)
    cmd/windows/powershell/meterpreter/bind_tcp                        Execute an x86 payload from a command via PowerShell. Listen for a connection (Windows x86)
    cmd/windows/powershell/meterpreter/bind_tcp_rc4                    Execute an x86 payload from a command via PowerShell. Listen for a connection
    cmd/windows/powershell/meterpreter/bind_tcp_uuid                   Execute an x86 payload from a command via PowerShell. Listen for a connection with UUID Support (Windows x86)
    cmd/windows/powershell/meterpreter/find_tag                        Execute an x86 payload from a command via PowerShell. Use an established connection
    cmd/windows/powershell/meterpreter/reverse_http                    Execute an x86 payload from a command via PowerShell. Tunnel communication over HTTP (Windows wininet)
    cmd/windows/powershell/meterpreter/reverse_http_proxy_pstore       Execute an x86 payload from a command via PowerShell. Tunnel communication over HTTP
    cmd/windows/powershell/meterpreter/reverse_https                   Execute an x86 payload from a command via PowerShell. Tunnel communication over HTTPS (Windows wininet)
    cmd/windows/powershell/meterpreter/reverse_ipv6_tcp                Execute an x86 payload from a command via PowerShell. Connect back to the attacker over IPv6
    cmd/windows/powershell/meterpreter/reverse_named_pipe              Execute an x86 payload from a command via PowerShell. Connect back to the attacker via a named pipe pivot
    cmd/windows/powershell/meterpreter/reverse_nonx_tcp                Execute an x86 payload from a command via PowerShell. Connect back to the attacker (No NX)
    cmd/windows/powershell/meterpreter/reverse_ord_tcp                 Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/meterpreter/reverse_tcp                     Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/meterpreter/reverse_tcp_allports            Execute an x86 payload from a command via PowerShell. Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    cmd/windows/powershell/meterpreter/reverse_tcp_dns                 Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/meterpreter/reverse_tcp_rc4                 Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/meterpreter/reverse_tcp_rc4_dns             Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/meterpreter/reverse_tcp_uuid                Execute an x86 payload from a command via PowerShell. Connect back to the attacker with UUID Support
    cmd/windows/powershell/meterpreter/reverse_winhttp                 Execute an x86 payload from a command via PowerShell. Tunnel communication over HTTP (Windows winhttp)
    cmd/windows/powershell/meterpreter/reverse_winhttps                Execute an x86 payload from a command via PowerShell. Tunnel communication over HTTPS (Windows winhttp)
    cmd/windows/powershell/metsvc_bind_tcp                             Execute an x86 payload from a command via PowerShell. Stub payload for interacting with a Meterpreter Service
    cmd/windows/powershell/metsvc_reverse_tcp                          Execute an x86 payload from a command via PowerShell. Stub payload for interacting with a Meterpreter Service
    cmd/windows/powershell/patchupdllinject/bind_hidden_ipknock_tcp    Execute an x86 payload from a command via PowerShell. Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will w
                                                                       ork as an authentication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed,"
                                                                       thus helping to hide the shellcode
    cmd/windows/powershell/patchupdllinject/bind_hidden_tcp            Execute an x86 payload from a command via PowerShell. Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    cmd/windows/powershell/patchupdllinject/bind_ipv6_tcp              Execute an x86 payload from a command via PowerShell. Listen for an IPv6 connection (Windows x86)
    cmd/windows/powershell/patchupdllinject/bind_ipv6_tcp_uuid         Execute an x86 payload from a command via PowerShell. Listen for an IPv6 connection with UUID Support (Windows x86)
    cmd/windows/powershell/patchupdllinject/bind_named_pipe            Execute an x86 payload from a command via PowerShell. Listen for a pipe connection (Windows x86)
    cmd/windows/powershell/patchupdllinject/bind_nonx_tcp              Execute an x86 payload from a command via PowerShell. Listen for a connection (No NX)
    cmd/windows/powershell/patchupdllinject/bind_tcp                   Execute an x86 payload from a command via PowerShell. Listen for a connection (Windows x86)
    cmd/windows/powershell/patchupdllinject/bind_tcp_rc4               Execute an x86 payload from a command via PowerShell. Listen for a connection
    cmd/windows/powershell/patchupdllinject/bind_tcp_uuid              Execute an x86 payload from a command via PowerShell. Listen for a connection with UUID Support (Windows x86)
    cmd/windows/powershell/patchupdllinject/find_tag                   Execute an x86 payload from a command via PowerShell. Use an established connection
    cmd/windows/powershell/patchupdllinject/reverse_ipv6_tcp           Execute an x86 payload from a command via PowerShell. Connect back to the attacker over IPv6
    cmd/windows/powershell/patchupdllinject/reverse_nonx_tcp           Execute an x86 payload from a command via PowerShell. Connect back to the attacker (No NX)
    cmd/windows/powershell/patchupdllinject/reverse_ord_tcp            Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/patchupdllinject/reverse_tcp                Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/patchupdllinject/reverse_tcp_allports       Execute an x86 payload from a command via PowerShell. Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    cmd/windows/powershell/patchupdllinject/reverse_tcp_dns            Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/patchupdllinject/reverse_tcp_rc4            Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/patchupdllinject/reverse_tcp_rc4_dns        Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/patchupdllinject/reverse_tcp_uuid           Execute an x86 payload from a command via PowerShell. Connect back to the attacker with UUID Support
    cmd/windows/powershell/patchupmeterpreter/bind_hidden_ipknock_tcp  Execute an x86 payload from a command via PowerShell. Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will w
                                                                       ork as an authentication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed,"
                                                                       thus helping to hide the shellcode
    cmd/windows/powershell/patchupmeterpreter/bind_hidden_tcp          Execute an x86 payload from a command via PowerShell. Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    cmd/windows/powershell/patchupmeterpreter/bind_ipv6_tcp            Execute an x86 payload from a command via PowerShell. Listen for an IPv6 connection (Windows x86)
    cmd/windows/powershell/patchupmeterpreter/bind_ipv6_tcp_uuid       Execute an x86 payload from a command via PowerShell. Listen for an IPv6 connection with UUID Support (Windows x86)
    cmd/windows/powershell/patchupmeterpreter/bind_named_pipe          Execute an x86 payload from a command via PowerShell. Listen for a pipe connection (Windows x86)
    cmd/windows/powershell/patchupmeterpreter/bind_nonx_tcp            Execute an x86 payload from a command via PowerShell. Listen for a connection (No NX)
    cmd/windows/powershell/patchupmeterpreter/bind_tcp                 Execute an x86 payload from a command via PowerShell. Listen for a connection (Windows x86)
    cmd/windows/powershell/patchupmeterpreter/bind_tcp_rc4             Execute an x86 payload from a command via PowerShell. Listen for a connection
    cmd/windows/powershell/patchupmeterpreter/bind_tcp_uuid            Execute an x86 payload from a command via PowerShell. Listen for a connection with UUID Support (Windows x86)
    cmd/windows/powershell/patchupmeterpreter/find_tag                 Execute an x86 payload from a command via PowerShell. Use an established connection
    cmd/windows/powershell/patchupmeterpreter/reverse_ipv6_tcp         Execute an x86 payload from a command via PowerShell. Connect back to the attacker over IPv6
    cmd/windows/powershell/patchupmeterpreter/reverse_nonx_tcp         Execute an x86 payload from a command via PowerShell. Connect back to the attacker (No NX)
    cmd/windows/powershell/patchupmeterpreter/reverse_ord_tcp          Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/patchupmeterpreter/reverse_tcp              Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/patchupmeterpreter/reverse_tcp_allports     Execute an x86 payload from a command via PowerShell. Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    cmd/windows/powershell/patchupmeterpreter/reverse_tcp_dns          Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/patchupmeterpreter/reverse_tcp_rc4          Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/patchupmeterpreter/reverse_tcp_rc4_dns      Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/patchupmeterpreter/reverse_tcp_uuid         Execute an x86 payload from a command via PowerShell. Connect back to the attacker with UUID Support
    cmd/windows/powershell/peinject/bind_hidden_ipknock_tcp            Execute an x86 payload from a command via PowerShell. Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will w
                                                                       ork as an authentication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed,"
                                                                       thus helping to hide the shellcode
    cmd/windows/powershell/peinject/bind_hidden_tcp                    Execute an x86 payload from a command via PowerShell. Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    cmd/windows/powershell/peinject/bind_ipv6_tcp                      Execute an x86 payload from a command via PowerShell. Listen for an IPv6 connection (Windows x86)
    cmd/windows/powershell/peinject/bind_ipv6_tcp_uuid                 Execute an x86 payload from a command via PowerShell. Listen for an IPv6 connection with UUID Support (Windows x86)
    cmd/windows/powershell/peinject/bind_named_pipe                    Execute an x86 payload from a command via PowerShell. Listen for a pipe connection (Windows x86)
    cmd/windows/powershell/peinject/bind_nonx_tcp                      Execute an x86 payload from a command via PowerShell. Listen for a connection (No NX)
    cmd/windows/powershell/peinject/bind_tcp                           Execute an x86 payload from a command via PowerShell. Listen for a connection (Windows x86)
    cmd/windows/powershell/peinject/bind_tcp_rc4                       Execute an x86 payload from a command via PowerShell. Listen for a connection
    cmd/windows/powershell/peinject/bind_tcp_uuid                      Execute an x86 payload from a command via PowerShell. Listen for a connection with UUID Support (Windows x86)
    cmd/windows/powershell/peinject/find_tag                           Execute an x86 payload from a command via PowerShell. Use an established connection
    cmd/windows/powershell/peinject/reverse_ipv6_tcp                   Execute an x86 payload from a command via PowerShell. Connect back to the attacker over IPv6
    cmd/windows/powershell/peinject/reverse_named_pipe                 Execute an x86 payload from a command via PowerShell. Connect back to the attacker via a named pipe pivot
    cmd/windows/powershell/peinject/reverse_nonx_tcp                   Execute an x86 payload from a command via PowerShell. Connect back to the attacker (No NX)
    cmd/windows/powershell/peinject/reverse_ord_tcp                    Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/peinject/reverse_tcp                        Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/peinject/reverse_tcp_allports               Execute an x86 payload from a command via PowerShell. Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    cmd/windows/powershell/peinject/reverse_tcp_dns                    Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/peinject/reverse_tcp_rc4                    Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/peinject/reverse_tcp_rc4_dns                Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/peinject/reverse_tcp_uuid                   Execute an x86 payload from a command via PowerShell. Connect back to the attacker with UUID Support
    cmd/windows/powershell/pingback_bind_tcp                           Execute an x86 payload from a command via PowerShell. Open a socket and report UUID when a connection is received (Windows x86)
    cmd/windows/powershell/pingback_reverse_tcp                        Execute an x86 payload from a command via PowerShell. Connect back to attacker and report UUID (Windows x86)
    cmd/windows/powershell/powershell_bind_tcp                         Execute an x86 payload from a command via PowerShell
    cmd/windows/powershell/powershell_reverse_tcp                      Execute an x86 payload from a command via PowerShell
    cmd/windows/powershell/powershell_reverse_tcp_ssl                  Execute an x86 payload from a command via PowerShell
    cmd/windows/powershell/shell/bind_hidden_ipknock_tcp               Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Listen for a connection. First, the port will need to be knocked from t
                                                                       he IP defined in KHOST. This IP will work as an authentication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP
                                                                       . The socket will appear as "closed," thus helping to hide the shellcode
    cmd/windows/powershell/shell/bind_hidden_tcp                       Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Listen for a connection from a hidden port and spawn a command shell to
                                                                        the allowed host.
    cmd/windows/powershell/shell/bind_ipv6_tcp                         Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Listen for an IPv6 connection (Windows x86)
    cmd/windows/powershell/shell/bind_ipv6_tcp_uuid                    Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Listen for an IPv6 connection with UUID Support (Windows x86)
    cmd/windows/powershell/shell/bind_named_pipe                       Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Listen for a pipe connection (Windows x86)
    cmd/windows/powershell/shell/bind_nonx_tcp                         Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Listen for a connection (No NX)
    cmd/windows/powershell/shell/bind_tcp                              Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Listen for a connection (Windows x86)
    cmd/windows/powershell/shell/bind_tcp_rc4                          Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Listen for a connection
    cmd/windows/powershell/shell/bind_tcp_uuid                         Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Listen for a connection with UUID Support (Windows x86)
    cmd/windows/powershell/shell/find_tag                              Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Use an established connection
    cmd/windows/powershell/shell/reverse_ipv6_tcp                      Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Connect back to the attacker over IPv6
    cmd/windows/powershell/shell/reverse_nonx_tcp                      Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Connect back to the attacker (No NX)
    cmd/windows/powershell/shell/reverse_ord_tcp                       Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Connect back to the attacker
    cmd/windows/powershell/shell/reverse_tcp                           Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Connect back to the attacker
    cmd/windows/powershell/shell/reverse_tcp_allports                  Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Try to connect back to the attacker, on all possible ports (1-65535, sl
                                                                       owly)
    cmd/windows/powershell/shell/reverse_tcp_dns                       Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Connect back to the attacker
    cmd/windows/powershell/shell/reverse_tcp_rc4                       Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Connect back to the attacker
    cmd/windows/powershell/shell/reverse_tcp_rc4_dns                   Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Connect back to the attacker
    cmd/windows/powershell/shell/reverse_tcp_uuid                      Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Connect back to the attacker with UUID Support
    cmd/windows/powershell/shell/reverse_udp                           Execute an x86 payload from a command via PowerShell. Spawn a piped command shell (staged). Connect back to the attacker with UUID Support
    cmd/windows/powershell/shell_bind_tcp                              Execute an x86 payload from a command via PowerShell. Listen for a connection and spawn a command shell
    cmd/windows/powershell/shell_bind_tcp_xpfw                         Execute an x86 payload from a command via PowerShell. Disable the Windows ICF, then listen for a connection and spawn a command shell
    cmd/windows/powershell/shell_hidden_bind_tcp                       Execute an x86 payload from a command via PowerShell. Listen for a connection from certain IP and spawn a command shell. The shellcode will reply with a RST packet
                                                                        if the connections is not coming from the IP defined in AHOST. This way the port will appear as "closed" helping us to hide the shellcode.
    cmd/windows/powershell/shell_reverse_tcp                           Execute an x86 payload from a command via PowerShell. Connect back to attacker and spawn a command shell
    cmd/windows/powershell/speak_pwned                                 Execute an x86 payload from a command via PowerShell
    cmd/windows/powershell/upexec/bind_hidden_ipknock_tcp              Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Listen for a connection. First, the port will need to be knocked
                                                                       from the IP defined in KHOST. This IP will work as an authentication method (you can spoof it with tools like hping). After that you could get your shellcode from
                                                                       any IP. The socket will appear as "closed," thus helping to hide the shellcode
    cmd/windows/powershell/upexec/bind_hidden_tcp                      Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Listen for a connection from a hidden port and spawn a command sh
                                                                       ell to the allowed host.
    cmd/windows/powershell/upexec/bind_ipv6_tcp                        Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Listen for an IPv6 connection (Windows x86)
    cmd/windows/powershell/upexec/bind_ipv6_tcp_uuid                   Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Listen for an IPv6 connection with UUID Support (Windows x86)
    cmd/windows/powershell/upexec/bind_named_pipe                      Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Listen for a pipe connection (Windows x86)
    cmd/windows/powershell/upexec/bind_nonx_tcp                        Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Listen for a connection (No NX)
    cmd/windows/powershell/upexec/bind_tcp                             Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Listen for a connection (Windows x86)
    cmd/windows/powershell/upexec/bind_tcp_rc4                         Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Listen for a connection
    cmd/windows/powershell/upexec/bind_tcp_uuid                        Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Listen for a connection with UUID Support (Windows x86)
    cmd/windows/powershell/upexec/find_tag                             Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Use an established connection
    cmd/windows/powershell/upexec/reverse_ipv6_tcp                     Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Connect back to the attacker over IPv6
    cmd/windows/powershell/upexec/reverse_nonx_tcp                     Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Connect back to the attacker (No NX)
    cmd/windows/powershell/upexec/reverse_ord_tcp                      Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Connect back to the attacker
    cmd/windows/powershell/upexec/reverse_tcp                          Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Connect back to the attacker
    cmd/windows/powershell/upexec/reverse_tcp_allports                 Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Try to connect back to the attacker, on all possible ports (1-655
                                                                       35, slowly)
    cmd/windows/powershell/upexec/reverse_tcp_dns                      Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Connect back to the attacker
    cmd/windows/powershell/upexec/reverse_tcp_rc4                      Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Connect back to the attacker
    cmd/windows/powershell/upexec/reverse_tcp_rc4_dns                  Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Connect back to the attacker
    cmd/windows/powershell/upexec/reverse_tcp_uuid                     Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Connect back to the attacker with UUID Support
    cmd/windows/powershell/upexec/reverse_udp                          Execute an x86 payload from a command via PowerShell. Uploads an executable and runs it (staged). Connect back to the attacker with UUID Support
    cmd/windows/powershell/vncinject/bind_hidden_ipknock_tcp           Execute an x86 payload from a command via PowerShell. Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will w
                                                                       ork as an authentication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed,"
                                                                       thus helping to hide the shellcode
    cmd/windows/powershell/vncinject/bind_hidden_tcp                   Execute an x86 payload from a command via PowerShell. Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    cmd/windows/powershell/vncinject/bind_ipv6_tcp                     Execute an x86 payload from a command via PowerShell. Listen for an IPv6 connection (Windows x86)
    cmd/windows/powershell/vncinject/bind_ipv6_tcp_uuid                Execute an x86 payload from a command via PowerShell. Listen for an IPv6 connection with UUID Support (Windows x86)
    cmd/windows/powershell/vncinject/bind_named_pipe                   Execute an x86 payload from a command via PowerShell. Listen for a pipe connection (Windows x86)
    cmd/windows/powershell/vncinject/bind_nonx_tcp                     Execute an x86 payload from a command via PowerShell. Listen for a connection (No NX)
    cmd/windows/powershell/vncinject/bind_tcp                          Execute an x86 payload from a command via PowerShell. Listen for a connection (Windows x86)
    cmd/windows/powershell/vncinject/bind_tcp_rc4                      Execute an x86 payload from a command via PowerShell. Listen for a connection
    cmd/windows/powershell/vncinject/bind_tcp_uuid                     Execute an x86 payload from a command via PowerShell. Listen for a connection with UUID Support (Windows x86)
    cmd/windows/powershell/vncinject/find_tag                          Execute an x86 payload from a command via PowerShell. Use an established connection
    cmd/windows/powershell/vncinject/reverse_http                      Execute an x86 payload from a command via PowerShell. Tunnel communication over HTTP (Windows wininet)
    cmd/windows/powershell/vncinject/reverse_http_proxy_pstore         Execute an x86 payload from a command via PowerShell. Tunnel communication over HTTP
    cmd/windows/powershell/vncinject/reverse_ipv6_tcp                  Execute an x86 payload from a command via PowerShell. Connect back to the attacker over IPv6
    cmd/windows/powershell/vncinject/reverse_nonx_tcp                  Execute an x86 payload from a command via PowerShell. Connect back to the attacker (No NX)
    cmd/windows/powershell/vncinject/reverse_ord_tcp                   Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/vncinject/reverse_tcp                       Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/vncinject/reverse_tcp_allports              Execute an x86 payload from a command via PowerShell. Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    cmd/windows/powershell/vncinject/reverse_tcp_dns                   Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/vncinject/reverse_tcp_rc4                   Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/vncinject/reverse_tcp_rc4_dns               Execute an x86 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/vncinject/reverse_tcp_uuid                  Execute an x86 payload from a command via PowerShell. Connect back to the attacker with UUID Support
    cmd/windows/powershell/vncinject/reverse_winhttp                   Execute an x86 payload from a command via PowerShell. Tunnel communication over HTTP (Windows winhttp)
    cmd/windows/powershell/x64/custom/bind_ipv6_tcp                    Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Listen for an IPv6 connection (Windows x64)
    cmd/windows/powershell/x64/custom/bind_ipv6_tcp_uuid               Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/powershell/x64/custom/bind_named_pipe                  Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Listen for a pipe connection (Windows x64)
    cmd/windows/powershell/x64/custom/bind_tcp                         Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Listen for a connection (Windows x64)
    cmd/windows/powershell/x64/custom/bind_tcp_rc4                     Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker
    cmd/windows/powershell/x64/custom/bind_tcp_uuid                    Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/powershell/x64/custom/reverse_http                     Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/powershell/x64/custom/reverse_https                    Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/powershell/x64/custom/reverse_named_pipe               Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker via a named pipe pivot
    cmd/windows/powershell/x64/custom/reverse_tcp                      Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker (Windows x64)
    cmd/windows/powershell/x64/custom/reverse_tcp_rc4                  Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker
    cmd/windows/powershell/x64/custom/reverse_tcp_uuid                 Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/powershell/x64/custom/reverse_winhttp                  Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/powershell/x64/custom/reverse_winhttps                 Execute an x64 payload from a command via PowerShell. Custom shellcode stage. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/powershell/x64/encrypted_shell/reverse_tcp             Execute an x64 payload from a command via PowerShell. Spawn a piped command shell (staged). Connect to MSF and read in stage
    cmd/windows/powershell/x64/exec                                    Execute an x64 payload from a command via PowerShell. Execute an arbitrary command (Windows x64)
    cmd/windows/powershell/x64/loadlibrary                             Execute an x64 payload from a command via PowerShell. Load an arbitrary x64 library path
    cmd/windows/powershell/x64/messagebox                              Execute an x64 payload from a command via PowerShell. Spawn a dialog via MessageBox using a customizable title, text & icon
    cmd/windows/powershell/x64/meterpreter/bind_ipv6_tcp               Execute an x64 payload from a command via PowerShell. Listen for an IPv6 connection (Windows x64)
    cmd/windows/powershell/x64/meterpreter/bind_ipv6_tcp_uuid          Execute an x64 payload from a command via PowerShell. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/powershell/x64/meterpreter/bind_named_pipe             Execute an x64 payload from a command via PowerShell. Listen for a pipe connection (Windows x64)
    cmd/windows/powershell/x64/meterpreter/bind_tcp                    Execute an x64 payload from a command via PowerShell. Listen for a connection (Windows x64)
    cmd/windows/powershell/x64/meterpreter/bind_tcp_rc4                Execute an x64 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/x64/meterpreter/bind_tcp_uuid               Execute an x64 payload from a command via PowerShell. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/powershell/x64/meterpreter/reverse_http                Execute an x64 payload from a command via PowerShell. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/powershell/x64/meterpreter/reverse_https               Execute an x64 payload from a command via PowerShell. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/powershell/x64/meterpreter/reverse_named_pipe          Execute an x64 payload from a command via PowerShell. Connect back to the attacker via a named pipe pivot
    cmd/windows/powershell/x64/meterpreter/reverse_tcp                 Execute an x64 payload from a command via PowerShell. Connect back to the attacker (Windows x64)
    cmd/windows/powershell/x64/meterpreter/reverse_tcp_rc4             Execute an x64 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/x64/meterpreter/reverse_tcp_uuid            Execute an x64 payload from a command via PowerShell. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/powershell/x64/meterpreter/reverse_winhttp             Execute an x64 payload from a command via PowerShell. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/powershell/x64/meterpreter/reverse_winhttps            Execute an x64 payload from a command via PowerShell. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/powershell/x64/peinject/bind_ipv6_tcp                  Execute an x64 payload from a command via PowerShell. Listen for an IPv6 connection (Windows x64)
    cmd/windows/powershell/x64/peinject/bind_ipv6_tcp_uuid             Execute an x64 payload from a command via PowerShell. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/powershell/x64/peinject/bind_named_pipe                Execute an x64 payload from a command via PowerShell. Listen for a pipe connection (Windows x64)
    cmd/windows/powershell/x64/peinject/bind_tcp                       Execute an x64 payload from a command via PowerShell. Listen for a connection (Windows x64)
    cmd/windows/powershell/x64/peinject/bind_tcp_rc4                   Execute an x64 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/x64/peinject/bind_tcp_uuid                  Execute an x64 payload from a command via PowerShell. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/powershell/x64/peinject/reverse_named_pipe             Execute an x64 payload from a command via PowerShell. Connect back to the attacker via a named pipe pivot
    cmd/windows/powershell/x64/peinject/reverse_tcp                    Execute an x64 payload from a command via PowerShell. Connect back to the attacker (Windows x64)
    cmd/windows/powershell/x64/peinject/reverse_tcp_rc4                Execute an x64 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/x64/peinject/reverse_tcp_uuid               Execute an x64 payload from a command via PowerShell. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/powershell/x64/pingback_reverse_tcp                    Execute an x64 payload from a command via PowerShell. Connect back to attacker and report UUID (Windows x64)
    cmd/windows/powershell/x64/powershell_bind_tcp                     Execute an x64 payload from a command via PowerShell
    cmd/windows/powershell/x64/powershell_reverse_tcp                  Execute an x64 payload from a command via PowerShell
    cmd/windows/powershell/x64/powershell_reverse_tcp_ssl              Execute an x64 payload from a command via PowerShell
    cmd/windows/powershell/x64/shell/bind_ipv6_tcp                     Execute an x64 payload from a command via PowerShell. Spawn a piped command shell (Windows x64) (staged). Listen for an IPv6 connection (Windows x64)
    cmd/windows/powershell/x64/shell/bind_ipv6_tcp_uuid                Execute an x64 payload from a command via PowerShell. Spawn a piped command shell (Windows x64) (staged). Listen for an IPv6 connection with UUID Support (Windows
                                                                       x64)
    cmd/windows/powershell/x64/shell/bind_named_pipe                   Execute an x64 payload from a command via PowerShell. Spawn a piped command shell (Windows x64) (staged). Listen for a pipe connection (Windows x64)
    cmd/windows/powershell/x64/shell/bind_tcp                          Execute an x64 payload from a command via PowerShell. Spawn a piped command shell (Windows x64) (staged). Listen for a connection (Windows x64)
    cmd/windows/powershell/x64/shell/bind_tcp_rc4                      Execute an x64 payload from a command via PowerShell. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker
    cmd/windows/powershell/x64/shell/bind_tcp_uuid                     Execute an x64 payload from a command via PowerShell. Spawn a piped command shell (Windows x64) (staged). Listen for a connection with UUID Support (Windows x64)
    cmd/windows/powershell/x64/shell/reverse_tcp                       Execute an x64 payload from a command via PowerShell. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker (Windows x64)
    cmd/windows/powershell/x64/shell/reverse_tcp_rc4                   Execute an x64 payload from a command via PowerShell. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker
    cmd/windows/powershell/x64/shell/reverse_tcp_uuid                  Execute an x64 payload from a command via PowerShell. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker with UUID Support (Windows x
                                                                       64)
    cmd/windows/powershell/x64/shell_bind_tcp                          Execute an x64 payload from a command via PowerShell. Listen for a connection and spawn a command shell (Windows x64)
    cmd/windows/powershell/x64/shell_reverse_tcp                       Execute an x64 payload from a command via PowerShell. Connect back to attacker and spawn a command shell (Windows x64)
    cmd/windows/powershell/x64/vncinject/bind_ipv6_tcp                 Execute an x64 payload from a command via PowerShell. Listen for an IPv6 connection (Windows x64)
    cmd/windows/powershell/x64/vncinject/bind_ipv6_tcp_uuid            Execute an x64 payload from a command via PowerShell. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/powershell/x64/vncinject/bind_named_pipe               Execute an x64 payload from a command via PowerShell. Listen for a pipe connection (Windows x64)
    cmd/windows/powershell/x64/vncinject/bind_tcp                      Execute an x64 payload from a command via PowerShell. Listen for a connection (Windows x64)
    cmd/windows/powershell/x64/vncinject/bind_tcp_rc4                  Execute an x64 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/x64/vncinject/bind_tcp_uuid                 Execute an x64 payload from a command via PowerShell. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/powershell/x64/vncinject/reverse_http                  Execute an x64 payload from a command via PowerShell. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/powershell/x64/vncinject/reverse_https                 Execute an x64 payload from a command via PowerShell. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/powershell/x64/vncinject/reverse_tcp                   Execute an x64 payload from a command via PowerShell. Connect back to the attacker (Windows x64)
    cmd/windows/powershell/x64/vncinject/reverse_tcp_rc4               Execute an x64 payload from a command via PowerShell. Connect back to the attacker
    cmd/windows/powershell/x64/vncinject/reverse_tcp_uuid              Execute an x64 payload from a command via PowerShell. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/powershell/x64/vncinject/reverse_winhttp               Execute an x64 payload from a command via PowerShell. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/powershell/x64/vncinject/reverse_winhttps              Execute an x64 payload from a command via PowerShell. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/powershell_bind_tcp                                    Interacts with a powershell session on an established socket connection
    cmd/windows/powershell_reverse_tcp                                 Interacts with a powershell session on an established socket connection
    cmd/windows/powershell_reverse_tcp_ssl                             Interacts with a powershell session on an established SSL socket connection
    cmd/windows/python/exec                                            Execute a Python payload from a command. Execute an arbitrary OS command. Compatible with Python 2.7 and 3.4+.
    cmd/windows/python/meterpreter/bind_tcp                            Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Listen for a connection
    cmd/windows/python/meterpreter/bind_tcp_uuid                       Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Listen for a connection with UUID Support
    cmd/windows/python/meterpreter/reverse_http                        Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Tunnel communication over HTTP
    cmd/windows/python/meterpreter/reverse_https                       Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Tunnel communication over HTTP using SSL
    cmd/windows/python/meterpreter/reverse_tcp                         Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Connect back to the attacker
    cmd/windows/python/meterpreter/reverse_tcp_ssl                     Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Reverse Python connect back stager using SSL
    cmd/windows/python/meterpreter/reverse_tcp_uuid                    Execute a Python payload from a command. Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Connect back to the attacker with UUID Support
    cmd/windows/python/meterpreter_bind_tcp                            Execute a Python payload from a command. Connect to the victim and spawn a Meterpreter shell
    cmd/windows/python/meterpreter_reverse_http                        Execute a Python payload from a command. Connect back to the attacker and spawn a Meterpreter shell
    cmd/windows/python/meterpreter_reverse_https                       Execute a Python payload from a command. Connect back to the attacker and spawn a Meterpreter shell
    cmd/windows/python/meterpreter_reverse_tcp                         Execute a Python payload from a command. Connect back to the attacker and spawn a Meterpreter shell
    cmd/windows/python/pingback_bind_tcp                               Execute a Python payload from a command. Listens for a connection from the attacker, sends a UUID, then terminates
    cmd/windows/python/pingback_reverse_tcp                            Execute a Python payload from a command. Connects back to the attacker, sends a UUID, then terminates
    cmd/windows/python/shell_bind_tcp                                  Execute a Python payload from a command. Creates an interactive shell via Python, encodes with base64 by design. Compatible with Python 2.4-2.7 and 3.4+.
    cmd/windows/python/shell_reverse_sctp                              Execute a Python payload from a command. Creates an interactive shell via Python, encodes with base64 by design. Compatible with Python 2.6-2.7 and 3.4+.
    cmd/windows/python/shell_reverse_tcp                               Execute a Python payload from a command. Creates an interactive shell via Python, encodes with base64 by design. Compatible with Python 2.4-2.7 and 3.4+.
    cmd/windows/python/shell_reverse_tcp_ssl                           Execute a Python payload from a command. Creates an interactive shell via Python, uses SSL, encodes with base64 by design. Compatible with Python 2.6-2.7 and 3.4+.
    cmd/windows/python/shell_reverse_udp                               Execute a Python payload from a command. Creates an interactive shell via Python, encodes with base64 by design. Compatible with Python 2.6-2.7 and 3.4+.
    cmd/windows/reverse_lua                                            Creates an interactive shell via Lua
    cmd/windows/reverse_perl                                           Creates an interactive shell via perl
    cmd/windows/reverse_powershell                                     Connect back and create a command shell via Powershell
    cmd/windows/reverse_ruby                                           Connect back and create a command shell via Ruby
    cmd/windows/smb/x64/custom/bind_ipv6_tcp                           Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Listen for an IPv6 connection (Windows x64)
    cmd/windows/smb/x64/custom/bind_ipv6_tcp_uuid                      Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/smb/x64/custom/bind_named_pipe                         Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Listen for a pipe connection (Windows x64)
    cmd/windows/smb/x64/custom/bind_tcp                                Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Listen for a connection (Windows x64)
    cmd/windows/smb/x64/custom/bind_tcp_rc4                            Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Connect back to the attacker
    cmd/windows/smb/x64/custom/bind_tcp_uuid                           Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/smb/x64/custom/reverse_http                            Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/smb/x64/custom/reverse_https                           Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/smb/x64/custom/reverse_named_pipe                      Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Connect back to the attacker via a named pipe pivot
    cmd/windows/smb/x64/custom/reverse_tcp                             Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Connect back to the attacker (Windows x64)
    cmd/windows/smb/x64/custom/reverse_tcp_rc4                         Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Connect back to the attacker
    cmd/windows/smb/x64/custom/reverse_tcp_uuid                        Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/smb/x64/custom/reverse_winhttp                         Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/smb/x64/custom/reverse_winhttps                        Fetch and execute an x64 payload from an SMB server. Custom shellcode stage. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/smb/x64/encrypted_shell/reverse_tcp                    Fetch and execute an x64 payload from an SMB server. Spawn a piped command shell (staged). Connect to MSF and read in stage
    cmd/windows/smb/x64/encrypted_shell_reverse_tcp                    Fetch and execute an x64 payload from an SMB server. Connect back to attacker and spawn an encrypted command shell
    cmd/windows/smb/x64/exec                                           Fetch and execute an x64 payload from an SMB server. Execute an arbitrary command (Windows x64)
    cmd/windows/smb/x64/loadlibrary                                    Fetch and execute an x64 payload from an SMB server. Load an arbitrary x64 library path
    cmd/windows/smb/x64/messagebox                                     Fetch and execute an x64 payload from an SMB server. Spawn a dialog via MessageBox using a customizable title, text & icon
    cmd/windows/smb/x64/meterpreter/bind_ipv6_tcp                      Fetch and execute an x64 payload from an SMB server. Listen for an IPv6 connection (Windows x64)
    cmd/windows/smb/x64/meterpreter/bind_ipv6_tcp_uuid                 Fetch and execute an x64 payload from an SMB server. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/smb/x64/meterpreter/bind_named_pipe                    Fetch and execute an x64 payload from an SMB server. Listen for a pipe connection (Windows x64)
    cmd/windows/smb/x64/meterpreter/bind_tcp                           Fetch and execute an x64 payload from an SMB server. Listen for a connection (Windows x64)
    cmd/windows/smb/x64/meterpreter/bind_tcp_rc4                       Fetch and execute an x64 payload from an SMB server. Connect back to the attacker
    cmd/windows/smb/x64/meterpreter/bind_tcp_uuid                      Fetch and execute an x64 payload from an SMB server. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/smb/x64/meterpreter/reverse_http                       Fetch and execute an x64 payload from an SMB server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/smb/x64/meterpreter/reverse_https                      Fetch and execute an x64 payload from an SMB server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/smb/x64/meterpreter/reverse_named_pipe                 Fetch and execute an x64 payload from an SMB server. Connect back to the attacker via a named pipe pivot
    cmd/windows/smb/x64/meterpreter/reverse_tcp                        Fetch and execute an x64 payload from an SMB server. Connect back to the attacker (Windows x64)
    cmd/windows/smb/x64/meterpreter/reverse_tcp_rc4                    Fetch and execute an x64 payload from an SMB server. Connect back to the attacker
    cmd/windows/smb/x64/meterpreter/reverse_tcp_uuid                   Fetch and execute an x64 payload from an SMB server. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/smb/x64/meterpreter/reverse_winhttp                    Fetch and execute an x64 payload from an SMB server. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/smb/x64/meterpreter/reverse_winhttps                   Fetch and execute an x64 payload from an SMB server. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/smb/x64/meterpreter_bind_named_pipe                    Fetch and execute an x64 payload from an SMB server. Connect to victim and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/smb/x64/meterpreter_bind_tcp                           Fetch and execute an x64 payload from an SMB server. Connect to victim and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/smb/x64/meterpreter_reverse_http                       Fetch and execute an x64 payload from an SMB server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/smb/x64/meterpreter_reverse_https                      Fetch and execute an x64 payload from an SMB server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/smb/x64/meterpreter_reverse_ipv6_tcp                   Fetch and execute an x64 payload from an SMB server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/smb/x64/meterpreter_reverse_tcp                        Fetch and execute an x64 payload from an SMB server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/smb/x64/peinject/bind_ipv6_tcp                         Fetch and execute an x64 payload from an SMB server. Listen for an IPv6 connection (Windows x64)
    cmd/windows/smb/x64/peinject/bind_ipv6_tcp_uuid                    Fetch and execute an x64 payload from an SMB server. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/smb/x64/peinject/bind_named_pipe                       Fetch and execute an x64 payload from an SMB server. Listen for a pipe connection (Windows x64)
    cmd/windows/smb/x64/peinject/bind_tcp                              Fetch and execute an x64 payload from an SMB server. Listen for a connection (Windows x64)
    cmd/windows/smb/x64/peinject/bind_tcp_rc4                          Fetch and execute an x64 payload from an SMB server. Connect back to the attacker
    cmd/windows/smb/x64/peinject/bind_tcp_uuid                         Fetch and execute an x64 payload from an SMB server. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/smb/x64/peinject/reverse_named_pipe                    Fetch and execute an x64 payload from an SMB server. Connect back to the attacker via a named pipe pivot
    cmd/windows/smb/x64/peinject/reverse_tcp                           Fetch and execute an x64 payload from an SMB server. Connect back to the attacker (Windows x64)
    cmd/windows/smb/x64/peinject/reverse_tcp_rc4                       Fetch and execute an x64 payload from an SMB server. Connect back to the attacker
    cmd/windows/smb/x64/peinject/reverse_tcp_uuid                      Fetch and execute an x64 payload from an SMB server. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/smb/x64/pingback_reverse_tcp                           Fetch and execute an x64 payload from an SMB server. Connect back to attacker and report UUID (Windows x64)
    cmd/windows/smb/x64/powershell_bind_tcp                            Fetch and execute an x64 payload from an SMB server.
    cmd/windows/smb/x64/powershell_reverse_tcp                         Fetch and execute an x64 payload from an SMB server.
    cmd/windows/smb/x64/powershell_reverse_tcp_ssl                     Fetch and execute an x64 payload from an SMB server.
    cmd/windows/smb/x64/shell/bind_ipv6_tcp                            Fetch and execute an x64 payload from an SMB server. Spawn a piped command shell (Windows x64) (staged). Listen for an IPv6 connection (Windows x64)
    cmd/windows/smb/x64/shell/bind_ipv6_tcp_uuid                       Fetch and execute an x64 payload from an SMB server. Spawn a piped command shell (Windows x64) (staged). Listen for an IPv6 connection with UUID Support (Windows x
                                                                       64)
    cmd/windows/smb/x64/shell/bind_named_pipe                          Fetch and execute an x64 payload from an SMB server. Spawn a piped command shell (Windows x64) (staged). Listen for a pipe connection (Windows x64)
    cmd/windows/smb/x64/shell/bind_tcp                                 Fetch and execute an x64 payload from an SMB server. Spawn a piped command shell (Windows x64) (staged). Listen for a connection (Windows x64)
    cmd/windows/smb/x64/shell/bind_tcp_rc4                             Fetch and execute an x64 payload from an SMB server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker
    cmd/windows/smb/x64/shell/bind_tcp_uuid                            Fetch and execute an x64 payload from an SMB server. Spawn a piped command shell (Windows x64) (staged). Listen for a connection with UUID Support (Windows x64)
    cmd/windows/smb/x64/shell/reverse_tcp                              Fetch and execute an x64 payload from an SMB server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker (Windows x64)
    cmd/windows/smb/x64/shell/reverse_tcp_rc4                          Fetch and execute an x64 payload from an SMB server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker
    cmd/windows/smb/x64/shell/reverse_tcp_uuid                         Fetch and execute an x64 payload from an SMB server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker with UUID Support (Windows x6
                                                                       4)
    cmd/windows/smb/x64/shell_bind_tcp                                 Fetch and execute an x64 payload from an SMB server. Listen for a connection and spawn a command shell (Windows x64)
    cmd/windows/smb/x64/shell_reverse_tcp                              Fetch and execute an x64 payload from an SMB server. Connect back to attacker and spawn a command shell (Windows x64)
    cmd/windows/smb/x64/vncinject/bind_ipv6_tcp                        Fetch and execute an x64 payload from an SMB server. Listen for an IPv6 connection (Windows x64)
    cmd/windows/smb/x64/vncinject/bind_ipv6_tcp_uuid                   Fetch and execute an x64 payload from an SMB server. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/smb/x64/vncinject/bind_named_pipe                      Fetch and execute an x64 payload from an SMB server. Listen for a pipe connection (Windows x64)
    cmd/windows/smb/x64/vncinject/bind_tcp                             Fetch and execute an x64 payload from an SMB server. Listen for a connection (Windows x64)
    cmd/windows/smb/x64/vncinject/bind_tcp_rc4                         Fetch and execute an x64 payload from an SMB server. Connect back to the attacker
    cmd/windows/smb/x64/vncinject/bind_tcp_uuid                        Fetch and execute an x64 payload from an SMB server. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/smb/x64/vncinject/reverse_http                         Fetch and execute an x64 payload from an SMB server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/smb/x64/vncinject/reverse_https                        Fetch and execute an x64 payload from an SMB server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/smb/x64/vncinject/reverse_tcp                          Fetch and execute an x64 payload from an SMB server. Connect back to the attacker (Windows x64)
    cmd/windows/smb/x64/vncinject/reverse_tcp_rc4                      Fetch and execute an x64 payload from an SMB server. Connect back to the attacker
    cmd/windows/smb/x64/vncinject/reverse_tcp_uuid                     Fetch and execute an x64 payload from an SMB server. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/smb/x64/vncinject/reverse_winhttp                      Fetch and execute an x64 payload from an SMB server. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/smb/x64/vncinject/reverse_winhttps                     Fetch and execute an x64 payload from an SMB server. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/tftp/x64/custom/bind_ipv6_tcp                          Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Listen for an IPv6 connection (Windows x64)
    cmd/windows/tftp/x64/custom/bind_ipv6_tcp_uuid                     Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/tftp/x64/custom/bind_named_pipe                        Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Listen for a pipe connection (Windows x64)
    cmd/windows/tftp/x64/custom/bind_tcp                               Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Listen for a connection (Windows x64)
    cmd/windows/tftp/x64/custom/bind_tcp_rc4                           Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Connect back to the attacker
    cmd/windows/tftp/x64/custom/bind_tcp_uuid                          Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/tftp/x64/custom/reverse_http                           Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/tftp/x64/custom/reverse_https                          Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/tftp/x64/custom/reverse_named_pipe                     Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Connect back to the attacker via a named pipe pivot
    cmd/windows/tftp/x64/custom/reverse_tcp                            Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Connect back to the attacker (Windows x64)
    cmd/windows/tftp/x64/custom/reverse_tcp_rc4                        Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Connect back to the attacker
    cmd/windows/tftp/x64/custom/reverse_tcp_uuid                       Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/tftp/x64/custom/reverse_winhttp                        Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/tftp/x64/custom/reverse_winhttps                       Fetch and execute an x64 payload from a TFTP server. Custom shellcode stage. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/tftp/x64/encrypted_shell/reverse_tcp                   Fetch and execute an x64 payload from a TFTP server. Spawn a piped command shell (staged). Connect to MSF and read in stage
    cmd/windows/tftp/x64/encrypted_shell_reverse_tcp                   Fetch and execute an x64 payload from a TFTP server. Connect back to attacker and spawn an encrypted command shell
    cmd/windows/tftp/x64/exec                                          Fetch and execute an x64 payload from a TFTP server. Execute an arbitrary command (Windows x64)
    cmd/windows/tftp/x64/loadlibrary                                   Fetch and execute an x64 payload from a TFTP server. Load an arbitrary x64 library path
    cmd/windows/tftp/x64/messagebox                                    Fetch and execute an x64 payload from a TFTP server. Spawn a dialog via MessageBox using a customizable title, text & icon
    cmd/windows/tftp/x64/meterpreter/bind_ipv6_tcp                     Fetch and execute an x64 payload from a TFTP server. Listen for an IPv6 connection (Windows x64)
    cmd/windows/tftp/x64/meterpreter/bind_ipv6_tcp_uuid                Fetch and execute an x64 payload from a TFTP server. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/tftp/x64/meterpreter/bind_named_pipe                   Fetch and execute an x64 payload from a TFTP server. Listen for a pipe connection (Windows x64)
    cmd/windows/tftp/x64/meterpreter/bind_tcp                          Fetch and execute an x64 payload from a TFTP server. Listen for a connection (Windows x64)
    cmd/windows/tftp/x64/meterpreter/bind_tcp_rc4                      Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker
    cmd/windows/tftp/x64/meterpreter/bind_tcp_uuid                     Fetch and execute an x64 payload from a TFTP server. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/tftp/x64/meterpreter/reverse_http                      Fetch and execute an x64 payload from a TFTP server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/tftp/x64/meterpreter/reverse_https                     Fetch and execute an x64 payload from a TFTP server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/tftp/x64/meterpreter/reverse_named_pipe                Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker via a named pipe pivot
    cmd/windows/tftp/x64/meterpreter/reverse_tcp                       Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker (Windows x64)
    cmd/windows/tftp/x64/meterpreter/reverse_tcp_rc4                   Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker
    cmd/windows/tftp/x64/meterpreter/reverse_tcp_uuid                  Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/tftp/x64/meterpreter/reverse_winhttp                   Fetch and execute an x64 payload from a TFTP server. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/tftp/x64/meterpreter/reverse_winhttps                  Fetch and execute an x64 payload from a TFTP server. Tunnel communication over HTTPS (Windows x64 winhttp)
    cmd/windows/tftp/x64/meterpreter_bind_named_pipe                   Fetch and execute an x64 payload from a TFTP server. Connect to victim and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/tftp/x64/meterpreter_bind_tcp                          Fetch and execute an x64 payload from a TFTP server. Connect to victim and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/tftp/x64/meterpreter_reverse_http                      Fetch and execute an x64 payload from a TFTP server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/tftp/x64/meterpreter_reverse_https                     Fetch and execute an x64 payload from a TFTP server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/tftp/x64/meterpreter_reverse_ipv6_tcp                  Fetch and execute an x64 payload from a TFTP server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/tftp/x64/meterpreter_reverse_tcp                       Fetch and execute an x64 payload from a TFTP server. Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    cmd/windows/tftp/x64/peinject/bind_ipv6_tcp                        Fetch and execute an x64 payload from a TFTP server. Listen for an IPv6 connection (Windows x64)
    cmd/windows/tftp/x64/peinject/bind_ipv6_tcp_uuid                   Fetch and execute an x64 payload from a TFTP server. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/tftp/x64/peinject/bind_named_pipe                      Fetch and execute an x64 payload from a TFTP server. Listen for a pipe connection (Windows x64)
    cmd/windows/tftp/x64/peinject/bind_tcp                             Fetch and execute an x64 payload from a TFTP server. Listen for a connection (Windows x64)
    cmd/windows/tftp/x64/peinject/bind_tcp_rc4                         Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker
    cmd/windows/tftp/x64/peinject/bind_tcp_uuid                        Fetch and execute an x64 payload from a TFTP server. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/tftp/x64/peinject/reverse_named_pipe                   Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker via a named pipe pivot
    cmd/windows/tftp/x64/peinject/reverse_tcp                          Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker (Windows x64)
    cmd/windows/tftp/x64/peinject/reverse_tcp_rc4                      Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker
    cmd/windows/tftp/x64/peinject/reverse_tcp_uuid                     Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/tftp/x64/pingback_reverse_tcp                          Fetch and execute an x64 payload from a TFTP server. Connect back to attacker and report UUID (Windows x64)
    cmd/windows/tftp/x64/powershell_bind_tcp                           Fetch and execute an x64 payload from a TFTP server.
    cmd/windows/tftp/x64/powershell_reverse_tcp                        Fetch and execute an x64 payload from a TFTP server.
    cmd/windows/tftp/x64/powershell_reverse_tcp_ssl                    Fetch and execute an x64 payload from a TFTP server.
    cmd/windows/tftp/x64/shell/bind_ipv6_tcp                           Fetch and execute an x64 payload from a TFTP server. Spawn a piped command shell (Windows x64) (staged). Listen for an IPv6 connection (Windows x64)
    cmd/windows/tftp/x64/shell/bind_ipv6_tcp_uuid                      Fetch and execute an x64 payload from a TFTP server. Spawn a piped command shell (Windows x64) (staged). Listen for an IPv6 connection with UUID Support (Windows x
                                                                       64)
    cmd/windows/tftp/x64/shell/bind_named_pipe                         Fetch and execute an x64 payload from a TFTP server. Spawn a piped command shell (Windows x64) (staged). Listen for a pipe connection (Windows x64)
    cmd/windows/tftp/x64/shell/bind_tcp                                Fetch and execute an x64 payload from a TFTP server. Spawn a piped command shell (Windows x64) (staged). Listen for a connection (Windows x64)
    cmd/windows/tftp/x64/shell/bind_tcp_rc4                            Fetch and execute an x64 payload from a TFTP server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker
    cmd/windows/tftp/x64/shell/bind_tcp_uuid                           Fetch and execute an x64 payload from a TFTP server. Spawn a piped command shell (Windows x64) (staged). Listen for a connection with UUID Support (Windows x64)
    cmd/windows/tftp/x64/shell/reverse_tcp                             Fetch and execute an x64 payload from a TFTP server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker (Windows x64)
    cmd/windows/tftp/x64/shell/reverse_tcp_rc4                         Fetch and execute an x64 payload from a TFTP server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker
    cmd/windows/tftp/x64/shell/reverse_tcp_uuid                        Fetch and execute an x64 payload from a TFTP server. Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker with UUID Support (Windows x6
                                                                       4)
    cmd/windows/tftp/x64/shell_bind_tcp                                Fetch and execute an x64 payload from a TFTP server. Listen for a connection and spawn a command shell (Windows x64)
    cmd/windows/tftp/x64/shell_reverse_tcp                             Fetch and execute an x64 payload from a TFTP server. Connect back to attacker and spawn a command shell (Windows x64)
    cmd/windows/tftp/x64/vncinject/bind_ipv6_tcp                       Fetch and execute an x64 payload from a TFTP server. Listen for an IPv6 connection (Windows x64)
    cmd/windows/tftp/x64/vncinject/bind_ipv6_tcp_uuid                  Fetch and execute an x64 payload from a TFTP server. Listen for an IPv6 connection with UUID Support (Windows x64)
    cmd/windows/tftp/x64/vncinject/bind_named_pipe                     Fetch and execute an x64 payload from a TFTP server. Listen for a pipe connection (Windows x64)
    cmd/windows/tftp/x64/vncinject/bind_tcp                            Fetch and execute an x64 payload from a TFTP server. Listen for a connection (Windows x64)
    cmd/windows/tftp/x64/vncinject/bind_tcp_rc4                        Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker
    cmd/windows/tftp/x64/vncinject/bind_tcp_uuid                       Fetch and execute an x64 payload from a TFTP server. Listen for a connection with UUID Support (Windows x64)
    cmd/windows/tftp/x64/vncinject/reverse_http                        Fetch and execute an x64 payload from a TFTP server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/tftp/x64/vncinject/reverse_https                       Fetch and execute an x64 payload from a TFTP server. Tunnel communication over HTTP (Windows x64 wininet)
    cmd/windows/tftp/x64/vncinject/reverse_tcp                         Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker (Windows x64)
    cmd/windows/tftp/x64/vncinject/reverse_tcp_rc4                     Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker
    cmd/windows/tftp/x64/vncinject/reverse_tcp_uuid                    Fetch and execute an x64 payload from a TFTP server. Connect back to the attacker with UUID Support (Windows x64)
    cmd/windows/tftp/x64/vncinject/reverse_winhttp                     Fetch and execute an x64 payload from a TFTP server. Tunnel communication over HTTP (Windows x64 winhttp)
    cmd/windows/tftp/x64/vncinject/reverse_winhttps                    Fetch and execute an x64 payload from a TFTP server. Tunnel communication over HTTPS (Windows x64 winhttp)
    firefox/exec                                                       This module runs a shell command on the target OS without touching the disk. On Windows, this command will flash the command prompt momentarily. This can be avoide
                                                                       d by setting WSCRIPT to true, which drops a jscript "launcher" to disk that hides the prompt.
    firefox/shell_bind_tcp                                             Creates an interactive shell via Javascript with access to Firefox's XPCOM API
    firefox/shell_reverse_tcp                                          Creates an interactive shell via Javascript with access to Firefox's XPCOM API
    generic/custom                                                     Use custom string or file as payload. Set either PAYLOADFILE or PAYLOADSTR.
    generic/debug_trap                                                 Generate a debug trap in the target process
    generic/shell_bind_aws_ssm                                         Creates an interactive shell using AWS SSM
    generic/shell_bind_tcp                                             Listen for a connection and spawn a command shell
    generic/shell_reverse_tcp                                          Connect back to attacker and spawn a command shell
    generic/ssh/interact                                               Interacts with a shell on an established SSH connection
    generic/tight_loop                                                 Generate a tight loop in the target process
    java/jsp_shell_bind_tcp                                            Listen for a connection and spawn a command shell
    java/jsp_shell_reverse_tcp                                         Connect back to attacker and spawn a command shell
    java/meterpreter/bind_tcp                                          Run a meterpreter server in Java. Listen for a connection
    java/meterpreter/reverse_http                                      Run a meterpreter server in Java. Tunnel communication over HTTP
    java/meterpreter/reverse_https                                     Run a meterpreter server in Java. Tunnel communication over HTTPS
    java/meterpreter/reverse_tcp                                       Run a meterpreter server in Java. Connect back stager
    java/shell/bind_tcp                                                Spawn a piped command shell (cmd.exe on Windows, /bin/sh everywhere else). Listen for a connection
    java/shell/reverse_tcp                                             Spawn a piped command shell (cmd.exe on Windows, /bin/sh everywhere else). Connect back stager
    java/shell_reverse_tcp                                             Connect back to attacker and spawn a command shell
    linux/aarch64/meterpreter/reverse_tcp                              Inject the mettle server payload (staged). Connect back to the attacker
    linux/aarch64/meterpreter_reverse_http                             Run the Meterpreter / Mettle server payload (stageless)
    linux/aarch64/meterpreter_reverse_https                            Run the Meterpreter / Mettle server payload (stageless)
    linux/aarch64/meterpreter_reverse_tcp                              Run the Meterpreter / Mettle server payload (stageless)
    linux/aarch64/shell/reverse_tcp                                    dup2 socket in x12, then execve. Connect back to the attacker
    linux/aarch64/shell_reverse_tcp                                    Connect back to attacker and spawn a command shell
    linux/armbe/meterpreter_reverse_http                               Run the Meterpreter / Mettle server payload (stageless)
    linux/armbe/meterpreter_reverse_https                              Run the Meterpreter / Mettle server payload (stageless)
    linux/armbe/meterpreter_reverse_tcp                                Run the Meterpreter / Mettle server payload (stageless)
    linux/armbe/shell_bind_tcp                                         Listen for a connection and spawn a command shell
    linux/armle/adduser                                                Create a new user with UID 0
    linux/armle/exec                                                   Execute an arbitrary command
    linux/armle/meterpreter/bind_tcp                                   Inject the mettle server payload (staged). Listen for a connection
    linux/armle/meterpreter/reverse_tcp                                Inject the mettle server payload (staged). Connect back to the attacker
    linux/armle/meterpreter_reverse_http                               Run the Meterpreter / Mettle server payload (stageless)
    linux/armle/meterpreter_reverse_https                              Run the Meterpreter / Mettle server payload (stageless)
    linux/armle/meterpreter_reverse_tcp                                Run the Meterpreter / Mettle server payload (stageless)
    linux/armle/shell/bind_tcp                                         dup2 socket in r12, then execve. Listen for a connection
    linux/armle/shell/reverse_tcp                                      dup2 socket in r12, then execve. Connect back to the attacker
    linux/armle/shell_bind_tcp                                         Connect to target and spawn a command shell
    linux/armle/shell_reverse_tcp                                      Connect back to attacker and spawn a command shell
    linux/mips64/meterpreter_reverse_http                              Run the Meterpreter / Mettle server payload (stageless)
    linux/mips64/meterpreter_reverse_https                             Run the Meterpreter / Mettle server payload (stageless)
    linux/mips64/meterpreter_reverse_tcp                               Run the Meterpreter / Mettle server payload (stageless)
    linux/mipsbe/exec                                                  A very small shellcode for executing commands. This module is sometimes helpful for testing purposes.
    linux/mipsbe/meterpreter/reverse_tcp                               Inject the mettle server payload (staged). Connect back to the attacker
    linux/mipsbe/meterpreter_reverse_http                              Run the Meterpreter / Mettle server payload (stageless)
    linux/mipsbe/meterpreter_reverse_https                             Run the Meterpreter / Mettle server payload (stageless)
    linux/mipsbe/meterpreter_reverse_tcp                               Run the Meterpreter / Mettle server payload (stageless)
    linux/mipsbe/reboot                                                A very small shellcode for rebooting the system. This payload is sometimes helpful for testing purposes or executing other payloads that rely on initial startup pr
                                                                       ocedures.
    linux/mipsbe/shell/reverse_tcp                                     Spawn a command shell (staged). Connect back to the attacker
    linux/mipsbe/shell_bind_tcp                                        Listen for a connection and spawn a command shell
    linux/mipsbe/shell_reverse_tcp                                     Connect back to attacker and spawn a command shell
    linux/mipsle/exec                                                  A very small shellcode for executing commands. This module is sometimes helpful for testing purposes as well as on targets with extremely limited buffer space.
    linux/mipsle/meterpreter/reverse_tcp                               Inject the mettle server payload (staged). Connect back to the attacker
    linux/mipsle/meterpreter_reverse_http                              Run the Meterpreter / Mettle server payload (stageless)
    linux/mipsle/meterpreter_reverse_https                             Run the Meterpreter / Mettle server payload (stageless)
    linux/mipsle/meterpreter_reverse_tcp                               Run the Meterpreter / Mettle server payload (stageless)
    linux/mipsle/reboot                                                A very small shellcode for rebooting the system. This payload is sometimes helpful for testing purposes.
    linux/mipsle/shell/reverse_tcp                                     Spawn a command shell (staged). Connect back to the attacker
    linux/mipsle/shell_bind_tcp                                        Listen for a connection and spawn a command shell
    linux/mipsle/shell_reverse_tcp                                     Connect back to attacker and spawn a command shell
    linux/ppc/meterpreter_reverse_http                                 Run the Meterpreter / Mettle server payload (stageless)
    linux/ppc/meterpreter_reverse_https                                Run the Meterpreter / Mettle server payload (stageless)
    linux/ppc/meterpreter_reverse_tcp                                  Run the Meterpreter / Mettle server payload (stageless)
    linux/ppc/shell_bind_tcp                                           Listen for a connection and spawn a command shell
    linux/ppc/shell_find_port                                          Spawn a shell on an established connection
    linux/ppc/shell_reverse_tcp                                        Connect back to attacker and spawn a command shell
    linux/ppc64/shell_bind_tcp                                         Listen for a connection and spawn a command shell
    linux/ppc64/shell_find_port                                        Spawn a shell on an established connection
    linux/ppc64/shell_reverse_tcp                                      Connect back to attacker and spawn a command shell
    linux/ppc64le/meterpreter_reverse_http                             Run the Meterpreter / Mettle server payload (stageless)
    linux/ppc64le/meterpreter_reverse_https                            Run the Meterpreter / Mettle server payload (stageless)
    linux/ppc64le/meterpreter_reverse_tcp                              Run the Meterpreter / Mettle server payload (stageless)
    linux/ppce500v2/meterpreter_reverse_http                           Run the Meterpreter / Mettle server payload (stageless)
    linux/ppce500v2/meterpreter_reverse_https                          Run the Meterpreter / Mettle server payload (stageless)
    linux/ppce500v2/meterpreter_reverse_tcp                            Run the Meterpreter / Mettle server payload (stageless)
    linux/riscv32le/exec                                               Execute an arbitrary command
    linux/riscv32le/reboot                                             A very small shellcode for rebooting the system using the reboot syscall. This payload is sometimes helpful for testing purposes.
    linux/riscv64le/exec                                               Execute an arbitrary command
    linux/riscv64le/reboot                                             A very small shellcode for rebooting the system using the reboot syscall. This payload is sometimes helpful for testing purposes.
    linux/x64/exec                                                     Execute an arbitrary command or just a /bin/sh shell
    linux/x64/meterpreter/bind_tcp                                     Inject the mettle server payload (staged). Listen for a connection
    linux/x64/meterpreter/reverse_sctp                                 Inject the mettle server payload (staged). Connect back to the attacker
    linux/x64/meterpreter/reverse_tcp                                  Inject the mettle server payload (staged). Connect back to the attacker
    linux/x64/meterpreter_reverse_http                                 Run the Meterpreter / Mettle server payload (stageless)
    linux/x64/meterpreter_reverse_https                                Run the Meterpreter / Mettle server payload (stageless)
    linux/x64/meterpreter_reverse_tcp                                  Run the Meterpreter / Mettle server payload (stageless)
    linux/x64/pingback_bind_tcp                                        Accept a connection from attacker and report UUID (Linux x64)
    linux/x64/pingback_reverse_tcp                                     Connect back to attacker and report UUID (Linux x64)
    linux/x64/shell/bind_tcp                                           Spawn a command shell (staged). Listen for a connection
    linux/x64/shell/reverse_sctp                                       Spawn a command shell (staged). Connect back to the attacker
    linux/x64/shell/reverse_tcp                                        Spawn a command shell (staged). Connect back to the attacker
    linux/x64/shell_bind_ipv6_tcp                                      Listen for an IPv6 connection and spawn a command shell
    linux/x64/shell_bind_tcp                                           Listen for a connection and spawn a command shell
    linux/x64/shell_bind_tcp_random_port                               Listen for a connection in a random port and spawn a command shell. Use nmap to discover the open port: 'nmap -sS target -p-'.
    linux/x64/shell_find_port                                          Spawn a shell on an established connection
    linux/x64/shell_reverse_ipv6_tcp                                   Connect back to attacker and spawn a command shell over IPv6
    linux/x64/shell_reverse_tcp                                        Connect back to attacker and spawn a command shell
    linux/x86/adduser                                                  Create a new user with UID 0
    linux/x86/chmod                                                    Runs chmod on specified file with specified mode
    linux/x86/exec                                                     Execute an arbitrary command or just a /bin/sh shell
    linux/x86/meterpreter/bind_ipv6_tcp                                Inject the mettle server payload (staged). Listen for an IPv6 connection (Linux x86)
    linux/x86/meterpreter/bind_ipv6_tcp_uuid                           Inject the mettle server payload (staged). Listen for an IPv6 connection with UUID Support (Linux x86)
    linux/x86/meterpreter/bind_nonx_tcp                                Inject the mettle server payload (staged). Listen for a connection
    linux/x86/meterpreter/bind_tcp                                     Inject the mettle server payload (staged). Listen for a connection (Linux x86)
    linux/x86/meterpreter/bind_tcp_uuid                                Inject the mettle server payload (staged). Listen for a connection with UUID Support (Linux x86)
    linux/x86/meterpreter/find_tag                                     Inject the mettle server payload (staged). Use an established connection
    linux/x86/meterpreter/reverse_ipv6_tcp                             Inject the mettle server payload (staged). Connect back to attacker over IPv6
    linux/x86/meterpreter/reverse_nonx_tcp                             Inject the mettle server payload (staged). Connect back to the attacker
    linux/x86/meterpreter/reverse_tcp                                  Inject the mettle server payload (staged). Connect back to the attacker
    linux/x86/meterpreter/reverse_tcp_uuid                             Inject the mettle server payload (staged). Connect back to the attacker
    linux/x86/meterpreter_reverse_http                                 Run the Meterpreter / Mettle server payload (stageless)
    linux/x86/meterpreter_reverse_https                                Run the Meterpreter / Mettle server payload (stageless)
    linux/x86/meterpreter_reverse_tcp                                  Run the Meterpreter / Mettle server payload (stageless)
    linux/x86/metsvc_bind_tcp                                          Stub payload for interacting with a Meterpreter Service
    linux/x86/metsvc_reverse_tcp                                       Stub payload for interacting with a Meterpreter Service
    linux/x86/read_file                                                Read up to 4096 bytes from the local file system and write it back out to the specified file descriptor
    linux/x86/shell/bind_ipv6_tcp                                      Spawn a command shell (staged). Listen for an IPv6 connection (Linux x86)
    linux/x86/shell/bind_ipv6_tcp_uuid                                 Spawn a command shell (staged). Listen for an IPv6 connection with UUID Support (Linux x86)
    linux/x86/shell/bind_nonx_tcp                                      Spawn a command shell (staged). Listen for a connection
    linux/x86/shell/bind_tcp                                           Spawn a command shell (staged). Listen for a connection (Linux x86)
    linux/x86/shell/bind_tcp_uuid                                      Spawn a command shell (staged). Listen for a connection with UUID Support (Linux x86)
    linux/x86/shell/find_tag                                           Spawn a command shell (staged). Use an established connection
    linux/x86/shell/reverse_ipv6_tcp                                   Spawn a command shell (staged). Connect back to attacker over IPv6
    linux/x86/shell/reverse_nonx_tcp                                   Spawn a command shell (staged). Connect back to the attacker
    linux/x86/shell/reverse_tcp                                        Spawn a command shell (staged). Connect back to the attacker
    linux/x86/shell/reverse_tcp_uuid                                   Spawn a command shell (staged). Connect back to the attacker
    linux/x86/shell_bind_ipv6_tcp                                      Listen for a connection over IPv6 and spawn a command shell
    linux/x86/shell_bind_tcp                                           Listen for a connection and spawn a command shell
    linux/x86/shell_bind_tcp_random_port                               Listen for a connection in a random port and spawn a command shell. Use nmap to discover the open port: 'nmap -sS target -p-'.
    linux/x86/shell_find_port                                          Spawn a shell on an established connection
    linux/x86/shell_find_tag                                           Spawn a shell on an established connection (proxy/nat safe)
    linux/x86/shell_reverse_tcp                                        Connect back to attacker and spawn a command shell
    linux/x86/shell_reverse_tcp_ipv6                                   Connect back to attacker and spawn a command shell over IPv6
    linux/zarch/meterpreter_reverse_http                               Run the Meterpreter / Mettle server payload (stageless)
    linux/zarch/meterpreter_reverse_https                              Run the Meterpreter / Mettle server payload (stageless)
    linux/zarch/meterpreter_reverse_tcp                                Run the Meterpreter / Mettle server payload (stageless)
    mainframe/shell_reverse_tcp                                        Listen for a connection and spawn a command shell. This implementation does not include ebcdic character translation, so a client with translation capabilities is
                                                                       required. MSF handles this automatically.
    multi/meterpreter/reverse_http                                     Handle Meterpreter sessions regardless of the target arch/platform. Tunnel communication over HTTP
    multi/meterpreter/reverse_https                                    Handle Meterpreter sessions regardless of the target arch/platform. Tunnel communication over HTTPS
    netware/shell/reverse_tcp                                          Connect to the NetWare console (staged). Connect back to the attacker
    nodejs/shell_bind_tcp                                              Creates an interactive shell via nodejs
    nodejs/shell_reverse_tcp                                           Creates an interactive shell via nodejs
    nodejs/shell_reverse_tcp_ssl                                       Creates an interactive shell via nodejs, uses SSL
    osx/aarch64/exec                                                   Execute an arbitrary command
    osx/aarch64/meterpreter/reverse_tcp                                Inject the mettle server payload (staged). Connect back to the attacker
    osx/aarch64/meterpreter_reverse_http                               Run the Meterpreter / Mettle server payload (stageless)
    osx/aarch64/meterpreter_reverse_https                              Run the Meterpreter / Mettle server payload (stageless)
    osx/aarch64/meterpreter_reverse_tcp                                Run the Meterpreter / Mettle server payload (stageless)
    osx/aarch64/shell_bind_tcp                                         Bind an arbitrary command to an arbitrary port
    osx/aarch64/shell_reverse_tcp                                      Connect back to attacker and spawn a command shell
    osx/armle/execute/bind_tcp                                         Spawn a command shell (staged). Listen for a connection
    osx/armle/execute/reverse_tcp                                      Spawn a command shell (staged). Connect back to the attacker
    osx/armle/shell/bind_tcp                                           Spawn a command shell (staged). Listen for a connection
    osx/armle/shell/reverse_tcp                                        Spawn a command shell (staged). Connect back to the attacker
    osx/armle/shell_bind_tcp                                           Listen for a connection and spawn a command shell
    osx/armle/shell_reverse_tcp                                        Connect back to attacker and spawn a command shell
    osx/armle/vibrate                                                  Causes the iPhone to vibrate, only works when the AudioToolkit library has been loaded. Based on work by Charlie Miller <cmiller[at]securityevaluators.com>.
    osx/ppc/shell/bind_tcp                                             Spawn a command shell (staged). Listen for a connection
    osx/ppc/shell/find_tag                                             Spawn a command shell (staged). Use an established connection
    osx/ppc/shell/reverse_tcp                                          Spawn a command shell (staged). Connect back to the attacker
    osx/ppc/shell_bind_tcp                                             Listen for a connection and spawn a command shell
    osx/ppc/shell_reverse_tcp                                          Connect back to attacker and spawn a command shell
    osx/x64/dupandexecve/bind_tcp                                      dup2 socket in edi, then execve. Listen, read length, read buffer, execute
    osx/x64/dupandexecve/reverse_tcp                                   dup2 socket in edi, then execve. Connect, read length, read buffer, execute
    osx/x64/dupandexecve/reverse_tcp_uuid                              dup2 socket in edi, then execve. Connect back to the attacker with UUID Support (OSX x64)
    osx/x64/exec                                                       Execute an arbitrary command
    osx/x64/meterpreter/bind_tcp                                       Inject the mettle server payload (staged). Listen, read length, read buffer, execute
    osx/x64/meterpreter/reverse_tcp                                    Inject the mettle server payload (staged). Connect, read length, read buffer, execute
    osx/x64/meterpreter/reverse_tcp_uuid                               Inject the mettle server payload (staged). Connect back to the attacker with UUID Support (OSX x64)
    osx/x64/meterpreter_reverse_http                                   Run the Meterpreter / Mettle server payload (stageless)
    osx/x64/meterpreter_reverse_https                                  Run the Meterpreter / Mettle server payload (stageless)
    osx/x64/meterpreter_reverse_tcp                                    Run the Meterpreter / Mettle server payload (stageless)
    osx/x64/say                                                        Say an arbitrary string outloud using Mac OS X text2speech
    osx/x64/shell_bind_tcp                                             Bind an arbitrary command to an arbitrary port
    osx/x64/shell_find_tag                                             Spawn a shell on an established connection (proxy/nat safe)
    osx/x64/shell_reverse_tcp                                          Connect back to attacker and spawn a command shell
    osx/x86/bundleinject/bind_tcp                                      Inject a custom Mach-O bundle into the exploited process. Listen, read length, read buffer, execute
    osx/x86/bundleinject/reverse_tcp                                   Inject a custom Mach-O bundle into the exploited process. Connect, read length, read buffer, execute
    osx/x86/exec                                                       Execute an arbitrary command
    osx/x86/isight/bind_tcp                                            Inject a Mach-O bundle to capture a photo from the iSight (staged). Listen, read length, read buffer, execute
    osx/x86/isight/reverse_tcp                                         Inject a Mach-O bundle to capture a photo from the iSight (staged). Connect, read length, read buffer, execute
    osx/x86/shell_bind_tcp                                             Listen for a connection and spawn a command shell
    osx/x86/shell_find_port                                            Spawn a shell on an established connection
    osx/x86/shell_reverse_tcp                                          Connect back to attacker and spawn a command shell
    osx/x86/vforkshell/bind_tcp                                        Call vfork() if necessary and spawn a command shell (staged). Listen, read length, read buffer, execute
    osx/x86/vforkshell/reverse_tcp                                     Call vfork() if necessary and spawn a command shell (staged). Connect, read length, read buffer, execute
    osx/x86/vforkshell_bind_tcp                                        Listen for a connection, vfork if necessary, and spawn a command shell
    osx/x86/vforkshell_reverse_tcp                                     Connect back to attacker, vfork if necessary, and spawn a command shell
    php/bind_perl                                                      Listen for a connection and spawn a command shell via perl (persistent)
    php/bind_perl_ipv6                                                 Listen for a connection and spawn a command shell via perl (persistent) over IPv6
    php/bind_php                                                       Listen for a connection and spawn a command shell via php
    php/bind_php_ipv6                                                  Listen for a connection and spawn a command shell via php (IPv6)
    php/download_exec                                                  Download an EXE from an HTTP URL and execute it
    php/exec                                                           Execute a single system command
    php/meterpreter/bind_tcp                                           Run a meterpreter server in PHP. Listen for a connection
    php/meterpreter/bind_tcp_ipv6                                      Run a meterpreter server in PHP. Listen for a connection over IPv6
    php/meterpreter/bind_tcp_ipv6_uuid                                 Run a meterpreter server in PHP. Listen for a connection over IPv6 with UUID Support
    php/meterpreter/bind_tcp_uuid                                      Run a meterpreter server in PHP. Listen for a connection with UUID Support
    php/meterpreter/reverse_tcp                                        Run a meterpreter server in PHP. Reverse PHP connect back stager with checks for disabled functions
    php/meterpreter/reverse_tcp_uuid                                   Run a meterpreter server in PHP. Reverse PHP connect back stager with checks for disabled functions
    php/meterpreter_reverse_tcp                                        Connect back to attacker and spawn a Meterpreter server (PHP)
    php/reverse_perl                                                   Creates an interactive shell via perl
    php/reverse_php                                                    Reverse PHP connect back shell with checks for disabled functions
    php/shell_findsock                                                 Spawn a shell on the established connection to the webserver. Unfortunately, this payload can leave conspicuous evil-looking entries in the apache error logs, so i
                                                                       t is probably a good idea to use a bind or reverse shell unless firewalls prevent them from working. The issue this payload takes advantage of (CLOEXEC flag not se
                                                                       t on sockets) appears to have been patched on the Ubuntu version of Apache and may not work on other Debian-based distributions. Only tested on Apache but it might
                                                                        work on other web servers that leak file descriptors to child processes.
    python/exec                                                        Execute an arbitrary OS command. Compatible with Python 2.7 and 3.4+.
    python/meterpreter/bind_tcp                                        Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Listen for a connection
    python/meterpreter/bind_tcp_uuid                                   Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Listen for a connection with UUID Support
    python/meterpreter/reverse_http                                    Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Tunnel communication over HTTP
    python/meterpreter/reverse_https                                   Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Tunnel communication over HTTP using SSL
    python/meterpreter/reverse_tcp                                     Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Connect back to the attacker
    python/meterpreter/reverse_tcp_ssl                                 Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Reverse Python connect back stager using SSL
    python/meterpreter/reverse_tcp_uuid                                Run a meterpreter server in Python (compatible with 2.5-2.7 & 3.1+). Connect back to the attacker with UUID Support
    python/meterpreter_bind_tcp                                        Connect to the victim and spawn a Meterpreter shell
    python/meterpreter_reverse_http                                    Connect back to the attacker and spawn a Meterpreter shell
    python/meterpreter_reverse_https                                   Connect back to the attacker and spawn a Meterpreter shell
    python/meterpreter_reverse_tcp                                     Connect back to the attacker and spawn a Meterpreter shell
    python/pingback_bind_tcp                                           Listens for a connection from the attacker, sends a UUID, then terminates
    python/pingback_reverse_tcp                                        Connects back to the attacker, sends a UUID, then terminates
    python/shell_bind_tcp                                              Creates an interactive shell via Python, encodes with base64 by design. Compatible with Python 2.4-2.7 and 3.4+.
    python/shell_reverse_sctp                                          Creates an interactive shell via Python, encodes with base64 by design. Compatible with Python 2.6-2.7 and 3.4+.
    python/shell_reverse_tcp                                           Creates an interactive shell via Python, encodes with base64 by design. Compatible with Python 2.4-2.7 and 3.4+.
    python/shell_reverse_tcp_ssl                                       Creates an interactive shell via Python, uses SSL, encodes with base64 by design. Compatible with Python 2.6-2.7 and 3.4+.
    python/shell_reverse_udp                                           Creates an interactive shell via Python, encodes with base64 by design. Compatible with Python 2.6-2.7 and 3.4+.
    r/shell_bind_tcp                                                   Continually listen for a connection and spawn a command shell via R
    r/shell_reverse_tcp                                                Connect back and create a command shell via R
    ruby/pingback_bind_tcp                                             Listens for a connection from the attacker, sends a UUID, then terminates
    ruby/pingback_reverse_tcp                                          Connect back to the attacker, sends a UUID, then terminates
    ruby/shell_bind_tcp                                                Continually listen for a connection and spawn a command shell via Ruby
    ruby/shell_bind_tcp_ipv6                                           Continually listen for a connection and spawn a command shell via Ruby
    ruby/shell_reverse_tcp                                             Connect back and create a command shell via Ruby
    ruby/shell_reverse_tcp_ssl                                         Connect back and create a command shell via Ruby, uses SSL
    solaris/sparc/shell_bind_tcp                                       Listen for a connection and spawn a command shell
    solaris/sparc/shell_find_port                                      Spawn a shell on an established connection
    solaris/sparc/shell_reverse_tcp                                    Connect back to attacker and spawn a command shell
    solaris/x86/shell_bind_tcp                                         Listen for a connection and spawn a command shell
    solaris/x86/shell_find_port                                        Spawn a shell on an established connection
    solaris/x86/shell_reverse_tcp                                      Connect back to attacker and spawn a command shell
    tty/unix/interact                                                  Interacts with a TTY on an established socket connection
    windows/adduser                                                    Create a new user and add them to local administration group. Note: The specified password is checked for common complexity requirements to prevent the target mach
                                                                       ine rejecting the user for failing to meet policy requirements. Complexity check: 8-14 chars (1 UPPER, 1 lower, 1 digit/special)
    windows/custom/bind_hidden_ipknock_tcp                             Custom shellcode stage. Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will work as an authentication metho
                                                                       d (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed," thus helping to hide the shell
                                                                       code
    windows/custom/bind_hidden_tcp                                     Custom shellcode stage. Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    windows/custom/bind_ipv6_tcp                                       Custom shellcode stage. Listen for an IPv6 connection (Windows x86)
    windows/custom/bind_ipv6_tcp_uuid                                  Custom shellcode stage. Listen for an IPv6 connection with UUID Support (Windows x86)
    windows/custom/bind_named_pipe                                     Custom shellcode stage. Listen for a pipe connection (Windows x86)
    windows/custom/bind_nonx_tcp                                       Custom shellcode stage. Listen for a connection (No NX)
    windows/custom/bind_tcp                                            Custom shellcode stage. Listen for a connection (Windows x86)
    windows/custom/bind_tcp_rc4                                        Custom shellcode stage. Listen for a connection
    windows/custom/bind_tcp_uuid                                       Custom shellcode stage. Listen for a connection with UUID Support (Windows x86)
    windows/custom/find_tag                                            Custom shellcode stage. Use an established connection
    windows/custom/reverse_http                                        Custom shellcode stage. Tunnel communication over HTTP (Windows wininet)
    windows/custom/reverse_http_proxy_pstore                           Custom shellcode stage. Tunnel communication over HTTP
    windows/custom/reverse_https                                       Custom shellcode stage. Tunnel communication over HTTPS (Windows wininet)
    windows/custom/reverse_ipv6_tcp                                    Custom shellcode stage. Connect back to the attacker over IPv6
    windows/custom/reverse_named_pipe                                  Custom shellcode stage. Connect back to the attacker via a named pipe pivot
    windows/custom/reverse_nonx_tcp                                    Custom shellcode stage. Connect back to the attacker (No NX)
    windows/custom/reverse_ord_tcp                                     Custom shellcode stage. Connect back to the attacker
    windows/custom/reverse_tcp                                         Custom shellcode stage. Connect back to the attacker
    windows/custom/reverse_tcp_allports                                Custom shellcode stage. Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    windows/custom/reverse_tcp_dns                                     Custom shellcode stage. Connect back to the attacker
    windows/custom/reverse_tcp_rc4                                     Custom shellcode stage. Connect back to the attacker
    windows/custom/reverse_tcp_rc4_dns                                 Custom shellcode stage. Connect back to the attacker
    windows/custom/reverse_tcp_uuid                                    Custom shellcode stage. Connect back to the attacker with UUID Support
    windows/custom/reverse_udp                                         Custom shellcode stage. Connect back to the attacker with UUID Support
    windows/custom/reverse_winhttp                                     Custom shellcode stage. Tunnel communication over HTTP (Windows winhttp)
    windows/custom/reverse_winhttps                                    Custom shellcode stage. Tunnel communication over HTTPS (Windows winhttp)
    windows/dllinject/bind_hidden_ipknock_tcp                          Inject a DLL via a reflective loader. Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will work as an authen
                                                                       tication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed," thus helping to
                                                                       hide the shellcode
    windows/dllinject/bind_hidden_tcp                                  Inject a DLL via a reflective loader. Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    windows/dllinject/bind_ipv6_tcp                                    Inject a DLL via a reflective loader. Listen for an IPv6 connection (Windows x86)
    windows/dllinject/bind_ipv6_tcp_uuid                               Inject a DLL via a reflective loader. Listen for an IPv6 connection with UUID Support (Windows x86)
    windows/dllinject/bind_named_pipe                                  Inject a DLL via a reflective loader. Listen for a pipe connection (Windows x86)
    windows/dllinject/bind_nonx_tcp                                    Inject a DLL via a reflective loader. Listen for a connection (No NX)
    windows/dllinject/bind_tcp                                         Inject a DLL via a reflective loader. Listen for a connection (Windows x86)
    windows/dllinject/bind_tcp_rc4                                     Inject a DLL via a reflective loader. Listen for a connection
    windows/dllinject/bind_tcp_uuid                                    Inject a DLL via a reflective loader. Listen for a connection with UUID Support (Windows x86)
    windows/dllinject/find_tag                                         Inject a DLL via a reflective loader. Use an established connection
    windows/dllinject/reverse_http                                     Inject a DLL via a reflective loader. Tunnel communication over HTTP (Windows wininet)
    windows/dllinject/reverse_http_proxy_pstore                        Inject a DLL via a reflective loader. Tunnel communication over HTTP
    windows/dllinject/reverse_ipv6_tcp                                 Inject a DLL via a reflective loader. Connect back to the attacker over IPv6
    windows/dllinject/reverse_nonx_tcp                                 Inject a DLL via a reflective loader. Connect back to the attacker (No NX)
    windows/dllinject/reverse_ord_tcp                                  Inject a DLL via a reflective loader. Connect back to the attacker
    windows/dllinject/reverse_tcp                                      Inject a DLL via a reflective loader. Connect back to the attacker
    windows/dllinject/reverse_tcp_allports                             Inject a DLL via a reflective loader. Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    windows/dllinject/reverse_tcp_dns                                  Inject a DLL via a reflective loader. Connect back to the attacker
    windows/dllinject/reverse_tcp_rc4                                  Inject a DLL via a reflective loader. Connect back to the attacker
    windows/dllinject/reverse_tcp_rc4_dns                              Inject a DLL via a reflective loader. Connect back to the attacker
    windows/dllinject/reverse_tcp_uuid                                 Inject a DLL via a reflective loader. Connect back to the attacker with UUID Support
    windows/dllinject/reverse_winhttp                                  Inject a DLL via a reflective loader. Tunnel communication over HTTP (Windows winhttp)
    windows/dns_txt_query_exec                                         Performs a TXT query against a series of DNS record(s) and executes the returned x86 shellcode. The DNSZONE option is used as the base name to iterate over. The pa
                                                                       yload will first request the TXT contents of the a hostname, followed by b, then c, etc. until there are no more records. For each record that is returned, exactly
                                                                        255 bytes from it are copied into a buffer that is eventually executed. This buffer should be encoded using x86/alpha_mixed with the BufferRegister option set to
                                                                       EDI.
    windows/download_exec                                              Download an EXE from an HTTP(S)/FTP URL and execute it
    windows/encrypted_shell/reverse_tcp                                Spawn a piped command shell (staged). Connect to MSF and read in stage
    windows/encrypted_shell_reverse_tcp                                Connect back to attacker and spawn an encrypted command shell
    windows/exec                                                       Execute an arbitrary command
    windows/format_all_drives                                          This payload formats all mounted disks in Windows (aka ShellcodeOfDeath). After formatting, this payload sets the volume label to the string specified in the VOLUM
                                                                       ELABEL option. If the code is unable to access a drive for any reason, it skips the drive and proceeds to the next volume.
    windows/loadlibrary                                                Load an arbitrary library path
    windows/messagebox                                                 Spawns a dialog via MessageBox using a customizable title, text & icon
    windows/meterpreter/bind_hidden_ipknock_tcp                        Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for a connection. First, the port wil
                                                                       l need to be knocked from the IP defined in KHOST. This IP will work as an authentication method (you can spoof it with tools like hping). After that you could get
                                                                        your shellcode from any IP. The socket will appear as "closed," thus helping to hide the shellcode
    windows/meterpreter/bind_hidden_tcp                                Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for a connection from a hidden port a
                                                                       nd spawn a command shell to the allowed host.
    windows/meterpreter/bind_ipv6_tcp                                  Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for an IPv6 connection (Windows x86)
    windows/meterpreter/bind_ipv6_tcp_uuid                             Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for an IPv6 connection with UUID Supp
                                                                       ort (Windows x86)
    windows/meterpreter/bind_named_pipe                                Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for a pipe connection (Windows x86)
    windows/meterpreter/bind_nonx_tcp                                  Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for a connection (No NX)
    windows/meterpreter/bind_tcp                                       Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for a connection (Windows x86)
    windows/meterpreter/bind_tcp_rc4                                   Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for a connection
    windows/meterpreter/bind_tcp_uuid                                  Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for a connection with UUID Support (W
                                                                       indows x86)
    windows/meterpreter/find_tag                                       Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Use an established connection
    windows/meterpreter/reverse_http                                   Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Tunnel communication over HTTP (Windows wini
                                                                       net)
    windows/meterpreter/reverse_http_proxy_pstore                      Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Tunnel communication over HTTP
    windows/meterpreter/reverse_https                                  Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Tunnel communication over HTTPS (Windows win
                                                                       inet)
    windows/meterpreter/reverse_ipv6_tcp                               Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker over IPv6
    windows/meterpreter/reverse_named_pipe                             Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker via a named pip
                                                                       e pivot
    windows/meterpreter/reverse_nonx_tcp                               Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker (No NX)
    windows/meterpreter/reverse_ord_tcp                                Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker
    windows/meterpreter/reverse_tcp                                    Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker
    windows/meterpreter/reverse_tcp_allports                           Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Try to connect back to the attacker, on all
                                                                       possible ports (1-65535, slowly)
    windows/meterpreter/reverse_tcp_dns                                Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker
    windows/meterpreter/reverse_tcp_rc4                                Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker
    windows/meterpreter/reverse_tcp_rc4_dns                            Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker
    windows/meterpreter/reverse_tcp_uuid                               Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker with UUID Suppo
                                                                       rt
    windows/meterpreter/reverse_winhttp                                Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Tunnel communication over HTTP (Windows winh
                                                                       ttp)
    windows/meterpreter/reverse_winhttps                               Inject the Meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Tunnel communication over HTTPS (Windows win
                                                                       http)
    windows/meterpreter_bind_named_pipe                                Connect to victim and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    windows/meterpreter_bind_tcp                                       Connect to victim and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    windows/meterpreter_reverse_http                                   Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    windows/meterpreter_reverse_https                                  Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    windows/meterpreter_reverse_ipv6_tcp                               Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    windows/meterpreter_reverse_tcp                                    Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    windows/metsvc_bind_tcp                                            Stub payload for interacting with a Meterpreter Service
    windows/metsvc_reverse_tcp                                         Stub payload for interacting with a Meterpreter Service
    windows/patchupdllinject/bind_hidden_ipknock_tcp                   Inject a custom DLL into the exploited process. Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will work as
                                                                        an authentication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed," thus h
                                                                       elping to hide the shellcode
    windows/patchupdllinject/bind_hidden_tcp                           Inject a custom DLL into the exploited process. Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    windows/patchupdllinject/bind_ipv6_tcp                             Inject a custom DLL into the exploited process. Listen for an IPv6 connection (Windows x86)
    windows/patchupdllinject/bind_ipv6_tcp_uuid                        Inject a custom DLL into the exploited process. Listen for an IPv6 connection with UUID Support (Windows x86)
    windows/patchupdllinject/bind_named_pipe                           Inject a custom DLL into the exploited process. Listen for a pipe connection (Windows x86)
    windows/patchupdllinject/bind_nonx_tcp                             Inject a custom DLL into the exploited process. Listen for a connection (No NX)
    windows/patchupdllinject/bind_tcp                                  Inject a custom DLL into the exploited process. Listen for a connection (Windows x86)
    windows/patchupdllinject/bind_tcp_rc4                              Inject a custom DLL into the exploited process. Listen for a connection
    windows/patchupdllinject/bind_tcp_uuid                             Inject a custom DLL into the exploited process. Listen for a connection with UUID Support (Windows x86)
    windows/patchupdllinject/find_tag                                  Inject a custom DLL into the exploited process. Use an established connection
    windows/patchupdllinject/reverse_ipv6_tcp                          Inject a custom DLL into the exploited process. Connect back to the attacker over IPv6
    windows/patchupdllinject/reverse_nonx_tcp                          Inject a custom DLL into the exploited process. Connect back to the attacker (No NX)
    windows/patchupdllinject/reverse_ord_tcp                           Inject a custom DLL into the exploited process. Connect back to the attacker
    windows/patchupdllinject/reverse_tcp                               Inject a custom DLL into the exploited process. Connect back to the attacker
    windows/patchupdllinject/reverse_tcp_allports                      Inject a custom DLL into the exploited process. Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    windows/patchupdllinject/reverse_tcp_dns                           Inject a custom DLL into the exploited process. Connect back to the attacker
    windows/patchupdllinject/reverse_tcp_rc4                           Inject a custom DLL into the exploited process. Connect back to the attacker
    windows/patchupdllinject/reverse_tcp_rc4_dns                       Inject a custom DLL into the exploited process. Connect back to the attacker
    windows/patchupdllinject/reverse_tcp_uuid                          Inject a custom DLL into the exploited process. Connect back to the attacker with UUID Support
    windows/patchupmeterpreter/bind_hidden_ipknock_tcp                 Inject the meterpreter server DLL (staged). Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will work as an
                                                                       authentication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed," thus helpi
                                                                       ng to hide the shellcode
    windows/patchupmeterpreter/bind_hidden_tcp                         Inject the meterpreter server DLL (staged). Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    windows/patchupmeterpreter/bind_ipv6_tcp                           Inject the meterpreter server DLL (staged). Listen for an IPv6 connection (Windows x86)
    windows/patchupmeterpreter/bind_ipv6_tcp_uuid                      Inject the meterpreter server DLL (staged). Listen for an IPv6 connection with UUID Support (Windows x86)
    windows/patchupmeterpreter/bind_named_pipe                         Inject the meterpreter server DLL (staged). Listen for a pipe connection (Windows x86)
    windows/patchupmeterpreter/bind_nonx_tcp                           Inject the meterpreter server DLL (staged). Listen for a connection (No NX)
    windows/patchupmeterpreter/bind_tcp                                Inject the meterpreter server DLL (staged). Listen for a connection (Windows x86)
    windows/patchupmeterpreter/bind_tcp_rc4                            Inject the meterpreter server DLL (staged). Listen for a connection
    windows/patchupmeterpreter/bind_tcp_uuid                           Inject the meterpreter server DLL (staged). Listen for a connection with UUID Support (Windows x86)
    windows/patchupmeterpreter/find_tag                                Inject the meterpreter server DLL (staged). Use an established connection
    windows/patchupmeterpreter/reverse_ipv6_tcp                        Inject the meterpreter server DLL (staged). Connect back to the attacker over IPv6
    windows/patchupmeterpreter/reverse_nonx_tcp                        Inject the meterpreter server DLL (staged). Connect back to the attacker (No NX)
    windows/patchupmeterpreter/reverse_ord_tcp                         Inject the meterpreter server DLL (staged). Connect back to the attacker
    windows/patchupmeterpreter/reverse_tcp                             Inject the meterpreter server DLL (staged). Connect back to the attacker
    windows/patchupmeterpreter/reverse_tcp_allports                    Inject the meterpreter server DLL (staged). Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    windows/patchupmeterpreter/reverse_tcp_dns                         Inject the meterpreter server DLL (staged). Connect back to the attacker
    windows/patchupmeterpreter/reverse_tcp_rc4                         Inject the meterpreter server DLL (staged). Connect back to the attacker
    windows/patchupmeterpreter/reverse_tcp_rc4_dns                     Inject the meterpreter server DLL (staged). Connect back to the attacker
    windows/patchupmeterpreter/reverse_tcp_uuid                        Inject the meterpreter server DLL (staged). Connect back to the attacker with UUID Support
    windows/peinject/bind_hidden_ipknock_tcp                           Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will work as an authentication method
                                                                       (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed," thus helping to hide the shellco
                                                                       de
    windows/peinject/bind_hidden_tcp                                   Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    windows/peinject/bind_ipv6_tcp                                     Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for an IPv6 connection (Windows x86)
    windows/peinject/bind_ipv6_tcp_uuid                                Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for an IPv6 connection with UUID Support (Windows x86)
    windows/peinject/bind_named_pipe                                   Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for a pipe connection (Windows x86)
    windows/peinject/bind_nonx_tcp                                     Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for a connection (No NX)
    windows/peinject/bind_tcp                                          Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for a connection (Windows x86)
    windows/peinject/bind_tcp_rc4                                      Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for a connection
    windows/peinject/bind_tcp_uuid                                     Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for a connection with UUID Support (Windows x86)
    windows/peinject/find_tag                                          Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Use an established connection
    windows/peinject/reverse_ipv6_tcp                                  Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker over IPv6
    windows/peinject/reverse_named_pipe                                Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker via a named pipe pivot
    windows/peinject/reverse_nonx_tcp                                  Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker (No NX)
    windows/peinject/reverse_ord_tcp                                   Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker
    windows/peinject/reverse_tcp                                       Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker
    windows/peinject/reverse_tcp_allports                              Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    windows/peinject/reverse_tcp_dns                                   Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker
    windows/peinject/reverse_tcp_rc4                                   Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker
    windows/peinject/reverse_tcp_rc4_dns                               Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker
    windows/peinject/reverse_tcp_uuid                                  Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker with UUID Support
    windows/pingback_bind_tcp                                          Open a socket and report UUID when a connection is received (Windows x86)
    windows/pingback_reverse_tcp                                       Connect back to attacker and report UUID (Windows x86)
    windows/powershell_bind_tcp                                        Listen for a connection and spawn an interactive powershell session
    windows/powershell_reverse_tcp                                     Listen for a connection and spawn an interactive powershell session
    windows/powershell_reverse_tcp_ssl                                 Listen for a connection and spawn an interactive powershell session over SSL
    windows/shell/bind_hidden_ipknock_tcp                              Spawn a piped command shell (staged). Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will work as an authen
                                                                       tication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed," thus helping to
                                                                       hide the shellcode
    windows/shell/bind_hidden_tcp                                      Spawn a piped command shell (staged). Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    windows/shell/bind_ipv6_tcp                                        Spawn a piped command shell (staged). Listen for an IPv6 connection (Windows x86)
    windows/shell/bind_ipv6_tcp_uuid                                   Spawn a piped command shell (staged). Listen for an IPv6 connection with UUID Support (Windows x86)
    windows/shell/bind_named_pipe                                      Spawn a piped command shell (staged). Listen for a pipe connection (Windows x86)
    windows/shell/bind_nonx_tcp                                        Spawn a piped command shell (staged). Listen for a connection (No NX)
    windows/shell/bind_tcp                                             Spawn a piped command shell (staged). Listen for a connection (Windows x86)
    windows/shell/bind_tcp_rc4                                         Spawn a piped command shell (staged). Listen for a connection
    windows/shell/bind_tcp_uuid                                        Spawn a piped command shell (staged). Listen for a connection with UUID Support (Windows x86)
    windows/shell/find_tag                                             Spawn a piped command shell (staged). Use an established connection
    windows/shell/reverse_ipv6_tcp                                     Spawn a piped command shell (staged). Connect back to the attacker over IPv6
    windows/shell/reverse_nonx_tcp                                     Spawn a piped command shell (staged). Connect back to the attacker (No NX)
    windows/shell/reverse_ord_tcp                                      Spawn a piped command shell (staged). Connect back to the attacker
    windows/shell/reverse_tcp                                          Spawn a piped command shell (staged). Connect back to the attacker
    windows/shell/reverse_tcp_allports                                 Spawn a piped command shell (staged). Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    windows/shell/reverse_tcp_dns                                      Spawn a piped command shell (staged). Connect back to the attacker
    windows/shell/reverse_tcp_rc4                                      Spawn a piped command shell (staged). Connect back to the attacker
    windows/shell/reverse_tcp_rc4_dns                                  Spawn a piped command shell (staged). Connect back to the attacker
    windows/shell/reverse_tcp_uuid                                     Spawn a piped command shell (staged). Connect back to the attacker with UUID Support
    windows/shell/reverse_udp                                          Spawn a piped command shell (staged). Connect back to the attacker with UUID Support
    windows/shell_bind_tcp                                             Listen for a connection and spawn a command shell
    windows/shell_bind_tcp_xpfw                                        Disable the Windows ICF, then listen for a connection and spawn a command shell
    windows/shell_hidden_bind_tcp                                      Listen for a connection from certain IP and spawn a command shell. The shellcode will reply with a RST packet if the connections is not coming from the IP defined
                                                                       in AHOST. This way the port will appear as "closed" helping us to hide the shellcode.
    windows/shell_reverse_tcp                                          Connect back to attacker and spawn a command shell
    windows/speak_pwned                                                Causes the target to say "You Got Pwned" via the Windows Speech API
    windows/upexec/bind_hidden_ipknock_tcp                             Uploads an executable and runs it (staged). Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will work as an
                                                                       authentication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed," thus helpi
                                                                       ng to hide the shellcode
    windows/upexec/bind_hidden_tcp                                     Uploads an executable and runs it (staged). Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    windows/upexec/bind_ipv6_tcp                                       Uploads an executable and runs it (staged). Listen for an IPv6 connection (Windows x86)
    windows/upexec/bind_ipv6_tcp_uuid                                  Uploads an executable and runs it (staged). Listen for an IPv6 connection with UUID Support (Windows x86)
    windows/upexec/bind_named_pipe                                     Uploads an executable and runs it (staged). Listen for a pipe connection (Windows x86)
    windows/upexec/bind_nonx_tcp                                       Uploads an executable and runs it (staged). Listen for a connection (No NX)
    windows/upexec/bind_tcp                                            Uploads an executable and runs it (staged). Listen for a connection (Windows x86)
    windows/upexec/bind_tcp_rc4                                        Uploads an executable and runs it (staged). Listen for a connection
    windows/upexec/bind_tcp_uuid                                       Uploads an executable and runs it (staged). Listen for a connection with UUID Support (Windows x86)
    windows/upexec/find_tag                                            Uploads an executable and runs it (staged). Use an established connection
    windows/upexec/reverse_ipv6_tcp                                    Uploads an executable and runs it (staged). Connect back to the attacker over IPv6
    windows/upexec/reverse_nonx_tcp                                    Uploads an executable and runs it (staged). Connect back to the attacker (No NX)
    windows/upexec/reverse_ord_tcp                                     Uploads an executable and runs it (staged). Connect back to the attacker
    windows/upexec/reverse_tcp                                         Uploads an executable and runs it (staged). Connect back to the attacker
    windows/upexec/reverse_tcp_allports                                Uploads an executable and runs it (staged). Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    windows/upexec/reverse_tcp_dns                                     Uploads an executable and runs it (staged). Connect back to the attacker
    windows/upexec/reverse_tcp_rc4                                     Uploads an executable and runs it (staged). Connect back to the attacker
    windows/upexec/reverse_tcp_rc4_dns                                 Uploads an executable and runs it (staged). Connect back to the attacker
    windows/upexec/reverse_tcp_uuid                                    Uploads an executable and runs it (staged). Connect back to the attacker with UUID Support
    windows/upexec/reverse_udp                                         Uploads an executable and runs it (staged). Connect back to the attacker with UUID Support
    windows/vncinject/bind_hidden_ipknock_tcp                          Inject a VNC Dll via a reflective loader (staged). Listen for a connection. First, the port will need to be knocked from the IP defined in KHOST. This IP will work
                                                                        as an authentication method (you can spoof it with tools like hping). After that you could get your shellcode from any IP. The socket will appear as "closed," thu
                                                                       s helping to hide the shellcode
    windows/vncinject/bind_hidden_tcp                                  Inject a VNC Dll via a reflective loader (staged). Listen for a connection from a hidden port and spawn a command shell to the allowed host.
    windows/vncinject/bind_ipv6_tcp                                    Inject a VNC Dll via a reflective loader (staged). Listen for an IPv6 connection (Windows x86)
    windows/vncinject/bind_ipv6_tcp_uuid                               Inject a VNC Dll via a reflective loader (staged). Listen for an IPv6 connection with UUID Support (Windows x86)
    windows/vncinject/bind_named_pipe                                  Inject a VNC Dll via a reflective loader (staged). Listen for a pipe connection (Windows x86)
    windows/vncinject/bind_nonx_tcp                                    Inject a VNC Dll via a reflective loader (staged). Listen for a connection (No NX)
    windows/vncinject/bind_tcp                                         Inject a VNC Dll via a reflective loader (staged). Listen for a connection (Windows x86)
    windows/vncinject/bind_tcp_rc4                                     Inject a VNC Dll via a reflective loader (staged). Listen for a connection
    windows/vncinject/bind_tcp_uuid                                    Inject a VNC Dll via a reflective loader (staged). Listen for a connection with UUID Support (Windows x86)
    windows/vncinject/find_tag                                         Inject a VNC Dll via a reflective loader (staged). Use an established connection
    windows/vncinject/reverse_http                                     Inject a VNC Dll via a reflective loader (staged). Tunnel communication over HTTP (Windows wininet)
    windows/vncinject/reverse_http_proxy_pstore                        Inject a VNC Dll via a reflective loader (staged). Tunnel communication over HTTP
    windows/vncinject/reverse_ipv6_tcp                                 Inject a VNC Dll via a reflective loader (staged). Connect back to the attacker over IPv6
    windows/vncinject/reverse_nonx_tcp                                 Inject a VNC Dll via a reflective loader (staged). Connect back to the attacker (No NX)
    windows/vncinject/reverse_ord_tcp                                  Inject a VNC Dll via a reflective loader (staged). Connect back to the attacker
    windows/vncinject/reverse_tcp                                      Inject a VNC Dll via a reflective loader (staged). Connect back to the attacker
    windows/vncinject/reverse_tcp_allports                             Inject a VNC Dll via a reflective loader (staged). Try to connect back to the attacker, on all possible ports (1-65535, slowly)
    windows/vncinject/reverse_tcp_dns                                  Inject a VNC Dll via a reflective loader (staged). Connect back to the attacker
    windows/vncinject/reverse_tcp_rc4                                  Inject a VNC Dll via a reflective loader (staged). Connect back to the attacker
    windows/vncinject/reverse_tcp_rc4_dns                              Inject a VNC Dll via a reflective loader (staged). Connect back to the attacker
    windows/vncinject/reverse_tcp_uuid                                 Inject a VNC Dll via a reflective loader (staged). Connect back to the attacker with UUID Support
    windows/vncinject/reverse_winhttp                                  Inject a VNC Dll via a reflective loader (staged). Tunnel communication over HTTP (Windows winhttp)
    windows/x64/custom/bind_ipv6_tcp                                   Custom shellcode stage. Listen for an IPv6 connection (Windows x64)
    windows/x64/custom/bind_ipv6_tcp_uuid                              Custom shellcode stage. Listen for an IPv6 connection with UUID Support (Windows x64)
    windows/x64/custom/bind_named_pipe                                 Custom shellcode stage. Listen for a pipe connection (Windows x64)
    windows/x64/custom/bind_tcp                                        Custom shellcode stage. Listen for a connection (Windows x64)
    windows/x64/custom/bind_tcp_rc4                                    Custom shellcode stage. Connect back to the attacker
    windows/x64/custom/bind_tcp_uuid                                   Custom shellcode stage. Listen for a connection with UUID Support (Windows x64)
    windows/x64/custom/reverse_http                                    Custom shellcode stage. Tunnel communication over HTTP (Windows x64 wininet)
    windows/x64/custom/reverse_https                                   Custom shellcode stage. Tunnel communication over HTTP (Windows x64 wininet)
    windows/x64/custom/reverse_named_pipe                              Custom shellcode stage. Connect back to the attacker via a named pipe pivot
    windows/x64/custom/reverse_tcp                                     Custom shellcode stage. Connect back to the attacker (Windows x64)
    windows/x64/custom/reverse_tcp_rc4                                 Custom shellcode stage. Connect back to the attacker
    windows/x64/custom/reverse_tcp_uuid                                Custom shellcode stage. Connect back to the attacker with UUID Support (Windows x64)
    windows/x64/custom/reverse_winhttp                                 Custom shellcode stage. Tunnel communication over HTTP (Windows x64 winhttp)
    windows/x64/custom/reverse_winhttps                                Custom shellcode stage. Tunnel communication over HTTPS (Windows x64 winhttp)
    windows/x64/encrypted_shell/reverse_tcp                            Spawn a piped command shell (staged). Connect to MSF and read in stage
    windows/x64/encrypted_shell_reverse_tcp                            Connect back to attacker and spawn an encrypted command shell
    windows/x64/exec                                                   Execute an arbitrary command (Windows x64)
    windows/x64/loadlibrary                                            Load an arbitrary x64 library path
    windows/x64/messagebox                                             Spawn a dialog via MessageBox using a customizable title, text & icon
    windows/x64/meterpreter/bind_ipv6_tcp                              Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for an IPv6 connection (Windows x64)
    windows/x64/meterpreter/bind_ipv6_tcp_uuid                         Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for an IPv6 connection with UUID Supp
                                                                       ort (Windows x64)
    windows/x64/meterpreter/bind_named_pipe                            Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for a pipe connection (Windows x64)
    windows/x64/meterpreter/bind_tcp                                   Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for a connection (Windows x64)
    windows/x64/meterpreter/bind_tcp_rc4                               Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker
    windows/x64/meterpreter/bind_tcp_uuid                              Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Listen for a connection with UUID Support (W
                                                                       indows x64)
    windows/x64/meterpreter/reverse_http                               Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Tunnel communication over HTTP (Windows x64
                                                                       wininet)
    windows/x64/meterpreter/reverse_https                              Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Tunnel communication over HTTP (Windows x64
                                                                       wininet)
    windows/x64/meterpreter/reverse_named_pipe                         Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker via a named pip
                                                                       e pivot
    windows/x64/meterpreter/reverse_tcp                                Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker (Windows x64)
    windows/x64/meterpreter/reverse_tcp_rc4                            Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker
    windows/x64/meterpreter/reverse_tcp_uuid                           Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Connect back to the attacker with UUID Suppo
                                                                       rt (Windows x64)
    windows/x64/meterpreter/reverse_winhttp                            Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Tunnel communication over HTTP (Windows x64
                                                                       winhttp)
    windows/x64/meterpreter/reverse_winhttps                           Inject the meterpreter server DLL via the Reflective Dll Injection payload (staged). Requires Windows XP SP2 or newer. Tunnel communication over HTTPS (Windows x64
                                                                        winhttp)
    windows/x64/meterpreter_bind_named_pipe                            Connect to victim and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    windows/x64/meterpreter_bind_tcp                                   Connect to victim and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    windows/x64/meterpreter_reverse_http                               Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    windows/x64/meterpreter_reverse_https                              Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    windows/x64/meterpreter_reverse_ipv6_tcp                           Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    windows/x64/meterpreter_reverse_tcp                                Connect back to attacker and spawn a Meterpreter shell. Requires Windows XP SP2 or newer.
    windows/x64/peinject/bind_ipv6_tcp                                 Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for an IPv6 connection (Windows x64)
    windows/x64/peinject/bind_ipv6_tcp_uuid                            Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for an IPv6 connection with UUID Support (Windows x64)
    windows/x64/peinject/bind_named_pipe                               Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for a pipe connection (Windows x64)
    windows/x64/peinject/bind_tcp                                      Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for a connection (Windows x64)
    windows/x64/peinject/bind_tcp_rc4                                  Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker
    windows/x64/peinject/bind_tcp_uuid                                 Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Listen for a connection with UUID Support (Windows x64)
    windows/x64/peinject/reverse_named_pipe                            Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker via a named pipe pivot
    windows/x64/peinject/reverse_tcp                                   Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker (Windows x64)
    windows/x64/peinject/reverse_tcp_rc4                               Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker
    windows/x64/peinject/reverse_tcp_uuid                              Inject a custom native PE file into the exploited process using a reflective PE loader. The reflective PE loader will execute the pre-mapped PE image starting from
                                                                        the address of entry after performing image base relocation and API address resolution. This module requires a PE file that contains relocation data and a valid (
                                                                       uncorrupted) import table. PE files with CLR(C#/.NET executables), bounded imports, and TLS callbacks are not currently supported. Also PE files which use resource
                                                                        loading might crash. Connect back to the attacker with UUID Support (Windows x64)
    windows/x64/pingback_reverse_tcp                                   Connect back to attacker and report UUID (Windows x64)
    windows/x64/powershell_bind_tcp                                    Listen for a connection and spawn an interactive powershell session
    windows/x64/powershell_reverse_tcp                                 Listen for a connection and spawn an interactive powershell session
    windows/x64/powershell_reverse_tcp_ssl                             Listen for a connection and spawn an interactive powershell session over SSL
    windows/x64/shell/bind_ipv6_tcp                                    Spawn a piped command shell (Windows x64) (staged). Listen for an IPv6 connection (Windows x64)
    windows/x64/shell/bind_ipv6_tcp_uuid                               Spawn a piped command shell (Windows x64) (staged). Listen for an IPv6 connection with UUID Support (Windows x64)
    windows/x64/shell/bind_named_pipe                                  Spawn a piped command shell (Windows x64) (staged). Listen for a pipe connection (Windows x64)
    windows/x64/shell/bind_tcp                                         Spawn a piped command shell (Windows x64) (staged). Listen for a connection (Windows x64)
    windows/x64/shell/bind_tcp_rc4                                     Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker
    windows/x64/shell/bind_tcp_uuid                                    Spawn a piped command shell (Windows x64) (staged). Listen for a connection with UUID Support (Windows x64)
    windows/x64/shell/reverse_tcp                                      Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker (Windows x64)
    windows/x64/shell/reverse_tcp_rc4                                  Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker
    windows/x64/shell/reverse_tcp_uuid                                 Spawn a piped command shell (Windows x64) (staged). Connect back to the attacker with UUID Support (Windows x64)
    windows/x64/shell_bind_tcp                                         Listen for a connection and spawn a command shell (Windows x64)
    windows/x64/shell_reverse_tcp                                      Connect back to attacker and spawn a command shell (Windows x64)
    windows/x64/vncinject/bind_ipv6_tcp                                Inject a VNC Dll via a reflective loader (Windows x64) (staged). Listen for an IPv6 connection (Windows x64)
    windows/x64/vncinject/bind_ipv6_tcp_uuid                           Inject a VNC Dll via a reflective loader (Windows x64) (staged). Listen for an IPv6 connection with UUID Support (Windows x64)
    windows/x64/vncinject/bind_named_pipe                              Inject a VNC Dll via a reflective loader (Windows x64) (staged). Listen for a pipe connection (Windows x64)
    windows/x64/vncinject/bind_tcp                                     Inject a VNC Dll via a reflective loader (Windows x64) (staged). Listen for a connection (Windows x64)
    windows/x64/vncinject/bind_tcp_rc4                                 Inject a VNC Dll via a reflective loader (Windows x64) (staged). Connect back to the attacker
    windows/x64/vncinject/bind_tcp_uuid                                Inject a VNC Dll via a reflective loader (Windows x64) (staged). Listen for a connection with UUID Support (Windows x64)
    windows/x64/vncinject/reverse_http                                 Inject a VNC Dll via a reflective loader (Windows x64) (staged). Tunnel communication over HTTP (Windows x64 wininet)
    windows/x64/vncinject/reverse_https                                Inject a VNC Dll via a reflective loader (Windows x64) (staged). Tunnel communication over HTTP (Windows x64 wininet)
    windows/x64/vncinject/reverse_tcp                                  Inject a VNC Dll via a reflective loader (Windows x64) (staged). Connect back to the attacker (Windows x64)
    windows/x64/vncinject/reverse_tcp_rc4                              Inject a VNC Dll via a reflective loader (Windows x64) (staged). Connect back to the attacker
    windows/x64/vncinject/reverse_tcp_uuid                             Inject a VNC Dll via a reflective loader (Windows x64) (staged). Connect back to the attacker with UUID Support (Windows x64)
    windows/x64/vncinject/reverse_winhttp                              Inject a VNC Dll via a reflective loader (Windows x64) (staged). Tunnel communication over HTTP (Windows x64 winhttp)
    windows/x64/vncinject/reverse_winhttps                             Inject a VNC Dll via a reflective loader (Windows x64) (staged). Tunnel communication over HTTPS (Windows x64 winhttp)
```


## format
```
Framework Executable Formats [--format <value>]
===============================================

    Name
    ----
    asp
    aspx
    aspx-exe
    axis2
    dll
    ducky-script-psh
    elf
    elf-so
    exe
    exe-only
    exe-service
    exe-small
    hta-psh
    jar
    jsp
    loop-vbs
    macho
    msi
    msi-nouac
    osx-app
    psh
    psh-cmd
    psh-net
    psh-reflection
    python-reflection
    vba
    vba-exe
    vba-psh
    vbs
    war

Framework Transform Formats [--format <value>]
==============================================

    Name
    ----
    base32
    base64
    bash
    c
    csharp
    dw
    dword
    go
    golang
    hex
    java
    js_be
    js_le
    masm
    nim
    nimlang
    num
    octal
    perl
    pl
    powershell
    ps1
    py
    python
    raw
    rb
    ruby
    rust
    rustlang
    sh
    vbapplication
    vbscript
    zig
```


## encoder
```
Framework Encoders [--encoder <value>]
======================================

    Name                          Rank       Description
    ----                          ----       -----------
    cmd/base64                    good       Base64 Command Encoder
    cmd/brace                     low        Bash Brace Expansion Command Encoder
    cmd/echo                      good       Echo Command Encoder
    cmd/generic_sh                manual     Generic Shell Variable Substitution Command Encoder
    cmd/ifs                       low        Bourne ${IFS} Substitution Command Encoder
    cmd/perl                      normal     Perl Command Encoder
    cmd/powershell_base64         excellent  Powershell Base64 Command Encoder
    cmd/printf_php_mq             manual     printf(1) via PHP magic_quotes Utility Command Encoder
    generic/eicar                 manual     The EICAR Encoder
    generic/none                  normal     The "none" Encoder
    mipsbe/byte_xori              normal     Byte XORi Encoder
    mipsbe/longxor                normal     XOR Encoder
    mipsle/byte_xori              normal     Byte XORi Encoder
    mipsle/longxor                normal     XOR Encoder
    php/base64                    great      PHP Base64 Encoder
    php/hex                       great      PHP Hex Encoder
    php/minify                    great      PHP Minify Encoder
    ppc/longxor                   normal     PPC LongXOR Encoder
    ppc/longxor_tag               normal     PPC LongXOR Encoder
    ruby/base64                   great      Ruby Base64 Encoder
    sparc/longxor_tag             normal     SPARC DWORD XOR Encoder
    x64/xor                       normal     XOR Encoder
    x64/xor_context               normal     Hostname-based Context Keyed Payload Encoder
    x64/xor_dynamic               normal     Dynamic key XOR Encoder
    x64/zutto_dekiru              manual     Zutto Dekiru
    x86/add_sub                   manual     Add/Sub Encoder
    x86/alpha_mixed               low        Alpha2 Alphanumeric Mixedcase Encoder
    x86/alpha_upper               low        Alpha2 Alphanumeric Uppercase Encoder
    x86/avoid_underscore_tolower  manual     Avoid underscore/tolower
    x86/avoid_utf8_tolower        manual     Avoid UTF8/tolower
    x86/bloxor                    manual     BloXor - A Metamorphic Block Based XOR Encoder
    x86/bmp_polyglot              manual     BMP Polyglot
    x86/call4_dword_xor           normal     Call+4 Dword XOR Encoder
    x86/context_cpuid             manual     CPUID-based Context Keyed Payload Encoder
    x86/context_stat              manual     stat(2)-based Context Keyed Payload Encoder
    x86/context_time              manual     time(2)-based Context Keyed Payload Encoder
    x86/countdown                 normal     Single-byte XOR Countdown Encoder
    x86/fnstenv_mov               normal     Variable-length Fnstenv/mov Dword XOR Encoder
    x86/jmp_call_additive         normal     Jump/Call XOR Additive Feedback Encoder
    x86/nonalpha                  low        Non-Alpha Encoder
    x86/nonupper                  low        Non-Upper Encoder
    x86/opt_sub                   manual     Sub Encoder (optimised)
    x86/service                   manual     Register Service
    x86/shikata_ga_nai            excellent  Polymorphic XOR Additive Feedback Encoder
    x86/single_static_bit         manual     Single Static Bit
    x86/unicode_mixed             manual     Alpha2 Alphanumeric Unicode Mixedcase Encoder
    x86/unicode_upper             manual     Alpha2 Alphanumeric Unicode Uppercase Encoder
    x86/xor_dynamic               normal     Dynamic key XOR Encoder
    x86/xor_poly                  normal     XOR POLY Encoder
```


## encrypt
```
Framework Encryption Formats [--encrypt <value>]
================================================

    Name
    ----
    aes256
    base64
    rc4
    xor
```


## arch
```
Framework Architectures [--arch <value>]
========================================

    Name
    ----
    aarch64
    armbe
    armle
    cbea
    cbea64
    cmd
    dalvik
    firefox
    java
    loongarch64
    mips
    mips64
    mips64le
    mipsbe
    mipsle
    nodejs
    php
    ppc
    ppc64
    ppc64le
    ppce500v2
    python
    r
    riscv32be
    riscv32le
    riscv64be
    riscv64le
    ruby
    sparc
    sparc64
    tty
    x64
    x86
    x86_64
    zarch
```


## platform
```
Framework Platforms [--platform <value>]
========================================

    Name
    ----
    aix
    android
    apple_ios
    arista
    brocade
    bsd
    bsdi
    cisco
    firefox
    freebsd
    hardware
    hpux
    irix
    java
    javascript
    juniper
    linux
    mainframe
    mikrotik
    multi
    netbsd
    netware
    nodejs
    openbsd
    osx
    php
    python
    r
    ruby
    solaris
    unifi
    unix
    unknown
    windows
```


## いろいろ
windows/x64/shell_reverse_tcp 
```

