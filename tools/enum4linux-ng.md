```sh
└─$ enum4linux-ng -A -u 'administrator' -p 'Ticketmaster1968' -t 15 -v 10.129.172.255
ENUM4LINUX - next generation (v1.3.4)

 ==========================
|    Target Information    |
 ==========================
[*] Target ........... 10.129.172.255
[*] Username ......... 'administrator'
[*] Random Username .. 'mfmpxqkh'
[*] Password ......... 'Ticketmaster1968'
[*] Timeout .......... 15 second(s)

 =======================================
|    Listener Scan on 10.129.172.255    |
 =======================================
[*] Checking LDAP
[+] LDAP is accessible on 389/tcp
[*] Checking LDAPS
[+] LDAPS is accessible on 636/tcp
[*] Checking SMB
[+] SMB is accessible on 445/tcp
[*] Checking SMB over NetBIOS
[+] SMB over NetBIOS is accessible on 139/tcp

 ======================================================
|    Domain Information via LDAP for 10.129.172.255    |
 ======================================================
[*] Trying LDAP
[+] Appears to be root/parent DC
[+] Long domain name is: active.htb

 =============================================================
|    NetBIOS Names and Workgroup/Domain for 10.129.172.255    |
 =============================================================
[V] Trying to get NetBIOS names information, running command: nmblookup -s /tmp/tmplp_82aoi -A 10.129.172.255
[-] Could not get NetBIOS names information via 'nmblookup': host does not reply

 ===========================================
|    SMB Dialect Check on 10.129.172.255    |
 ===========================================
[*] Trying on 445/tcp
[+] Supported dialects and settings:
Supported dialects:                                                                                                                                                                                                                         
  SMB 1.0: false                                                                                                                                                                                                                            
  SMB 2.02: true                                                                                                                                                                                                                            
  SMB 2.1: true                                                                                                                                                                                                                             
  SMB 3.0: false                                                                                                                                                                                                                            
  SMB 3.1.1: false                                                                                                                                                                                                                          
Preferred dialect: SMB 2.1                                                                                                                                                                                                                  
SMB1 only: false                                                                                                                                                                                                                            
SMB signing required: true                                                                                                                                                                                                                  

 =============================================================
|    Domain Information via SMB session for 10.129.172.255    |
 =============================================================
[*] Enumerating via unauthenticated SMB session on 445/tcp
[+] Found domain information via SMB
NetBIOS computer name: DC                                                                                                                                                                                                                   
NetBIOS domain name: ACTIVE                                                                                                                                                                                                                 
DNS domain: active.htb                                                                                                                                                                                                                      
FQDN: DC.active.htb                                                                                                                                                                                                                         
Derived membership: domain member                                                                                                                                                                                                           
Derived domain: ACTIVE                                                                                                                                                                                                                      

 ===========================================
|    RPC Session Check on 10.129.172.255    |
 ===========================================
[*] Check for null session
[V] Attempting to make session, running command: smbclient -W ACTIVE -U % -s /tmp/tmplp_82aoi -t 15 -c help '//10.129.172.255/ipc$'
[+] Server allows session using username '', password ''
[*] Check for user session
[V] Attempting to make session, running command: smbclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -t 15 -c help '//10.129.172.255/ipc$'
[+] Server allows session using username 'administrator', password 'Ticketmaster1968'
[*] Check for random user
[V] Attempting to make session, running command: smbclient -W ACTIVE -U mfmpxqkh%Ticketmaster1968 -s /tmp/tmplp_82aoi -t 15 -c help '//10.129.172.255/ipc$'
[-] Could not establish random user session: STATUS_LOGON_FAILURE

 =====================================================
|    Domain Information via RPC for 10.129.172.255    |
 =====================================================
[V] Attempting to get domain SID, running command: rpcclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -c lsaquery 10.129.172.255
[+] Domain: ACTIVE
[+] Domain SID: S-1-5-21-405608879-3187717380-1996298813
[+] Membership: domain member

 =================================================
|    OS Information via RPC for 10.129.172.255    |
 =================================================
[*] Enumerating via unauthenticated SMB session on 445/tcp
[+] Found OS information via SMB
[*] Enumerating via 'srvinfo'
[V] Attempting to get OS info with command, running command: rpcclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -c srvinfo 10.129.172.255
[+] Found OS information via 'srvinfo'
[+] After merging OS information we have the following result:
OS: Windows 7, Windows Server 2008 R2                                                                                                                                                                                                       
OS version: '6.1'                                                                                                                                                                                                                           
OS release: ''                                                                                                                                                                                                                              
OS build: '7601'                                                                                                                                                                                                                            
Native OS: not supported                                                                                                                                                                                                                    
Native LAN manager: not supported                                                                                                                                                                                                           
Platform id: '500'                                                                                                                                                                                                                          
Server type: '0x80102b'                                                                                                                                                                                                                     
Server type string: Wk Sv PDC Tim NT     Domain Controller                                                                                                                                                                                  

 =======================================
|    Users via RPC on 10.129.172.255    |
 =======================================
[*] Enumerating users via 'querydispinfo'
[V] Attempting to get userlist, running command: rpcclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -c querydispinfo 10.129.172.255
[+] Found 4 user(s) via 'querydispinfo'
[*] Enumerating users via 'enumdomusers'
[V] Attempting to get userlist, running command: rpcclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -c enumdomusers 10.129.172.255
[+] Found 4 user(s) via 'enumdomusers'
[+] After merging user results we have 4 user(s) total:
'1103':                                                                                                                                                                                                                                     
  username: SVC_TGS                                                                                                                                                                                                                         
  name: SVC_TGS                                                                                                                                                                                                                             
  acb: '0x00000210'                                                                                                                                                                                                                         
  description: (null)                                                                                                                                                                                                                       
'500':                                                                                                                                                                                                                                      
  username: Administrator                                                                                                                                                                                                                   
  name: (null)                                                                                                                                                                                                                              
  acb: '0x00000210'                                                                                                                                                                                                                         
  description: Built-in account for administering the computer/domain                                                                                                                                                                       
'501':                                                                                                                                                                                                                                      
  username: Guest                                                                                                                                                                                                                           
  name: (null)                                                                                                                                                                                                                              
  acb: '0x00000215'                                                                                                                                                                                                                         
  description: Built-in account for guest access to the computer/domain                                                                                                                                                                     
'502':                                                                                                                                                                                                                                      
  username: krbtgt                                                                                                                                                                                                                          
  name: (null)                                                                                                                                                                                                                              
  acb: '0x00020011'                                                                                                                                                                                                                         
  description: Key Distribution Center Service Account                                                                                                                                                                                      

 ========================================
|    Groups via RPC on 10.129.172.255    |
 ========================================
[*] Enumerating local groups
[V] Attempting to get local groups, running command: rpcclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -c 'enumalsgroups domain' 10.129.172.255
[+] Found 5 group(s) via 'enumalsgroups domain'
[*] Enumerating builtin groups
[V] Attempting to get builtin groups, running command: rpcclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -c 'enumalsgroups builtin' 10.129.172.255
[+] Found 21 group(s) via 'enumalsgroups builtin'
[*] Enumerating domain groups
[V] Attempting to get domain groups, running command: rpcclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -c enumdomgroups 10.129.172.255
[+] Found 11 group(s) via 'enumdomgroups'
[+] After merging groups results we have 37 group(s) total:
'1101':                                                                                                                                                                                                                                     
  groupname: DnsAdmins                                                                                                                                                                                                                      
  type: local                                                                                                                                                                                                                               
'1102':                                                                                                                                                                                                                                     
  groupname: DnsUpdateProxy                                                                                                                                                                                                                 
  type: domain                                                                                                                                                                                                                              
'498':                                                                                                                                                                                                                                      
  groupname: Enterprise Read-only Domain Controllers                                                                                                                                                                                        
  type: domain                                                                                                                                                                                                                              
'512':                                                                                                                                                                                                                                      
  groupname: Domain Admins                                                                                                                                                                                                                  
  type: domain                                                                                                                                                                                                                              
'513':                                                                                                                                                                                                                                      
  groupname: Domain Users                                                                                                                                                                                                                   
  type: domain                                                                                                                                                                                                                              
'514':                                                                                                                                                                                                                                      
  groupname: Domain Guests                                                                                                                                                                                                                  
  type: domain                                                                                                                                                                                                                              
'515':                                                                                                                                                                                                                                      
  groupname: Domain Computers                                                                                                                                                                                                               
  type: domain                                                                                                                                                                                                                              
'516':                                                                                                                                                                                                                                      
  groupname: Domain Controllers                                                                                                                                                                                                             
  type: domain                                                                                                                                                                                                                              
'517':                                                                                                                                                                                                                                      
  groupname: Cert Publishers                                                                                                                                                                                                                
  type: local                                                                                                                                                                                                                               
'518':                                                                                                                                                                                                                                      
  groupname: Schema Admins                                                                                                                                                                                                                  
  type: domain                                                                                                                                                                                                                              
'519':                                                                                                                                                                                                                                      
  groupname: Enterprise Admins                                                                                                                                                                                                              
  type: domain                                                                                                                                                                                                                              
'520':                                                                                                                                                                                                                                      
  groupname: Group Policy Creator Owners                                                                                                                                                                                                    
  type: domain                                                                                                                                                                                                                              
'521':                                                                                                                                                                                                                                      
  groupname: Read-only Domain Controllers                                                                                                                                                                                                   
  type: domain                                                                                                                                                                                                                              
'544':                                                                                                                                                                                                                                      
  groupname: Administrators                                                                                                                                                                                                                 
  type: builtin                                                                                                                                                                                                                             
'545':                                                                                                                                                                                                                                      
  groupname: Users                                                                                                                                                                                                                          
  type: builtin                                                                                                                                                                                                                             
'546':                                                                                                                                                                                                                                      
  groupname: Guests                                                                                                                                                                                                                         
  type: builtin                                                                                                                                                                                                                             
'548':                                                                                                                                                                                                                                      
  groupname: Account Operators                                                                                                                                                                                                              
  type: builtin                                                                                                                                                                                                                             
'549':                                                                                                                                                                                                                                      
  groupname: Server Operators                                                                                                                                                                                                               
  type: builtin                                                                                                                                                                                                                             
'550':                                                                                                                                                                                                                                      
  groupname: Print Operators                                                                                                                                                                                                                
  type: builtin                                                                                                                                                                                                                             
'551':                                                                                                                                                                                                                                      
  groupname: Backup Operators                                                                                                                                                                                                               
  type: builtin                                                                                                                                                                                                                             
'552':                                                                                                                                                                                                                                      
  groupname: Replicator                                                                                                                                                                                                                     
  type: builtin                                                                                                                                                                                                                             
'553':                                                                                                                                                                                                                                      
  groupname: RAS and IAS Servers                                                                                                                                                                                                            
  type: local                                                                                                                                                                                                                               
'554':                                                                                                                                                                                                                                      
  groupname: Pre-Windows 2000 Compatible Access                                                                                                                                                                                             
  type: builtin                                                                                                                                                                                                                             
'555':                                                                                                                                                                                                                                      
  groupname: Remote Desktop Users                                                                                                                                                                                                           
  type: builtin                                                                                                                                                                                                                             
'556':                                                                                                                                                                                                                                      
  groupname: Network Configuration Operators                                                                                                                                                                                                
  type: builtin                                                                                                                                                                                                                             
'557':                                                                                                                                                                                                                                      
  groupname: Incoming Forest Trust Builders                                                                                                                                                                                                 
  type: builtin                                                                                                                                                                                                                             
'558':                                                                                                                                                                                                                                      
  groupname: Performance Monitor Users                                                                                                                                                                                                      
  type: builtin                                                                                                                                                                                                                             
'559':                                                                                                                                                                                                                                      
  groupname: Performance Log Users                                                                                                                                                                                                          
  type: builtin                                                                                                                                                                                                                             
'560':                                                                                                                                                                                                                                      
  groupname: Windows Authorization Access Group                                                                                                                                                                                             
  type: builtin                                                                                                                                                                                                                             
'561':                                                                                                                                                                                                                                      
  groupname: Terminal Server License Servers                                                                                                                                                                                                
  type: builtin                                                                                                                                                                                                                             
'562':                                                                                                                                                                                                                                      
  groupname: Distributed COM Users                                                                                                                                                                                                          
  type: builtin                                                                                                                                                                                                                             
'568':                                                                                                                                                                                                                                      
  groupname: IIS_IUSRS                                                                                                                                                                                                                      
  type: builtin                                                                                                                                                                                                                             
'569':                                                                                                                                                                                                                                      
  groupname: Cryptographic Operators                                                                                                                                                                                                        
  type: builtin                                                                                                                                                                                                                             
'571':                                                                                                                                                                                                                                      
  groupname: Allowed RODC Password Replication Group                                                                                                                                                                                        
  type: local                                                                                                                                                                                                                               
'572':                                                                                                                                                                                                                                      
  groupname: Denied RODC Password Replication Group                                                                                                                                                                                         
  type: local                                                                                                                                                                                                                               
'573':                                                                                                                                                                                                                                      
  groupname: Event Log Readers                                                                                                                                                                                                              
  type: builtin                                                                                                                                                                                                                             
'574':                                                                                                                                                                                                                                      
  groupname: Certificate Service DCOM Access                                                                                                                                                                                                
  type: builtin                                                                                                                                                                                                                             

 ========================================
|    Shares via RPC on 10.129.172.255    |
 ========================================
[V] Attempting to get share list using authentication, running command: smbclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -t 15 -L //10.129.172.255 -g
[*] Enumerating shares
[+] Found 7 share(s):
ADMIN$:                                                                                                                                                                                                                                     
  comment: Remote Admin                                                                                                                                                                                                                     
  type: Disk                                                                                                                                                                                                                                
C$:                                                                                                                                                                                                                                         
  comment: Default share                                                                                                                                                                                                                    
  type: Disk                                                                                                                                                                                                                                
IPC$:                                                                                                                                                                                                                                       
  comment: Remote IPC                                                                                                                                                                                                                       
  type: IPC                                                                                                                                                                                                                                 
NETLOGON:                                                                                                                                                                                                                                   
  comment: Logon server share                                                                                                                                                                                                               
  type: Disk                                                                                                                                                                                                                                
Replication:                                                                                                                                                                                                                                
  comment: ''                                                                                                                                                                                                                               
  type: Disk                                                                                                                                                                                                                                
SYSVOL:                                                                                                                                                                                                                                     
  comment: Logon server share                                                                                                                                                                                                               
  type: Disk                                                                                                                                                                                                                                
Users:                                                                                                                                                                                                                                      
  comment: ''                                                                                                                                                                                                                               
  type: Disk                                                                                                                                                                                                                                
[*] Testing share ADMIN$
[V] Attempting to map share //10.129.172.255/ADMIN$, running command: smbclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -t 15 -c dir '//10.129.172.255/ADMIN$'
[+] Mapping: OK, Listing: OK
[*] Testing share C$
[V] Attempting to map share //10.129.172.255/C$, running command: smbclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -t 15 -c dir '//10.129.172.255/C$'
[+] Mapping: OK, Listing: OK
[*] Testing share IPC$
[V] Attempting to map share //10.129.172.255/IPC$, running command: smbclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -t 15 -c dir '//10.129.172.255/IPC$'
[-] Could not check share: STATUS_INVALID_PARAMETER
[*] Testing share NETLOGON
[V] Attempting to map share //10.129.172.255/NETLOGON, running command: smbclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -t 15 -c dir //10.129.172.255/NETLOGON
[+] Mapping: OK, Listing: OK
[*] Testing share Replication
[V] Attempting to map share //10.129.172.255/Replication, running command: smbclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -t 15 -c dir //10.129.172.255/Replication
[+] Mapping: OK, Listing: OK
[*] Testing share SYSVOL
[V] Attempting to map share //10.129.172.255/SYSVOL, running command: smbclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -t 15 -c dir //10.129.172.255/SYSVOL
[+] Mapping: OK, Listing: OK
[*] Testing share Users
[V] Attempting to map share //10.129.172.255/Users, running command: smbclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -t 15 -c dir //10.129.172.255/Users
[+] Mapping: OK, Listing: OK

 ===========================================
|    Policies via RPC for 10.129.172.255    |
 ===========================================
[*] Trying port 445/tcp
[+] Found policy:
Domain password information:                                                                                                                                                                                                                
  Password history length: 24                                                                                                                                                                                                               
  Minimum password length: 7                                                                                                                                                                                                                
  Maximum password age: 41 days 23 hours 53 minutes                                                                                                                                                                                         
  Password properties:                                                                                                                                                                                                                      
  - DOMAIN_PASSWORD_COMPLEX: true                                                                                                                                                                                                           
  - DOMAIN_PASSWORD_NO_ANON_CHANGE: false                                                                                                                                                                                                   
  - DOMAIN_PASSWORD_NO_CLEAR_CHANGE: false                                                                                                                                                                                                  
  - DOMAIN_PASSWORD_LOCKOUT_ADMINS: false                                                                                                                                                                                                   
  - DOMAIN_PASSWORD_PASSWORD_STORE_CLEARTEXT: false                                                                                                                                                                                         
  - DOMAIN_PASSWORD_REFUSE_PASSWORD_CHANGE: false                                                                                                                                                                                           
Domain lockout information:                                                                                                                                                                                                                 
  Lockout observation window: 30 minutes                                                                                                                                                                                                    
  Lockout duration: 30 minutes                                                                                                                                                                                                              
  Lockout threshold: None                                                                                                                                                                                                                   
Domain logoff information:                                                                                                                                                                                                                  
  Force logoff time: not set                                                                                                                                                                                                                

 ===========================================
|    Printers via RPC for 10.129.172.255    |
 ===========================================
[V] Attempting to get printer info, running command: rpcclient -W ACTIVE -U administrator%Ticketmaster1968 -s /tmp/tmplp_82aoi -c enumprinters 10.129.172.255
[+] No printers available

Completed after 151.50 seconds
```
