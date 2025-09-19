```sh
└─$ impacket-netview -target 10.129.138.203 -delay 30 -ts -debug 'htb.local/svc-alfresco:s3rvice'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-09-01 13:13:06] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-09-01 13:13:06] [*] Importing targets
[2025-09-01 13:13:06] [*] Got 1 machines
[2025-09-01 13:13:06] [+] Sleeping for 30 seconds
[2025-09-01 13:13:06] [+] Currently monitoring 0 active targets
[2025-09-01 13:13:06] [+] 10.129.138.203: alive!
[2025-09-01 13:13:06] [+] up: 1, down: 0, total: 1
[2025-09-01 13:13:16] [+] up: 1, down: 0, total: 1
[2025-09-01 13:13:26] [+] up: 1, down: 0, total: 1
[2025-09-01 13:13:36] [+] Adding 10.129.138.203 to the up list
[2025-09-01 13:13:36] [+] up: 1, down: 0, total: 1
[2025-09-01 13:13:44] [*] 10.129.138.203: user HTB\Administrator logged in LOCALLY
[2025-09-01 13:13:44] [*] 10.129.138.203: user HTB\FOREST$ logged in LOCALLY

[2025-09-01 13:13:44] [+] Sleeping for 30 seconds
[2025-09-01 13:13:44] [+] Currently monitoring 1 active targets
[2025-09-01 13:13:46] [+] up: 1, down: 0, total: 1
[2025-09-01 13:13:56] [+] up: 1, down: 0, total: 1
[2025-09-01 13:14:06] [+] up: 1, down: 0, total: 1
[2025-09-01 13:14:15] [*] 10.129.138.203: user FOREST$ logged from host [fe80::f078:8d45:3c85:5444] - active: 7, idle: 1
[2025-09-01 13:14:15] [*] 10.129.138.203: user FOREST$ logged from host [::1] - active: 1, idle: 1

[2025-09-01 13:14:16] [+] Sleeping for 30 seconds
[2025-09-01 13:14:16] [+] Currently monitoring 1 active targets
[2025-09-01 13:14:16] [+] up: 1, down: 0, total: 1
[2025-09-01 13:14:26] [+] up: 1, down: 0, total: 1
[2025-09-01 13:14:36] [+] up: 1, down: 0, total: 1
[2025-09-01 13:14:46] [+] up: 1, down: 0, total: 1
[2025-09-01 13:14:47] [*] 10.129.138.203: user FOREST$ logged off from host [::1]

[2025-09-01 13:14:48] [+] Sleeping for 30 seconds
[2025-09-01 13:14:48] [+] Currently monitoring 1 active targets
^C[2025-09-01 13:14:50] [*] Quitting.. please wait
^CTraceback (most recent call last):
  File "/usr/lib/python3.13/threading.py", line 1542, in _shutdown
    _thread_shutdown()
KeyboardInterrupt:
```
