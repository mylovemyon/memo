### -L
```sh
└─$ smbclient -L 10.129.175.223 -U 'active.htb/administrator%Ticketmaster1968'

 Sharename       Type      Comment
 ---------       ----      -------
 ADMIN$          Disk      Remote Admin
 C$              Disk      Default share
 IPC$            IPC       Remote IPC
 NETLOGON        Disk      Logon server share 
 Replication     Disk      
 SYSVOL          Disk      Logon server share 
 Users           Disk      
do_connect: Connection to 10.129.175.223 failed (Error NT_STATUS_RESOURCE_NAME_NOT_FOUND)
Unable to connect with SMB1 -- no workgroup available
```


### -c
```sh
└─$ smbclient -U 'active.htb/administrator%Ticketmaster1968' -c 'ls' '//10.129.175.223/Replication/'
  .                                   D        0  Sat Jul 21 06:37:44 2018
  ..                                  D        0  Sat Jul 21 06:37:44 2018
  active.htb                          D        0  Sat Jul 21 06:37:44 2018

  5217023 blocks of size 4096. 277137 blocks available
```
