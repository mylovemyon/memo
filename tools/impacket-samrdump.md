```sh
└─$ impacket-samrdump -ts -debug 'htb.local/svc-alfresco:s3rvice@10.129.95.210'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[2025-09-18 22:13:35] [+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[2025-09-18 22:13:35] [*] Retrieving endpoint list from 10.129.95.210
[2025-09-18 22:13:35] [+] StringBinding ncacn_np:10.129.95.210[\pipe\samr]
Found domain(s):
 . HTB
 . Builtin
[2025-09-18 22:13:40] [*] Looking up users in domain HTB
Found user: Administrator, uid = 500
Found user: Guest, uid = 501
Found user: krbtgt, uid = 502
Found user: DefaultAccount, uid = 503
Found user: $331000-VK4ADACQNUCA, uid = 1123
Found user: SM_2c8eef0a09b545acb, uid = 1124
Found user: SM_ca8c2ed5bdab4dc9b, uid = 1125
Found user: SM_75a538d3025e4db9a, uid = 1126
Found user: SM_681f53d4942840e18, uid = 1127
Found user: SM_1b41c9286325456bb, uid = 1128
Found user: SM_9b69f1b9d2cc45549, uid = 1129
Found user: SM_7c96b981967141ebb, uid = 1130
Found user: SM_c75ee099d0a64c91b, uid = 1131
Found user: SM_1ffab36a2f5f479cb, uid = 1132
Found user: HealthMailboxc3d7722, uid = 1134
Found user: HealthMailboxfc9daad, uid = 1135
Found user: HealthMailboxc0a90c9, uid = 1136
Found user: HealthMailbox670628e, uid = 1137
Found user: HealthMailbox968e74d, uid = 1138
Found user: HealthMailbox6ded678, uid = 1139
Found user: HealthMailbox83d6781, uid = 1140
Found user: HealthMailboxfd87238, uid = 1141
Found user: HealthMailboxb01ac64, uid = 1142
Found user: HealthMailbox7108a4e, uid = 1143
Found user: HealthMailbox0659cc1, uid = 1144
Found user: sebastien, uid = 1145
Found user: lucinda, uid = 1146
Found user: svc-alfresco, uid = 1147
Found user: andy, uid = 1150
Found user: mark, uid = 1151
Found user: santi, uid = 1152
Administrator (500)/FullName: Administrator
Administrator (500)/AdminComment: Built-in account for administering the computer/domain
Administrator (500)/UserComment: 
Administrator (500)/PrimaryGroupId: 513
Administrator (500)/BadPasswordCount: 0
Administrator (500)/LogonCount: 129
Administrator (500)/PasswordLastSet: 2021-08-30 20:51:58.690463
Administrator (500)/PasswordDoesNotExpire: False
Administrator (500)/AccountIsDisabled: False
Administrator (500)/ScriptPath: 
Guest (501)/FullName: 
Guest (501)/AdminComment: Built-in account for guest access to the computer/domain
Guest (501)/UserComment: 
Guest (501)/PrimaryGroupId: 514
Guest (501)/BadPasswordCount: 0
Guest (501)/LogonCount: 0
Guest (501)/PasswordLastSet: <never>
Guest (501)/PasswordDoesNotExpire: True
Guest (501)/AccountIsDisabled: True
Guest (501)/ScriptPath: 
krbtgt (502)/FullName: 
krbtgt (502)/AdminComment: Key Distribution Center Service Account
krbtgt (502)/UserComment: 
krbtgt (502)/PrimaryGroupId: 513
krbtgt (502)/BadPasswordCount: 0
krbtgt (502)/LogonCount: 0
krbtgt (502)/PasswordLastSet: 2019-09-18 06:53:23.467452
krbtgt (502)/PasswordDoesNotExpire: False
krbtgt (502)/AccountIsDisabled: True
krbtgt (502)/ScriptPath: 
DefaultAccount (503)/FullName: 
DefaultAccount (503)/AdminComment: A user account managed by the system.
DefaultAccount (503)/UserComment: 
DefaultAccount (503)/PrimaryGroupId: 513
DefaultAccount (503)/BadPasswordCount: 0
DefaultAccount (503)/LogonCount: 0
DefaultAccount (503)/PasswordLastSet: <never>
DefaultAccount (503)/PasswordDoesNotExpire: True
DefaultAccount (503)/AccountIsDisabled: True
DefaultAccount (503)/ScriptPath: 
$331000-VK4ADACQNUCA (1123)/FullName: 
$331000-VK4ADACQNUCA (1123)/AdminComment: 
$331000-VK4ADACQNUCA (1123)/UserComment: 
$331000-VK4ADACQNUCA (1123)/PrimaryGroupId: 513
$331000-VK4ADACQNUCA (1123)/BadPasswordCount: 0
$331000-VK4ADACQNUCA (1123)/LogonCount: 0
$331000-VK4ADACQNUCA (1123)/PasswordLastSet: <never>
$331000-VK4ADACQNUCA (1123)/PasswordDoesNotExpire: False
$331000-VK4ADACQNUCA (1123)/AccountIsDisabled: True
$331000-VK4ADACQNUCA (1123)/ScriptPath: 
SM_2c8eef0a09b545acb (1124)/FullName: Microsoft Exchange Approval Assistant
SM_2c8eef0a09b545acb (1124)/AdminComment: 
SM_2c8eef0a09b545acb (1124)/UserComment: 
SM_2c8eef0a09b545acb (1124)/PrimaryGroupId: 513
SM_2c8eef0a09b545acb (1124)/BadPasswordCount: 0
SM_2c8eef0a09b545acb (1124)/LogonCount: 0
SM_2c8eef0a09b545acb (1124)/PasswordLastSet: <never>
SM_2c8eef0a09b545acb (1124)/PasswordDoesNotExpire: False
SM_2c8eef0a09b545acb (1124)/AccountIsDisabled: True
SM_2c8eef0a09b545acb (1124)/ScriptPath: 
SM_ca8c2ed5bdab4dc9b (1125)/FullName: Microsoft Exchange
SM_ca8c2ed5bdab4dc9b (1125)/AdminComment: 
SM_ca8c2ed5bdab4dc9b (1125)/UserComment: 
SM_ca8c2ed5bdab4dc9b (1125)/PrimaryGroupId: 513
SM_ca8c2ed5bdab4dc9b (1125)/BadPasswordCount: 0
SM_ca8c2ed5bdab4dc9b (1125)/LogonCount: 0
SM_ca8c2ed5bdab4dc9b (1125)/PasswordLastSet: <never>
SM_ca8c2ed5bdab4dc9b (1125)/PasswordDoesNotExpire: False
SM_ca8c2ed5bdab4dc9b (1125)/AccountIsDisabled: True
SM_ca8c2ed5bdab4dc9b (1125)/ScriptPath: 
SM_75a538d3025e4db9a (1126)/FullName: Microsoft Exchange
SM_75a538d3025e4db9a (1126)/AdminComment: 
SM_75a538d3025e4db9a (1126)/UserComment: 
SM_75a538d3025e4db9a (1126)/PrimaryGroupId: 513
SM_75a538d3025e4db9a (1126)/BadPasswordCount: 0
SM_75a538d3025e4db9a (1126)/LogonCount: 0
SM_75a538d3025e4db9a (1126)/PasswordLastSet: <never>
SM_75a538d3025e4db9a (1126)/PasswordDoesNotExpire: False
SM_75a538d3025e4db9a (1126)/AccountIsDisabled: True
SM_75a538d3025e4db9a (1126)/ScriptPath: 
SM_681f53d4942840e18 (1127)/FullName: Discovery Search Mailbox
SM_681f53d4942840e18 (1127)/AdminComment: 
SM_681f53d4942840e18 (1127)/UserComment: 
SM_681f53d4942840e18 (1127)/PrimaryGroupId: 513
SM_681f53d4942840e18 (1127)/BadPasswordCount: 0
SM_681f53d4942840e18 (1127)/LogonCount: 0
SM_681f53d4942840e18 (1127)/PasswordLastSet: <never>
SM_681f53d4942840e18 (1127)/PasswordDoesNotExpire: False
SM_681f53d4942840e18 (1127)/AccountIsDisabled: True
SM_681f53d4942840e18 (1127)/ScriptPath: 
SM_1b41c9286325456bb (1128)/FullName: Microsoft Exchange Migration
SM_1b41c9286325456bb (1128)/AdminComment: 
SM_1b41c9286325456bb (1128)/UserComment: 
SM_1b41c9286325456bb (1128)/PrimaryGroupId: 513
SM_1b41c9286325456bb (1128)/BadPasswordCount: 0
SM_1b41c9286325456bb (1128)/LogonCount: 0
SM_1b41c9286325456bb (1128)/PasswordLastSet: <never>
SM_1b41c9286325456bb (1128)/PasswordDoesNotExpire: False
SM_1b41c9286325456bb (1128)/AccountIsDisabled: True
SM_1b41c9286325456bb (1128)/ScriptPath: 
SM_9b69f1b9d2cc45549 (1129)/FullName: Microsoft Exchange Federation Mailbox
SM_9b69f1b9d2cc45549 (1129)/AdminComment: 
SM_9b69f1b9d2cc45549 (1129)/UserComment: 
SM_9b69f1b9d2cc45549 (1129)/PrimaryGroupId: 513
SM_9b69f1b9d2cc45549 (1129)/BadPasswordCount: 0
SM_9b69f1b9d2cc45549 (1129)/LogonCount: 0
SM_9b69f1b9d2cc45549 (1129)/PasswordLastSet: <never>
SM_9b69f1b9d2cc45549 (1129)/PasswordDoesNotExpire: False
SM_9b69f1b9d2cc45549 (1129)/AccountIsDisabled: True
SM_9b69f1b9d2cc45549 (1129)/ScriptPath: 
SM_7c96b981967141ebb (1130)/FullName: E4E Encryption Store - Active
SM_7c96b981967141ebb (1130)/AdminComment: 
SM_7c96b981967141ebb (1130)/UserComment: 
SM_7c96b981967141ebb (1130)/PrimaryGroupId: 513
SM_7c96b981967141ebb (1130)/BadPasswordCount: 0
SM_7c96b981967141ebb (1130)/LogonCount: 0
SM_7c96b981967141ebb (1130)/PasswordLastSet: <never>
SM_7c96b981967141ebb (1130)/PasswordDoesNotExpire: False
SM_7c96b981967141ebb (1130)/AccountIsDisabled: True
SM_7c96b981967141ebb (1130)/ScriptPath: 
SM_c75ee099d0a64c91b (1131)/FullName: Microsoft Exchange
SM_c75ee099d0a64c91b (1131)/AdminComment: 
SM_c75ee099d0a64c91b (1131)/UserComment: 
SM_c75ee099d0a64c91b (1131)/PrimaryGroupId: 513
SM_c75ee099d0a64c91b (1131)/BadPasswordCount: 0
SM_c75ee099d0a64c91b (1131)/LogonCount: 0
SM_c75ee099d0a64c91b (1131)/PasswordLastSet: <never>
SM_c75ee099d0a64c91b (1131)/PasswordDoesNotExpire: False
SM_c75ee099d0a64c91b (1131)/AccountIsDisabled: True
SM_c75ee099d0a64c91b (1131)/ScriptPath: 
SM_1ffab36a2f5f479cb (1132)/FullName: SystemMailbox{8cc370d3-822a-4ab8-a926-bb94bd0641a9}
SM_1ffab36a2f5f479cb (1132)/AdminComment: 
SM_1ffab36a2f5f479cb (1132)/UserComment: 
SM_1ffab36a2f5f479cb (1132)/PrimaryGroupId: 513
SM_1ffab36a2f5f479cb (1132)/BadPasswordCount: 0
SM_1ffab36a2f5f479cb (1132)/LogonCount: 0
SM_1ffab36a2f5f479cb (1132)/PasswordLastSet: <never>
SM_1ffab36a2f5f479cb (1132)/PasswordDoesNotExpire: False
SM_1ffab36a2f5f479cb (1132)/AccountIsDisabled: True
SM_1ffab36a2f5f479cb (1132)/ScriptPath: 
HealthMailboxc3d7722 (1134)/FullName: HealthMailbox-EXCH01-Mailbox-Database-1118319013
HealthMailboxc3d7722 (1134)/AdminComment: 
HealthMailboxc3d7722 (1134)/UserComment: 
HealthMailboxc3d7722 (1134)/PrimaryGroupId: 513
HealthMailboxc3d7722 (1134)/BadPasswordCount: 0
HealthMailboxc3d7722 (1134)/LogonCount: 1470
HealthMailboxc3d7722 (1134)/PasswordLastSet: 2019-09-23 18:51:31.892097
HealthMailboxc3d7722 (1134)/PasswordDoesNotExpire: True
HealthMailboxc3d7722 (1134)/AccountIsDisabled: False
HealthMailboxc3d7722 (1134)/ScriptPath: 
HealthMailboxfc9daad (1135)/FullName: HealthMailbox-EXCH01-001
HealthMailboxfc9daad (1135)/AdminComment: 
HealthMailboxfc9daad (1135)/UserComment: 
HealthMailboxfc9daad (1135)/PrimaryGroupId: 513
HealthMailboxfc9daad (1135)/BadPasswordCount: 0
HealthMailboxfc9daad (1135)/LogonCount: 59
HealthMailboxfc9daad (1135)/PasswordLastSet: 2019-09-23 18:51:35.267114
HealthMailboxfc9daad (1135)/PasswordDoesNotExpire: True
HealthMailboxfc9daad (1135)/AccountIsDisabled: False
HealthMailboxfc9daad (1135)/ScriptPath: 
HealthMailboxc0a90c9 (1136)/FullName: HealthMailbox-EXCH01-002
HealthMailboxc0a90c9 (1136)/AdminComment: 
HealthMailboxc0a90c9 (1136)/UserComment: 
HealthMailboxc0a90c9 (1136)/PrimaryGroupId: 513
HealthMailboxc0a90c9 (1136)/BadPasswordCount: 0
HealthMailboxc0a90c9 (1136)/LogonCount: 0
HealthMailboxc0a90c9 (1136)/PasswordLastSet: 2019-09-19 07:56:35.206329
HealthMailboxc0a90c9 (1136)/PasswordDoesNotExpire: True
HealthMailboxc0a90c9 (1136)/AccountIsDisabled: False
HealthMailboxc0a90c9 (1136)/ScriptPath: 
HealthMailbox670628e (1137)/FullName: HealthMailbox-EXCH01-003
HealthMailbox670628e (1137)/AdminComment: 
HealthMailbox670628e (1137)/UserComment: 
HealthMailbox670628e (1137)/PrimaryGroupId: 513
HealthMailbox670628e (1137)/BadPasswordCount: 0
HealthMailbox670628e (1137)/LogonCount: 0
HealthMailbox670628e (1137)/PasswordLastSet: 2019-09-19 07:56:45.643993
HealthMailbox670628e (1137)/PasswordDoesNotExpire: True
HealthMailbox670628e (1137)/AccountIsDisabled: False
HealthMailbox670628e (1137)/ScriptPath: 
HealthMailbox968e74d (1138)/FullName: HealthMailbox-EXCH01-004
HealthMailbox968e74d (1138)/AdminComment: 
HealthMailbox968e74d (1138)/UserComment: 
HealthMailbox968e74d (1138)/PrimaryGroupId: 513
HealthMailbox968e74d (1138)/BadPasswordCount: 0
HealthMailbox968e74d (1138)/LogonCount: 0
HealthMailbox968e74d (1138)/PasswordLastSet: 2019-09-19 07:56:56.143969
HealthMailbox968e74d (1138)/PasswordDoesNotExpire: True
HealthMailbox968e74d (1138)/AccountIsDisabled: False
HealthMailbox968e74d (1138)/ScriptPath: 
HealthMailbox6ded678 (1139)/FullName: HealthMailbox-EXCH01-005
HealthMailbox6ded678 (1139)/AdminComment: 
HealthMailbox6ded678 (1139)/UserComment: 
HealthMailbox6ded678 (1139)/PrimaryGroupId: 513
HealthMailbox6ded678 (1139)/BadPasswordCount: 0
HealthMailbox6ded678 (1139)/LogonCount: 0
HealthMailbox6ded678 (1139)/PasswordLastSet: 2019-09-19 07:57:06.597012
HealthMailbox6ded678 (1139)/PasswordDoesNotExpire: True
HealthMailbox6ded678 (1139)/AccountIsDisabled: False
HealthMailbox6ded678 (1139)/ScriptPath: 
HealthMailbox83d6781 (1140)/FullName: HealthMailbox-EXCH01-006
HealthMailbox83d6781 (1140)/AdminComment: 
HealthMailbox83d6781 (1140)/UserComment: 
HealthMailbox83d6781 (1140)/PrimaryGroupId: 513
HealthMailbox83d6781 (1140)/BadPasswordCount: 0
HealthMailbox83d6781 (1140)/LogonCount: 0
HealthMailbox83d6781 (1140)/PasswordLastSet: 2019-09-19 07:57:17.065809
HealthMailbox83d6781 (1140)/PasswordDoesNotExpire: True
HealthMailbox83d6781 (1140)/AccountIsDisabled: False
HealthMailbox83d6781 (1140)/ScriptPath: 
HealthMailboxfd87238 (1141)/FullName: HealthMailbox-EXCH01-007
HealthMailboxfd87238 (1141)/AdminComment: 
HealthMailboxfd87238 (1141)/UserComment: 
HealthMailboxfd87238 (1141)/PrimaryGroupId: 513
HealthMailboxfd87238 (1141)/BadPasswordCount: 0
HealthMailboxfd87238 (1141)/LogonCount: 0
HealthMailboxfd87238 (1141)/PasswordLastSet: 2019-09-19 07:57:27.487679
HealthMailboxfd87238 (1141)/PasswordDoesNotExpire: True
HealthMailboxfd87238 (1141)/AccountIsDisabled: False
HealthMailboxfd87238 (1141)/ScriptPath: 
HealthMailboxb01ac64 (1142)/FullName: HealthMailbox-EXCH01-008
HealthMailboxb01ac64 (1142)/AdminComment: 
HealthMailboxb01ac64 (1142)/UserComment: 
HealthMailboxb01ac64 (1142)/PrimaryGroupId: 513
HealthMailboxb01ac64 (1142)/BadPasswordCount: 0
HealthMailboxb01ac64 (1142)/LogonCount: 0
HealthMailboxb01ac64 (1142)/PasswordLastSet: 2019-09-19 07:57:37.878559
HealthMailboxb01ac64 (1142)/PasswordDoesNotExpire: True
HealthMailboxb01ac64 (1142)/AccountIsDisabled: False
HealthMailboxb01ac64 (1142)/ScriptPath: 
HealthMailbox7108a4e (1143)/FullName: HealthMailbox-EXCH01-009
HealthMailbox7108a4e (1143)/AdminComment: 
HealthMailbox7108a4e (1143)/UserComment: 
HealthMailbox7108a4e (1143)/PrimaryGroupId: 513
HealthMailbox7108a4e (1143)/BadPasswordCount: 0
HealthMailbox7108a4e (1143)/LogonCount: 0
HealthMailbox7108a4e (1143)/PasswordLastSet: 2019-09-19 07:57:48.253341
HealthMailbox7108a4e (1143)/PasswordDoesNotExpire: True
HealthMailbox7108a4e (1143)/AccountIsDisabled: False
HealthMailbox7108a4e (1143)/ScriptPath: 
HealthMailbox0659cc1 (1144)/FullName: HealthMailbox-EXCH01-010
HealthMailbox0659cc1 (1144)/AdminComment: 
HealthMailbox0659cc1 (1144)/UserComment: 
HealthMailbox0659cc1 (1144)/PrimaryGroupId: 513
HealthMailbox0659cc1 (1144)/BadPasswordCount: 0
HealthMailbox0659cc1 (1144)/LogonCount: 0
HealthMailbox0659cc1 (1144)/PasswordLastSet: 2019-09-19 07:57:58.643994
HealthMailbox0659cc1 (1144)/PasswordDoesNotExpire: True
HealthMailbox0659cc1 (1144)/AccountIsDisabled: False
HealthMailbox0659cc1 (1144)/ScriptPath: 
sebastien (1145)/FullName: Sebastien Caron
sebastien (1145)/AdminComment: 
sebastien (1145)/UserComment: 
sebastien (1145)/PrimaryGroupId: 513
sebastien (1145)/BadPasswordCount: 0
sebastien (1145)/LogonCount: 8
sebastien (1145)/PasswordLastSet: 2019-09-19 20:29:59.544725
sebastien (1145)/PasswordDoesNotExpire: True
sebastien (1145)/AccountIsDisabled: False
sebastien (1145)/ScriptPath: 
lucinda (1146)/FullName: Lucinda Berger
lucinda (1146)/AdminComment: 
lucinda (1146)/UserComment: 
lucinda (1146)/PrimaryGroupId: 513
lucinda (1146)/BadPasswordCount: 0
lucinda (1146)/LogonCount: 0
lucinda (1146)/PasswordLastSet: 2019-09-19 20:44:13.233891
lucinda (1146)/PasswordDoesNotExpire: True
lucinda (1146)/AccountIsDisabled: False
lucinda (1146)/ScriptPath: 
svc-alfresco (1147)/FullName: svc-alfresco
svc-alfresco (1147)/AdminComment: 
svc-alfresco (1147)/UserComment: 
svc-alfresco (1147)/PrimaryGroupId: 513
svc-alfresco (1147)/BadPasswordCount: 0
svc-alfresco (1147)/LogonCount: 6
svc-alfresco (1147)/PasswordLastSet: 2025-09-18 22:21:32.329691
svc-alfresco (1147)/PasswordDoesNotExpire: True
svc-alfresco (1147)/AccountIsDisabled: False
svc-alfresco (1147)/ScriptPath: 
andy (1150)/FullName: Andy Hislip
andy (1150)/AdminComment: 
andy (1150)/UserComment: 
andy (1150)/PrimaryGroupId: 513
andy (1150)/BadPasswordCount: 0
andy (1150)/LogonCount: 0
andy (1150)/PasswordLastSet: 2019-09-22 18:44:16.291082
andy (1150)/PasswordDoesNotExpire: True
andy (1150)/AccountIsDisabled: False
andy (1150)/ScriptPath: 
mark (1151)/FullName: Mark Brandt
mark (1151)/AdminComment: 
mark (1151)/UserComment: 
mark (1151)/PrimaryGroupId: 513
mark (1151)/BadPasswordCount: 0
mark (1151)/LogonCount: 0
mark (1151)/PasswordLastSet: 2019-09-20 18:57:30.243568
mark (1151)/PasswordDoesNotExpire: True
mark (1151)/AccountIsDisabled: False
mark (1151)/ScriptPath: 
santi (1152)/FullName: Santi Rodriguez
santi (1152)/AdminComment: 
santi (1152)/UserComment: 
santi (1152)/PrimaryGroupId: 513
santi (1152)/BadPasswordCount: 0
santi (1152)/LogonCount: 0
santi (1152)/PasswordLastSet: 2019-09-20 19:02:55.134828
santi (1152)/PasswordDoesNotExpire: True
santi (1152)/AccountIsDisabled: False
santi (1152)/ScriptPath: 
[2025-09-18 22:14:55] [*] Received 31 entries.
```
