## help
```sh
---------------         ----------------------
       UNIXINFO
       getpwuid         Get shell and homedir
       uidtosid         Convert uid to sid
---------------         ----------------------
         MDSSVC
fetch_properties                Fetch connection properties
fetch_attributes                Fetch attributes for a CNID
---------------         ----------------------
        CLUSAPI
clusapi_open_cluster            Open cluster
clusapi_get_cluster_name                Get cluster name
clusapi_get_cluster_version             Get cluster version
clusapi_get_quorum_resource             Get quorum resource
clusapi_create_enum             Create enum query
clusapi_create_enumex           Create enumex query
clusapi_open_resource           Open cluster resource
clusapi_online_resource         Set cluster resource online
clusapi_offline_resource                Set cluster resource offline
clusapi_get_resource_state              Get cluster resource state
clusapi_get_cluster_version2            Get cluster version2
clusapi_pause_node              Pause cluster node
clusapi_resume_node             Resume cluster node
---------------         ----------------------
        WITNESS
GetInterfaceList                List the interfaces to which witness client connections can be made
       Register         Register for resource state change notifications of a NetName and IPAddress
     UnRegister         Unregister for notifications from the server</para></listitem></varlistentry>
    AsyncNotify         Request notification of registered resource changes from the server
     RegisterEx         Register for resource state change notifications of a NetName, ShareName and multiple IPAddresses
---------------         ----------------------
          FSRVP
fss_is_path_sup         Check whether a share supports shadow-copy requests
fss_get_sup_version             Get supported FSRVP version from server
fss_create_expose               Request shadow-copy creation and exposure
     fss_delete         Request shadow-copy share deletion
fss_has_shadow_copy             Check for an associated share shadow-copy
fss_get_mapping         Get shadow-copy share mapping information
fss_recovery_complete           Flag read-write snapshot as recovery complete, allowing further shadow-copy requests
---------------         ----------------------
         WINREG
 winreg_enumkey         Enumerate Keys
querymultiplevalues             Query multiple values
querymultiplevalues2            Query multiple values
 winreg_enumval         Enumerate Values
---------------         ----------------------
       EVENTLOG
eventlog_readlog                Read Eventlog
eventlog_numrecord              Get number of records
eventlog_oldestrecord           Get oldest record
eventlog_reportevent            Report event
eventlog_reporteventsource              Report event and source
eventlog_registerevsource               Register event source
eventlog_backuplog              Backup Eventlog File
eventlog_loginfo                Get Eventlog Information
---------------         ----------------------
        DRSUAPI
   dscracknames         Crack Name
    dsgetdcinfo         Get Domain Controller Info
 dsgetncchanges         Get NC Changes
dswriteaccountspn               Write Account SPN
---------------         ----------------------
         NTSVCS
ntsvcs_getversion               Query NTSVCS version
ntsvcs_validatedevinst          Query NTSVCS device instance
ntsvcs_hwprofflags              Query NTSVCS HW prof flags
ntsvcs_hwprofinfo               Query NTSVCS HW prof info
ntsvcs_getdevregprop            Query NTSVCS device registry property
ntsvcs_getdevlistsize           Query NTSVCS device list size
ntsvcs_getdevlist               Query NTSVCS device list
---------------         ----------------------
         WKSSVC
wkssvc_wkstagetinfo             Query WKSSVC Workstation Information
wkssvc_getjoininformation               Query WKSSVC Join Information
wkssvc_messagebuffersend                Send WKSSVC message
wkssvc_enumeratecomputernames           Enumerate WKSSVC computer names
wkssvc_enumerateusers           Enumerate WKSSVC users
---------------         ----------------------
       SHUTDOWN
---------------         ----------------------
       EPMAPPER
         epmmap         Map a binding
      epmlookup         Lookup bindings
---------------         ----------------------
           ECHO
     echoaddone         Add one to a number
       echodata         Echo data
       sinkdata         Sink data
     sourcedata         Source data
---------------         ----------------------
            DFS
     dfsversion         Query DFS support
         dfsadd         Add a DFS share
      dfsremove         Remove a DFS share
     dfsgetinfo         Query DFS share info
        dfsenum         Enumerate dfs shares
      dfsenumex         Enumerate dfs shares
---------------         ----------------------
         SRVSVC
        srvinfo         Server query info
   netshareenum         Enumerate shares
netshareenumall         Enumerate all shares
netsharegetinfo         Get Share Info
netsharesetinfo         Set Share Info
netsharesetdfsflags             Set DFS flags
    netfileenum         Enumerate open files
   netremotetod         Fetch remote time of day
netnamevalidate         Validate sharename
  netfilegetsec         Get File security
     netsessdel         Delete Session
    netsessenum         Enumerate Sessions
    netdiskenum         Enumerate Disks
    netconnenum         Enumerate Connections
    netshareadd         Add share
    netsharedel         Delete share
---------------         ----------------------
       NETLOGON
     logonctrl2         Logon Control 2
   getanydcname         Get trusted DC name
      getdcname         Get trusted PDC name
  dsr_getdcname         Get trusted DC name
dsr_getdcnameex         Get trusted DC name
dsr_getdcnameex2                Get trusted DC name
dsr_getsitename         Get sitename
dsr_getforesttrustinfo          Get Forest Trust Info
      logonctrl         Logon Control
       samlogon         Sam Logon
change_trust_pw         Change Trust Account Password
    gettrustrid         Get trust rid
dsr_enumtrustdom                Enumerate trusted domains
dsenumdomtrusts         Enumerate all trusted domains in an AD forest
deregisterdnsrecords            Deregister DNS records
netrenumtrusteddomains          Enumerate trusted domains
netrenumtrusteddomainsex                Enumerate trusted domains
getdcsitecoverage               Get the Site-Coverage from a DC
   capabilities         Return Capabilities
logongetdomaininfo              Return LogonGetDomainInfo
---------------         ----------------------
IRemoteWinspool
winspool_AsyncOpenPrinter               Open printer handle
winspool_AsyncCorePrinterDriverInstalled                Query Core Printer Driver Installed
---------------         ----------------------
        SPOOLSS
      adddriver         Add a print driver
     addprinter         Add a printer
      deldriver         Delete a printer driver
    deldriverex         Delete a printer driver with files
       enumdata         Enumerate printer data
     enumdataex         Enumerate printer data for a key
        enumkey         Enumerate printer keys
       enumjobs         Enumerate print jobs
         getjob         Get print job
         setjob         Set print job
      enumports         Enumerate printer ports
    enumdrivers         Enumerate installed printer drivers
   enumprinters         Enumerate printers
        getdata         Get print driver data
      getdataex         Get printer driver data with keyname
      getdriver         Get print driver information
   getdriverdir         Get print driver upload directory
getdriverpackagepath            Get print driver package download directory
     getprinter         Get printer info
    openprinter         Open printer handle
 openprinter_ex         Open printer handle
      setdriver         Set printer driver
getprintprocdir         Get print processor directory
        addform         Add form
        setform         Set form
        getform         Get form
     deleteform         Delete form
      enumforms         Enumerate forms
     setprinter         Set printer comment
 setprintername         Set printername
 setprinterdata         Set REG_SZ printer data
       rffpcnex         Rffpcnex test
     printercmp         Printer comparison test
      enumprocs         Enumerate Print Processors
enumprocdatatypes               Enumerate Print Processor Data Types
   enummonitors         Enumerate Print Monitors
createprinteric         Create Printer IC
playgdiscriptonprinteric                Create Printer IC
getcoreprinterdrivers           Get CorePrinterDriver
enumpermachineconnections               Enumerate Per Machine Connections
addpermachineconnection         Add Per Machine Connection
delpermachineconnection         Delete Per Machine Connection
---------------         ----------------------
           SAMR
      queryuser         Query user info
     querygroup         Query group info
queryusergroups         Query user groups
queryuseraliases                Query user aliases
  querygroupmem         Query group membership
  queryaliasmem         Query alias membership
 queryaliasinfo         Query alias info
    deletealias         Delete an alias
  querydispinfo         Query display info
 querydispinfo2         Query display info
 querydispinfo3         Query display info
   querydominfo         Query domain info
   enumdomusers         Enumerate domain users
  enumdomgroups         Enumerate domain groups
  enumalsgroups         Enumerate alias groups
    enumdomains         Enumerate domains
  createdomuser         Create domain user
 createdomgroup         Create domain group
 createdomalias         Create domain alias
 samlookupnames         Look up names
  samlookuprids         Look up names
 deletedomgroup         Delete domain group
  deletedomuser         Delete domain user
 samquerysecobj         Query SAMR security object
   getdompwinfo         Retrieve domain password info
getusrdompwinfo         Retrieve user domain password info
   lookupdomain         Lookup Domain Name
      chgpasswd         Change user password
     chgpasswd2         Change user password
     chgpasswd3         Change user password
     chgpasswd4         Change user password
 getdispinfoidx         Get Display Information Index
    setuserinfo         Set user info
   setuserinfo2         Set user info2
---------------         ----------------------
      LSARPC-DS
  dsroledominfo         Get Primary Domain Information
---------------         ----------------------
         LSARPC
       lsaquery         Query info policy
     lookupsids         Convert SIDs to names
    lookupsids3         Convert SIDs to names
lookupsids_level                Convert SIDs to names
    lookupnames         Convert names to SIDs
   lookupnames4         Convert names to SIDs
lookupnames_level               Convert names to SIDs
      enumtrust         Enumerate trusted domains
      enumprivs         Enumerate privileges
    getdispname         Get the privilege name
     lsaenumsid         Enumerate the LSA SIDS
lsacreateaccount                Create a new lsa account
lsaenumprivsaccount             Enumerate the privileges of an SID
lsaenumacctrights               Enumerate the rights of an SID
     lsaaddpriv         Assign a privilege to a SID
     lsadelpriv         Revoke a privilege from a SID
lsaaddacctrights                Add rights to an account
lsaremoveacctrights             Remove rights from an account
lsalookupprivvalue              Get a privilege value given its name
 lsaquerysecobj         Query LSA security object
lsaquerytrustdominfo            Query LSA trusted domains info (given a SID)
lsaquerytrustdominfobyname              Query LSA trusted domains info (given a name), only works for Windows > 2k
lsaquerytrustdominfobysid               Query LSA trusted domains info (given a SID)
lsasettrustdominfo              Set LSA trusted domain info
    getusername         Get username
   createsecret         Create Secret
   deletesecret         Delete Secret
    querysecret         Query Secret
      setsecret         Set Secret
retrieveprivatedata             Retrieve Private Data
storeprivatedata                Store Private Data
 createtrustdom         Create Trusted Domain
createtrustdomex2               Create Trusted Domain (Ex2 Variant)
createtrustdomex3               Create Trusted Domain (Ex3 Variant)
 deletetrustdom         Delete Trusted Domain
---------------         ----------------------
GENERAL OPTIONS
           help         Get help on commands
              ?         Get help on commands
     debuglevel         Set debug level
          debug         Set debug level
           list         List available commands on <pipe>
           exit         Exit program
           quit         Exit program
           sign         Force RPC pipe connections to be signed
           seal         Force RPC pipe connections to be sealed
         packet         Force RPC pipe connections with packet authentication level
       schannel         Force RPC pipe connections to be sealed with 'schannel'. Assumes valid machine account to this domain controller.
   schannelsign         Force RPC pipe connections to be signed (not sealed) with 'schannel'.  Assumes valid machine account to this domain controller.
        timeout         Set timeout (in milliseconds) for RPC operations
      transport         Choose ncacn transport for RPC operations
           none         Force RPC pipe connections to have no special properties
```



## WINREG
### winreg_enumkey
[ソース](https://github.com/samba-team/samba/blob/d4d231dc50f1bbf42ae8cd8fb49f96ae6c4c0ee8/source3/rpcclient/cmd_winreg.c#L47)を見たかんじ、プログラム側に問題がありそう
```sh
rpcclient $> winreg_enumkey 'Software\Microsoft\Windows\CurrentVersion\Run'
result was WERR_INVALID_PARAMETER
```
### winreg_enumval
```sh
rpcclient $> winreg_enumval 'Software\Microsoft\Windows\CurrentVersion'
00: ProgramFilesDir     : REG_SZ: C:\Program Files
01: CommonFilesDir      : REG_SZ: C:\Program Files\Common Files
02: ProgramFilesDir (x86): REG_SZ: C:\Program Files (x86)
03: CommonFilesDir (x86): REG_SZ: C:\Program Files (x86)\Common Files
04: CommonW6432Dir      : REG_SZ: C:\Program Files\Common Files
05: DevicePath          s: unknown type 0x02:
06: MediaPathUnexpanded s: unknown type 0x02:
07: ProgramFilesPath    s: unknown type 0x02:
08: ProgramW6432Dir     : REG_SZ: C:\Program Files
result was WERR_NO_MORE_ITEMS
```
### querymultiplevalues
```sh
rpcclient $> querymultiplevalues 'Software\Microsoft\Windows\CurrentVersion' ProgramFilesDir CommonFilesDir 'ProgramFilesDir (x86)'
ProgramFilesDir     : REG_SZ: C:\Program Files
CommonFilesDir      : REG_SZ: C:\Program Files\Common Files
ProgramFilesDir (x86): REG_SZ: C:\Program Files (x86)
```
### querymultiplevalues2
```sh
rpcclient $> querymultiplevalues2 'Software\Microsoft\Windows\CurrentVersion' ProgramFilesDir CommonFilesDir 'ProgramFilesDir (x86)'
ProgramFilesDir     : REG_SZ: C:\Program Files
CommonFilesDir      : REG_SZ: C:\Program Files\Common Files
ProgramFilesDir (x86): REG_SZ: C:\Program Files (x86)
```



## EVENTLOG
### eventlog_numrecord
```sh
rpcclient $> eventlog_numrecord security
number of records: 183107
rpcclient $> eventlog_numrecord system
number of records: 5932
```
### eventlog_oldestrecord
```sh
rpcclient $> eventlog_oldestrecord security
oldest entry: 1
rpcclient $> eventlog_oldestrecord system
oldest entry: 1
```
### eventlog_reportevent
```sh
rpcclient $> eventlog_reportevent security
result was NT_STATUS_ACCESS_DENIED
rpcclient $> eventlog_reportevent system
entry: 0 written at Wed, 31 Dec 1969 19:00:00 EST
```
### eventlog_loginfo
```sh
rpcclient $> eventlog_loginfo security
rpcclient $> eventlog_loginfo system
```



## DRSUAPI
administartorでもアクセス拒否



## WKSSVC
### wkssvc_wkstagetinfo
```sh
rpcclient $> wkssvc_wkstagetinfo
rpcclient $> 
```
### wkssvc_getjoininformation
```sh
rpcclient $> wkssvc_getjoininformation
HTB (3)
```
### wkssvc_enumeratecomputernames
```sh
rpcclient $> wkssvc_enumeratecomputernames
name: 0 FOREST.htb.local
```
### wkssvc_enumerateusers
```sh
rpcclient $> wkssvc_enumerateusers
result was WERR_INVALID_PARAMETER
```



## DFS
### dfsversion
```sh
rpcclient $> dfsversion
dfs is present (6)
```
### dfsenum
```sh
rpcclient $> dfsenum
result was WERR_NOT_SUPPORTED
```



## SRVSVC
### srvinfo
```sh
rpcclient $> srvinfo
        10.129.149.11  Wk Sv PDC Tim NT     
        platform_id     :       500
        os version      :       10.0
        server type     :       0x80102b
```
### netshareenum
```sh
rpcclient $> netshareenum
netname: SYSVOL
        remark: Logon server share 
        path:   C:\Windows\SYSVOL\sysvol
        password:       (null)
netname: NETLOGON
        remark: Logon server share 
        path:   C:\Windows\SYSVOL\sysvol\htb.local\SCRIPTS
        password:       (null)
netname: Users
        remark:
        path:   C:\Shares\Users
        password:       (null)
```
### netshareenumall
```sh
rpcclient $> netshareenumall
netname: ADMIN$
        remark: Remote Admin
        path:   C:\Windows
        password:       (null)
netname: C$
        remark: Default share
        path:   C:\
        password:       (null)
netname: IPC$
        remark: Remote IPC
        path:
        password:       (null)
netname: NETLOGON
        remark: Logon server share 
        path:   C:\Windows\SYSVOL\sysvol\htb.local\SCRIPTS
        password:       (null)
netname: SYSVOL
        remark: Logon server share 
        path:   C:\Windows\SYSVOL\sysvol
        password:       (null)
```
### netsharegetinfo
```sh
rpcclient $> netsharegetinfo C$ 502
netname: C$
        remark: Default share
        path:   C:\
        password:       (null)
        type:   0x80000000
        perms:  0
        max_uses:       -1
        num_uses:       0
rpcclient $> netsharegetinfo C$ 1005
flags: 0x0
csc caching: 0
```
### netfileenum
```sh
rpcclient $> netfileenum
\srvsvc
```
### netsessenum
```sh
rpcclient $> netsessenum
trying level: 1
Received 2 entries.
```



## EPMAPPER
### epmmap
```sh
rpcclient $> epmmap
num_tower[2]
tower[0] ncacn_np:\\FOREST[\pipe\3b02dbd95ea4e67e,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]
tower[1] ncacn_np:\\FOREST[\pipe\lsass,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]
```
### epmlookup
```sh
rpcclient $> epmlookup
9e56cbc5-e634-4267-818e-ffa7dce1fa86 ncalrpc:[csebpub,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
5bc1ed07-f5f5-485f-9dfd-6fd0acf9a23c ncalrpc:[OLE158AECD90E61C4BB815639A8BD24,abstract_syntax=897e2e5f-93f3-4376-9c9c-fd2277495c27/0x00000001]: Frs2 Service
5bc1ed07-f5f5-485f-9dfd-6fd0acf9a23c ncacn_ip_tcp:0.0.0.0[52962,abstract_syntax=897e2e5f-93f3-4376-9c9c-fd2277495c27/0x00000001]: Frs2 Service
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49698,abstract_syntax=50abc2a4-574d-40b3-9d66-ee4fd5fba076/0x00000005]: 
3bdb59a0-d736-4d44-9074-c1ee00000001 ncalrpc:[LRPC-776328fe4f4cbb17f7,abstract_syntax=f3f09ffd-fbcf-4291-944d-70ad6e0e73bb/0x00000001]: 
b08669ee-8cb5-43a5-a017-84fe00000001 ncalrpc:[WMsgKRpc072421,abstract_syntax=76f226c3-ec14-4325-8a99-6a46348418af/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49685,abstract_syntax=367abb81-9844-35f1-ad32-98f038001003/0x00000002]: 
a5404c28-31a0-4baa-a6b7-854d13011c63 ncalrpc:[LRPC-f87c5fd9cd80ea8f8f,abstract_syntax=906b0ce0-c70b-1067-b317-00dd010662da/0x00000001]: 
a8e3f15e-3657-4526-b4aa-de9d1fef8b40 ncalrpc:[LRPC-f87c5fd9cd80ea8f8f,abstract_syntax=906b0ce0-c70b-1067-b317-00dd010662da/0x00000001]: 
46c41475-6208-4d42-96d7-f00935beec4b ncalrpc:[LRPC-f87c5fd9cd80ea8f8f,abstract_syntax=906b0ce0-c70b-1067-b317-00dd010662da/0x00000001]: 
d577d489-936a-4106-b9b9-106fd991dd1e ncalrpc:[OLED36D78FE8BF711699CD80A47440C,abstract_syntax=906b0ce0-c70b-1067-b317-00dd010662da/0x00000001]: 
d577d489-936a-4106-b9b9-106fd991dd1e ncalrpc:[LRPC-ddd79069aad5320db5,abstract_syntax=906b0ce0-c70b-1067-b317-00dd010662da/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-3266d6c948d3d76c8e,abstract_syntax=4c9dbf19-d39e-4bb9-90ee-8f7179b20283/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-3266d6c948d3d76c8e,abstract_syntax=e38f5360-8572-473e-b696-1b46873beeab/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-d912d609127cdf0e52,abstract_syntax=98716d03-89ac-44c7-bb8c-285824e51c4a/0x00000001]: XactSrv service
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-d912d609127cdf0e52,abstract_syntax=1a0d010f-1c33-432c-b0f5-8cf4e8053099/0x00000001]: IdSegSrv service
7364746e-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\lsass,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
7364746e-0000-0000-0000-000000000000 ncalrpc:[audit,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
7364746e-0000-0000-0000-000000000000 ncalrpc:[securityevent,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
7364746e-0000-0000-0000-000000000000 ncalrpc:[LSARPC_ENDPOINT,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
7364746e-0000-0000-0000-000000000000 ncalrpc:[lsacap,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
7364746e-0000-0000-0000-000000000000 ncalrpc:[LSA_EAS_ENDPOINT,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
7364746e-0000-0000-0000-000000000000 ncalrpc:[lsapolicylookup,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
7364746e-0000-0000-0000-000000000000 ncalrpc:[lsasspirpc,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
7364746e-0000-0000-0000-000000000000 ncalrpc:[protected_storage,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
7364746e-0000-0000-0000-000000000000 ncalrpc:[SidKey Local End Point,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
7364746e-0000-0000-0000-000000000000 ncalrpc:[samss lpc,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
7364746e-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49666,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
7364746e-0000-0000-0000-000000000000 ncalrpc:[OLE06619CC2EB526244151AC00EE533,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\lsass,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[audit,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[securityevent,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[LSARPC_ENDPOINT,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[lsacap,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[LSA_EAS_ENDPOINT,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[lsapolicylookup,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[lsasspirpc,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[protected_storage,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[SidKey Local End Point,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[samss lpc,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49666,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[OLE06619CC2EB526244151AC00EE533,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[NTDS_LPC,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncacn_http:0.0.0.0[49676,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\3b02dbd95ea4e67e,abstract_syntax=e3514235-4b06-11d1-ab04-00c04fc2dcd2/0x00000004]: MS NT Directory DRS Interface
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\lsass,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[audit,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[securityevent,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[LSARPC_ENDPOINT,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[lsacap,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[LSA_EAS_ENDPOINT,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[lsapolicylookup,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[lsasspirpc,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[protected_storage,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[SidKey Local End Point,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[samss lpc,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49666,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[OLE06619CC2EB526244151AC00EE533,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[NTDS_LPC,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncacn_http:0.0.0.0[49676,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\3b02dbd95ea4e67e,abstract_syntax=f5cc5a18-4264-101a-8c59-08002b2f8426/0x00000038]: MS NT Directory NSP Interface
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\lsass,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[audit,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[securityevent,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LSARPC_ENDPOINT,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[lsacap,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LSA_EAS_ENDPOINT,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[lsapolicylookup,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[lsasspirpc,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[protected_storage,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[SidKey Local End Point,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[samss lpc,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49666,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[OLE06619CC2EB526244151AC00EE533,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[NTDS_LPC,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncacn_http:0.0.0.0[49676,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\3b02dbd95ea4e67e,abstract_syntax=12345778-1234-abcd-ef00-0123456789ab/0x00000000]: 
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\lsass,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[audit,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[securityevent,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LSARPC_ENDPOINT,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[lsacap,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LSA_EAS_ENDPOINT,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[lsapolicylookup,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[lsasspirpc,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[protected_storage,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[SidKey Local End Point,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[samss lpc,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49666,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[OLE06619CC2EB526244151AC00EE533,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[NTDS_LPC,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_http:0.0.0.0[49676,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\3b02dbd95ea4e67e,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49677,abstract_syntax=12345778-1234-abcd-ef00-0123456789ac/0x00000001]: 
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncacn_np:\\FOREST[\pipe\lsass,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncalrpc:[audit,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncalrpc:[securityevent,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncalrpc:[LSARPC_ENDPOINT,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncalrpc:[lsacap,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncalrpc:[LSA_EAS_ENDPOINT,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncalrpc:[lsapolicylookup,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncalrpc:[lsasspirpc,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncalrpc:[protected_storage,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncalrpc:[SidKey Local End Point,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncalrpc:[samss lpc,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncacn_ip_tcp:0.0.0.0[49666,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncalrpc:[OLE06619CC2EB526244151AC00EE533,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncalrpc:[NTDS_LPC,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncacn_http:0.0.0.0[49676,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncacn_np:\\FOREST[\pipe\3b02dbd95ea4e67e,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncacn_ip_tcp:0.0.0.0[49677,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
5fc860e0-6f6e-4fc2-83cd-46324f25e90b ncalrpc:[NETLOGON_LRPC,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncacn_np:\\FOREST[\pipe\lsass,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncalrpc:[audit,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncalrpc:[securityevent,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncalrpc:[LSARPC_ENDPOINT,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncalrpc:[lsacap,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncalrpc:[LSA_EAS_ENDPOINT,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncalrpc:[lsapolicylookup,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncalrpc:[lsasspirpc,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncalrpc:[protected_storage,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncalrpc:[SidKey Local End Point,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncalrpc:[samss lpc,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncacn_ip_tcp:0.0.0.0[49666,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncalrpc:[OLE06619CC2EB526244151AC00EE533,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncalrpc:[NTDS_LPC,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncacn_http:0.0.0.0[49676,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncacn_np:\\FOREST[\pipe\3b02dbd95ea4e67e,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncacn_ip_tcp:0.0.0.0[49677,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
9a81c2bd-a525-471d-a4ed-49907c0b23da ncalrpc:[NETLOGON_LRPC,abstract_syntax=0b1c2170-5732-4e0e-8cd3-d9b16f3b84d7/0x00000000]: RemoteAccessCheck
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\lsass,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[audit,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[securityevent,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LSARPC_ENDPOINT,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[lsacap,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LSA_EAS_ENDPOINT,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[lsapolicylookup,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[lsasspirpc,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[protected_storage,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[SidKey Local End Point,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[samss lpc,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49666,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[OLE06619CC2EB526244151AC00EE533,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[NTDS_LPC,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_http:0.0.0.0[49676,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\3b02dbd95ea4e67e,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49677,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[NETLOGON_LRPC,abstract_syntax=12345678-1234-abcd-ef00-01234567cffb/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-0ccc76924f89f2f184,abstract_syntax=df1941c5-fe89-4e79-bf10-463657acf44d/0x00000001]: EFS RPC Interface
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\efsrpc,abstract_syntax=df1941c5-fe89-4e79-bf10-463657acf44d/0x00000001]: EFS RPC Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-0ccc76924f89f2f184,abstract_syntax=04eeb297-cbf4-466b-8a2a-bfd6a2f10bba/0x00000001]: EFSK RPC Interface
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\efsrpc,abstract_syntax=04eeb297-cbf4-466b-8a2a-bfd6a2f10bba/0x00000001]: EFSK RPC Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[ipsec,abstract_syntax=6b5bdd1e-528c-422c-af8c-a4079be4fe48/0x00000001]: Remote Fw APIs
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49669,abstract_syntax=6b5bdd1e-528c-422c-af8c-a4079be4fe48/0x00000001]: Remote Fw APIs
00000000-0000-0000-0000-000000000000 ncalrpc:[DNSResolver,abstract_syntax=f2c9b409-c1c9-4100-8639-d8ab1486694a/0x00000001]: Witness Client Upcall Server
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-527e89d3d284bf11e7,abstract_syntax=f2c9b409-c1c9-4100-8639-d8ab1486694a/0x00000001]: Witness Client Upcall Server
00000000-0000-0000-0000-000000000000 ncalrpc:[DNSResolver,abstract_syntax=eb081a0d-10ee-478a-a1dd-50995283e7a8/0x00000003]: Witness Client Test Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-527e89d3d284bf11e7,abstract_syntax=eb081a0d-10ee-478a-a1dd-50995283e7a8/0x00000003]: Witness Client Test Interface
00000000-0000-0000-0000-000000000000 ncalrpc:[DNSResolver,abstract_syntax=7f1343fe-50a9-4927-a778-0c5859517bac/0x00000001]: DfsDs service
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-527e89d3d284bf11e7,abstract_syntax=7f1343fe-50a9-4927-a778-0c5859517bac/0x00000001]: DfsDs service
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\PIPE\wkssvc,abstract_syntax=7f1343fe-50a9-4927-a778-0c5859517bac/0x00000001]: DfsDs service
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-0f7c78577855ab4b44,abstract_syntax=dd490425-5325-4565-b774-7e27d6c09c24/0x00000001]: Base Firewall Engine API
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-0f7c78577855ab4b44,abstract_syntax=7f9d11bf-7fb9-436b-a812-b2d50c5d4c03/0x00000001]: Fw APIs
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-36e89894f8a124763b,abstract_syntax=7f9d11bf-7fb9-436b-a812-b2d50c5d4c03/0x00000001]: Fw APIs
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-0f7c78577855ab4b44,abstract_syntax=f47433c3-3e9d-4157-aad4-83aa1f5c2d4c/0x00000001]: Fw APIs
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-36e89894f8a124763b,abstract_syntax=f47433c3-3e9d-4157-aad4-83aa1f5c2d4c/0x00000001]: Fw APIs
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-0f7c78577855ab4b44,abstract_syntax=2fb92682-6599-42dc-ae13-bd2ca89bd11c/0x00000001]: Fw APIs
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-36e89894f8a124763b,abstract_syntax=2fb92682-6599-42dc-ae13-bd2ca89bd11c/0x00000001]: Fw APIs
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-0f7c78577855ab4b44,abstract_syntax=df4df73a-c52d-4e3a-8003-8437fdf8302a/0x00000000]: WM_WindowManagerRPC\Server
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-36e89894f8a124763b,abstract_syntax=df4df73a-c52d-4e3a-8003-8437fdf8302a/0x00000000]: WM_WindowManagerRPC\Server
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-319381ae38d657ebeb,abstract_syntax=df4df73a-c52d-4e3a-8003-8437fdf8302a/0x00000000]: WM_WindowManagerRPC\Server
6c637067-6569-746e-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
24d1f7c7-76af-4f28-9ccd-7f6cb6468601 ncalrpc:[LRPC-0a3da6e1a734875903,abstract_syntax=2eb08e3e-639f-4fba-97b1-14f878961076/0x00000001]: Group Policy RPC Interface
666f7270-6c69-7365-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
736e6573-0000-0000-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
736e6573-0000-0000-0000-000000000000 ncalrpc:[OLEA1A1626453D76B8C2AB4EAF719B1,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
736e6573-0000-0000-0000-000000000000 ncalrpc:[senssvc,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
00000000-0000-0000-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=0a74ef1c-41a4-4e06-83ae-dc74fb1cdd53/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[OLEA1A1626453D76B8C2AB4EAF719B1,abstract_syntax=0a74ef1c-41a4-4e06-83ae-dc74fb1cdd53/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[senssvc,abstract_syntax=0a74ef1c-41a4-4e06-83ae-dc74fb1cdd53/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=1ff70682-0a51-30e8-076d-740be8cee98b/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[OLEA1A1626453D76B8C2AB4EAF719B1,abstract_syntax=1ff70682-0a51-30e8-076d-740be8cee98b/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[senssvc,abstract_syntax=1ff70682-0a51-30e8-076d-740be8cee98b/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\PIPE\atsvc,abstract_syntax=1ff70682-0a51-30e8-076d-740be8cee98b/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=378e52b0-c0a9-11cf-822d-00aa0051e40f/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[OLEA1A1626453D76B8C2AB4EAF719B1,abstract_syntax=378e52b0-c0a9-11cf-822d-00aa0051e40f/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[senssvc,abstract_syntax=378e52b0-c0a9-11cf-822d-00aa0051e40f/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\PIPE\atsvc,abstract_syntax=378e52b0-c0a9-11cf-822d-00aa0051e40f/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=86d35949-83c9-4044-b424-db363231fd0c/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[OLEA1A1626453D76B8C2AB4EAF719B1,abstract_syntax=86d35949-83c9-4044-b424-db363231fd0c/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[senssvc,abstract_syntax=86d35949-83c9-4044-b424-db363231fd0c/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\PIPE\atsvc,abstract_syntax=86d35949-83c9-4044-b424-db363231fd0c/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[ubpmtaskhostchannel,abstract_syntax=86d35949-83c9-4044-b424-db363231fd0c/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49668,abstract_syntax=86d35949-83c9-4044-b424-db363231fd0c/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=3a9ef155-691d-4449-8d05-09ad57031823/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[OLEA1A1626453D76B8C2AB4EAF719B1,abstract_syntax=3a9ef155-691d-4449-8d05-09ad57031823/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[senssvc,abstract_syntax=3a9ef155-691d-4449-8d05-09ad57031823/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\PIPE\atsvc,abstract_syntax=3a9ef155-691d-4449-8d05-09ad57031823/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[ubpmtaskhostchannel,abstract_syntax=3a9ef155-691d-4449-8d05-09ad57031823/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49668,abstract_syntax=3a9ef155-691d-4449-8d05-09ad57031823/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=a398e520-d59a-4bdd-aa7a-3c1e0303a511/0x00000001]: IKE/Authip API
00000000-0000-0000-0000-000000000000 ncalrpc:[OLEA1A1626453D76B8C2AB4EAF719B1,abstract_syntax=a398e520-d59a-4bdd-aa7a-3c1e0303a511/0x00000001]: IKE/Authip API
00000000-0000-0000-0000-000000000000 ncalrpc:[senssvc,abstract_syntax=a398e520-d59a-4bdd-aa7a-3c1e0303a511/0x00000001]: IKE/Authip API
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\PIPE\atsvc,abstract_syntax=a398e520-d59a-4bdd-aa7a-3c1e0303a511/0x00000001]: IKE/Authip API
00000000-0000-0000-0000-000000000000 ncalrpc:[ubpmtaskhostchannel,abstract_syntax=a398e520-d59a-4bdd-aa7a-3c1e0303a511/0x00000001]: IKE/Authip API
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49668,abstract_syntax=a398e520-d59a-4bdd-aa7a-3c1e0303a511/0x00000001]: IKE/Authip API
00000000-0000-0000-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=552d076a-cb29-4e44-8b6a-d15e59e2c0af/0x00000001]: IP Transition Configuration endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[OLEA1A1626453D76B8C2AB4EAF719B1,abstract_syntax=552d076a-cb29-4e44-8b6a-d15e59e2c0af/0x00000001]: IP Transition Configuration endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[senssvc,abstract_syntax=552d076a-cb29-4e44-8b6a-d15e59e2c0af/0x00000001]: IP Transition Configuration endpoint
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\PIPE\atsvc,abstract_syntax=552d076a-cb29-4e44-8b6a-d15e59e2c0af/0x00000001]: IP Transition Configuration endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[ubpmtaskhostchannel,abstract_syntax=552d076a-cb29-4e44-8b6a-d15e59e2c0af/0x00000001]: IP Transition Configuration endpoint
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49668,abstract_syntax=552d076a-cb29-4e44-8b6a-d15e59e2c0af/0x00000001]: IP Transition Configuration endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=2e6035b2-e8f1-41a7-a044-656b439c4c34/0x00000001]: Proxy Manager provider server endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[OLEA1A1626453D76B8C2AB4EAF719B1,abstract_syntax=2e6035b2-e8f1-41a7-a044-656b439c4c34/0x00000001]: Proxy Manager provider server endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[senssvc,abstract_syntax=2e6035b2-e8f1-41a7-a044-656b439c4c34/0x00000001]: Proxy Manager provider server endpoint
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\PIPE\atsvc,abstract_syntax=2e6035b2-e8f1-41a7-a044-656b439c4c34/0x00000001]: Proxy Manager provider server endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[ubpmtaskhostchannel,abstract_syntax=2e6035b2-e8f1-41a7-a044-656b439c4c34/0x00000001]: Proxy Manager provider server endpoint
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49668,abstract_syntax=2e6035b2-e8f1-41a7-a044-656b439c4c34/0x00000001]: Proxy Manager provider server endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=c36be077-e14b-4fe9-8abc-e856ef4f048b/0x00000001]: Proxy Manager client server endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[OLEA1A1626453D76B8C2AB4EAF719B1,abstract_syntax=c36be077-e14b-4fe9-8abc-e856ef4f048b/0x00000001]: Proxy Manager client server endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[senssvc,abstract_syntax=c36be077-e14b-4fe9-8abc-e856ef4f048b/0x00000001]: Proxy Manager client server endpoint
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\PIPE\atsvc,abstract_syntax=c36be077-e14b-4fe9-8abc-e856ef4f048b/0x00000001]: Proxy Manager client server endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[ubpmtaskhostchannel,abstract_syntax=c36be077-e14b-4fe9-8abc-e856ef4f048b/0x00000001]: Proxy Manager client server endpoint
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49668,abstract_syntax=c36be077-e14b-4fe9-8abc-e856ef4f048b/0x00000001]: Proxy Manager client server endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=c49a5a70-8a7f-4e70-ba16-1e8f1f193ef1/0x00000001]: Adh APIs
00000000-0000-0000-0000-000000000000 ncalrpc:[OLEA1A1626453D76B8C2AB4EAF719B1,abstract_syntax=c49a5a70-8a7f-4e70-ba16-1e8f1f193ef1/0x00000001]: Adh APIs
00000000-0000-0000-0000-000000000000 ncalrpc:[senssvc,abstract_syntax=c49a5a70-8a7f-4e70-ba16-1e8f1f193ef1/0x00000001]: Adh APIs
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\PIPE\atsvc,abstract_syntax=c49a5a70-8a7f-4e70-ba16-1e8f1f193ef1/0x00000001]: Adh APIs
00000000-0000-0000-0000-000000000000 ncalrpc:[ubpmtaskhostchannel,abstract_syntax=c49a5a70-8a7f-4e70-ba16-1e8f1f193ef1/0x00000001]: Adh APIs
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49668,abstract_syntax=c49a5a70-8a7f-4e70-ba16-1e8f1f193ef1/0x00000001]: Adh APIs
00000000-0000-0000-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=b18fbab6-56f8-4702-84e0-41053293a869/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncalrpc:[OLEA1A1626453D76B8C2AB4EAF719B1,abstract_syntax=b18fbab6-56f8-4702-84e0-41053293a869/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncalrpc:[senssvc,abstract_syntax=b18fbab6-56f8-4702-84e0-41053293a869/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\PIPE\atsvc,abstract_syntax=b18fbab6-56f8-4702-84e0-41053293a869/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncalrpc:[ubpmtaskhostchannel,abstract_syntax=b18fbab6-56f8-4702-84e0-41053293a869/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49668,abstract_syntax=b18fbab6-56f8-4702-84e0-41053293a869/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-d7414fba9a6992ac5a,abstract_syntax=b18fbab6-56f8-4702-84e0-41053293a869/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncalrpc:[IUserProfile2,abstract_syntax=0d3c7f20-1c8d-4654-a1b3-51563b298bda/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncalrpc:[OLEA1A1626453D76B8C2AB4EAF719B1,abstract_syntax=0d3c7f20-1c8d-4654-a1b3-51563b298bda/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncalrpc:[senssvc,abstract_syntax=0d3c7f20-1c8d-4654-a1b3-51563b298bda/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\PIPE\atsvc,abstract_syntax=0d3c7f20-1c8d-4654-a1b3-51563b298bda/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncalrpc:[ubpmtaskhostchannel,abstract_syntax=0d3c7f20-1c8d-4654-a1b3-51563b298bda/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49668,abstract_syntax=0d3c7f20-1c8d-4654-a1b3-51563b298bda/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-d7414fba9a6992ac5a,abstract_syntax=0d3c7f20-1c8d-4654-a1b3-51563b298bda/0x00000001]: UserMgrCli
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-36b7172ed7dff56cda,abstract_syntax=30adc50c-5cbc-46ce-9a0e-91914789e23c/0x00000001]: NRP server endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-36b7172ed7dff56cda,abstract_syntax=f6beaff7-1e19-4fbb-9f8f-b89e2018337c/0x00000001]: Event log TCPIP
00000000-0000-0000-0000-000000000000 ncalrpc:[eventlog,abstract_syntax=f6beaff7-1e19-4fbb-9f8f-b89e2018337c/0x00000001]: Event log TCPIP
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\eventlog,abstract_syntax=f6beaff7-1e19-4fbb-9f8f-b89e2018337c/0x00000001]: Event log TCPIP
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49665,abstract_syntax=f6beaff7-1e19-4fbb-9f8f-b89e2018337c/0x00000001]: Event log TCPIP
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-36b7172ed7dff56cda,abstract_syntax=3c4728c5-f0ab-448b-bda1-6ce01eb0a6d6/0x00000001]: DHCPv6 Client LRPC Endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[eventlog,abstract_syntax=3c4728c5-f0ab-448b-bda1-6ce01eb0a6d6/0x00000001]: DHCPv6 Client LRPC Endpoint
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\eventlog,abstract_syntax=3c4728c5-f0ab-448b-bda1-6ce01eb0a6d6/0x00000001]: DHCPv6 Client LRPC Endpoint
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49665,abstract_syntax=3c4728c5-f0ab-448b-bda1-6ce01eb0a6d6/0x00000001]: DHCPv6 Client LRPC Endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[dhcpcsvc6,abstract_syntax=3c4728c5-f0ab-448b-bda1-6ce01eb0a6d6/0x00000001]: DHCPv6 Client LRPC Endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-36b7172ed7dff56cda,abstract_syntax=3c4728c5-f0ab-448b-bda1-6ce01eb0a6d5/0x00000001]: DHCP Client LRPC Endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[eventlog,abstract_syntax=3c4728c5-f0ab-448b-bda1-6ce01eb0a6d5/0x00000001]: DHCP Client LRPC Endpoint
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\eventlog,abstract_syntax=3c4728c5-f0ab-448b-bda1-6ce01eb0a6d5/0x00000001]: DHCP Client LRPC Endpoint
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49665,abstract_syntax=3c4728c5-f0ab-448b-bda1-6ce01eb0a6d5/0x00000001]: DHCP Client LRPC Endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[dhcpcsvc6,abstract_syntax=3c4728c5-f0ab-448b-bda1-6ce01eb0a6d5/0x00000001]: DHCP Client LRPC Endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[dhcpcsvc,abstract_syntax=3c4728c5-f0ab-448b-bda1-6ce01eb0a6d5/0x00000001]: DHCP Client LRPC Endpoint
b5ccd5ef-4238-440b-bba0-999f828f1cfe ncalrpc:[LRPC-36b7172ed7dff56cda,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
b5ccd5ef-4238-440b-bba0-999f828f1cfe ncalrpc:[eventlog,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
b5ccd5ef-4238-440b-bba0-999f828f1cfe ncacn_np:\\FOREST[\pipe\eventlog,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
b5ccd5ef-4238-440b-bba0-999f828f1cfe ncacn_ip_tcp:0.0.0.0[49665,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
b5ccd5ef-4238-440b-bba0-999f828f1cfe ncalrpc:[dhcpcsvc6,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
b5ccd5ef-4238-440b-bba0-999f828f1cfe ncalrpc:[dhcpcsvc,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
b5ccd5ef-4238-440b-bba0-999f828f1cfe ncalrpc:[LRPC-0eac74a80ab89908b5,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-36b7172ed7dff56cda,abstract_syntax=a500d4c6-0dd1-4543-bc0c-d5f93486eaf8/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[eventlog,abstract_syntax=a500d4c6-0dd1-4543-bc0c-d5f93486eaf8/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\eventlog,abstract_syntax=a500d4c6-0dd1-4543-bc0c-d5f93486eaf8/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_ip_tcp:0.0.0.0[49665,abstract_syntax=a500d4c6-0dd1-4543-bc0c-d5f93486eaf8/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[dhcpcsvc6,abstract_syntax=a500d4c6-0dd1-4543-bc0c-d5f93486eaf8/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[dhcpcsvc,abstract_syntax=a500d4c6-0dd1-4543-bc0c-d5f93486eaf8/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-0eac74a80ab89908b5,abstract_syntax=a500d4c6-0dd1-4543-bc0c-d5f93486eaf8/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-0aad2707be16128a6e,abstract_syntax=a500d4c6-0dd1-4543-bc0c-d5f93486eaf8/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-e30a5dc2f4f17163ea,abstract_syntax=7ea70bcf-48af-4f6a-8968-6a440754d5fa/0x00000001]: NSI server endpoint
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-e30a5dc2f4f17163ea,abstract_syntax=3473dd4d-2e88-4006-9cba-22570909dd10/0x00010005]: WinHttp Auto-Proxy Service
00000000-0000-0000-0000-000000000000 ncalrpc:[OLEE2699C1057F556182FCA64192C2B,abstract_syntax=3473dd4d-2e88-4006-9cba-22570909dd10/0x00010005]: WinHttp Auto-Proxy Service
765294ba-60bc-48b8-92e9-89fd77769d91 ncalrpc:[WMsgKRpc071CB0,abstract_syntax=d95afe70-a6d5-4259-822e-2c84da1ddb0d/0x00000001]: 
765294ba-60bc-48b8-92e9-89fd77769d91 ncacn_np:\\FOREST[\PIPE\InitShutdown,abstract_syntax=d95afe70-a6d5-4259-822e-2c84da1ddb0d/0x00000001]: 
765294ba-60bc-48b8-92e9-89fd77769d91 ncalrpc:[WindowsShutdown,abstract_syntax=d95afe70-a6d5-4259-822e-2c84da1ddb0d/0x00000001]: 
765294ba-60bc-48b8-92e9-89fd77769d91 ncacn_ip_tcp:0.0.0.0[49664,abstract_syntax=d95afe70-a6d5-4259-822e-2c84da1ddb0d/0x00000001]: 
b08669ee-8cb5-43a5-a017-84fe00000000 ncalrpc:[WMsgKRpc071CB0,abstract_syntax=76f226c3-ec14-4325-8a99-6a46348418af/0x00000001]: 
b08669ee-8cb5-43a5-a017-84fe00000000 ncacn_np:\\FOREST[\PIPE\InitShutdown,abstract_syntax=76f226c3-ec14-4325-8a99-6a46348418af/0x00000001]: 
b08669ee-8cb5-43a5-a017-84fe00000000 ncalrpc:[WindowsShutdown,abstract_syntax=76f226c3-ec14-4325-8a99-6a46348418af/0x00000001]: 
6d726574-7273-0076-0000-000000000000 ncalrpc:[umpo,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
6d726574-7273-0076-0000-000000000000 ncalrpc:[actkernel,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
6d726574-7273-0076-0000-000000000000 ncalrpc:[LRPC-e816d8360ad1f9b70b,abstract_syntax=c9ac6db5-82b7-4e55-ae8a-e464ed7b4277/0x00000001]: Impl friendly name
db57eb61-1aa2-4906-9396-23e8b8024c32 ncalrpc:[umpo,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
db57eb61-1aa2-4906-9396-23e8b8024c32 ncalrpc:[actkernel,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
db57eb61-1aa2-4906-9396-23e8b8024c32 ncalrpc:[LRPC-e816d8360ad1f9b70b,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
db57eb61-1aa2-4906-9396-23e8b8024c32 ncalrpc:[LSMApi,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
db57eb61-1aa2-4906-9396-23e8b8024c32 ncacn_np:\\FOREST[\pipe\LSM_API_service,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
db57eb61-1aa2-4906-9396-23e8b8024c32 ncalrpc:[LRPC-5f8bd2ac484ba33a5c,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[umpo,abstract_syntax=697dcda9-3ba9-4eb2-9247-e11f1901b0d2/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[actkernel,abstract_syntax=697dcda9-3ba9-4eb2-9247-e11f1901b0d2/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-e816d8360ad1f9b70b,abstract_syntax=697dcda9-3ba9-4eb2-9247-e11f1901b0d2/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LSMApi,abstract_syntax=697dcda9-3ba9-4eb2-9247-e11f1901b0d2/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncacn_np:\\FOREST[\pipe\LSM_API_service,abstract_syntax=697dcda9-3ba9-4eb2-9247-e11f1901b0d2/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-5f8bd2ac484ba33a5c,abstract_syntax=697dcda9-3ba9-4eb2-9247-e11f1901b0d2/0x00000001]: 
00000000-0000-0000-0000-000000000000 ncalrpc:[LRPC-51e7bb84e16863d074,abstract_syntax=697dcda9-3ba9-4eb2-9247-e11f1901b0d2/0x00000001]: 
9e56cbc5-e634-4267-818e-ffa7dce1fa86 ncalrpc:[umpo,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
9e56cbc5-e634-4267-818e-ffa7dce1fa86 ncalrpc:[actkernel,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
9e56cbc5-e634-4267-818e-ffa7dce1fa86 ncalrpc:[LRPC-e816d8360ad1f9b70b,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
9e56cbc5-e634-4267-818e-ffa7dce1fa86 ncalrpc:[LSMApi,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
9e56cbc5-e634-4267-818e-ffa7dce1fa86 ncacn_np:\\FOREST[\pipe\LSM_API_service,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
9e56cbc5-e634-4267-818e-ffa7dce1fa86 ncalrpc:[LRPC-5f8bd2ac484ba33a5c,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
9e56cbc5-e634-4267-818e-ffa7dce1fa86 ncalrpc:[LRPC-51e7bb84e16863d074,abstract_syntax=d09bdeb5-6171-4a34-bfe2-06fa82652568/0x00000001]: 
epm_Lookup no more entries
```
