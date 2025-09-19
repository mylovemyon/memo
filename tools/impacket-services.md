### list
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' list
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Listing services available on target
                      1394ohci -                                    1394 OHCI Compliant Host Controller -  STOPPED
                         3ware -                                                                  3ware -  RUNNING
                          ACPI -                                                  Microsoft ACPI Driver -  RUNNING
                       AcpiDev -                                                    ACPI Devices driver -  STOPPED
                        acpiex -                                                Microsoft ACPIEx Driver -  RUNNING
                      acpipagr -                                       ACPI Processor Aggregator Driver -  STOPPED
                       AcpiPmi -                                                ACPI Power Meter Driver -  STOPPED
                      acpitime -                                                 ACPI Wake Alarm Driver -  STOPPED
                       ADP80XX -                                                                ADP80XX -  RUNNING
                          ADWS -                                          Active Directory Web Services -  RUNNING
                           AFD -                                  Ancillary Function Driver for Winsock -  RUNNING
                       ahcache -                                        Application Compatibility Cache -  RUNNING
                         AmdK8 -                                                AMD K8 Processor Driver -  STOPPED
                        AmdPPM -                                                   AMD Processor Driver -  RUNNING
                       amdsata -                                                                amdsata -  RUNNING
                        amdsbs -                                                                 amdsbs -  RUNNING
                       amdxata -                                                                amdxata -  RUNNING
                         AppID -                                                           AppID Driver -  STOPPED
                      AppIDSvc -                                                   Application Identity -  STOPPED
                 applockerfltr -                                              Smartlocker Filter Driver -  STOPPED
                       AppMgmt -                                                 Application Management -  STOPPED
                       AppXSvc -                                      AppX Deployment Service (AppXSVC) -  STOPPED
                        arcsas -                    Adaptec SAS/SATA-II RAID Storport's Miniport Driver -  RUNNING
                      AsyncMac -                                          RAS Asynchronous Media Driver -  STOPPED
                         atapi -                                                            IDE Channel -  RUNNING
                       b06bdrv -                                             QLogic Network Adapter VBD -  RUNNING
                  BasicDisplay -                                                           BasicDisplay -  RUNNING
                   BasicRender -                                                            BasicRender -  RUNNING
                     bfadfcoei -                                                              bfadfcoei -  RUNNING
                         bfadi -                                                                  bfadi -  RUNNING
                           BFE -                                                  Base Filtering Engine -  RUNNING
                          BITS -                                Background Intelligent Transfer Service -  STOPPED
                        bowser -                                                 Browser Support Driver -  RUNNING
                       Browser -                                                       Computer Browser -  STOPPED
                        bxfcoe -                                             QLogic FCoE Offload driver -  RUNNING
                         bxois -                                            QLogic Offload iSCSI Driver -  RUNNING
                          cdfs -                                              CD/DVD File System Reader -  STOPPED
                         cdrom -                                                          CD-ROM Driver -  STOPPED
                   CertPropSvc -                                                Certificate Propagation -  STOPPED
                     cht4iscsi -                                                              cht4iscsi -  STOPPED
                       cht4vbd -                                             Chelsio Virtual Bus Driver -  STOPPED
                          CLFS -                                                      Common Log (CLFS) -  RUNNING
                       ClipSVC -                                       Client License Service (ClipSVC) -  STOPPED
                        CmBatt -                           Microsoft ACPI Control Method Battery Driver -  RUNNING
                           CNG -                                                                    CNG -  RUNNING
                  CompositeBus -                                        Composite Bus Enumerator Driver -  RUNNING
                     COMSysApp -                                                COM+ System Application -  RUNNING
                        ConDrv -                                                         Console Driver -  RUNNING
        CoreMessagingRegistrar -                                                          CoreMessaging -  RUNNING
                      CryptSvc -                                                 Cryptographic Services -  RUNNING
                    DcomLaunch -                                           DCOM Server Process Launcher -  RUNNING
                     defragsvc -                                                        Optimize drives -  STOPPED
                 DeviceInstall -                                                 Device Install Service -  STOPPED
                           Dfs -                                                          DFS Namespace -  RUNNING
                          Dfsc -                                            DFS Namespace Client Driver -  RUNNING
                     DfsDriver -                                     DFS Namespace Server Filter Driver -  RUNNING
                          DFSR -                                                        DFS Replication -  RUNNING
                        DfsrRo -                                        DFS Replication ReadOnly Driver -  RUNNING
                          Dhcp -                                                            DHCP Client -  RUNNING
diagnosticshub.standardcollector.service -               Microsoft (R) Diagnostics Hub Standard Collector Service -  STOPPED
                     DiagTrack -                               Connected User Experiences and Telemetry -  RUNNING
                          disk -                                                            Disk Driver -  RUNNING
                         dmvsc -                                                                  dmvsc -  STOPPED
                           DNS -                                                             DNS Server -  RUNNING
                      Dnscache -                                                             DNS Client -  RUNNING
                           DPS -                                              Diagnostic Policy Service -  RUNNING
                     DsRoleSvc -                                                         DS Role Server -  STOPPED
                       DXGKrnl -                                                LDDM Graphics Subsystem -  RUNNING
                    e1iexpress -              Intel(R) PRO/1000 PCI Express Network Connection Driver I -  RUNNING
                       EapHost -                                     Extensible Authentication Protocol -  STOPPED
                         ebdrv -                                 QLogic 10 Gigabit Ethernet Adapter VBD -  RUNNING
                           EFS -                                           Encrypting File System (EFS) -  RUNNING
                       elxfcoe -                                                                elxfcoe -  RUNNING
                       elxstor -                                                                elxstor -  RUNNING
                        ErrDev -                                 Microsoft Hardware Error Device Driver -  STOPPED
                      EventLog -                                                      Windows Event Log -  RUNNING
                   EventSystem -                                                      COM+ Event System -  RUNNING
                         exfat -                                               exFAT File System Driver -  STOPPED
                       fastfat -                                         FAT12/16/32 File System Driver -  RUNNING
                         fcvsc -                                                                  fcvsc -  STOPPED
                           fdc -                                          Floppy Disk Controller Driver -  STOPPED
                       fdPHost -                                       Function Discovery Provider Host -  STOPPED
                      FileInfo -                                         File Information FS MiniFilter -  STOPPED
                      flpydisk -                                                     Floppy Disk Driver -  STOPPED
                        FltMgr -                                                                 FltMgr -  RUNNING
                     FontCache -                                             Windows Font Cache Service -  STOPPED
                     FsDepends -                                      File System Dependency Minifilter -  STOPPED
                    gencounter -                                   Microsoft Hyper-V Generation Counter -  RUNNING
                   GPIOClx0101 -                                  Microsoft GPIO Class Extension Driver -  STOPPED
                         gpsvc -                                                    Group Policy Client -  RUNNING
                       HidBatt -                                                 HID UPS Battery Driver -  STOPPED
                       hidserv -                                         Human Interface Device Service -  STOPPED
                        HidUsb -                                             Microsoft HID Class Driver -  STOPPED
                        HpSAMD -                                                                 HpSAMD -  RUNNING
                          HTTP -                                                           HTTP Service -  RUNNING
                        HvHost -                                                        HV Host Service -  STOPPED
                     hvservice -                              Hypervisor/Virtual Machine Support Driver -  STOPPED
                      hwpolicy -                                                 Hardware Policy Driver -  STOPPED
                      hyperkbd -                                                               hyperkbd -  STOPPED
                    HyperVideo -                                                             HyperVideo -  STOPPED
                      i8042prt -                              i8042 Keyboard and PS/2 Mouse Port Driver -  RUNNING
                      iaStorAV -                                  Intel(R) SATA RAID Controller Windows -  RUNNING
                       iaStorV -                                        Intel RAID Controller Windows 7 -  RUNNING
                         ibbus -                             Mellanox InfiniBand Bus/AL (Filter Driver) -  STOPPED
                        IKEEXT -                                    IKE and AuthIP IPsec Keying Modules -  RUNNING
                      intelide -                                                               intelide -  RUNNING
                      intelppm -                                                 Intel Processor Driver -  STOPPED
                      iphlpsvc -                                                              IP Helper -  RUNNING
                       IPMIDRV -                                                                IPMIDRV -  STOPPED
                         IPNAT -                                          IP Network Address Translator -  STOPPED
                       IPsecGW -                                           Windows IPsec Gateway Driver -  STOPPED
                        isapnp -                                                                 isapnp -  RUNNING
                      iScsiPrt -                                                       iScsiPort Driver -  STOPPED
                       IsmServ -                                                    Intersite Messaging -  RUNNING
                      kbdclass -                                                  Keyboard Class Driver -  RUNNING
                        kbdhid -                                                    Keyboard HID Driver -  STOPPED
                           Kdc -                                       Kerberos Key Distribution Center -  RUNNING
                         kdnic -                    Microsoft Kernel Debug Network Miniport (NDIS 6.20) -  RUNNING
                        KdsSvc -                                     Microsoft Key Distribution Service -  STOPPED
                        KeyIso -                                                      CNG Key Isolation -  STOPPED
                        KPSSVC -                                         KDC Proxy Server service (KPS) -  STOPPED
                        KSecDD -                                                                 KSecDD -  RUNNING
                       KSecPkg -                                                                KSecPkg -  RUNNING
                         KtmRm -                          KtmRm for Distributed Transaction Coordinator -  STOPPED
                  LanmanServer -                                                                 Server -  RUNNING
             LanmanWorkstation -                                                            Workstation -  RUNNING
                        lltdio -                        Link-Layer Topology Discovery Mapper I/O Driver -  RUNNING
                       lltdsvc -                                   Link-Layer Topology Discovery Mapper -  STOPPED
                       lmhosts -                                                  TCP/IP NetBIOS Helper -  RUNNING
                       LSI_SAS -                                                                LSI_SAS -  RUNNING
                     LSI_SAS2i -                                                              LSI_SAS2i -  RUNNING
                     LSI_SAS3i -                                                              LSI_SAS3i -  RUNNING
                       LSI_SSS -                                                                LSI_SSS -  RUNNING
                           LSM -                                                  Local Session Manager -  RUNNING
                       megasas -                                                                megasas -  RUNNING
                        megasr -                                                                 megasr -  RUNNING
                      mlx4_bus -                                       Mellanox ConnectX Bus Enumerator -  STOPPED
                       monitor -                        Microsoft Monitor Class Function Driver Service -  RUNNING
                      mouclass -                                                     Mouse Class Driver -  RUNNING
                        mouhid -                                                       Mouse HID Driver -  STOPPED
                      mountmgr -                                                    Mount Point Manager -  RUNNING
                        mpsdrv -                                  Windows Firewall Authorization Driver -  RUNNING
                        MpsSvc -                                                       Windows Firewall -  RUNNING
                        mrxsmb -                                  SMB MiniRedirector Wrapper and Engine -  RUNNING
                      mrxsmb10 -                                                 SMB 1.x MiniRedirector -  RUNNING
                      mrxsmb20 -                                                 SMB 2.0 MiniRedirector -  RUNNING
                         MSDTC -                                    Distributed Transaction Coordinator -  RUNNING
                          Msfs -                                                                   Msfs -  RUNNING
                      msisadrv -                                                               msisadrv -  RUNNING
                       MSiSCSI -                                      Microsoft iSCSI Initiator Service -  STOPPED
                     msiserver -                                                      Windows Installer -  STOPPED
                MsLbfoProvider -                             Microsoft Load Balancing/Failover Provider -  STOPPED
                         MsRPC -                                                                  MsRPC -  STOPPED
                      mssmbios -                                Microsoft System Management BIOS Driver -  RUNNING
                      MTConfig -                                   Microsoft Input Configuration Driver -  STOPPED
                           Mup -                                                                    Mup -  RUNNING
                        mvumis -                                                                 mvumis -  RUNNING
                        NcaSvc -                                         Network Connectivity Assistant -  STOPPED
                        ndfltr -                                                  NetworkDirect Service -  STOPPED
                          NDIS -                                                     NDIS System Driver -  RUNNING
                       NdisCap -                                                 Microsoft NDIS Capture -  STOPPED
                NdisImPlatform -                         Microsoft Network Adapter Multiplexor Protocol -  STOPPED
                      NdisTapi -                                         Remote Access NDIS TAPI Driver -  STOPPED
                       Ndisuio -                                             NDIS Usermode I/O Protocol -  STOPPED
                NdisVirtualBus -                           Microsoft Virtual Network Adapter Enumerator -  RUNNING
                       NdisWan -                                          Remote Access NDIS WAN Driver -  STOPPED
                 ndiswanlegacy -                                   Remote Access LEGACY NDIS WAN Driver -  STOPPED
                       ndproxy -                @%SystemRoot%\system32\drivers\todo.sys,-101;NDIS Proxy -  STOPPED
                       NetBIOS -                                                      NetBIOS Interface -  RUNNING
                         NetBT -                                                                  NetBT -  RUNNING
                      Netlogon -                                                               Netlogon -  RUNNING
                      netprofm -                                                   Network List Service -  RUNNING
                   NetSetupSvc -                                                  Network Setup Service -  STOPPED
             NetTcpPortSharing -                                           Net.Tcp Port Sharing Service -  STOPPED
                        netvsc -                                                                 netvsc -  STOPPED
                        NlaSvc -                                             Network Location Awareness -  RUNNING
                          Npfs -                                                                   Npfs -  RUNNING
                     npsvctrig -                                    Named pipe service trigger provider -  RUNNING
                           nsi -                                        Network Store Interface Service -  RUNNING
                      nsiproxy -                                               NSI Proxy Service Driver -  RUNNING
                          NTDS -                                       Active Directory Domain Services -  RUNNING
                         NtFrs -                                                       File Replication -  STOPPED
                          Ntfs -                                                                   Ntfs -  RUNNING
                          Null -                                                                   Null -  RUNNING
                        nvraid -                                                                 nvraid -  RUNNING
                        nvstor -                                                                 nvstor -  RUNNING
                       Parport -                                                   Parallel port driver -  STOPPED
                       partmgr -                                                       Partition driver -  RUNNING
                           pci -                                                         PCI Bus Driver -  RUNNING
                        pciide -                                                                 pciide -  RUNNING
                           pcw -                                Performance Counters for Windows Driver -  RUNNING
                           pdc -                                                                    pdc -  RUNNING
                     percsas2i -                                                              percsas2i -  RUNNING
                     percsas3i -                                                              percsas3i -  RUNNING
                      PerfHost -                                           Performance Counter DLL Host -  STOPPED
                           pla -                                              Performance Logs & Alerts -  STOPPED
                      PlugPlay -                                                          Plug and Play -  RUNNING
                   PolicyAgent -                                                     IPsec Policy Agent -  RUNNING
                         Power -                                                                  Power -  RUNNING
                  PptpMiniport -                                                    WAN Miniport (PPTP) -  STOPPED
                     Processor -                                                       Processor Driver -  STOPPED
                       ProfSvc -                                                   User Profile Service -  RUNNING
                        Psched -                                                   QoS Packet Scheduler -  RUNNING
                       ql2300i -                 QLogic Fibre Channel STOR Miniport Inbox Driver (wx64) -  RUNNING
                      ql40xx2i -                                     QLogic iSCSI Miniport Inbox Driver -  RUNNING
                       qlfcoei -                        QLogic [FCoE] STOR Miniport Inbox Driver (wx64) -  RUNNING
                   RasAgileVpn -                                                   WAN Miniport (IKEv2) -  STOPPED
                        RasGre -                                                     WAN Miniport (GRE) -  STOPPED
                       Rasl2tp -                                                    WAN Miniport (L2TP) -  STOPPED
                        RasMan -                                       Remote Access Connection Manager -  STOPPED
                      RasPppoe -                                             Remote Access PPPOE Driver -  STOPPED
                       RasSstp -                                                    WAN Miniport (SSTP) -  STOPPED
                         rdbss -                                        Redirected Buffering Sub System -  RUNNING
                         RDPDR -                                Remote Desktop Device Redirector Driver -  STOPPED
              RdpVideoMiniport -                                   Remote Desktop Video Miniport Driver -  STOPPED
                          ReFS -                                                                   ReFS -  STOPPED
                        ReFSv1 -                                                                 ReFSv1 -  STOPPED
                  RemoteAccess -                                              Routing and Remote Access -  STOPPED
                RemoteRegistry -                                                        Remote Registry -  STOPPED
                  RpcEptMapper -                                                    RPC Endpoint Mapper -  RUNNING
                         RpcSs -                                            Remote Procedure Call (RPC) -  RUNNING
                      RSoPProv -                                       Resultant Set of Policy Provider -  STOPPED
                        rspndr -                                Link-Layer Topology Discovery Responder -  RUNNING
                         s3cap -                                                                  s3cap -  STOPPED
                        sacdrv -                                                                 sacdrv -  STOPPED
                        sacsvr -                                  Special Administration Console Helper -  STOPPED
                         SamSs -                                              Security Accounts Manager -  RUNNING
                      sbp2port -                                    SBP-2 Transport/Protocol Bus Driver -  RUNNING
                      SCardSvr -                                                             Smart Card -  STOPPED
                  ScDeviceEnum -                                  Smart Card Device Enumeration Service -  STOPPED
                      scfilter -                                     Smart card PnP Class Filter Driver -  STOPPED
                      Schedule -                                                         Task Scheduler -  RUNNING
                        scmbus -                              Microsoft Storage Class Memory Bus Driver -  RUNNING
                   scmdisk0101 -                                         Microsoft NVDIMM-N disk driver -  STOPPED
                   SCPolicySvc -                                              Smart Card Removal Policy -  STOPPED
                      seclogon -                                                        Secondary Logon -  STOPPED
                          SENS -                                      System Event Notification Service -  RUNNING
                         SerCx -                                            Serial UART Support Library -  STOPPED
                       Serenum -                                                  Serenum Filter Driver -  STOPPED
                        Serial -                                                     Serial port driver -  STOPPED
                      sermouse -                                                    Serial Mouse Driver -  STOPPED
                    SessionEnv -                                           Remote Desktop Configuration -  STOPPED
                       sfloppy -                                        High-Capacity Floppy Disk Drive -  STOPPED
                  SharedAccess -                                      Internet Connection Sharing (ICS) -  STOPPED
                      SiSRaid2 -                                                               SiSRaid2 -  RUNNING
                      SiSRaid4 -                                                               SiSRaid4 -  RUNNING
                     smbdirect -                                                              smbdirect -  STOPPED
                       smphost -                                           Microsoft Storage Spaces SMP -  STOPPED
                      SNMPTRAP -                                                              SNMP Trap -  STOPPED
                     spaceport -                                                  Storage Spaces Driver -  RUNNING
                         SpbCx -                                  Simple Peripheral Bus Support Library -  STOPPED
                       Spooler -                                                          Print Spooler -  STOPPED
                        sppsvc -                                                    Software Protection -  STOPPED
                           srv -                                                Server SMB 1.xxx Driver -  RUNNING
                          srv2 -                                                Server SMB 2.xxx Driver -  RUNNING
                        srvnet -                                                                 srvnet -  RUNNING
                       SstpSvc -                               Secure Socket Tunneling Protocol Service -  STOPPED
               StateRepository -                                               State Repository Service -  STOPPED
                      stexstor -                                                               stexstor -  RUNNING
                      storahci -                                    Microsoft Standard SATA AHCI Driver -  RUNNING
                       storflt -                                  Microsoft Hyper-V Storage Accelerator -  RUNNING
                      stornvme -                                  Microsoft Standard NVM Express Driver -  RUNNING
                    storqosflt -                                              Storage QoS Filter Driver -  RUNNING
                       storvsc -                                                                storvsc -  RUNNING
                         svsvc -                                                          Spot Verifier -  STOPPED
                        swenum -                                                    Software Bus Driver -  RUNNING
                         swprv -                                Microsoft Software Shadow Copy Provider -  STOPPED
                    Synth3dVsc -                                                             Synth3dVsc -  STOPPED
                       SysMain -                                                             Superfetch -  STOPPED
            SystemEventsBroker -                                                   System Events Broker -  RUNNING
                         Tcpip -                                                 TCP/IP Protocol Driver -  RUNNING
                        Tcpip6 -                          @todo.dll,-100;Microsoft IPv6 Protocol Driver -  STOPPED
                      tcpipreg -                                          TCP/IP Registry Compatibility -  RUNNING
                           tdx -                                        NetIO Legacy TDI Support Driver -  RUNNING
                      terminpt -                                  Microsoft Remote Desktop Input Driver -  STOPPED
                   TermService -                                                Remote Desktop Services -  STOPPED
          TieringEngineService -                                               Storage Tiers Management -  STOPPED
                 TimeBrokerSvc -                                                            Time Broker -  RUNNING
                           TPM -                                                                    TPM -  STOPPED
              TrustedInstaller -                                              Windows Modules Installer -  STOPPED
                      tsusbhub -                                                 Remote Desktop USB Hub -  STOPPED
                        tunnel -                               Microsoft Tunnel Miniport Adapter Driver -  RUNNING
                        UALSVC -                                            User Access Logging Service -  RUNNING
                      UASPStor -                                         USB Attached SCSI (UAS) Driver -  RUNNING
                      Ucx01000 -                                               USB Host Support Library -  RUNNING
                          udfs -                                                                   udfs -  STOPPED
                          UEFI -                                                  Microsoft UEFI Driver -  STOPPED
                         umbus -                                                UMBus Enumerator Driver -  RUNNING
                        UmPass -                                                Microsoft UMPass Driver -  STOPPED
                  UmRdpService -                       Remote Desktop Services UserMode Port Redirector -  STOPPED
                       usbccgp -                                    Microsoft USB Generic Parent Driver -  RUNNING
                       usbehci -             Microsoft USB 2.0 Enhanced Host Controller Miniport Driver -  RUNNING
                        usbhub -                                      Microsoft USB Standard Hub Driver -  RUNNING
                       USBHUB3 -                                                         SuperSpeed Hub -  RUNNING
                       usbohci -                     Microsoft USB Open Host Controller Miniport Driver -  STOPPED
                      usbprint -                                            Microsoft USB PRINTER Class -  STOPPED
                        usbser -                                            Microsoft USB Serial Driver -  STOPPED
                       USBSTOR -                                                USB Mass Storage Driver -  RUNNING
                       usbuhci -                Microsoft USB Universal Host Controller Miniport Driver -  STOPPED
                       USBXHCI -                                     USB xHCI Compliant Host Controller -  RUNNING
                   UserManager -                                                           User Manager -  RUNNING
                        UsoSvc -                         Update Orchestrator Service for Windows Update -  STOPPED
                      VaultSvc -                                                     Credential Manager -  STOPPED
                      vdrvroot -                                     Microsoft Virtual Drive Enumerator -  RUNNING
                           vds -                                                           Virtual Disk -  RUNNING
                   VerifierExt -                                                            VerifierExt -  STOPPED
                 VGAuthService -                                VMware Alias Manager and Ticket Service -  RUNNING
                         vhdmp -                                                                  vhdmp -  STOPPED
                        vm3dmp -                                                                 vm3dmp -  RUNNING
                  vm3dmp-debug -                                                           vm3dmp-debug -  STOPPED
                  vm3dmp-stats -                                                           vm3dmp-stats -  STOPPED
                 vm3dmp_loader -                                                          vm3dmp_loader -  RUNNING
                         vmbus -                                                    Virtual Machine Bus -  RUNNING
                      VMBusHID -                                                               VMBusHID -  STOPPED
                          vmci -                                                 VMware VMCI Bus Driver -  RUNNING
                         vmgid -                          Microsoft Hyper-V Guest Infrastructure Driver -  STOPPED
            vmicguestinterface -                                        Hyper-V Guest Service Interface -  STOPPED
                 vmicheartbeat -                                              Hyper-V Heartbeat Service -  STOPPED
               vmickvpexchange -                                          Hyper-V Data Exchange Service -  STOPPED
                       vmicrdv -                          Hyper-V Remote Desktop Virtualization Service -  STOPPED
                  vmicshutdown -                                         Hyper-V Guest Shutdown Service -  STOPPED
                  vmictimesync -                                   Hyper-V Time Synchronization Service -  STOPPED
                 vmicvmsession -                                      Hyper-V PowerShell Direct Service -  STOPPED
                       vmicvss -                                   Hyper-V Volume Shadow Copy Requestor -  STOPPED
                      vmmemctl -                                                  Memory Control Driver -  RUNNING
                       vmmouse -                                                 VMware Pointing Device -  RUNNING
                       VMTools -                                                           VMware Tools -  RUNNING
                    vmusbmouse -                                             VMware USB Pointing Device -  STOPPED
                         vmvss -                                               VMware Snapshot Provider -  STOPPED
     VMwareCAFCommAmqpListener -                                  VMware CAF AMQP Communication Service -  STOPPED
  VMwareCAFManagementAgentHost -                                    VMware CAF Management Agent Service -  STOPPED
                        volmgr -                                                  Volume Manager Driver -  RUNNING
                       volmgrx -                                                 Dynamic Volume Manager -  RUNNING
                       volsnap -                                              Volume Shadow Copy driver -  RUNNING
                        volume -                                                          Volume driver -  RUNNING
                          vpci -                                      Microsoft Hyper-V Virtual PCI Bus -  STOPPED
                       vsmraid -                                                                vsmraid -  RUNNING
                         vsock -        vSockets Virtual Machine Communication Interface Sockets driver -  RUNNING
                           VSS -                                                     Volume Shadow Copy -  STOPPED
                      VSTXRAID -                       VIA StorX Storage RAID Controller Windows Driver -  RUNNING
                       W32Time -                                                           Windows Time -  RUNNING
                      WacomPen -                                            Wacom Serial Pen HID Driver -  STOPPED
                        wanarp -                                            Remote Access IP ARP Driver -  STOPPED
                      wanarpv6 -                                          Remote Access IPv6 ARP Driver -  STOPPED
                        WdBoot -                                           Windows Defender Boot Driver -  STOPPED
                      Wdf01000 -                                  Kernel Mode Driver Frameworks service -  RUNNING
                      WdFilter -                                    Windows Defender Mini-Filter Driver -  RUNNING
                WdiServiceHost -                                                Diagnostic Service Host -  STOPPED
                 WdiSystemHost -                                                 Diagnostic System Host -  STOPPED
                      WdNisDrv -                      Windows Defender Network Inspection System Driver -  STOPPED
                      WdNisSvc -                            Windows Defender Network Inspection Service -  STOPPED
                        Wecsvc -                                                Windows Event Collector -  STOPPED
                        WerSvc -                                        Windows Error Reporting Service -  STOPPED
                       WFPLWFS -                                   Microsoft Windows Filtering Platform -  RUNNING
                      WIMMount -                                                               WIMMount -  STOPPED
                     WinDefend -                                               Windows Defender Service -  RUNNING
           WinHttpAutoProxySvc -                               WinHTTP Web Proxy Auto-Discovery Service -  RUNNING
                        WinMad -                                                         WinMad Service -  STOPPED
                       Winmgmt -                                     Windows Management Instrumentation -  RUNNING
                        WinNat -                                                     Windows NAT Driver -  STOPPED
                         WinRM -                              Windows Remote Management (WS-Management) -  RUNNING
                        WINUSB -                                                          WinUsb Driver -  STOPPED
                      WinVerbs -                                                       WinVerbs Service -  STOPPED
                         wisvc -                                                Windows Insider Service -  STOPPED
                       WmiAcpi -                        Microsoft Windows Management Interface for ACPI -  STOPPED
                      wmiApSrv -                                                WMI Performance Adapter -  STOPPED
                           Wof -                              Windows Overlay File System Filter Driver -  RUNNING
                       ws2ifsl -        Windows Socket 2.0 Non-IFS Service Provider Support Environment -  RUNNING
                      wuauserv -                                                         Windows Update -  STOPPED
                        WudfPf -                            User Mode Driver Frameworks Platform Driver -  STOPPED
                        WUDFRd -                                                                 WUDFRd -  STOPPED
                       wudfsvc -                 Windows Driver Foundation - User-mode Driver Framework -  STOPPED
Total Services: 372
```
### status
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' status -name MpsSvc 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
Querying status for MpsSvc
                        MpsSvc -  RUNNING
```
### start
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' start -name MpsSvc
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Starting service MpsSvc
```
### stop
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' stop -name MpsSvc
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Stopping service MpsSvc
```
### config
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' config -name MpsSvc
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Querying service config for MpsSvc
TYPE              : 32 -  SERVICE_WIN32_SHARE_PROCESS  
START_TYPE        :  2 -  AUTO START
ERROR_CONTROL     :  1 -  NORMAL
BINARY_PATH_NAME  : C:\Windows\system32\svchost.exe -k LocalServiceNoNetwork
LOAD_ORDER_GROUP  : NetworkProvider
TAG               : 0
DISPLAY_NAME      : Windows Firewall
DEPENDENCIES      : mpsdrv/bfe/
SERVICE_START_NAME: NT Authority\LocalService
```
### create
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' create -name test -display test -path 'C:\Windows\System32\cmd.exe'
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]


└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' config -name test
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Querying service config for test
TYPE              : 16 -  SERVICE_WIN32_OWN_PROCESS  
START_TYPE        :  2 -  AUTO START
ERROR_CONTROL     :  0 -  IGNORE
BINARY_PATH_NAME  : C:\Windows\System32\cmd.exe
LOAD_ORDER_GROUP  : 
TAG               : 0
DISPLAY_NAME      : test
DEPENDENCIES      : /
SERVICE_START_NAME: LocalSystem
```
### change
```sh
# https://learn.microsoft.com/en-us/dotnet/api/system.serviceprocess.servicetype?view=netframework-4.8.1#fields
# https://learn.microsoft.com/en-us/dotnet/api/system.serviceprocess.servicestartmode?view=netframework-4.8.1#fields

└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' change -name test -display test -service_type 32 -start_type 3
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Changing service config for test
                                                                                                                                                                                

└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' config -name test 
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Querying service config for test
TYPE              : 32 -  SERVICE_WIN32_SHARE_PROCESS  
START_TYPE        :  3 -  DEMAND START
ERROR_CONTROL     :  0 -  IGNORE
BINARY_PATH_NAME  : C:\Windows\System32\cmd.exe
LOAD_ORDER_GROUP  : 
TAG               : 0
DISPLAY_NAME      : test
DEPENDENCIES      : /
SERVICE_START_NAME: LocalSystem
```
### delete
```sh
└─$ impacket-services -debug -hashes ':32693b11e6aa90eb43d32c72a07ceea6' 'htb.local/administrator@10.129.95.210' delete -name test
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] StringBinding ncacn_np:10.129.95.210[\pipe\svcctl]
[*] Deleting service test
```
