```sh
└─$ impacket-smbclient -debug 'htb.local/svc-alfresco:s3rvice@10.129.95.210'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
Type help for list of commands
#
```
### help
```sh
#help

 open {host,port=445} - opens a SMB connection against the target host/port
 login {domain/username,passwd} - logs into the current SMB connection, no parameters for NULL connection. If no password specified, it'll be prompted
 kerberos_login {domain/username,passwd} - logs into the current SMB connection using Kerberos. If no password specified, it'll be prompted. Use the DNS resolvable domain name
 login_hash {domain/username,lmhash:nthash} - logs into the current SMB connection using the password hashes
 logoff - logs off
 shares - list available shares
 use {sharename} - connect to an specific share
 cd {path} - changes the current directory to {path}
 lcd {path} - changes the current local directory to {path}
 pwd - shows current remote directory
 password - changes the user password, the new password will be prompted for input
 ls {wildcard} - lists all the files in the current directory
 lls {dirname} - lists all the files on the local filesystem.
 tree {filepath} - recursively lists all files in folder and sub folders
 rm {file} - removes the selected file
 mkdir {dirname} - creates the directory under the current path
 rmdir {dirname} - removes the directory under the current path
 put {filename} - uploads the filename into the current path
 get {filename} - downloads the filename from the current path
 mget {mask} - downloads all files from the current directory matching the provided mask
 cat {filename} - reads the filename from the current path
 mount {target,path} - creates a mount point from {path} to {target} (admin required)
 umount {path} - removes the mount point at {path} without deleting the directory (admin required)
 list_snapshots {path} - lists the vss snapshots for the specified path
 info - returns NetrServerInfo main results
 who - returns the sessions currently connected at the target host (admin required)
 close - closes the current SMB Session
 exit - terminates the server process (and this session)
```
### logoff
```sh
# logoff
#
```
### open
```sh
# open 10.129.95.210
[*] SMBv3.0 dialect used
```
### login_hash
```sh
# login_hash htb.local/administrator :32693b11e6aa90eb43d32c72a07ceea6
[*] USER Session Granted
```
### shares
```sh
# shares
ADMIN$
C$
IPC$
NETLOGON
SYSVOL
```
### use
```sh
# use SYSVOL
```
### pwd
```sh
# pwd
/
```
### ls
```sh
# ls
drw-rw-rw-          0  Wed Sep 18 13:46:00 2019 .
drw-rw-rw-          0  Wed Sep 18 13:46:00 2019 ..
drw-rw-rw-          0  Wed Sep 18 13:46:00 2019 htb.local
```
### cd
```sh
# cd htb.local
#
```
### tree
```sh
# tree
/htb.local/DfsrPrivate/ConflictAndDeleted
/htb.local/DfsrPrivate/Deleted
/htb.local/DfsrPrivate/Installing
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/GPT.INI
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/USER
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/GPT.INI
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/USER
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Microsoft
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Scripts
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE/Microsoft
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Microsoft/Windows NT
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Scripts/Shutdown
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Scripts/Startup
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE/Microsoft/Windows NT
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Microsoft/Windows NT/SecEdit
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE/Microsoft/Windows NT/SecEdit
/htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/MACHINE/Microsoft/Windows NT/SecEdit/GptTmpl.inf
/htb.local/Policies/{6AC1786C-016F-11D2-945F-00C04fB984F9}/MACHINE/Microsoft/Windows NT/SecEdit/GptTmpl.inf
Finished - 25 files and folders
```
### cat
```sh
# cat /htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/GPT.INI
[+] Encoding detection: ascii is most likely the one.
[General]
Version=6
```
### get
```sh
# get /htb.local/Policies/{31B2F340-016D-11D2-945F-00C04FB984F9}/GPT.INI
#
```
### info
```sh
# info
Version Major: 10
Version Minor: 0
Server Name: FOREST
Server Comment: 
Server UserPath: c:\
Simultaneous Users: 16777216
```
### who
```
# who
host:   \\10.10.16.20, user: administrator, active:  1209, idle:     0
host: \\[fe80::8ac:ee0f:f73e:1363], user: FOREST$, active:     8, idle:     8
```
