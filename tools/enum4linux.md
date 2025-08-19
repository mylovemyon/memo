```sh
└─$ enum4linux -a -d -u svc-alfresco -p s3rvice -w htb.local -v 10.129.149.11

[V] Dependent program "nmblookup" found in /usr/bin/nmblookup


[V] Dependent program "net" found in /usr/bin/net


[V] Dependent program "rpcclient" found in /usr/bin/rpcclient


[V] Dependent program "smbclient" found in /usr/bin/smbclient


[V] Dependent program "polenum" found in /usr/bin/polenum


[V] Dependent program "ldapsearch" found in /usr/bin/ldapsearch

Starting enum4linux v0.9.1 ( http://labs.portcullis.co.uk/application/enum4linux/ ) on Tue Aug 19 10:21:04 2025

 =========================================( Target Information )=========================================

Target ........... 10.129.149.11
RID Range ........ 500-550,1000-1050
Username ......... 'svc-alfresco'
Password ......... 's3rvice'
Known Usernames .. administrator, guest, krbtgt, domain admins, root, bin, none


 ===========================( Enumerating Workgroup/Domain on 10.129.149.11 )===========================


[V] Attempting to get domain name with command: nmblookup -A '10.129.149.11'


[+] Got domain/workgroup name: htb.local


 ===============================( Nbtstat Information for 10.129.149.11 )===============================

Looking up status of 10.129.149.11
No reply from 10.129.149.11

 ===================================( Session Check on 10.129.149.11 )===================================


[V] Attempting to make null session using command: smbclient -W 'htb.local' //'10.129.149.11'/ipc$ -U'svc-alfresco'%'s3rvice' -c 'help' 2>&1


[+] Server 10.129.149.11 allows sessions using username 'svc-alfresco', password 's3rvice'


 ================================( Getting domain SID for 10.129.149.11 )================================


[V] Attempting to get domain SID with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' 10.129.149.11 -c 'lsaquery' 2>&1

Domain Name: HTB
Domain Sid: S-1-5-21-3072663084-364016917-1341370565

[+] Host is part of a domain (not a workgroup)


 ==================================( OS information on 10.129.149.11 )==================================
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get OS info with command: smbclient -W 'htb.local' //'10.129.149.11'/ipc$ -U'svc-alfresco'%'s3rvice' -c 'q' 2>&1                                                                                                          
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] Can't get OS info with smbclient                                                                                                                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get OS info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'srvinfo' '10.129.149.11' 2>&1                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Got OS info for 10.129.149.11 from srvinfo:                                                                                                                                                                                             
        10.129.149.11  Wk Sv PDC Tim NT                                                                                                                                                                                                     
        platform_id     :       500
        os version      :       10.0
        server type     :       0x80102b


 =======================================( Users on 10.129.149.11 )=======================================
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get userlist with command: rpcclient -W 'htb.local' -c querydispinfo -U'svc-alfresco'%'s3rvice' '10.129.149.11' 2>&1                                                                                                      
                                                                                                                                                                                                                                            
index: 0x2137 RID: 0x463 acb: 0x00020015 Account: $331000-VK4ADACQNUCA  Name: (null)    Desc: (null)                                                                                                                                        
index: 0xfbc RID: 0x1f4 acb: 0x00000010 Account: Administrator  Name: Administrator     Desc: Built-in account for administering the computer/domain
index: 0x2369 RID: 0x47e acb: 0x00000210 Account: andy  Name: Andy Hislip       Desc: (null)
index: 0xfbe RID: 0x1f7 acb: 0x00000215 Account: DefaultAccount Name: (null)    Desc: A user account managed by the system.
index: 0xfbd RID: 0x1f5 acb: 0x00000215 Account: Guest  Name: (null)    Desc: Built-in account for guest access to the computer/domain
index: 0x2352 RID: 0x478 acb: 0x00000210 Account: HealthMailbox0659cc1  Name: HealthMailbox-EXCH01-010  Desc: (null)
index: 0x234b RID: 0x471 acb: 0x00000210 Account: HealthMailbox670628e  Name: HealthMailbox-EXCH01-003  Desc: (null)
index: 0x234d RID: 0x473 acb: 0x00000210 Account: HealthMailbox6ded678  Name: HealthMailbox-EXCH01-005  Desc: (null)
index: 0x2351 RID: 0x477 acb: 0x00000210 Account: HealthMailbox7108a4e  Name: HealthMailbox-EXCH01-009  Desc: (null)
index: 0x234e RID: 0x474 acb: 0x00000210 Account: HealthMailbox83d6781  Name: HealthMailbox-EXCH01-006  Desc: (null)
index: 0x234c RID: 0x472 acb: 0x00000210 Account: HealthMailbox968e74d  Name: HealthMailbox-EXCH01-004  Desc: (null)
index: 0x2350 RID: 0x476 acb: 0x00000210 Account: HealthMailboxb01ac64  Name: HealthMailbox-EXCH01-008  Desc: (null)
index: 0x234a RID: 0x470 acb: 0x00000210 Account: HealthMailboxc0a90c9  Name: HealthMailbox-EXCH01-002  Desc: (null)
index: 0x2348 RID: 0x46e acb: 0x00000210 Account: HealthMailboxc3d7722  Name: HealthMailbox-EXCH01-Mailbox-Database-1118319013  Desc: (null)
index: 0x2349 RID: 0x46f acb: 0x00000210 Account: HealthMailboxfc9daad  Name: HealthMailbox-EXCH01-001  Desc: (null)
index: 0x234f RID: 0x475 acb: 0x00000210 Account: HealthMailboxfd87238  Name: HealthMailbox-EXCH01-007  Desc: (null)
index: 0xff4 RID: 0x1f6 acb: 0x00000011 Account: krbtgt Name: (null)    Desc: Key Distribution Center Service Account
index: 0x2360 RID: 0x47a acb: 0x00000210 Account: lucinda       Name: Lucinda Berger    Desc: (null)
index: 0x236a RID: 0x47f acb: 0x00000210 Account: mark  Name: Mark Brandt       Desc: (null)
index: 0x236b RID: 0x480 acb: 0x00000210 Account: santi Name: Santi Rodriguez   Desc: (null)
index: 0x235c RID: 0x479 acb: 0x00000210 Account: sebastien     Name: Sebastien Caron   Desc: (null)
index: 0x215a RID: 0x468 acb: 0x00020011 Account: SM_1b41c9286325456bb  Name: Microsoft Exchange Migration      Desc: (null)
index: 0x2161 RID: 0x46c acb: 0x00020011 Account: SM_1ffab36a2f5f479cb  Name: SystemMailbox{8cc370d3-822a-4ab8-a926-bb94bd0641a9}       Desc: (null)
index: 0x2156 RID: 0x464 acb: 0x00020011 Account: SM_2c8eef0a09b545acb  Name: Microsoft Exchange Approval Assistant     Desc: (null)
index: 0x2159 RID: 0x467 acb: 0x00020011 Account: SM_681f53d4942840e18  Name: Discovery Search Mailbox  Desc: (null)
index: 0x2158 RID: 0x466 acb: 0x00020011 Account: SM_75a538d3025e4db9a  Name: Microsoft Exchange        Desc: (null)
index: 0x215c RID: 0x46a acb: 0x00020011 Account: SM_7c96b981967141ebb  Name: E4E Encryption Store - Active     Desc: (null)
index: 0x215b RID: 0x469 acb: 0x00020011 Account: SM_9b69f1b9d2cc45549  Name: Microsoft Exchange Federation Mailbox     Desc: (null)
index: 0x215d RID: 0x46b acb: 0x00020011 Account: SM_c75ee099d0a64c91b  Name: Microsoft Exchange        Desc: (null)
index: 0x2157 RID: 0x465 acb: 0x00020011 Account: SM_ca8c2ed5bdab4dc9b  Name: Microsoft Exchange        Desc: (null)
index: 0x2365 RID: 0x47b acb: 0x00010210 Account: svc-alfresco  Name: svc-alfresco      Desc: (null)


[V] Attempting to get userlist with command: rpcclient -W 'htb.local' -c enumdomusers -U'svc-alfresco'%'s3rvice' '10.129.149.11' 2>&1                                                                                                       
                                                                                                                                                                                                                                            
user:[Administrator] rid:[0x1f4]                                                                                                                                                                                                            
user:[Guest] rid:[0x1f5]
user:[krbtgt] rid:[0x1f6]
user:[DefaultAccount] rid:[0x1f7]
user:[$331000-VK4ADACQNUCA] rid:[0x463]
user:[SM_2c8eef0a09b545acb] rid:[0x464]
user:[SM_ca8c2ed5bdab4dc9b] rid:[0x465]
user:[SM_75a538d3025e4db9a] rid:[0x466]
user:[SM_681f53d4942840e18] rid:[0x467]
user:[SM_1b41c9286325456bb] rid:[0x468]
user:[SM_9b69f1b9d2cc45549] rid:[0x469]
user:[SM_7c96b981967141ebb] rid:[0x46a]
user:[SM_c75ee099d0a64c91b] rid:[0x46b]
user:[SM_1ffab36a2f5f479cb] rid:[0x46c]
user:[HealthMailboxc3d7722] rid:[0x46e]
user:[HealthMailboxfc9daad] rid:[0x46f]
user:[HealthMailboxc0a90c9] rid:[0x470]
user:[HealthMailbox670628e] rid:[0x471]
user:[HealthMailbox968e74d] rid:[0x472]
user:[HealthMailbox6ded678] rid:[0x473]
user:[HealthMailbox83d6781] rid:[0x474]
user:[HealthMailboxfd87238] rid:[0x475]
user:[HealthMailboxb01ac64] rid:[0x476]
user:[HealthMailbox7108a4e] rid:[0x477]
user:[HealthMailbox0659cc1] rid:[0x478]
user:[sebastien] rid:[0x479]
user:[lucinda] rid:[0x47a]
user:[svc-alfresco] rid:[0x47b]
user:[andy] rid:[0x47e]
user:[mark] rid:[0x47f]
user:[santi] rid:[0x480]

[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 501' '10.129.149.11' 2>&1                                                                                          
                                                                                                                                                                                                                                            
        User Name   :   Guest                                                                                                                                                                                                               
        Full Name   :
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :   Built-in account for guest access to the computer/domain
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x1f5
        group_rid:      0x202
        acb_info :      0x00000215
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1139' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   HealthMailbox6ded678                                                                                                                                                                                                
        Full Name   :   HealthMailbox-EXCH01-005
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Thu, 19 Sep 2019 07:57:07 EDT
        Password can change Time :      Fri, 20 Sep 2019 07:57:07 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x473
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1150' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   andy                                                                                                                                                                                                                
        Full Name   :   Andy Hislip
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Sun, 22 Sep 2019 18:44:16 EDT
        Password can change Time :      Mon, 23 Sep 2019 18:44:16 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x47e
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1140' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   HealthMailbox83d6781                                                                                                                                                                                                
        Full Name   :   HealthMailbox-EXCH01-006
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Thu, 19 Sep 2019 07:57:17 EDT
        Password can change Time :      Fri, 20 Sep 2019 07:57:17 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x474
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1142' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   HealthMailboxb01ac64                                                                                                                                                                                                
        Full Name   :   HealthMailbox-EXCH01-008
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Thu, 19 Sep 2019 07:57:38 EDT
        Password can change Time :      Fri, 20 Sep 2019 07:57:38 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x476
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1152' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   santi                                                                                                                                                                                                               
        Full Name   :   Santi Rodriguez
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Fri, 20 Sep 2019 19:02:55 EDT
        Password can change Time :      Sat, 21 Sep 2019 19:02:55 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x480
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1145' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   sebastien                                                                                                                                                                                                           
        Full Name   :   Sebastien Caron
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Sun, 22 Sep 2019 18:29:30 EDT
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Thu, 19 Sep 2019 20:30:00 EDT
        Password can change Time :      Fri, 20 Sep 2019 20:30:00 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x479
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000008
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1125' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   SM_ca8c2ed5bdab4dc9b                                                                                                                                                                                                
        Full Name   :   Microsoft Exchange
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 31 Dec 1969 19:00:00 EST
        unknown_2[0..31]...
        user_rid :      0x465
        group_rid:      0x201
        acb_info :      0x00020011
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : False
        Account locked out       : False
        Password expired         : True
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1124' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   SM_2c8eef0a09b545acb                                                                                                                                                                                                
        Full Name   :   Microsoft Exchange Approval Assistant
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 31 Dec 1969 19:00:00 EST
        unknown_2[0..31]...
        user_rid :      0x464
        group_rid:      0x201
        acb_info :      0x00020011
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : False
        Account locked out       : False
        Password expired         : True
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1144' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   HealthMailbox0659cc1                                                                                                                                                                                                
        Full Name   :   HealthMailbox-EXCH01-010
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Thu, 19 Sep 2019 07:57:59 EDT
        Password can change Time :      Fri, 20 Sep 2019 07:57:59 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x478
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1131' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   SM_c75ee099d0a64c91b                                                                                                                                                                                                
        Full Name   :   Microsoft Exchange
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 31 Dec 1969 19:00:00 EST
        unknown_2[0..31]...
        user_rid :      0x46b
        group_rid:      0x201
        acb_info :      0x00020011
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : False
        Account locked out       : False
        Password expired         : True
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1128' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   SM_1b41c9286325456bb                                                                                                                                                                                                
        Full Name   :   Microsoft Exchange Migration
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 31 Dec 1969 19:00:00 EST
        unknown_2[0..31]...
        user_rid :      0x468
        group_rid:      0x201
        acb_info :      0x00020011
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : False
        Account locked out       : False
        Password expired         : True
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 503' '10.129.149.11' 2>&1                                                                                          
                                                                                                                                                                                                                                            
        User Name   :   DefaultAccount                                                                                                                                                                                                      
        Full Name   :
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :   A user account managed by the system.
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x1f7
        group_rid:      0x201
        acb_info :      0x00000215
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1146' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   lucinda                                                                                                                                                                                                             
        Full Name   :   Lucinda Berger
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Thu, 19 Sep 2019 20:44:13 EDT
        Password can change Time :      Fri, 20 Sep 2019 20:44:13 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x47a
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1126' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   SM_75a538d3025e4db9a                                                                                                                                                                                                
        Full Name   :   Microsoft Exchange
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 31 Dec 1969 19:00:00 EST
        unknown_2[0..31]...
        user_rid :      0x466
        group_rid:      0x201
        acb_info :      0x00020011
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : False
        Account locked out       : False
        Password expired         : True
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1147' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   svc-alfresco                                                                                                                                                                                                        
        Full Name   :   svc-alfresco
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Mon, 23 Sep 2019 07:09:48 EDT
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 31 Dec 1969 19:00:00 EST
        Password last set Time   :      Tue, 19 Aug 2025 10:30:25 EDT
        Password can change Time :      Wed, 20 Aug 2025 10:30:25 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x47b
        group_rid:      0x201
        acb_info :      0x00010210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000006
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1127' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   SM_681f53d4942840e18                                                                                                                                                                                                
        Full Name   :   Discovery Search Mailbox
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 31 Dec 1969 19:00:00 EST
        unknown_2[0..31]...
        user_rid :      0x467
        group_rid:      0x201
        acb_info :      0x00020011
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : False
        Account locked out       : False
        Password expired         : True
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 502' '10.129.149.11' 2>&1                                                                                          
                                                                                                                                                                                                                                            
        User Name   :   krbtgt                                                                                                                                                                                                              
        Full Name   :
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :   Key Distribution Center Service Account
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 18 Sep 2019 06:53:23 EDT
        Password can change Time :      Thu, 19 Sep 2019 06:53:23 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x1f6
        group_rid:      0x201
        acb_info :      0x00000011
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : False
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1141' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   HealthMailboxfd87238                                                                                                                                                                                                
        Full Name   :   HealthMailbox-EXCH01-007
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Thu, 19 Sep 2019 07:57:27 EDT
        Password can change Time :      Fri, 20 Sep 2019 07:57:27 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x475
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1134' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   HealthMailboxc3d7722                                                                                                                                                                                                
        Full Name   :   HealthMailbox-EXCH01-Mailbox-Database-1118319013
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Mon, 23 Sep 2019 18:57:12 EDT
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Mon, 23 Sep 2019 18:51:32 EDT
        Password can change Time :      Tue, 24 Sep 2019 18:51:32 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x46e
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x000005be
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1151' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   mark                                                                                                                                                                                                                
        Full Name   :   Mark Brandt
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Fri, 20 Sep 2019 18:57:30 EDT
        Password can change Time :      Sat, 21 Sep 2019 18:57:30 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x47f
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1138' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   HealthMailbox968e74d                                                                                                                                                                                                
        Full Name   :   HealthMailbox-EXCH01-004
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Thu, 19 Sep 2019 07:56:56 EDT
        Password can change Time :      Fri, 20 Sep 2019 07:56:56 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x472
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1137' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   HealthMailbox670628e                                                                                                                                                                                                
        Full Name   :   HealthMailbox-EXCH01-003
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Thu, 19 Sep 2019 07:56:46 EDT
        Password can change Time :      Fri, 20 Sep 2019 07:56:46 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x471
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1136' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   HealthMailboxc0a90c9                                                                                                                                                                                                
        Full Name   :   HealthMailbox-EXCH01-002
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Thu, 19 Sep 2019 07:56:35 EDT
        Password can change Time :      Fri, 20 Sep 2019 07:56:35 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x470
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1129' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   SM_9b69f1b9d2cc45549                                                                                                                                                                                                
        Full Name   :   Microsoft Exchange Federation Mailbox
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 31 Dec 1969 19:00:00 EST
        unknown_2[0..31]...
        user_rid :      0x469
        group_rid:      0x201
        acb_info :      0x00020011
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : False
        Account locked out       : False
        Password expired         : True
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1130' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   SM_7c96b981967141ebb                                                                                                                                                                                                
        Full Name   :   E4E Encryption Store - Active
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 31 Dec 1969 19:00:00 EST
        unknown_2[0..31]...
        user_rid :      0x46a
        group_rid:      0x201
        acb_info :      0x00020011
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : False
        Account locked out       : False
        Password expired         : True
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1123' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   $331000-VK4ADACQNUCA                                                                                                                                                                                                
        Full Name   :
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 31 Dec 1969 19:00:00 EST
        unknown_2[0..31]...
        user_rid :      0x463
        group_rid:      0x201
        acb_info :      0x00020015
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : False
        Account locked out       : False
        Password expired         : True
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1143' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   HealthMailbox7108a4e                                                                                                                                                                                                
        Full Name   :   HealthMailbox-EXCH01-009
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Thu, 19 Sep 2019 07:57:48 EDT
        Password can change Time :      Fri, 20 Sep 2019 07:57:48 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x477
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 500' '10.129.149.11' 2>&1                                                                                          
                                                                                                                                                                                                                                            
        User Name   :   Administrator                                                                                                                                                                                                       
        Full Name   :   Administrator
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :   Built-in account for administering the computer/domain
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Tue, 19 Aug 2025 09:39:37 EDT
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 31 Dec 1969 19:00:00 EST
        Password last set Time   :      Mon, 30 Aug 2021 20:51:59 EDT
        Password can change Time :      Tue, 31 Aug 2021 20:51:59 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x1f4
        group_rid:      0x201
        acb_info :      0x00000010
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000086
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : False
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1135' '10.129.149.11' 2>&1
                                                                                                                                                                                                                                           
        User Name   :   HealthMailboxfc9daad                                                                                                                                                                                                
        Full Name   :   HealthMailbox-EXCH01-001
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Mon, 23 Sep 2019 18:52:06 EDT
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Mon, 23 Sep 2019 18:51:35 EDT
        Password can change Time :      Tue, 24 Sep 2019 18:51:35 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x46f
        group_rid:      0x201
        acb_info :      0x00000210
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x0000003b
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1132' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   SM_1ffab36a2f5f479cb                                                                                                                                                                                                
        Full Name   :   SystemMailbox{8cc370d3-822a-4ab8-a926-bb94bd0641a9}
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 31 Dec 1969 19:00:00 EST
        unknown_2[0..31]...
        user_rid :      0x46c
        group_rid:      0x201
        acb_info :      0x00020011
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : False
        Account locked out       : False
        Password expired         : True
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False


 =================================( Share Enumeration on 10.129.149.11 )=================================
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get share list using authentication                                                                                                                                                                                       
                                                                                                                                                                                                                                            
do_connect: Connection to 10.129.149.11 failed (Error NT_STATUS_RESOURCE_NAME_NOT_FOUND)                                                                                                                                                    

        Sharename       Type      Comment
        ---------       ----      -------
        ADMIN$          Disk      Remote Admin
        C$              Disk      Default share
        IPC$            IPC       Remote IPC
        NETLOGON        Disk      Logon server share 
        SYSVOL          Disk      Logon server share 
Reconnecting with SMB1 for workgroup listing.
Unable to connect with SMB1 -- no workgroup available

[+] Attempting to map shares on 10.129.149.11                                                                                                                                                                                               
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting map to share //10.129.149.11/ADMIN$ with command: smbclient -W 'htb.local' //'10.129.149.11'/'ADMIN$' -U'svc-alfresco'%'s3rvice' -c dir 2>&1                                                                                 
                                                                                                                                                                                                                                            
//10.129.149.11/ADMIN$  Mapping: DENIED Listing: N/A Writing: N/A                                                                                                                                                                           

[V] Attempting map to share //10.129.149.11/C$ with command: smbclient -W 'htb.local' //'10.129.149.11'/'C$' -U'svc-alfresco'%'s3rvice' -c dir 2>&1                                                                                         
                                                                                                                                                                                                                                            
//10.129.149.11/C$      Mapping: DENIED Listing: N/A Writing: N/A                                                                                                                                                                           

[V] Attempting map to share //10.129.149.11/IPC$ with command: smbclient -W 'htb.local' //'10.129.149.11'/'IPC$' -U'svc-alfresco'%'s3rvice' -c dir 2>&1                                                                                     
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] Can't understand response:                                                                                                                                                                                                              
                                                                                                                                                                                                                                            
NT_STATUS_NO_SUCH_FILE listing \*                                                                                                                                                                                                           
//10.129.149.11/IPC$    Mapping: N/A Listing: N/A Writing: N/A

[V] Attempting map to share //10.129.149.11/NETLOGON with command: smbclient -W 'htb.local' //'10.129.149.11'/'NETLOGON' -U'svc-alfresco'%'s3rvice' -c dir 2>&1                                                                             
                                                                                                                                                                                                                                            
//10.129.149.11/NETLOGON        Mapping: OK Listing: OK Writing: N/A                                                                                                                                                                        

[V] Attempting map to share //10.129.149.11/SYSVOL with command: smbclient -W 'htb.local' //'10.129.149.11'/'SYSVOL' -U'svc-alfresco'%'s3rvice' -c dir 2>&1                                                                                 
                                                                                                                                                                                                                                            
//10.129.149.11/SYSVOL  Mapping: OK Listing: OK Writing: N/A                                                                                                                                                                                

 ===========================( Password Policy Information for 10.129.149.11 )===========================
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get Password Policy info with command: polenum 'svc-alfresco':'s3rvice'@'10.129.149.11' 2>&1                                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            

[+] Attaching to 10.129.149.11 using svc-alfresco:s3rvice

[+] Trying protocol 139/SMB...

        [!] Protocol failed: Cannot request session (Called Name:10.129.149.11)

[+] Trying protocol 445/SMB...

[+] Found domain(s):

        [+] HTB
        [+] Builtin

[+] Password Info for Domain: HTB

        [+] Minimum password length: 7
        [+] Password history length: 24
        [+] Maximum password age: Not Set
        [+] Password Complexity Flags: 000000

                [+] Domain Refuse Password Change: 0
                [+] Domain Password Store Cleartext: 0
                [+] Domain Password Lockout Admins: 0
                [+] Domain Password No Clear Change: 0
                [+] Domain Password No Anon Change: 0
                [+] Domain Password Complex: 0

        [+] Minimum password age: 1 day 4 minutes 
        [+] Reset Account Lockout Counter: 30 minutes 
        [+] Locked Account Duration: 30 minutes 
        [+] Account Lockout Threshold: None
        [+] Forced Log off Time: Not Set


[V] Attempting to get Password Policy info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' '10.129.149.11' -c "getdompwinfo" 2>&1                                                                                         
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            

[+] Retieved partial password policy with rpcclient:                                                                                                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Password Complexity: Disabled                                                                                                                                                                                                               
Minimum Password Length: 7


 ======================================( Groups on 10.129.149.11 )======================================
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Getting builtin groups with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' '10.129.149.11' -c 'enumalsgroups builtin' 2>&1                                                                                                
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting builtin groups:                                                                                                                                                                                                                 
                                                                                                                                                                                                                                            
group:[Account Operators] rid:[0x224]                                                                                                                                                                                                       
group:[Pre-Windows 2000 Compatible Access] rid:[0x22a]
group:[Incoming Forest Trust Builders] rid:[0x22d]
group:[Windows Authorization Access Group] rid:[0x230]
group:[Terminal Server License Servers] rid:[0x231]
group:[Administrators] rid:[0x220]
group:[Users] rid:[0x221]
group:[Guests] rid:[0x222]
group:[Print Operators] rid:[0x226]
group:[Backup Operators] rid:[0x227]
group:[Replicator] rid:[0x228]
group:[Remote Desktop Users] rid:[0x22b]
group:[Network Configuration Operators] rid:[0x22c]
group:[Performance Monitor Users] rid:[0x22e]
group:[Performance Log Users] rid:[0x22f]
group:[Distributed COM Users] rid:[0x232]
group:[IIS_IUSRS] rid:[0x238]
group:[Cryptographic Operators] rid:[0x239]
group:[Event Log Readers] rid:[0x23d]
group:[Certificate Service DCOM Access] rid:[0x23e]
group:[RDS Remote Access Servers] rid:[0x23f]
group:[RDS Endpoint Servers] rid:[0x240]
group:[RDS Management Servers] rid:[0x241]
group:[Hyper-V Administrators] rid:[0x242]
group:[Access Control Assistance Operators] rid:[0x243]
group:[Remote Management Users] rid:[0x244]
group:[System Managed Accounts Group] rid:[0x245]
group:[Storage Replica Administrators] rid:[0x246]
group:[Server Operators] rid:[0x225]

[+]  Getting builtin group memberships:                                                                                                                                                                                                     
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Network Configuration Operators' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Remote Management Users' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: Remote Management Users' (RID: 580) has member: HTB\Privileged IT Accounts                                                                                                                                                           

[V] Running command: net rpc group members 'Performance Log Users' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Guests' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: Guests' (RID: 546) has member: HTB\Guest                                                                                                                                                                                             
Group: Guests' (RID: 546) has member: HTB\Domain Guests

[V] Running command: net rpc group members 'Incoming Forest Trust Builders' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                               
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'RDS Remote Access Servers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                    
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Distributed COM Users' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Replicator' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                                   
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Cryptographic Operators' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Storage Replica Administrators' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                               
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Access Control Assistance Operators' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                          
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Terminal Server License Servers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Backup Operators' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Windows Authorization Access Group' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: Windows Authorization Access Group' (RID: 560) has member: NT AUTHORITY\ENTERPRISE DOMAIN CONTROLLERS                                                                                                                                
Group: Windows Authorization Access Group' (RID: 560) has member: HTB\Exchange Servers

[V] Running command: net rpc group members 'Remote Desktop Users' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                         
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'RDS Endpoint Servers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                         
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Event Log Readers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'RDS Management Servers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Print Operators' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Account Operators' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: Account Operators' (RID: 548) has member: HTB\Privileged IT Accounts                                                                                                                                                                 

[V] Running command: net rpc group members 'Hyper-V Administrators' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Certificate Service DCOM Access' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Users' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: Users' (RID: 545) has member: NT AUTHORITY\INTERACTIVE                                                                                                                                                                               
Group: Users' (RID: 545) has member: NT AUTHORITY\Authenticated Users
Group: Users' (RID: 545) has member: HTB\Domain Users

[V] Running command: net rpc group members 'IIS_IUSRS' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                                    
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: IIS_IUSRS' (RID: 568) has member: NT AUTHORITY\IUSR                                                                                                                                                                                  

[V] Running command: net rpc group members 'Server Operators' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Administrators' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                               
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: Administrators' (RID: 544) has member: HTB\Administrator                                                                                                                                                                             
Group: Administrators' (RID: 544) has member: HTB\Enterprise Admins
Group: Administrators' (RID: 544) has member: HTB\Domain Admins

[V] Running command: net rpc group members 'Pre-Windows 2000 Compatible Access' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: Pre-Windows 2000 Compatible Access' (RID: 554) has member: NT AUTHORITY\ANONYMOUS LOGON                                                                                                                                              
Group: Pre-Windows 2000 Compatible Access' (RID: 554) has member: \Everyone

[V] Running command: net rpc group members 'System Managed Accounts Group' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: System Managed Accounts Group' (RID: 581) has member: HTB\DefaultAccount                                                                                                                                                             

[V] Running command: net rpc group members 'Performance Monitor Users' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                    
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Network Configuration Operators (RID: 556)                                                                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 556' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Remote Management Users (RID: 580)                                                                                                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 580' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Performance Log Users (RID: 559)                                                                                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 559' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Guests (RID: 546)                                                                                                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 546' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Incoming Forest Trust Builders (RID: 557)                                                                                                                                                               
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 557' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group RDS Remote Access Servers (RID: 575)                                                                                                                                                                    
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 575' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Distributed COM Users (RID: 562)                                                                                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 562' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Replicator (RID: 552)                                                                                                                                                                                   
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 552' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Cryptographic Operators (RID: 569)                                                                                                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 569' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Storage Replica Administrators (RID: 582)                                                                                                                                                               
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 582' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Access Control Assistance Operators (RID: 579)                                                                                                                                                          
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 579' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Terminal Server License Servers (RID: 561)                                                                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 561' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Backup Operators (RID: 551)                                                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 551' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Windows Authorization Access Group (RID: 560)                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 560' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Remote Desktop Users (RID: 555)                                                                                                                                                                         
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 555' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group RDS Endpoint Servers (RID: 576)                                                                                                                                                                         
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 576' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Event Log Readers (RID: 573)                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 573' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group RDS Management Servers (RID: 577)                                                                                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 577' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Print Operators (RID: 550)                                                                                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 550' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Account Operators (RID: 548)                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 548' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Hyper-V Administrators (RID: 578)                                                                                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 578' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Certificate Service DCOM Access (RID: 574)                                                                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 574' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Users (RID: 545)                                                                                                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 545' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group IIS_IUSRS (RID: 568)                                                                                                                                                                                    
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 568' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Server Operators (RID: 549)                                                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 549' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Administrators (RID: 544)                                                                                                                                                                               
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 544' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Pre-Windows 2000 Compatible Access (RID: 554)                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 554' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group System Managed Accounts Group (RID: 581)                                                                                                                                                                
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 581' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Performance Monitor Users (RID: 558)                                                                                                                                                                    
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 558' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Getting local groups with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' '10.129.149.11' -c 'enumalsgroups domain' 2>&1                                                                                                   
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+]  Getting local groups:                                                                                                                                                                                                                  
                                                                                                                                                                                                                                            
group:[Cert Publishers] rid:[0x205]                                                                                                                                                                                                         
group:[RAS and IAS Servers] rid:[0x229]
group:[Allowed RODC Password Replication Group] rid:[0x23b]
group:[Denied RODC Password Replication Group] rid:[0x23c]
group:[DnsAdmins] rid:[0x44d]

[+]  Getting local group memberships:                                                                                                                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'RAS and IAS Servers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                          
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Denied RODC Password Replication Group' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: Denied RODC Password Replication Group' (RID: 572) has member: HTB\krbtgt                                                                                                                                                            
Group: Denied RODC Password Replication Group' (RID: 572) has member: HTB\Domain Controllers
Group: Denied RODC Password Replication Group' (RID: 572) has member: HTB\Schema Admins
Group: Denied RODC Password Replication Group' (RID: 572) has member: HTB\Enterprise Admins
Group: Denied RODC Password Replication Group' (RID: 572) has member: HTB\Cert Publishers
Group: Denied RODC Password Replication Group' (RID: 572) has member: HTB\Domain Admins
Group: Denied RODC Password Replication Group' (RID: 572) has member: HTB\Group Policy Creator Owners
Group: Denied RODC Password Replication Group' (RID: 572) has member: HTB\Read-only Domain Controllers

[V] Running command: net rpc group members 'Cert Publishers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'DnsAdmins' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                                    
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Allowed RODC Password Replication Group' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group RAS and IAS Servers (RID: 553)                                                                                                                                                                          
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 553' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Denied RODC Password Replication Group (RID: 572)                                                                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 572' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Cert Publishers (RID: 517)                                                                                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 517' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group DnsAdmins (RID: 1101)                                                                                                                                                                                   
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1101' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Allowed RODC Password Replication Group (RID: 571)                                                                                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 571' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Getting domain groups with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' '10.129.149.11' -c "enumdomgroups" 2>&1                                                                                                         
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+]  Getting domain groups:                                                                                                                                                                                                                 
                                                                                                                                                                                                                                            
group:[Enterprise Read-only Domain Controllers] rid:[0x1f2]                                                                                                                                                                                 
group:[Domain Admins] rid:[0x200]
group:[Domain Users] rid:[0x201]
group:[Domain Guests] rid:[0x202]
group:[Domain Computers] rid:[0x203]
group:[Domain Controllers] rid:[0x204]
group:[Schema Admins] rid:[0x206]
group:[Enterprise Admins] rid:[0x207]
group:[Group Policy Creator Owners] rid:[0x208]
group:[Read-only Domain Controllers] rid:[0x209]
group:[Cloneable Domain Controllers] rid:[0x20a]
group:[Protected Users] rid:[0x20d]
group:[Key Admins] rid:[0x20e]
group:[Enterprise Key Admins] rid:[0x20f]
group:[DnsUpdateProxy] rid:[0x44e]
group:[Organization Management] rid:[0x450]
group:[Recipient Management] rid:[0x451]
group:[View-Only Organization Management] rid:[0x452]
group:[Public Folder Management] rid:[0x453]
group:[UM Management] rid:[0x454]
group:[Help Desk] rid:[0x455]
group:[Records Management] rid:[0x456]
group:[Discovery Management] rid:[0x457]
group:[Server Management] rid:[0x458]
group:[Delegated Setup] rid:[0x459]
group:[Hygiene Management] rid:[0x45a]
group:[Compliance Management] rid:[0x45b]
group:[Security Reader] rid:[0x45c]
group:[Security Administrator] rid:[0x45d]
group:[Exchange Servers] rid:[0x45e]
group:[Exchange Trusted Subsystem] rid:[0x45f]
group:[Managed Availability Servers] rid:[0x460]
group:[Exchange Windows Permissions] rid:[0x461]
group:[ExchangeLegacyInterop] rid:[0x462]
group:[$D31000-NSEL5BRJ63V7] rid:[0x46d]
group:[Service Accounts] rid:[0x47c]
group:[Privileged IT Accounts] rid:[0x47d]
group:[test] rid:[0x13ed]

[+]  Getting domain group memberships:                                                                                                                                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Key Admins' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                                   
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Enterprise Read-only Domain Controllers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Records Management' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Organization Management' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Organization Management' (RID: 1104) has member: HTB\Administrator                                                                                                                                                                  

[V] Running command: net rpc group members 'Read-only Domain Controllers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                 
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Cloneable Domain Controllers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                 
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Security Administrator' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Recipient Management' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                         
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Domain Controllers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Domain Controllers' (RID: 516) has member: HTB\FOREST$                                                                                                                                                                              

[V] Running command: net rpc group members 'Hygiene Management' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Group Policy Creator Owners' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                  
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Group Policy Creator Owners' (RID: 520) has member: HTB\Administrator                                                                                                                                                               

[V] Running command: net rpc group members 'Privileged IT Accounts' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Privileged IT Accounts' (RID: 1149) has member: HTB\Service Accounts                                                                                                                                                                

[V] Running command: net rpc group members 'Exchange Windows Permissions' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                 
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Exchange Windows Permissions' (RID: 1121) has member: HTB\Exchange Trusted Subsystem                                                                                                                                                

[V] Running command: net rpc group members 'Domain Admins' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                                
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Domain Admins' (RID: 512) has member: HTB\Administrator                                                                                                                                                                             

[V] Running command: net rpc group members '$D31000-NSEL5BRJ63V7' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                         
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: '$D31000-NSEL5BRJ63V7' (RID: 1133) has member: HTB\EXCH01$                                                                                                                                                                           

[V] Running command: net rpc group members 'test' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                                         
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'ExchangeLegacyInterop' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Protected Users' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Server Management' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Managed Availability Servers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                 
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Managed Availability Servers' (RID: 1120) has member: HTB\EXCH01$                                                                                                                                                                   
Group: 'Managed Availability Servers' (RID: 1120) has member: HTB\Exchange Servers

[V] Running command: net rpc group members 'Exchange Trusted Subsystem' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                   
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Exchange Trusted Subsystem' (RID: 1119) has member: HTB\EXCH01$                                                                                                                                                                     

[V] Running command: net rpc group members 'Schema Admins' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                                
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Schema Admins' (RID: 518) has member: HTB\Administrator                                                                                                                                                                             

[V] Running command: net rpc group members 'Delegated Setup' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Service Accounts' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Service Accounts' (RID: 1148) has member: HTB\svc-alfresco                                                                                                                                                                          

[V] Running command: net rpc group members 'Enterprise Admins' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Enterprise Admins' (RID: 519) has member: Could not initialise pipe samr. Error was NT_STATUS_INVALID_NETWORK_RESPONSE                                                                                                              

[V] Running command: net rpc group members 'Security Reader' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Enterprise Key Admins' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'DnsUpdateProxy' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                               
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'View-Only Organization Management' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Public Folder Management' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                     
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'UM Management' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                                
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Domain Guests' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                                
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Domain Guests' (RID: 514) has member: HTB\Guest                                                                                                                                                                                     

[V] Running command: net rpc group members 'Exchange Servers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Exchange Servers' (RID: 1118) has member: HTB\EXCH01$                                                                                                                                                                               
Group: 'Exchange Servers' (RID: 1118) has member: HTB\$D31000-NSEL5BRJ63V7

[V] Running command: net rpc group members 'Domain Computers' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Domain Computers' (RID: 515) has member: HTB\EXCH01$                                                                                                                                                                                

[V] Running command: net rpc group members 'Domain Users' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                                 
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
Group: 'Domain Users' (RID: 513) has member: HTB\Administrator                                                                                                                                                                              
Group: 'Domain Users' (RID: 513) has member: HTB\DefaultAccount
Group: 'Domain Users' (RID: 513) has member: HTB\krbtgt
Group: 'Domain Users' (RID: 513) has member: HTB\$331000-VK4ADACQNUCA
Group: 'Domain Users' (RID: 513) has member: HTB\SM_2c8eef0a09b545acb
Group: 'Domain Users' (RID: 513) has member: HTB\SM_ca8c2ed5bdab4dc9b
Group: 'Domain Users' (RID: 513) has member: HTB\SM_75a538d3025e4db9a
Group: 'Domain Users' (RID: 513) has member: HTB\SM_681f53d4942840e18
Group: 'Domain Users' (RID: 513) has member: HTB\SM_1b41c9286325456bb
Group: 'Domain Users' (RID: 513) has member: HTB\SM_9b69f1b9d2cc45549
Group: 'Domain Users' (RID: 513) has member: HTB\SM_7c96b981967141ebb
Group: 'Domain Users' (RID: 513) has member: HTB\SM_c75ee099d0a64c91b
Group: 'Domain Users' (RID: 513) has member: HTB\SM_1ffab36a2f5f479cb
Group: 'Domain Users' (RID: 513) has member: HTB\HealthMailboxc3d7722
Group: 'Domain Users' (RID: 513) has member: HTB\HealthMailboxfc9daad
Group: 'Domain Users' (RID: 513) has member: HTB\HealthMailboxc0a90c9
Group: 'Domain Users' (RID: 513) has member: HTB\HealthMailbox670628e
Group: 'Domain Users' (RID: 513) has member: HTB\HealthMailbox968e74d
Group: 'Domain Users' (RID: 513) has member: HTB\HealthMailbox6ded678
Group: 'Domain Users' (RID: 513) has member: HTB\HealthMailbox83d6781
Group: 'Domain Users' (RID: 513) has member: HTB\HealthMailboxfd87238
Group: 'Domain Users' (RID: 513) has member: HTB\HealthMailboxb01ac64
Group: 'Domain Users' (RID: 513) has member: HTB\HealthMailbox7108a4e
Group: 'Domain Users' (RID: 513) has member: HTB\HealthMailbox0659cc1
Group: 'Domain Users' (RID: 513) has member: HTB\sebastien
Group: 'Domain Users' (RID: 513) has member: HTB\lucinda
Group: 'Domain Users' (RID: 513) has member: HTB\svc-alfresco
Group: 'Domain Users' (RID: 513) has member: HTB\andy
Group: 'Domain Users' (RID: 513) has member: HTB\mark
Group: 'Domain Users' (RID: 513) has member: HTB\santi

[V] Running command: net rpc group members 'Help Desk' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                                    
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Discovery Management' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                         
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Running command: net rpc group members 'Compliance Management' -W 'htb.local' -I '10.129.149.11' -U'svc-alfresco'%'s3rvice' 2>&1                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Getting detailed info for group Key Admins (RID: 526)                                                                                                                                                                                   
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 526' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Key Admins                                                                                                                                                                                                          
        Description:    Members of this group can perform administrative actions on key objects within the domain.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Enterprise Read-only Domain Controllers (RID: 498)                                                                                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 498' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Enterprise Read-only Domain Controllers                                                                                                                                                                             
        Description:    Members of this group are Read-Only Domain Controllers in the enterprise
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Records Management (RID: 1110)                                                                                                                                                                          
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1110' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Records Management                                                                                                                                                                                                  
        Description:    Members of this management role group can configure compliance features such as retention policy tags, message classifications, transport rules, and more.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Organization Management (RID: 1104)                                                                                                                                                                     
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1104' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Organization Management                                                                                                                                                                                             
        Description:    Members of this management role group have permissions to manage Exchange objects and their properties in the Exchange organization. Members can also delegate role groups and management roles in the organization. This role group shouldn't be deleted.
        Group Attribute:7
        Num Members:1


[+] Getting detailed info for group Read-only Domain Controllers (RID: 521)                                                                                                                                                                 
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 521' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Read-only Domain Controllers                                                                                                                                                                                        
        Description:    Members of this group are Read-Only Domain Controllers in the domain
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Cloneable Domain Controllers (RID: 522)                                                                                                                                                                 
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 522' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Cloneable Domain Controllers                                                                                                                                                                                        
        Description:    Members of this group that are domain controllers may be cloned.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Security Administrator (RID: 1117)                                                                                                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1117' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Security Administrator                                                                                                                                                                                              
        Description:    Membership in this role group is synchronized across services and managed centrally. This role group is not manageable through the administrator portals. Members of this role group may include cross-service administrators, as well as external partner groups and Microsoft Support. By default, this group may not be assigned any roles. However, it will be a member of the Security Administrators role groups and will inherit the capabilities of that role group.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Recipient Management (RID: 1105)                                                                                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1105' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Recipient Management                                                                                                                                                                                                
        Description:    Members of this management role group have rights to create, manage, and remove Exchange recipient objects in the Exchange organization.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Domain Controllers (RID: 516)                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 516' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Domain Controllers                                                                                                                                                                                                  
        Description:    All domain controllers in the domain
        Group Attribute:7
        Num Members:1


[+] Getting detailed info for group Hygiene Management (RID: 1114)                                                                                                                                                                          
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1114' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Hygiene Management                                                                                                                                                                                                  
        Description:    Members of this management role group can manage Exchange anti-spam features and grant permissions for antivirus products to integrate with Exchange.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Group Policy Creator Owners (RID: 520)                                                                                                                                                                  
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 520' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Group Policy Creator Owners                                                                                                                                                                                         
        Description:    Members in this group can modify group policy for the domain
        Group Attribute:7
        Num Members:1


[+] Getting detailed info for group Privileged IT Accounts (RID: 1149)                                                                                                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1149' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Privileged IT Accounts                                                                                                                                                                                              
        Description:
        Group Attribute:7
        Num Members:1


[+] Getting detailed info for group Exchange Windows Permissions (RID: 1121)                                                                                                                                                                
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1121' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Exchange Windows Permissions                                                                                                                                                                                        
        Description:    This group contains Exchange servers that run Exchange cmdlets on behalf of users via the management service. Its members have permission to read and modify all Windows accounts and groups. This group should not be deleted.
        Group Attribute:7
        Num Members:1


[+] Getting detailed info for group Domain Admins (RID: 512)                                                                                                                                                                                
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 512' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Domain Admins                                                                                                                                                                                                       
        Description:    Designated administrators of the domain
        Group Attribute:7
        Num Members:1


[+] Getting detailed info for group $D31000-NSEL5BRJ63V7 (RID: 1133)                                                                                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1133' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     $D31000-NSEL5BRJ63V7                                                                                                                                                                                                
        Description:    This group is used during Exchange setup and is not intended to be used for other purposes.
        Group Attribute:7
        Num Members:1


[+] Getting detailed info for group test (RID: 5101)                                                                                                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 5101' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     test                                                                                                                                                                                                                
        Description:
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group ExchangeLegacyInterop (RID: 1122)                                                                                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1122' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     ExchangeLegacyInterop                                                                                                                                                                                               
        Description:    This group is for interoperability with Exchange 2003 servers within the same forest. This group should not be deleted.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Protected Users (RID: 525)                                                                                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 525' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Protected Users                                                                                                                                                                                                     
        Description:    Members of this group are afforded additional protections against authentication security threats. See http://go.microsoft.com/fwlink/?LinkId=298939 for more information.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Server Management (RID: 1112)                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1112' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Server Management                                                                                                                                                                                                   
        Description:    Members of this management role group have permissions to manage all Exchange servers within the Exchange organization, but members don't have permissions to perform operations that have global impact in the Exchange organization.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Managed Availability Servers (RID: 1120)                                                                                                                                                                
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1120' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Managed Availability Servers                                                                                                                                                                                        
        Description:    This group contains all the Managed Availability servers. This group shouldn't be deleted.
        Group Attribute:7
        Num Members:2


[+] Getting detailed info for group Exchange Trusted Subsystem (RID: 1119)                                                                                                                                                                  
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1119' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Exchange Trusted Subsystem                                                                                                                                                                                          
        Description:    This group contains Exchange servers that run Exchange cmdlets on behalf of users via the management service. Its members have permission to read and modify all Exchange configuration, as well as user accounts and groups. This group should not be deleted.
        Group Attribute:7
        Num Members:1


[+] Getting detailed info for group Schema Admins (RID: 518)                                                                                                                                                                                
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 518' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Schema Admins                                                                                                                                                                                                       
        Description:    Designated administrators of the schema
        Group Attribute:7
        Num Members:1


[+] Getting detailed info for group Delegated Setup (RID: 1113)                                                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1113' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Delegated Setup                                                                                                                                                                                                     
        Description:    Members of this management role group have permissions to install and uninstall Exchange on provisioned servers. This role group shouldn't be deleted.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Service Accounts (RID: 1148)                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1148' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Service Accounts                                                                                                                                                                                                    
        Description:
        Group Attribute:7
        Num Members:1


[+] Getting detailed info for group Enterprise Admins (RID: 519)                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 519' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Enterprise Admins                                                                                                                                                                                                   
        Description:    Designated administrators of the enterprise
        Group Attribute:7
        Num Members:1


[+] Getting detailed info for group Security Reader (RID: 1116)                                                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1116' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Security Reader                                                                                                                                                                                                     
        Description:    Membership in this role group is synchronized across services and managed centrally. This role group is not manageable through the administrator portals. Members of this role group may include cross-service administrators, as well as external partner groups and Microsoft Support. By default, this group may not be assigned any roles. However, it will be a member of the Security Reader role groups and will inherit the capabilities of that role group.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Enterprise Key Admins (RID: 527)                                                                                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 527' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Enterprise Key Admins                                                                                                                                                                                               
        Description:    Members of this group can perform administrative actions on key objects within the forest.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group DnsUpdateProxy (RID: 1102)                                                                                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1102' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     DnsUpdateProxy                                                                                                                                                                                                      
        Description:    DNS clients who are permitted to perform dynamic updates on behalf of some other clients (such as DHCP servers).
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group View-Only Organization Management (RID: 1106)                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1106' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     View-Only Organization Management                                                                                                                                                                                   
        Description:    Members of this management role group can view recipient and configuration objects and their properties in the Exchange organization.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Public Folder Management (RID: 1107)                                                                                                                                                                    
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1107' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Public Folder Management                                                                                                                                                                                            
        Description:    Members of this management role group can manage public folders. Members can create and delete public folders and manage public folder settings such as replicas, quotas, age limits, and permissions as well as mail-enable and mail-disable public folders.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group UM Management (RID: 1108)                                                                                                                                                                               
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1108' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     UM Management                                                                                                                                                                                                       
        Description:    Members of this management role group can manage Unified Messaging organization, server, and recipient configuration.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Domain Guests (RID: 514)                                                                                                                                                                                
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 514' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Domain Guests                                                                                                                                                                                                       
        Description:    All domain guests
        Group Attribute:7
        Num Members:1


[+] Getting detailed info for group Exchange Servers (RID: 1118)                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1118' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Exchange Servers                                                                                                                                                                                                    
        Description:    This group contains all the Exchange servers. This group shouldn't be deleted.
        Group Attribute:7
        Num Members:2


[+] Getting detailed info for group Domain Computers (RID: 515)                                                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 515' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Domain Computers                                                                                                                                                                                                    
        Description:    All workstations and servers joined to the domain
        Group Attribute:7
        Num Members:1


[+] Getting detailed info for group Domain Users (RID: 513)                                                                                                                                                                                 
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 513' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Domain Users                                                                                                                                                                                                        
        Description:    All domain users
        Group Attribute:7
        Num Members:30


[+] Getting detailed info for group Help Desk (RID: 1109)                                                                                                                                                                                   
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1109' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Help Desk                                                                                                                                                                                                           
        Description:    Members of this management role group can view and manage the configuration for individual recipients and view recipients in an Exchange organization. Members of this role group can only manage the configuration each user can manage on his or her own mailbox. Additional  permissions can be added by assigning additional management roles to this role group.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Discovery Management (RID: 1111)                                                                                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1111' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Discovery Management                                                                                                                                                                                                
        Description:    Members of this management role group can perform searches of mailboxes in the Exchange organization for data that meets specific criteria.
        Group Attribute:7
        Num Members:0


[+] Getting detailed info for group Compliance Management (RID: 1115)                                                                                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 1115' '10.129.149.11' 2>&1                                                                                       
                                                                                                                                                                                                                                            
        Group Name:     Compliance Management                                                                                                                                                                                               
        Description:    This role group will allow a specified user, responsible for compliance, to properly configure and manage compliance settings within Exchange in accordance with their policy.
        Group Attribute:7
        Num Members:0


 ==================( Users on 10.129.149.11 via RID cycling (RIDS: 500-550,1000-1050) )==================
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get SID from 10.129.149.11 with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' '10.129.149.11' -c 'lookupnames administrator' 2>&1                                                                          
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Assuming that user "administrator" exists                                                                                                                                                                                               
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get SID from 10.129.149.11 with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' '10.129.149.11' -c 'lookupnames guest' 2>&1                                                                                  
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Assuming that user "guest" exists                                                                                                                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[I] Found new SID:                                                                                                                                                                                                                          
S-1-5-21-3072663084-364016917-1341370565                                                                                                                                                                                                    

[V] Attempting to get SID from 10.129.149.11 with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' '10.129.149.11' -c 'lookupnames krbtgt' 2>&1                                                                                 
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Assuming that user "krbtgt" exists                                                                                                                                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[I] Found new SID:                                                                                                                                                                                                                          
S-1-5-21-3072663084-364016917-1341370565                                                                                                                                                                                                    

[V] Attempting to get SID from 10.129.149.11 with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' '10.129.149.11' -c 'lookupnames domain admins' 2>&1                                                                          
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Assuming that user "domain admins" exists                                                                                                                                                                                               
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] User "domain admins" doesn't exist.  User enumeration should be possible, but SID needed...                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get SID from 10.129.149.11 with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' '10.129.149.11' -c 'lookupnames root' 2>&1                                                                                   
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Assuming that user "root" exists                                                                                                                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] User "root" doesn't exist.  User enumeration should be possible, but SID needed...                                                                                                                                                      
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get SID from 10.129.149.11 with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' '10.129.149.11' -c 'lookupnames bin' 2>&1                                                                                    
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Assuming that user "bin" exists                                                                                                                                                                                                         
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] User "bin" doesn't exist.  User enumeration should be possible, but SID needed...                                                                                                                                                       
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get SID from 10.129.149.11 with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' '10.129.149.11' -c 'lookupnames none' 2>&1                                                                                   
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Assuming that user "none" exists                                                                                                                                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get SIDs from 10.129.149.11 with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' '10.129.149.11' -c lsaenumsid 2>&1                                                                                          
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Processing SID S-1-5-9                                                                                                                                                                                                                  
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Processing SID S-1-5-80-3139157870-2983391045-3678747466-658725712-1809340420                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Processing SID S-1-5-80-0                                                                                                                                                                                                               
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Processing SID S-1-5-6                                                                                                                                                                                                                  
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Processing SID S-1-5-32-559                                                                                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Processing SID S-1-5-32-554                                                                                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[I] Found new SID:                                                                                                                                                                                                                          
S-1-5-32                                                                                                                                                                                                                                    

[V] Processing SID S-1-5-32-551                                                                                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[I] Found new SID:                                                                                                                                                                                                                          
S-1-5-32                                                                                                                                                                                                                                    

[V] Processing SID S-1-5-32-550                                                                                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[I] Found new SID:                                                                                                                                                                                                                          
S-1-5-32                                                                                                                                                                                                                                    

[V] Processing SID S-1-5-32-549                                                                                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[I] Found new SID:                                                                                                                                                                                                                          
S-1-5-32                                                                                                                                                                                                                                    

[V] Processing SID S-1-5-32-548                                                                                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[I] Found new SID:                                                                                                                                                                                                                          
S-1-5-32                                                                                                                                                                                                                                    

[V] Processing SID S-1-5-32-545                                                                                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[I] Found new SID:                                                                                                                                                                                                                          
S-1-5-32                                                                                                                                                                                                                                    

[V] Processing SID S-1-5-32-544                                                                                                                                                                                                             
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[I] Found new SID:                                                                                                                                                                                                                          
S-1-5-32                                                                                                                                                                                                                                    

[V] Processing SID S-1-5-21-3072663084-364016917-1341370565-1118                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[I] Found new SID:                                                                                                                                                                                                                          
S-1-5-21-3072663084-364016917-1341370565                                                                                                                                                                                                    

[V] Processing SID S-1-5-20                                                                                                                                                                                                                 
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Processing SID S-1-5-19                                                                                                                                                                                                                 
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Processing SID S-1-5-11                                                                                                                                                                                                                 
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Processing SID S-1-1-0                                                                                                                                                                                                                  
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Enumerating users using SID S-1-5-80-3139157870-2983391045-3678747466-658725712 and logon username 'svc-alfresco', password 's3rvice'                                                                                                   
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Enumerating users using SID S-1-5-21-3508106956-637366738-4258756832 and logon username 'svc-alfresco', password 's3rvice'                                                                                                              
                                                                                                                                                                                                                                            
S-1-5-21-3508106956-637366738-4258756832-500 FOREST\Administrator (Local User)                                                                                                                                                              

[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 500' '10.129.149.11' 2>&1                                                                                          
                                                                                                                                                                                                                                            
        User Name   :   Administrator                                                                                                                                                                                                       
        Full Name   :   Administrator
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :   Built-in account for administering the computer/domain
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Tue, 19 Aug 2025 09:39:37 EDT
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 31 Dec 1969 19:00:00 EST
        Password last set Time   :      Mon, 30 Aug 2021 20:51:59 EDT
        Password can change Time :      Tue, 31 Aug 2021 20:51:59 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x1f4
        group_rid:      0x201
        acb_info :      0x00000010
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000086
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : False
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False

S-1-5-21-3508106956-637366738-4258756832-501 FOREST\Guest (Local User)

[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 501' '10.129.149.11' 2>&1                                                                                          
                                                                                                                                                                                                                                            
        User Name   :   Guest                                                                                                                                                                                                               
        Full Name   :
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :   Built-in account for guest access to the computer/domain
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x1f5
        group_rid:      0x202
        acb_info :      0x00000215
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False

S-1-5-21-3508106956-637366738-4258756832-503 FOREST\DefaultAccount (Local User)

[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 503' '10.129.149.11' 2>&1                                                                                          
                                                                                                                                                                                                                                            
        User Name   :   DefaultAccount                                                                                                                                                                                                      
        Full Name   :
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :   A user account managed by the system.
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x1f7
        group_rid:      0x201
        acb_info :      0x00000215
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False

S-1-5-21-3508106956-637366738-4258756832-513 FOREST\None (Domain Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 513' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Domain Users                                                                                                                                                                                                        
        Description:    All domain users
        Group Attribute:7
        Num Members:30


[+] Enumerating users using SID S-1-5-32 and logon username 'svc-alfresco', password 's3rvice'                                                                                                                                              
                                                                                                                                                                                                                                            
S-1-5-32-544 BUILTIN\Administrators (Local Group)                                                                                                                                                                                           

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 544' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
S-1-5-32-545 BUILTIN\Users (Local Group)                                                                                                                                                                                                    

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 545' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
S-1-5-32-546 BUILTIN\Guests (Local Group)                                                                                                                                                                                                   

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 546' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
S-1-5-32-548 BUILTIN\Account Operators (Local Group)                                                                                                                                                                                        

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 548' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
S-1-5-32-549 BUILTIN\Server Operators (Local Group)                                                                                                                                                                                         

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 549' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
S-1-5-32-550 BUILTIN\Print Operators (Local Group)                                                                                                                                                                                          

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 550' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Enumerating users using SID S-1-5-80 and logon username 'svc-alfresco', password 's3rvice'                                                                                                                                              
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[+] Enumerating users using SID S-1-5-21-3072663084-364016917-1341370565 and logon username 'svc-alfresco', password 's3rvice'                                                                                                              
                                                                                                                                                                                                                                            
S-1-5-21-3072663084-364016917-1341370565-500 HTB\Administrator (Local User)                                                                                                                                                                 

[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 500' '10.129.149.11' 2>&1                                                                                          
                                                                                                                                                                                                                                            
        User Name   :   Administrator                                                                                                                                                                                                       
        Full Name   :   Administrator
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :   Built-in account for administering the computer/domain
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Tue, 19 Aug 2025 09:39:37 EDT
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 31 Dec 1969 19:00:00 EST
        Password last set Time   :      Mon, 30 Aug 2021 20:51:59 EDT
        Password can change Time :      Tue, 31 Aug 2021 20:51:59 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x1f4
        group_rid:      0x201
        acb_info :      0x00000010
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000086
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : False
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False

S-1-5-21-3072663084-364016917-1341370565-501 HTB\Guest (Local User)

[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 501' '10.129.149.11' 2>&1                                                                                          
                                                                                                                                                                                                                                            
        User Name   :   Guest                                                                                                                                                                                                               
        Full Name   :
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :   Built-in account for guest access to the computer/domain
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x1f5
        group_rid:      0x202
        acb_info :      0x00000215
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False

S-1-5-21-3072663084-364016917-1341370565-502 HTB\krbtgt (Local User)

[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 502' '10.129.149.11' 2>&1                                                                                          
                                                                                                                                                                                                                                            
        User Name   :   krbtgt                                                                                                                                                                                                              
        Full Name   :
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :   Key Distribution Center Service Account
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 18 Sep 2019 06:53:23 EDT
        Password can change Time :      Thu, 19 Sep 2019 06:53:23 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x1f6
        group_rid:      0x201
        acb_info :      0x00000011
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : False
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False

S-1-5-21-3072663084-364016917-1341370565-503 HTB\DefaultAccount (Local User)

[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 503' '10.129.149.11' 2>&1                                                                                          
                                                                                                                                                                                                                                            
        User Name   :   DefaultAccount                                                                                                                                                                                                      
        Full Name   :
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :   A user account managed by the system.
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Wed, 31 Dec 1969 19:00:00 EST
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Wed, 31 Dec 1969 19:00:00 EST
        Password can change Time :      Wed, 31 Dec 1969 19:00:00 EST
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x1f7
        group_rid:      0x201
        acb_info :      0x00000215
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000000
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : True
        Password does not expire : True
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : False
        Trusted for delegation   : False

S-1-5-21-3072663084-364016917-1341370565-512 HTB\Domain Admins (Domain Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 512' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Domain Admins                                                                                                                                                                                                       
        Description:    Designated administrators of the domain
        Group Attribute:7
        Num Members:1

S-1-5-21-3072663084-364016917-1341370565-513 HTB\Domain Users (Domain Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 513' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Domain Users                                                                                                                                                                                                        
        Description:    All domain users
        Group Attribute:7
        Num Members:30

S-1-5-21-3072663084-364016917-1341370565-514 HTB\Domain Guests (Domain Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 514' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Domain Guests                                                                                                                                                                                                       
        Description:    All domain guests
        Group Attribute:7
        Num Members:1

S-1-5-21-3072663084-364016917-1341370565-515 HTB\Domain Computers (Domain Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 515' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Domain Computers                                                                                                                                                                                                    
        Description:    All workstations and servers joined to the domain
        Group Attribute:7
        Num Members:1

S-1-5-21-3072663084-364016917-1341370565-516 HTB\Domain Controllers (Domain Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 516' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Domain Controllers                                                                                                                                                                                                  
        Description:    All domain controllers in the domain
        Group Attribute:7
        Num Members:1

S-1-5-21-3072663084-364016917-1341370565-517 HTB\Cert Publishers (Local Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 517' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[E] No info found                                                                                                                                                                                                                           
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
S-1-5-21-3072663084-364016917-1341370565-518 HTB\Schema Admins (Domain Group)                                                                                                                                                               

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 518' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Schema Admins                                                                                                                                                                                                       
        Description:    Designated administrators of the schema
        Group Attribute:7
        Num Members:1

S-1-5-21-3072663084-364016917-1341370565-519 HTB\Enterprise Admins (Domain Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 519' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Enterprise Admins                                                                                                                                                                                                   
        Description:    Designated administrators of the enterprise
        Group Attribute:7
        Num Members:1

S-1-5-21-3072663084-364016917-1341370565-520 HTB\Group Policy Creator Owners (Domain Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 520' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Group Policy Creator Owners                                                                                                                                                                                         
        Description:    Members in this group can modify group policy for the domain
        Group Attribute:7
        Num Members:1

S-1-5-21-3072663084-364016917-1341370565-521 HTB\Read-only Domain Controllers (Domain Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 521' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Read-only Domain Controllers                                                                                                                                                                                        
        Description:    Members of this group are Read-Only Domain Controllers in the domain
        Group Attribute:7
        Num Members:0

S-1-5-21-3072663084-364016917-1341370565-522 HTB\Cloneable Domain Controllers (Domain Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 522' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Cloneable Domain Controllers                                                                                                                                                                                        
        Description:    Members of this group that are domain controllers may be cloned.
        Group Attribute:7
        Num Members:0

S-1-5-21-3072663084-364016917-1341370565-525 HTB\Protected Users (Domain Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 525' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Protected Users                                                                                                                                                                                                     
        Description:    Members of this group are afforded additional protections against authentication security threats. See http://go.microsoft.com/fwlink/?LinkId=298939 for more information.
        Group Attribute:7
        Num Members:0

S-1-5-21-3072663084-364016917-1341370565-526 HTB\Key Admins (Domain Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 526' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Key Admins                                                                                                                                                                                                          
        Description:    Members of this group can perform administrative actions on key objects within the domain.
        Group Attribute:7
        Num Members:0

S-1-5-21-3072663084-364016917-1341370565-527 HTB\Enterprise Key Admins (Domain Group)

[V] Attempting to get detailed group info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'querygroup 527' '10.129.149.11' 2>&1                                                                                        
                                                                                                                                                                                                                                            
        Group Name:     Enterprise Key Admins                                                                                                                                                                                               
        Description:    Members of this group can perform administrative actions on key objects within the forest.
        Group Attribute:7
        Num Members:0

S-1-5-21-3072663084-364016917-1341370565-1000 HTB\FOREST$ (Local User)

[V] Attempting to get detailed user info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'queryuser 1000' '10.129.149.11' 2>&1                                                                                         
                                                                                                                                                                                                                                            
        User Name   :   FOREST$                                                                                                                                                                                                             
        Full Name   :
        Home Drive  :
        Dir Drive   :
        Profile Path:
        Logon Script:
        Description :
        Workstations:
        Comment     :
        Remote Dial :
        Logon Time               :      Tue, 19 Aug 2025 09:39:17 EDT
        Logoff Time              :      Wed, 31 Dec 1969 19:00:00 EST
        Kickoff Time             :      Wed, 13 Sep 30828 22:48:05 EDT
        Password last set Time   :      Tue, 19 Aug 2025 09:38:48 EDT
        Password can change Time :      Wed, 20 Aug 2025 09:38:48 EDT
        Password must change Time:      Wed, 13 Sep 30828 22:48:05 EDT
        unknown_2[0..31]...
        user_rid :      0x3e8
        group_rid:      0x204
        acb_info :      0x00002100
        fields_present: 0x00ffffff
        logon_divs:     168
        bad_password_count:     0x00000000
        logon_count:    0x00000055
        padding1[0..7]...
        logon_hrs[0..21]...
        Account Disabled         : False
        Password does not expire : False
        Account locked out       : False
        Password expired         : False
        Interdomain trust account: False
        Workstation trust account: False
        Server trust account     : True
        Trusted for delegation   : True


 ===============================( Getting printer info for 10.129.149.11 )===============================
                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                            
[V] Attempting to get printer info with command: rpcclient -W 'htb.local' -U'svc-alfresco'%'s3rvice' -c 'enumprinters' '10.129.149.11' 2>&1                                                                                                 
                                                                                                                                                                                                                                            
do_cmd: Could not initialise spoolss. Error was NT_STATUS_OBJECT_NAME_NOT_FOUND                                                                                                                                                             


enum4linux complete on Tue Aug 19 11:37:25 2025
```
