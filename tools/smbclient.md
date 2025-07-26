### -L
```sh
└─$ smbclient -L 10.129.175.223 -U 'active.htb/administrator%Ticketmaster1968' -d 3
lp_load_ex: refreshing parameters
Initialising global parameters
rlimit_max: increasing rlimit_max (1024) to minimum Windows limit (16384)
Processing section "[global]"
added interface docker0 ip=172.17.0.1 bcast=172.17.255.255 netmask=255.255.0.0
added interface eth0 ip=172.26.114.246 bcast=172.26.127.255 netmask=255.255.240.0
Client started (version 4.22.2-Debian-4.22.2+dfsg-1).
Connecting to 10.129.175.223 at port 445
Connecting to 10.129.175.223 at port 139
GENSEC backend 'gssapi_spnego' registered
GENSEC backend 'gssapi_krb5' registered
GENSEC backend 'gssapi_krb5_sasl' registered
GENSEC backend 'spnego' registered
GENSEC backend 'schannel' registered
GENSEC backend 'ncalrpc_as_system' registered
GENSEC backend 'sasl-EXTERNAL' registered
GENSEC backend 'ntlmssp' registered
GENSEC backend 'ntlmssp_resume_ccache' registered
GENSEC backend 'http_basic' registered
GENSEC backend 'http_ntlm' registered
GENSEC backend 'http_negotiate' registered
GENSEC backend 'krb5' registered
GENSEC backend 'fake_gssapi_krb5' registered
gensec_gse_client_start: Not using kerberos to cifs/10.129.175.223 as ACTIVE.HTB\administrator: NT_STATUS_INVALID_PARAMETER
Got challenge flags:
Got NTLMSSP neg_flags=0x62898215
NTLMSSP: Set final flags:
Got NTLMSSP neg_flags=0x62088215
NTLMSSP Sign/Seal - Initialising with flags:
Got NTLMSSP neg_flags=0x62088215
NTLMSSP Sign/Seal - Initialising with flags:
Got NTLMSSP neg_flags=0x62088215

 Sharename       Type      Comment
 ---------       ----      -------
 ADMIN$          Disk      Remote Admin
 C$              Disk      Default share
 IPC$            IPC       Remote IPC
 NETLOGON        Disk      Logon server share 
 Replication     Disk      
 SYSVOL          Disk      Logon server share 
 Users           Disk      
Reconnecting with SMB1 for workgroup listing.
Connecting to 10.129.175.223 at port 139
Connecting to 10.129.175.223 at port 139
do_connect: Connection to 10.129.175.223 failed (Error NT_STATUS_RESOURCE_NAME_NOT_FOUND)
Unable to connect with SMB1 -- no workgroup available
```


### -c
```sh
└─$ smbclient -U 'active.htb/administrator%Ticketmaster1968' -c 'ls' '//10.129.175.223/Replication/' -d 3
lp_load_ex: refreshing parameters
Initialising global parameters
rlimit_max: increasing rlimit_max (1024) to minimum Windows limit (16384)
Processing section "[global]"
added interface docker0 ip=172.17.0.1 bcast=172.17.255.255 netmask=255.255.0.0
added interface eth0 ip=172.26.114.246 bcast=172.26.127.255 netmask=255.255.240.0
Client started (version 4.22.2-Debian-4.22.2+dfsg-1).
Connecting to 10.129.175.223 at port 445
Connecting to 10.129.175.223 at port 139
GENSEC backend 'gssapi_spnego' registered
GENSEC backend 'gssapi_krb5' registered
GENSEC backend 'gssapi_krb5_sasl' registered
GENSEC backend 'spnego' registered
GENSEC backend 'schannel' registered
GENSEC backend 'ncalrpc_as_system' registered
GENSEC backend 'sasl-EXTERNAL' registered
GENSEC backend 'ntlmssp' registered
GENSEC backend 'ntlmssp_resume_ccache' registered
GENSEC backend 'http_basic' registered
GENSEC backend 'http_ntlm' registered
GENSEC backend 'http_negotiate' registered
GENSEC backend 'krb5' registered
GENSEC backend 'fake_gssapi_krb5' registered
gensec_gse_client_start: Not using kerberos to cifs/10.129.175.223 as ACTIVE.HTB\administrator: NT_STATUS_INVALID_PARAMETER
Got challenge flags:
Got NTLMSSP neg_flags=0x62898215
NTLMSSP: Set final flags:
Got NTLMSSP neg_flags=0x62088215
NTLMSSP Sign/Seal - Initialising with flags:
Got NTLMSSP neg_flags=0x62088215
NTLMSSP Sign/Seal - Initialising with flags:
Got NTLMSSP neg_flags=0x62088215
dos_clean_name [\*]
unix_clean_name [\*]
  .                                   D        0  Sat Jul 21 06:37:44 2018
  ..                                  D        0  Sat Jul 21 06:37:44 2018
  active.htb                          D        0  Sat Jul 21 06:37:44 2018

  5217023 blocks of size 4096. 277137 blocks available
Total bytes listed: 0
```
