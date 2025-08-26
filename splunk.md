## "frothly\\\billy.tun"
### index="botsv*" "frothly\\\billy.tun" process_name="netsh.exe"
```sh
08/23/2017 08:33:29 PM
LogName=Security
SourceName=Microsoft Windows security auditing.
EventCode=4688
EventType=0
Type=Information
ComputerName=wrk-btun.frothly.local
TaskCategory=Process Creation
OpCode=Info
RecordNumber=57321
Keywords=Audit Success
Message=A new process has been created.

Subject:
	Security ID:		FROTHLY\billy.tun
	Account Name:		billy.tun
	Account Domain:		FROTHLY
	Logon ID:		0x25276

Process Information:
	New Process ID:		0x1168
	New Process Name:	C:\Windows\System32\netsh.exe
	Token Elevation Type:	TokenElevationTypeFull (2)
	Creator Process ID:	0xe80
	Process Command Line:	"C:\Windows\system32\netsh.exe"  advfirewall set allprofiles state off

Token Elevation Type indicates the type of token that was assigned to the new process in accordance with User Account Control policy.

Type 1 is a full token with no privileges removed or groups disabled.  A full token is only used if User Account Control is disabled or if the user is the built-in Administrator account or a service account.

Type 2 is an elevated token with no privileges removed or groups disabled.  An elevated token is used when User Account Control is enabled and the user chooses to start the program using Run as administrator.  An elevated token is also used when an application is configured to always require administrative privilege or to always require maximum privilege, and the user is a member of the Administrators group.

Type 3 is a limited token with administrative privileges removed and administrative groups disabled.  The limited token is used when User Account Control is enabled, the application does not require administrative privilege, and the user does not choose to start the program using Run as administrator.
```
