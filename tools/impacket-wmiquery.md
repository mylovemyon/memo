- https://learn.microsoft.com/ja-jp/windows/win32/cimwin32prov/win32-provider
- https://learn.microsoft.com/en-us/windows/win32/wmisdk/wql-sql-for-wmi


### command
```sh
└─$ impacket-wmiquery -debug 'htb.local/administrator@10.129.138.203' -hashes 'aad3b435b51404eeaad3b435b51404ee:32693b11e6aa90eb43d32c72a07ceea6'                          
Impacket v0.13.0.dev0 - Copyright Fortra, LLC and its affiliated companies 

[+] Impacket Library Installation Path: /usr/lib/python3/dist-packages/impacket
[+] Target system is 10.129.138.203 and isFQDN is False
[+] StringBinding: \\\\FOREST[\\PIPE\\atsvc]
[+] StringBinding: FOREST[49668]
[+] StringBinding: 10.129.138.203[49668]
[+] StringBinding chosen: ncacn_ip_tcp:10.129.138.203[49668]
[!] Press help for extra shell commands
```

### Win32_AssociatedProcessorMemory
```
WQL> SELECT * FROM Win32_AssociatedProcessorMemory
| Antecedent | Dependent | BusSpeed | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 0" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 1" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None | 
| \\FOREST\root\cimv2:Win32_CacheMemory.DeviceID="Cache Memory 2" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" | None |
```

### Win32_AutochkSetting
```sh
WQL> SELECT * FROM Win32_AutochkSetting
| SettingID | Caption | Description | UserInputDelay | 
| Microsoft Windows Server 2016 Standard|C:\Windows|\Device\Harddisk0\Partition4 | None | None | 10 |
```

### Win32_BaseBoard
```sh
WQL> SELECT * FROM Win32_BaseBoard
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | Height | Depth | Width | Weight | HostingBoard | SlotLayout | RequiresDaughterBoard | SpecialRequirements | RequirementsDescription | Product | ConfigOptions | 
| Base Board | Base Board | None | Base Board | OK | Win32_BaseBoard | Intel Corporation | None | None | None | Base Board | None | None | None | True | False | False | False | None | None | None | None | False | None | False | True | None | 440BX Desktop Reference Platform | None |
```

### Win32_BIOS
```sh
WQL> SELECT * FROM Win32_BIOS
| Caption | Description | InstallDate | Name | Status | Version | SoftwareElementState | SoftwareElementID | TargetOperatingSystem | OtherTargetOS | Manufacturer | BuildNumber | SerialNumber | CodeSet | IdentificationCode | LanguageEdition | PrimaryBIOS | ReleaseDate | BiosCharacteristics | InstallableLanguages | ListOfLanguages | CurrentLanguage | SMBIOSPresent | SMBIOSMajorVersion | SMBIOSMinorVersion | SMBIOSBIOSVersion | BIOSVersion | SystemBiosMajorVersion | SystemBiosMinorVersion | EmbeddedControllerMajorVersion | EmbeddedControllerMinorVersion | 
| VMW71.00V.24504846.B64.2501180334 | VMW71.00V.24504846.B64.2501180334 | None | VMW71.00V.24504846.B64.2501180334 | OK | INTEL  - 6040000 | 3 | VMW71.00V.24504846.B64.2501180334 | 0 | None | VMware, Inc. | None | VMware-42 14 dd 01 77 df ed 36-48 41 b0 f9 f7 10 45 bd | None | None | None | True | 20250118000000.000000+000 | 4 7 9 11 42 43  | None | None | None | True | 2 | 7 | VMW71.00V.24504846.B64.2501180334 | INTEL  - 6040000 VMW71.00V.24504846.B64.2501180334 VMware, Inc. - 10000  | 255 | 255 | 255 | 255 |
```

### Win32_Bus
```sh
WQL> SELECT * FROM Win32_Bus
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | BusNum | BusType | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | ACPIBus_BUS_0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 0 | 17 | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | PCI_BUS_0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 0 | 5 | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | PCI_BUS_11 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 11 | 5 | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | PCI_BUS_2&DABA3FF&1 | None | ACPI\PNP0A03\2&DABA3FF&1 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 2 | 5 | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | PNP_BUS_0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 0 | 15 | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | PCI_BUS_3 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 3 | 5 | 
| Bus | Bus | None | Bus | None | 65535 | Win32_Bus | None | True | PCI_BUS_2 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 2 | 5 |
```

### Win32_CacheMemory
```sh
WQL> SELECT * FROM Win32_CacheMemory
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | StartingAddress | EndingAddress | ErrorInfo | OtherErrorDescription | CorrectableError | ErrorTime | ErrorAccess | ErrorTransferSize | ErrorData | ErrorDataOrder | ErrorAddress | SystemLevelAddress | ErrorResolution | AdditionalErrorData | Level | WritePolicy | CacheType | LineSize | ReplacementPolicy | ReadPolicy | FlushTimer | Associativity | Location | MaxCacheSize | InstalledSize | SupportedSRAM | CurrentSRAM | ErrorCorrectType | CacheSpeed | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 0 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 64 | L1 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 3 | 3 | 5 | None | 65535 | 65535 | None | 7 | 0 | 64 | 64 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 1 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 512 | L2 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 4 | 3 | 5 | None | 65535 | 65535 | None | 7 | 1 | 512 | 512 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 2 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 65536 | None | 512 | L3 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 5 | 3 | 5 | None | 65535 | 65535 | None | 8 | 1 | 32768 | 32768 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 3 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 64 | L1 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 3 | 3 | 5 | None | 65535 | 65535 | None | 7 | 0 | 64 | 64 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 4 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 1024 | None | 512 | L2 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 4 | 3 | 5 | None | 65535 | 65535 | None | 7 | 1 | 512 | 512 | 2 3 4 5 6  | 6  | 2 | None | 
| Cache Memory | Cache Memory | None | Cache Memory | OK | 3 | Win32_CacheMemory | None | True | Cache Memory 5 | None | None | True | 3 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 65536 | None | 512 | L3 CACHE | 18446744073709551615 | 18446744073709551615 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | 5 | 3 | 5 | None | 65535 | 65535 | None | 8 | 1 | 32768 | 32768 | 2 3 4 5 6  | 6  | 2 | None |
```

### Win32_CIMLogicalDeviceCIMDataFile
```sh
WQL> SELECT * FROM Win32_CIMLogicalDeviceCIMDataFile
| Antecedent | Dependent | Purpose | PurposeDescription | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\ACPI0003\\1" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\CMBATT.SYS" | 2 | Control Method Battery Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A8" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A9" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AA" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AB" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AC" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AD" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AE" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AF" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B1" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B2" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B3" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B4" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B5" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B6" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B7" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B8" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B9" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BA" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BB" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BC" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BD" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BE" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BF" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C1" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C2" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C3" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C4" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C5" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C6" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C7" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_10D3&SUBSYS_07D015AD&REV_00\\005056FFFFB441AF00" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\E1I63X64.SYS" | 2 | Intel(R) Gigabit Adapter NDIS 6.x driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\VOLMGR\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VOLMGR.SYS" | 2 | Volume Manager Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\ATAPI.SYS" | 2 | ATAPI IDE Miniport Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&1" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\ATAPI.SYS" | 2 | ATAPI IDE Miniport Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\VMW0001\\7" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VMGENCOUNTER.SYS" | 2 | Virtual Machine Generation Counter | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\BASICDISPLAY\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\BASICDISPLAY.SYS" | 2 | Microsoft Basic Display Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\VMW0003\\4&25EE97C0&0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\I8042PRT.SYS" | 2 | i8042 Port Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\AUTHENTICAMD_-_AMD64_FAMILY_25_MODEL_1_-_AMD_EPYC_7513_32-CORE_PROCESSOR________________\\_0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\AMDPPM.SYS" | 2 | Processor Device Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\AUTHENTICAMD_-_AMD64_FAMILY_25_MODEL_1_-_AMD_EPYC_7513_32-CORE_PROCESSOR________________\\_1" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\AMDPPM.SYS" | 2 | Processor Device Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\COMPOSITEBUS\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERSTORE\\FILEREPOSITORY\\COMPOSITEBUS.INF_AMD64_A140581A8F8B58B7\\COMPOSITEBUS.SYS" | 2 | Multi-Transport Composite Bus Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\VDRVROOT\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VDRVROOT.SYS" | 2 | Virtual Drive Root Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="SWD\\IP_TUNNEL_VBUS\\ISATAP_0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\TUNNEL.SYS" | 2 | Microsoft Tunnel Interface Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\SPACEPORT\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\SPACEPORT.SYS" | 2 | Storage Spaces Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\KDNIC\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\KDNIC.SYS" | 2 | Microsoft Kernel Debugger Network Miniport | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_1000&DEV_0054&SUBSYS_197615AD&REV_01\\4&2732702B&0&00A8" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\LSI_SAS.SYS" | 2 | LSI Fusion-MPT SAS Driver (StorPort) | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\UMBUS\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\UMBUS.SYS" | 2 | User-Mode Bus Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="SCSI\\DISK&VEN_VMWARE&PROD_VIRTUAL_DISK\\5&1982005&0&000100" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\DISK.SYS" | 2 | PnP Disk Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7110&SUBSYS_197615AD&REV_08\\3&18D45AA6&0&38" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\MSISADRV.SYS" | 2 | ISA Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0303\\4&25EE97C0&0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\I8042PRT.SYS" | 2 | i8042 Port Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI_HAL\\PNP0C08\\0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\ACPI.SYS" | 2 | ACPI Driver for NT | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\BASICRENDER\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\BASICRENDER.SYS" | 2 | Microsoft Basic Render Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="STORAGE\\VOLUME\\{E52A11BF-0A55-11EC-B2C3-806E6F6E6963}#0000000000004400" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VOLUME.SYS" | 2 | Volume driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="STORAGE\\VOLUME\\{E52A11BF-0A55-11EC-B2C3-806E6F6E6963}#0000000008100000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VOLUME.SYS" | 2 | Volume driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="DISPLAY\\DEFAULT_MONITOR\\4&31BE19FA&0&UID0" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\MONITOR.SYS" | 2 | Monitor Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07E0&SUBSYS_07E015AD&REV_00\\4&B70F118&0&0888" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\STORAHCI.SYS" | 2 | MS AHCI Storport Miniport Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\VMWVMCIHOSTDEV\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VMCI.SYS" | 2 | VMware PCI VMCI Bus Device | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7191&SUBSYS_00000000&REV_01\\3&18D45AA6&0&08" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="STORAGE\\VOLUME\\{E52A11BF-0A55-11EC-B2C3-806E6F6E6963}#0000000024300000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VOLUME.SYS" | 2 | Volume driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\NDISVIRTUALBUS\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\NDISVIRTUALBUS.SYS" | 2 | Microsoft Virtual Network Adapter Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0740&SUBSYS_074015AD&REV_10\\3&18D45AA6&0&3F" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VMCI.SYS" | 2 | VMware PCI VMCI Bus Device | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="STORAGE\\VOLUME\\{E52A11BF-0A55-11EC-B2C3-806E6F6E6963}#000000002A600000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VOLUME.SYS" | 2 | Volume driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\MSSMBIOS\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\MSSMBIOS.SYS" | 2 | System Management BIOS Driver | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0790&SUBSYS_079015AD&REV_02\\3&18D45AA6&0&88" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\PCI.SYS" | 2 | NT Plug and Play PCI Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ROOT\\SYSTEM\\0000" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\SWENUM.SYS" | 2 | Plug and Play Software Device Enumerator | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0405&SUBSYS_040515AD&REV_00\\3&18D45AA6&0&78" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\VM3DMP_LOADER.SYS" | 2 | VMware SVGA 3D Miniport Loader | 
| \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\\3&18D45AA6&0&39" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\WINDOWS\\SYSTEM32\\DRIVERS\\INTELIDE.SYS" | 2 | Intel PCI IDE Driver |
```

### Win32_ComputerSystemProcessor
```sh
WQL> SELECT * FROM Win32_ComputerSystemProcessor
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_ComputerSystem.Name="FOREST" | \\FOREST\root\cimv2:Win32_Processor.DeviceID="CPU0" |
```

### Win32_DesktopMonitor
```sh
WQL> SELECT * FROM Win32_DesktopMonitor
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | IsLocked | DisplayType | Bandwidth | ScreenHeight | ScreenWidth | MonitorManufacturer | MonitorType | PixelsPerXLogicalInch | PixelsPerYLogicalInch | 
| Generic Non-PnP Monitor | Generic Non-PnP Monitor | None | Generic Non-PnP Monitor | OK | 8 | Win32_DesktopMonitor | 0 | False | DesktopMonitor1 | None | DISPLAY\DEFAULT_MONITOR\4&31BE19FA&0&UID0 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | True | 65535 | None | None | None | (Standard monitor types) | Generic Non-PnP Monitor | 96 | 96 |
```

### Win32_DeviceBus
```sh
WQL> SELECT * FROM Win32_DeviceBus
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\4" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\ACPI0003\\1" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A8" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A9" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AA" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AB" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AC" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AD" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AE" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AF" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B1" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B2" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B3" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B4" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B5" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B6" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B7" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B8" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B9" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BA" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BB" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BC" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BD" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BE" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BF" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C1" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C2" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C3" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C4" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C5" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C6" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C7" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_11" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_10D3&SUBSYS_07D015AD&REV_00\\005056FFFFB441AF00" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0100\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\VMW0001\\7" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\VMW0003\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PNP_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="SWD\\IP_TUNNEL_VBUS\\IP_TUNNEL_DEVICE_ROOT" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A05\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\AUTHENTICAMD_-_AMD64_FAMILY_25_MODEL_1_-_AMD_EPYC_7513_32-CORE_PROCESSOR________________\\_0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\AUTHENTICAMD_-_AMD64_FAMILY_25_MODEL_1_-_AMD_EPYC_7513_32-CORE_PROCESSOR________________\\_1" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PNP_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="SWD\\IP_TUNNEL_VBUS\\ISATAP_0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_3" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_1000&DEV_0054&SUBSYS_197615AD&REV_01\\4&2732702B&0&00A8" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0103\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0B00\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7110&SUBSYS_197615AD&REV_08\\3&18D45AA6&0&38" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0303\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\FIXEDBUTTON\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0200\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7190&SUBSYS_197615AD&REV_01\\3&18D45AA6&0&00" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PNP_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="DISPLAY\\DEFAULT_MONITOR\\4&31BE19FA&0&UID0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_2" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07E0&SUBSYS_07E015AD&REV_00\\4&B70F118&0&0888" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7191&SUBSYS_00000000&REV_01\\3&18D45AA6&0&08" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0740&SUBSYS_074015AD&REV_10\\3&18D45AA6&0&3F" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0790&SUBSYS_079015AD&REV_02\\3&18D45AA6&0&88" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0800\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0405&SUBSYS_040515AD&REV_00\\3&18D45AA6&0&78" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="ACPIBus_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0001\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_Bus.DeviceID="PCI_BUS_0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\\3&18D45AA6&0&39" |
```

### Win32_DeviceMemoryAddress
```sh
WQL> SELECT * FROM Win32_DeviceMemoryAddress
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | CreationClassName | StartingAddress | EndingAddress | MemoryType | 
| 0xE0000000-0xE7FFFFFF | 0xE0000000-0xE7FFFFFF | None | 0xE0000000-0xE7FFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 3758096384 | 3892314111 | None | 
| 0xFFC00000-0xFFDFFFFF | 0xFFC00000-0xFFDFFFFF | None | 0xFFC00000-0xFFDFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4290772992 | 4292870143 | None | 
| 0xFEA00000-0xFEAFFFFF | 0xFEA00000-0xFEAFFFFF | None | 0xFEA00000-0xFEAFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4271898624 | 4272947199 | WindowDecode | 
| 0xFE900000-0xFE9FFFFF | 0xFE900000-0xFE9FFFFF | None | 0xFE900000-0xFE9FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4270850048 | 4271898623 | WindowDecode | 
| 0xFA200000-0xFA2FFFFF | 0xFA200000-0xFA2FFFFF | None | 0xFA200000-0xFA2FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4196401152 | 4197449727 | None | 
| 0xFE800000-0xFE8FFFFF | 0xFE800000-0xFE8FFFFF | None | 0xFE800000-0xFE8FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4269801472 | 4270850047 | WindowDecode | 
| 0xFA100000-0xFA1FFFFF | 0xFA100000-0xFA1FFFFF | None | 0xFA100000-0xFA1FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4195352576 | 4196401151 | None | 
| 0xFE700000-0xFE7FFFFF | 0xFE700000-0xFE7FFFFF | None | 0xFE700000-0xFE7FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4268752896 | 4269801471 | WindowDecode | 
| 0xFA000000-0xFA0FFFFF | 0xFA000000-0xFA0FFFFF | None | 0xFA000000-0xFA0FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4194304000 | 4195352575 | None | 
| 0xFE600000-0xFE6FFFFF | 0xFE600000-0xFE6FFFFF | None | 0xFE600000-0xFE6FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4267704320 | 4268752895 | WindowDecode | 
| 0xF9F00000-0xF9FFFFFF | 0xF9F00000-0xF9FFFFFF | None | 0xF9F00000-0xF9FFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4193255424 | 4194303999 | None | 
| 0xFE500000-0xFE5FFFFF | 0xFE500000-0xFE5FFFFF | None | 0xFE500000-0xFE5FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4266655744 | 4267704319 | WindowDecode | 
| 0xF9E00000-0xF9EFFFFF | 0xF9E00000-0xF9EFFFFF | None | 0xF9E00000-0xF9EFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4192206848 | 4193255423 | None | 
| 0xFE400000-0xFE4FFFFF | 0xFE400000-0xFE4FFFFF | None | 0xFE400000-0xFE4FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4265607168 | 4266655743 | WindowDecode | 
| 0xF9D00000-0xF9DFFFFF | 0xF9D00000-0xF9DFFFFF | None | 0xF9D00000-0xF9DFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4191158272 | 4192206847 | None | 
| 0xFE300000-0xFE3FFFFF | 0xFE300000-0xFE3FFFFF | None | 0xFE300000-0xFE3FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4264558592 | 4265607167 | WindowDecode | 
| 0xF9C00000-0xF9CFFFFF | 0xF9C00000-0xF9CFFFFF | None | 0xF9C00000-0xF9CFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4190109696 | 4191158271 | None | 
| 0xFE200000-0xFE2FFFFF | 0xFE200000-0xFE2FFFFF | None | 0xFE200000-0xFE2FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4263510016 | 4264558591 | WindowDecode | 
| 0xFE100000-0xFE1FFFFF | 0xFE100000-0xFE1FFFFF | None | 0xFE100000-0xFE1FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4262461440 | 4263510015 | WindowDecode | 
| 0xF9B00000-0xF9BFFFFF | 0xF9B00000-0xF9BFFFFF | None | 0xF9B00000-0xF9BFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4189061120 | 4190109695 | None | 
| 0xFE000000-0xFE0FFFFF | 0xFE000000-0xFE0FFFFF | None | 0xFE000000-0xFE0FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4261412864 | 4262461439 | WindowDecode | 
| 0xF9A00000-0xF9AFFFFF | 0xF9A00000-0xF9AFFFFF | None | 0xF9A00000-0xF9AFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4188012544 | 4189061119 | None | 
| 0xFDF00000-0xFDFFFFFF | 0xFDF00000-0xFDFFFFFF | None | 0xFDF00000-0xFDFFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4260364288 | 4261412863 | WindowDecode | 
| 0xF9900000-0xF99FFFFF | 0xF9900000-0xF99FFFFF | None | 0xF9900000-0xF99FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4186963968 | 4188012543 | None | 
| 0xFDE00000-0xFDEFFFFF | 0xFDE00000-0xFDEFFFFF | None | 0xFDE00000-0xFDEFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4259315712 | 4260364287 | WindowDecode | 
| 0xF9800000-0xF98FFFFF | 0xF9800000-0xF98FFFFF | None | 0xF9800000-0xF98FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4185915392 | 4186963967 | None | 
| 0xFDD00000-0xFDDFFFFF | 0xFDD00000-0xFDDFFFFF | None | 0xFDD00000-0xFDDFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4258267136 | 4259315711 | WindowDecode | 
| 0xF9700000-0xF97FFFFF | 0xF9700000-0xF97FFFFF | None | 0xF9700000-0xF97FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4184866816 | 4185915391 | None | 
| 0xFDC00000-0xFDCFFFFF | 0xFDC00000-0xFDCFFFFF | None | 0xFDC00000-0xFDCFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4257218560 | 4258267135 | WindowDecode | 
| 0xF9600000-0xF96FFFFF | 0xF9600000-0xF96FFFFF | None | 0xF9600000-0xF96FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4183818240 | 4184866815 | None | 
| 0xFDB00000-0xFDBFFFFF | 0xFDB00000-0xFDBFFFFF | None | 0xFDB00000-0xFDBFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4256169984 | 4257218559 | WindowDecode | 
| 0xF9500000-0xF95FFFFF | 0xF9500000-0xF95FFFFF | None | 0xF9500000-0xF95FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4182769664 | 4183818239 | None | 
| 0xFDA00000-0xFDAFFFFF | 0xFDA00000-0xFDAFFFFF | None | 0xFDA00000-0xFDAFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4255121408 | 4256169983 | WindowDecode | 
| 0xF9400000-0xF94FFFFF | 0xF9400000-0xF94FFFFF | None | 0xF9400000-0xF94FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4181721088 | 4182769663 | None | 
| 0xFD900000-0xFD9FFFFF | 0xFD900000-0xFD9FFFFF | None | 0xFD900000-0xFD9FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4254072832 | 4255121407 | WindowDecode | 
| 0xF9300000-0xF93FFFFF | 0xF9300000-0xF93FFFFF | None | 0xF9300000-0xF93FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4180672512 | 4181721087 | None | 
| 0xFD800000-0xFD8FFFFF | 0xFD800000-0xFD8FFFFF | None | 0xFD800000-0xFD8FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4253024256 | 4254072831 | WindowDecode | 
| 0xF9200000-0xF92FFFFF | 0xF9200000-0xF92FFFFF | None | 0xF9200000-0xF92FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4179623936 | 4180672511 | None | 
| 0xFD700000-0xFD7FFFFF | 0xFD700000-0xFD7FFFFF | None | 0xFD700000-0xFD7FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4251975680 | 4253024255 | WindowDecode | 
| 0xF9100000-0xF91FFFFF | 0xF9100000-0xF91FFFFF | None | 0xF9100000-0xF91FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4178575360 | 4179623935 | None | 
| 0xFD600000-0xFD6FFFFF | 0xFD600000-0xFD6FFFFF | None | 0xFD600000-0xFD6FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4250927104 | 4251975679 | WindowDecode | 
| 0xF9000000-0xF90FFFFF | 0xF9000000-0xF90FFFFF | None | 0xF9000000-0xF90FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4177526784 | 4178575359 | None | 
| 0xFD500000-0xFD5FFFFF | 0xFD500000-0xFD5FFFFF | None | 0xFD500000-0xFD5FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4249878528 | 4250927103 | WindowDecode | 
| 0xF8F00000-0xF8FFFFFF | 0xF8F00000-0xF8FFFFFF | None | 0xF8F00000-0xF8FFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4176478208 | 4177526783 | None | 
| 0xFD400000-0xFD4FFFFF | 0xFD400000-0xFD4FFFFF | None | 0xFD400000-0xFD4FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4248829952 | 4249878527 | WindowDecode | 
| 0xF8E00000-0xF8EFFFFF | 0xF8E00000-0xF8EFFFFF | None | 0xF8E00000-0xF8EFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4175429632 | 4176478207 | None | 
| 0xFD300000-0xFD3FFFFF | 0xFD300000-0xFD3FFFFF | None | 0xFD300000-0xFD3FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4247781376 | 4248829951 | WindowDecode | 
| 0xF8D00000-0xF8DFFFFF | 0xF8D00000-0xF8DFFFFF | None | 0xF8D00000-0xF8DFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4174381056 | 4175429631 | None | 
| 0xFD200000-0xFD2FFFFF | 0xFD200000-0xFD2FFFFF | None | 0xFD200000-0xFD2FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4246732800 | 4247781375 | WindowDecode | 
| 0xF8C00000-0xF8CFFFFF | 0xF8C00000-0xF8CFFFFF | None | 0xF8C00000-0xF8CFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4173332480 | 4174381055 | None | 
| 0xFD100000-0xFD1FFFFF | 0xFD100000-0xFD1FFFFF | None | 0xFD100000-0xFD1FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4245684224 | 4246732799 | WindowDecode | 
| 0xF8B00000-0xF8BFFFFF | 0xF8B00000-0xF8BFFFFF | None | 0xF8B00000-0xF8BFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4172283904 | 4173332479 | None | 
| 0xFD000000-0xFD0FFFFF | 0xFD000000-0xFD0FFFFF | None | 0xFD000000-0xFD0FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4244635648 | 4245684223 | WindowDecode | 
| 0xF8A00000-0xF8AFFFFF | 0xF8A00000-0xF8AFFFFF | None | 0xF8A00000-0xF8AFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4171235328 | 4172283903 | None | 
| 0xFCF00000-0xFCFFFFFF | 0xFCF00000-0xFCFFFFFF | None | 0xFCF00000-0xFCFFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4243587072 | 4244635647 | WindowDecode | 
| 0xF8900000-0xF89FFFFF | 0xF8900000-0xF89FFFFF | None | 0xF8900000-0xF89FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4170186752 | 4171235327 | None | 
| 0xFCE00000-0xFCEFFFFF | 0xFCE00000-0xFCEFFFFF | None | 0xFCE00000-0xFCEFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4242538496 | 4243587071 | WindowDecode | 
| 0xF8800000-0xF88FFFFF | 0xF8800000-0xF88FFFFF | None | 0xF8800000-0xF88FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4169138176 | 4170186751 | None | 
| 0xFCD00000-0xFCDFFFFF | 0xFCD00000-0xFCDFFFFF | None | 0xFCD00000-0xFCDFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4241489920 | 4242538495 | WindowDecode | 
| 0xF8700000-0xF87FFFFF | 0xF8700000-0xF87FFFFF | None | 0xF8700000-0xF87FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4168089600 | 4169138175 | None | 
| 0xFCC00000-0xFCCFFFFF | 0xFCC00000-0xFCCFFFFF | None | 0xFCC00000-0xFCCFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4240441344 | 4241489919 | WindowDecode | 
| 0xF8600000-0xF86FFFFF | 0xF8600000-0xF86FFFFF | None | 0xF8600000-0xF86FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4167041024 | 4168089599 | None | 
| 0xFCB00000-0xFCBFFFFF | 0xFCB00000-0xFCBFFFFF | None | 0xFCB00000-0xFCBFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4239392768 | 4240441343 | WindowDecode | 
| 0xF8500000-0xF85FFFFF | 0xF8500000-0xF85FFFFF | None | 0xF8500000-0xF85FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4165992448 | 4167041023 | None | 
| 0xFE220000-0xFE23FFFF | 0xFE220000-0xFE23FFFF | None | 0xFE220000-0xFE23FFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4263641088 | 4263772159 | Bar | 
| 0xFE250000-0xFE253FFF | 0xFE250000-0xFE253FFF | None | 0xFE250000-0xFE253FFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4263837696 | 4263854079 | Bar | 
| 0xFEF00000-0xFFDFFFFF | 0xFEF00000-0xFFDFFFFF | None | 0xFEF00000-0xFFDFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4277141504 | 4292870143 | None | 
| 0xFED45000-0xFEDFFFFF | 0xFED45000-0xFEDFFFFF | None | 0xFED45000-0xFEDFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4275326976 | 4276092927 | None | 
| 0xFEC10000-0xFED3FFFF | 0xFEC10000-0xFED3FFFF | None | 0xFEC10000-0xFED3FFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4274061312 | 4275306495 | None | 
| 0xFA300000-0xFEBFFFFF | 0xFA300000-0xFEBFFFFF | None | 0xFA300000-0xFEBFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4197449728 | 4273995775 | None | 
| 0xF0000000-0xFA2FFFFF | 0xF0000000-0xFA2FFFFF | None | 0xF0000000-0xFA2FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4026531840 | 4197449727 | None | 
| 0xC0000000-0xEFFFFFFF | 0xC0000000-0xEFFFFFFF | None | 0xC0000000-0xEFFFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 3221225472 | 4026531839 | None | 
| 0xA0000-0xBFFFF | 0xA0000-0xBFFFF | None | 0xA0000-0xBFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 655360 | 786431 | None | 
| 0xC4000-0xC7FFF | 0xC4000-0xC7FFF | None | 0xC4000-0xC7FFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 802816 | 819199 | None | 
| 0xC8000-0xCBFFF | 0xC8000-0xCBFFF | None | 0xC8000-0xCBFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 819200 | 835583 | None | 
| 0xD4000-0xD7FFF | 0xD4000-0xD7FFF | None | 0xD4000-0xD7FFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 868352 | 884735 | None | 
| 0xD8000-0xDBFFF | 0xD8000-0xDBFFF | None | 0xD8000-0xDBFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 884736 | 901119 | None | 
| 0xE4000-0xE7FFF | 0xE4000-0xE7FFF | None | 0xE4000-0xE7FFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 933888 | 950271 | None | 
| 0xE8000-0xEBFFF | 0xE8000-0xEBFFF | None | 0xE8000-0xEBFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 950272 | 966655 | None | 
| 0xEC000-0xEFFFF | 0xEC000-0xEFFFF | None | 0xEC000-0xEFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 966656 | 983039 | None | 
| 0xFEA10000-0xFEA13FFF | 0xFEA10000-0xFEA13FFF | None | 0xFEA10000-0xFEA13FFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4271964160 | 4271980543 | Bar | 
| 0xFED00000-0xFED003FF | 0xFED00000-0xFED003FF | None | 0xFED00000-0xFED003FF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4275044352 | 4275045375 | None | 
| 0xFC010000-0xFC010FFF | 0xFC010000-0xFC010FFF | None | 0xFC010000-0xFC010FFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4227923968 | 4227928063 | Bar | 
| 0xFFBFE000-0xFFBFFFFF | 0xFFBFE000-0xFFBFFFFF | None | 0xFFBFE000-0xFFBFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4290764800 | 4290772991 | Bar | 
| 0xFC000000-0xFC9FFFFF | 0xFC000000-0xFC9FFFFF | None | 0xFC000000-0xFC9FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4227858432 | 4238344191 | WindowDecode | 
| 0xF8000000-0xF84FFFFF | 0xF8000000-0xF84FFFFF | None | 0xF8000000-0xF84FFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4160749568 | 4165992447 | None | 
| 0xFB800000-0xFBFFFFFF | 0xFB800000-0xFBFFFFFF | None | 0xFB800000-0xFBFFFFFF | OK | Win32_ComputerSystem | FOREST | Win32_DeviceMemoryAddress | 4219469824 | 4227858431 | Bar |
```

### Win32_DiskDrive
```sh
WQL> SELECT * FROM Win32_DiskDrive
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Capabilities | CapabilityDescriptions | CompressionMethod | ErrorMethodology | MaxMediaSize | DefaultBlockSize | MaxBlockSize | MinBlockSize | NumberOfMediaSupported | NeedsCleaning | BytesPerSector | InterfaceType | Partitions | SectorsPerTrack | TotalCylinders | TotalHeads | TotalSectors | TotalTracks | TracksPerCylinder | Index | Manufacturer | MediaLoaded | MediaType | Model | SCSIBus | SCSILogicalUnit | SCSIPort | SCSITargetId | Size | Signature | SerialNumber | FirmwareRevision | 
| VMware Virtual disk SCSI Disk Device | Disk drive | None | \\.\PHYSICALDRIVE0 | OK | 65535 | Win32_DiskDrive | 0 | False | \\.\PHYSICALDRIVE0 | None | SCSI\DISK&VEN_VMWARE&PROD_VIRTUAL_DISK\5&1982005&0&000100 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 3 4  | 396 411  | None | None | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | 18446744073709551615 | None | True | 512 | SCSI | 3 | 63 | 2610 | 255 | 41929650 | 665550 | 255 | 0 | (Standard disk drives) | True | Fixed hard disk media | VMware Virtual disk SCSI Disk Device | 0 | 0 | 0 | 1 | 21467980800 | None | 6000c29c9f4f2e0c794e36b137fda25f | 2.0  |
```

### Win32_DiskDriveToDiskPartition
```sh
WQL> SELECT * FROM Win32_DiskDriveToDiskPartition
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_DiskDrive.DeviceID="\\\\.\\PHYSICALDRIVE0" | \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #0" | 
| \\FOREST\root\cimv2:Win32_DiskDrive.DeviceID="\\\\.\\PHYSICALDRIVE0" | \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #1" | 
| \\FOREST\root\cimv2:Win32_DiskDrive.DeviceID="\\\\.\\PHYSICALDRIVE0" | \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #2" |
```

### Win32_DiskPartition
```sh
WQL> SELECT * FROM Win32_DiskPartition
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | Bootable | PrimaryPartition | BootPartition | DiskIndex | HiddenSectors | Index | RewritePartition | Size | StartingOffset | Type | 
| Disk #0, Partition #0 | GPT: Unknown | None | Disk #0, Partition #0 | None | 65535 | Win32_DiskPartition | None | True | Disk #0, Partition #0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 512 | None | 921600 | None | False | False | False | 0 | None | 0 | None | 471859200 | 135266304 | GPT: Unknown | 
| Disk #0, Partition #1 | GPT: System | None | Disk #0, Partition #1 | None | 65535 | Win32_DiskPartition | None | True | Disk #0, Partition #1 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 512 | None | 202752 | None | True | True | True | 0 | None | 1 | None | 103809024 | 607125504 | GPT: System | 
| Disk #0, Partition #2 | GPT: Basic Data | None | Disk #0, Partition #2 | None | 65535 | Win32_DiskPartition | None | True | Disk #0, Partition #2 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 512 | None | 40552448 | None | False | True | False | 0 | None | 2 | None | 20762853376 | 710934528 | GPT: Basic Data |
```

### Win32_DisplayControllerConfiguration
```sh
WQL> SELECT * FROM Win32_DisplayControllerConfiguration
| SettingID | Caption | Description | BitsPerPixel | ColorPlanes | DeviceEntriesInAColorTable | DeviceSpecificPens | HorizontalResolution | Name | RefreshRate | ReservedSystemPaletteEntries | SystemPaletteEntries | VerticalResolution | VideoMode | 
| VMware SVGA 3D | VMware SVGA 3D | VMware SVGA 3D | 32 | 1 | None | None | 1024 | VMware SVGA 3D | 60 | None | None | 768 | 1024 by 768 pixels, True Color, 60 Hertz |
```

### Win32_DMAChannel
```sh
WQL> SELECT * FROM Win32_DMAChannel
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | CreationClassName | DMAChannel | Availability | BurstMode | TransferWidths | AddressSize | MaxTransferSize | ByteMode | WordMode | ChannelTiming | TypeCTiming | Port | 
| Channel 4 | Channel 4 | None | Channel 4 | OK | Win32_ComputerSystem | FOREST | Win32_DMAChannel | 4 | 4 | True | 0  | 0 | 0 | 2 | 2 | 2 | 2 | None |
```

### Win32_IDEController
```sh
WQL> SELECT * FROM Win32_IDEController
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | MaxNumberControlled | ProtocolSupported | TimeOfLastReset | Manufacturer | 
| ATA Channel 0 | IDE Channel | None | ATA Channel 0 | OK | 65535 | Win32_IDEController | 0 | False | PCIIDE\IDECHANNEL\4&39EC5D8A&0&0 | None | PCIIDE\IDECHANNEL\4&39EC5D8A&0&0 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 37 | None | (Standard IDE ATA/ATAPI controllers) | 
| ATA Channel 1 | IDE Channel | None | ATA Channel 1 | OK | 65535 | Win32_IDEController | 0 | False | PCIIDE\IDECHANNEL\4&39EC5D8A&0&1 | None | PCIIDE\IDECHANNEL\4&39EC5D8A&0&1 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 37 | None | (Standard IDE ATA/ATAPI controllers) | 
| Standard SATA AHCI Controller | Standard SATA AHCI Controller | None | Standard SATA AHCI Controller | OK | 65535 | Win32_IDEController | 0 | False | PCI\VEN_15AD&DEV_07E0&SUBSYS_07E015AD&REV_00\4&B70F118&0&0888 | None | PCI\VEN_15AD&DEV_07E0&SUBSYS_07E015AD&REV_00\4&B70F118&0&0888 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 37 | None | Standard SATA AHCI Controller | 
| Intel(R) 82371AB/EB PCI Bus Master IDE Controller | Intel(R) 82371AB/EB PCI Bus Master IDE Controller | None | Intel(R) 82371AB/EB PCI Bus Master IDE Controller | OK | 65535 | Win32_IDEController | 0 | False | PCI\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\3&18D45AA6&0&39 | None | PCI\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\3&18D45AA6&0&39 | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | 37 | None | Intel |
```

### Win32_IDEControllerDevice
```sh
WQL> SELECT * FROM Win32_IDEControllerDevice
| Antecedent | Dependent | NegotiatedSpeed | NegotiatedDataWidth | AccessState | NumberOfHardResets | NumberOfSoftResets | 
| \\FOREST\root\cimv2:Win32_IDEController.DeviceID="PCI\\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\\3&18D45AA6&0&39" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&0" | 18446744073709551615 | None | 65535 | None | None | 
| \\FOREST\root\cimv2:Win32_IDEController.DeviceID="PCI\\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\\3&18D45AA6&0&39" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&1" | 18446744073709551615 | None | 65535 | None | None |
```

### Win32_IRQResource
```sh
WQL> SELECT * FROM Win32_IRQResource
| Caption | Description | InstallDate | Name | Status | CSCreationClassName | CSName | CreationClassName | IRQNumber | Availability | TriggerType | TriggerLevel | Shareable | Vector | Hardware | 
| IRQ 4294967293 | IRQ 4294967293 | None | IRQ4294967293 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967293 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967292 | IRQ 4294967292 | None | IRQ4294967292 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967292 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967291 | IRQ 4294967291 | None | IRQ4294967291 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967291 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967290 | IRQ 4294967290 | None | IRQ4294967290 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967290 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967289 | IRQ 4294967289 | None | IRQ4294967289 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967289 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967288 | IRQ 4294967288 | None | IRQ4294967288 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967288 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967287 | IRQ 4294967287 | None | IRQ4294967287 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967287 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967286 | IRQ 4294967286 | None | IRQ4294967286 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967286 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967285 | IRQ 4294967285 | None | IRQ4294967285 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967285 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967284 | IRQ 4294967284 | None | IRQ4294967284 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967284 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967283 | IRQ 4294967283 | None | IRQ4294967283 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967283 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967282 | IRQ 4294967282 | None | IRQ4294967282 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967282 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967281 | IRQ 4294967281 | None | IRQ4294967281 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967281 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967280 | IRQ 4294967280 | None | IRQ4294967280 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967280 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967279 | IRQ 4294967279 | None | IRQ4294967279 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967279 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967278 | IRQ 4294967278 | None | IRQ4294967278 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967278 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967277 | IRQ 4294967277 | None | IRQ4294967277 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967277 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967276 | IRQ 4294967276 | None | IRQ4294967276 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967276 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967275 | IRQ 4294967275 | None | IRQ4294967275 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967275 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967274 | IRQ 4294967274 | None | IRQ4294967274 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967274 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967273 | IRQ 4294967273 | None | IRQ4294967273 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967273 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967272 | IRQ 4294967272 | None | IRQ4294967272 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967272 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967271 | IRQ 4294967271 | None | IRQ4294967271 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967271 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967270 | IRQ 4294967270 | None | IRQ4294967270 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967270 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967269 | IRQ 4294967269 | None | IRQ4294967269 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967269 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967268 | IRQ 4294967268 | None | IRQ4294967268 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967268 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967267 | IRQ 4294967267 | None | IRQ4294967267 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967267 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967266 | IRQ 4294967266 | None | IRQ4294967266 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967266 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967265 | IRQ 4294967265 | None | IRQ4294967265 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967265 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967264 | IRQ 4294967264 | None | IRQ4294967264 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967264 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967263 | IRQ 4294967263 | None | IRQ4294967263 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967263 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967294 | IRQ 4294967294 | None | IRQ4294967294 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967294 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967258 | IRQ 4294967258 | None | IRQ4294967258 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967258 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967257 | IRQ 4294967257 | None | IRQ4294967257 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967257 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967256 | IRQ 4294967256 | None | IRQ4294967256 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967256 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967255 | IRQ 4294967255 | None | IRQ4294967255 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967255 | 2 | 2 | 2 | True | None | True | 
| IRQ 0 | IRQ 0 | None | IRQ0 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 0 | 2 | 2 | 2 | True | None | True | 
| IRQ 14 | IRQ 14 | None | IRQ14 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 14 | 2 | 2 | 2 | True | 14 | True | 
| IRQ 15 | IRQ 15 | None | IRQ15 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 15 | 2 | 2 | 2 | True | 15 | True | 
| IRQ 12 | IRQ 12 | None | IRQ12 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 12 | 2 | 2 | 2 | True | 12 | True | 
| IRQ 4294967260 | IRQ 4294967260 | None | IRQ4294967260 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967260 | 2 | 2 | 2 | True | None | True | 
| IRQ 8 | IRQ 8 | None | IRQ8 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 8 | 2 | 2 | 2 | True | 8 | True | 
| IRQ 1 | IRQ 1 | None | IRQ1 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 1 | 2 | 2 | 2 | True | 1 | True | 
| IRQ 54 | IRQ 54 | None | IRQ54 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 54 | 2 | 2 | 2 | True | 54 | True | 
| IRQ 55 | IRQ 55 | None | IRQ55 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 55 | 2 | 2 | 2 | True | 55 | True | 

~~~

| IRQ 511 | IRQ 511 | None | IRQ511 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 511 | 2 | 2 | 2 | True | 511 | True | 
| IRQ 4294967259 | IRQ 4294967259 | None | IRQ4294967259 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967259 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967262 | IRQ 4294967262 | None | IRQ4294967262 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967262 | 2 | 2 | 2 | True | None | True | 
| IRQ 4294967261 | IRQ 4294967261 | None | IRQ4294967261 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 4294967261 | 2 | 2 | 2 | True | None | True | 
| IRQ 16 | IRQ 16 | None | IRQ16 | OK | Win32_ComputerSystem | FOREST | Win32_IRQResource | 16 | 2 | 2 | 2 | True | 16 | True |
```

### Win32_Keyboard
```sh
WQL> SELECT * FROM Win32_Keyboard
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | IsLocked | Layout | NumberOfFunctionKeys | Password | 
| Enhanced (101- or 102-key) | Standard PS/2 Keyboard | None | Enhanced (101- or 102-key) | OK | 65535 | Win32_Keyboard | 0 | False | ACPI\PNP0303\4&25EE97C0&0 | None | ACPI\PNP0303\4&25EE97C0&0 | False | 65535 | Win32_ComputerSystem | FOREST | None | None | True | True | 00000409 | 12 | 65535 |
```

### Win32_LogicalDisk
```sh
WQL> SELECT * FROM Win32_LogicalDisk
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | FreeSpace | Size | Compressed | DriveType | FileSystem | MaximumComponentLength | ProviderName | SupportsFileBasedCompression | VolumeName | VolumeSerialNumber | MediaType | SupportsDiskQuotas | QuotasDisabled | QuotasIncomplete | QuotasRebuilding | VolumeDirty | 
| C: | Local Fixed Disk | None | C: | None | 65535 | Win32_LogicalDisk | None | True | C: | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 0 | 18446744073709551615 | None | 18446744073709551615 | None | 10267963392 | 20762849280 | False | 3 | NTFS | 255 | None | True |  | 61F2A88F | 12 | True | True | False | False | False |
```

### Win32_LogicalDiskRootDirectory
```sh
WQL> SELECT * FROM Win32_LogicalDiskRootDirectory
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_LogicalDisk.DeviceID="C:" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\" |
```

### Win32_LogicalDiskToPartition
```sh
WQL> SELECT * FROM Win32_LogicalDiskToPartition
| Antecedent | Dependent | StartingAddress | EndingAddress | 
| \\FOREST\root\cimv2:Win32_DiskPartition.DeviceID="Disk #0, Partition #2" | \\FOREST\root\cimv2:Win32_LogicalDisk.DeviceID="C:" | 710934528 | 21473787903 |
```

### Win32_LogicalProgramGroup
```sh
WQL> SELECT * FROM Win32_LogicalProgramGroup
| Caption | Description | InstallDate | Name | Status | GroupName | UserName | 
| Logical program group "Default:Start Menu" | Logical program group "Default:Start Menu" | 20160716061803.459804-420 | Default:Start Menu | None | Start Menu | Default | 
| Logical program group "Default:Start Menu\Programs" | Logical program group "Default:Start Menu\Programs" | 20160716061803.459804-420 | Default:Start Menu\Programs | None | Start Menu\Programs | Default | 
| Logical program group "Default:Start Menu\Programs\Accessories" | Logical program group "Default:Start Menu\Programs\Accessories" | 20160716061803.459804-420 | Default:Start Menu\Programs\Accessories | None | Start Menu\Programs\Accessories | Default | 
| Logical program group "Default:Start Menu\Programs\Startup" | Logical program group "Default:Start Menu\Programs\Startup" | 20190920131824.168535-420 | Default:Start Menu\Programs\Startup | None | Start Menu\Programs\Startup | Default | 
| Logical program group "Default:Start Menu\Programs\System Tools" | Logical program group "Default:Start Menu\Programs\System Tools" | 20160716061803.459804-420 | Default:Start Menu\Programs\System Tools | None | Start Menu\Programs\System Tools | Default | 
| Logical program group "Default:Start Menu\Programs\Windows PowerShell" | Logical program group "Default:Start Menu\Programs\Windows PowerShell" | 20160716061803.459804-420 | Default:Start Menu\Programs\Windows PowerShell | None | Start Menu\Programs\Windows PowerShell | Default | 
| Logical program group "Public:Start Menu" | Logical program group "Public:Start Menu" | 20160716061803.444179-420 | Public:Start Menu | None | Start Menu | Public | 
| Logical program group "Public:Start Menu\Programs" | Logical program group "Public:Start Menu\Programs" | 20160716061803.444179-420 | Public:Start Menu\Programs | None | Start Menu\Programs | Public | 
| Logical program group "Public:Start Menu\Programs\Administrative Tools" | Logical program group "Public:Start Menu\Programs\Administrative Tools" | 20160716061803.444179-420 | Public:Start Menu\Programs\Administrative Tools | None | Start Menu\Programs\Administrative Tools | Public | 
| Logical program group "Public:Start Menu\Programs\StartUp" | Logical program group "Public:Start Menu\Programs\StartUp" | 20160716061803.444179-420 | Public:Start Menu\Programs\StartUp | None | Start Menu\Programs\StartUp | Public | 
| Logical program group "Public:Start Menu\Programs\System Tools" | Logical program group "Public:Start Menu\Programs\System Tools" | 20160716061803.444179-420 | Public:Start Menu\Programs\System Tools | None | Start Menu\Programs\System Tools | Public | 
| Logical program group "Public:Start Menu\Programs\VMware" | Logical program group "Public:Start Menu\Programs\VMware" | 20190922165619.352516-420 | Public:Start Menu\Programs\VMware | None | Start Menu\Programs\VMware | Public | 
| Logical program group "Public:Start Menu\Programs\VMware\VMware Tools" | Logical program group "Public:Start Menu\Programs\VMware\VMware Tools" | 20190922165619.352516-420 | Public:Start Menu\Programs\VMware\VMware Tools | None | Start Menu\Programs\VMware\VMware Tools | Public | 
| Logical program group "HTB\Administrator:Start Menu" | Logical program group "HTB\Administrator:Start Menu" | 20190918100908.358468-420 | HTB\Administrator:Start Menu | None | Start Menu | HTB\Administrator | 
| Logical program group "HTB\Administrator:Start Menu\Programs" | Logical program group "HTB\Administrator:Start Menu\Programs" | 20190918100908.358468-420 | HTB\Administrator:Start Menu\Programs | None | Start Menu\Programs | HTB\Administrator | 
| Logical program group "HTB\Administrator:Start Menu\Programs\Accessories" | Logical program group "HTB\Administrator:Start Menu\Programs\Accessories" | 20190918100908.358468-420 | HTB\Administrator:Start Menu\Programs\Accessories | None | Start Menu\Programs\Accessories | HTB\Administrator | 
| Logical program group "HTB\Administrator:Start Menu\Programs\Administrative Tools" | Logical program group "HTB\Administrator:Start Menu\Programs\Administrative Tools" | 20190918100910.795976-420 | HTB\Administrator:Start Menu\Programs\Administrative Tools | None | Start Menu\Programs\Administrative Tools | HTB\Administrator | 
| Logical program group "HTB\Administrator:Start Menu\Programs\Startup" | Logical program group "HTB\Administrator:Start Menu\Programs\Startup" | 20190918100910.795976-420 | HTB\Administrator:Start Menu\Programs\Startup | None | Start Menu\Programs\Startup | HTB\Administrator | 
| Logical program group "HTB\Administrator:Start Menu\Programs\System Tools" | Logical program group "HTB\Administrator:Start Menu\Programs\System Tools" | 20190918100908.358468-420 | HTB\Administrator:Start Menu\Programs\System Tools | None | Start Menu\Programs\System Tools | HTB\Administrator | 
| Logical program group "HTB\Administrator:Start Menu\Programs\Windows PowerShell" | Logical program group "HTB\Administrator:Start Menu\Programs\Windows PowerShell" | 20190918100908.358468-420 | HTB\Administrator:Start Menu\Programs\Windows PowerShell | None | Start Menu\Programs\Windows PowerShell | HTB\Administrator |
```

### Win32_LogicalProgramGroupDirectory
```sh
WQL> SELECT * FROM Win32_LogicalProgramGroupDirectory
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Default:Start Menu" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Default:Start Menu\\Programs" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Default:Start Menu\\Programs\\Accessories" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Accessories" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Default:Start Menu\\Programs\\Startup" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Startup" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Default:Start Menu\\Programs\\System Tools" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Default:Start Menu\\Programs\\Windows PowerShell" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Windows PowerShell" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Public:Start Menu" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Public:Start Menu\\Programs" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Public:Start Menu\\Programs\\Administrative Tools" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Public:Start Menu\\Programs\\StartUp" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\StartUp" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Public:Start Menu\\Programs\\System Tools" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Public:Start Menu\\Programs\\VMware" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\VMware" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="Public:Start Menu\\Programs\\VMware\\VMware Tools" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\VMware\\VMware Tools" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="HTB\\Administrator:Start Menu" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="HTB\\Administrator:Start Menu\\Programs" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="HTB\\Administrator:Start Menu\\Programs\\Accessories" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Accessories" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="HTB\\Administrator:Start Menu\\Programs\\Administrative Tools" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="HTB\\Administrator:Start Menu\\Programs\\Startup" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Startup" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="HTB\\Administrator:Start Menu\\Programs\\System Tools" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroup.Name="HTB\\Administrator:Start Menu\\Programs\\Windows PowerShell" | \\FOREST\root\cimv2:Win32_Directory.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Windows PowerShell" |
```

### Win32_LogicalProgramGroupItem
```sh
WQL> SELECT * FROM Win32_LogicalProgramGroupItem
| Caption | Description | InstallDate | Name | Status | 
| Logical program group item 'Default:Start Menu\Programs\Accessories\desktop.ini' | Logical program group item 'Default:Start Menu\Programs\Accessories\desktop.ini' | 20160716061813.161954-420 | Default:Start Menu\Programs\Accessories\desktop.ini | None | 
| Logical program group item 'Default:Start Menu\Programs\Accessories\Notepad.lnk' | Logical program group item 'Default:Start Menu\Programs\Accessories\Notepad.lnk' | 20160716061251.475984-420 | Default:Start Menu\Programs\Accessories\Notepad.lnk | None | 
| Logical program group item 'Default:Start Menu\Programs\System Tools\Command Prompt.lnk' | Logical program group item 'Default:Start Menu\Programs\System Tools\Command Prompt.lnk' | 20160716060952.652329-420 | Default:Start Menu\Programs\System Tools\Command Prompt.lnk | None | 
| Logical program group item 'Default:Start Menu\Programs\System Tools\computer.lnk' | Logical program group item 'Default:Start Menu\Programs\System Tools\computer.lnk' | 20160716061251.085360-420 | Default:Start Menu\Programs\System Tools\computer.lnk | None | 
| Logical program group item 'Default:Start Menu\Programs\System Tools\Control Panel.lnk' | Logical program group item 'Default:Start Menu\Programs\System Tools\Control Panel.lnk' | 20160716061251.100985-420 | Default:Start Menu\Programs\System Tools\Control Panel.lnk | None | 
| Logical program group item 'Default:Start Menu\Programs\System Tools\Default Apps.lnk' | Logical program group item 'Default:Start Menu\Programs\System Tools\Default Apps.lnk' | 20160716061251.038486-420 | Default:Start Menu\Programs\System Tools\Default Apps.lnk | None | 
| Logical program group item 'Default:Start Menu\Programs\System Tools\desktop.ini' | Logical program group item 'Default:Start Menu\Programs\System Tools\desktop.ini' | 20160716061813.161954-420 | Default:Start Menu\Programs\System Tools\desktop.ini | None | 
| Logical program group item 'Default:Start Menu\Programs\System Tools\Devices.lnk' | Logical program group item 'Default:Start Menu\Programs\System Tools\Devices.lnk' | 20160716061251.069735-420 | Default:Start Menu\Programs\System Tools\Devices.lnk | None | 
| Logical program group item 'Default:Start Menu\Programs\System Tools\File Explorer.lnk' | Logical program group item 'Default:Start Menu\Programs\System Tools\File Explorer.lnk' | 20160716061251.147860-420 | Default:Start Menu\Programs\System Tools\File Explorer.lnk | None | 
| Logical program group item 'Default:Start Menu\Programs\System Tools\Run.lnk' | Logical program group item 'Default:Start Menu\Programs\System Tools\Run.lnk' | 20160716061251.132236-420 | Default:Start Menu\Programs\System Tools\Run.lnk | None | 
| Logical program group item 'Default:Start Menu\Programs\Windows PowerShell\Windows PowerShell (x86).lnk' | Logical program group item 'Default:Start Menu\Programs\Windows PowerShell\Windows PowerShell (x86).lnk' | 20160716061805.256664-420 | Default:Start Menu\Programs\Windows PowerShell\Windows PowerShell (x86).lnk | None | 
| Logical program group item 'Default:Start Menu\Programs\Windows PowerShell\Windows PowerShell.lnk' | Logical program group item 'Default:Start Menu\Programs\Windows PowerShell\Windows PowerShell.lnk' | 20160716061805.256664-420 | Default:Start Menu\Programs\Windows PowerShell\Windows PowerShell.lnk | None | 
| Logical program group item 'Public:Start Menu\desktop.ini' | Logical program group item 'Public:Start Menu\desktop.ini' | 20160716061805.225414-420 | Public:Start Menu\desktop.ini | None | 
| Logical program group item 'Public:Start Menu\Programs\desktop.ini' | Logical program group item 'Public:Start Menu\Programs\desktop.ini' | 20160716061805.225414-420 | Public:Start Menu\Programs\desktop.ini | None | 
| Logical program group item 'Public:Start Menu\Programs\Administrative Tools\Active Directory PowerShell Snap-In.lnk' | Logical program group item 'Public:Start Menu\Programs\Administrative Tools\Active Directory PowerShell Snap-In.lnk' | 20160716061130.319027-420 | Public:Start Menu\Programs\Administrative Tools\Active Directory PowerShell Snap-In.lnk | None | 
| Logical program group item 'Public:Start Menu\Programs\Administrative Tools\desktop.ini' | Logical program group item 'Public:Start Menu\Programs\Administrative Tools\desktop.ini' | 20160716061805.225414-420 | Public:Start Menu\Programs\Administrative Tools\desktop.ini | None | 
| Logical program group item 'Public:Start Menu\Programs\Administrative Tools\Group Policy Management.lnk' | Logical program group item 'Public:Start Menu\Programs\Administrative Tools\Group Policy Management.lnk' | 20160716061123.444041-420 | Public:Start Menu\Programs\Administrative Tools\Group Policy Management.lnk | None | 
| Logical program group item 'Public:Start Menu\Programs\Administrative Tools\iSCSI Initiator.lnk' | Logical program group item 'Public:Start Menu\Programs\Administrative Tools\iSCSI Initiator.lnk' | 20160716061243.658754-420 | Public:Start Menu\Programs\Administrative Tools\iSCSI Initiator.lnk | None | 
| Logical program group item 'Public:Start Menu\Programs\Administrative Tools\ODBC Data Sources (32-bit).lnk' | Logical program group item 'Public:Start Menu\Programs\Administrative Tools\ODBC Data Sources (32-bit).lnk' | 20160716061101.825936-420 | Public:Start Menu\Programs\Administrative Tools\ODBC Data Sources (32-bit).lnk | None | 
| Logical program group item 'Public:Start Menu\Programs\Administrative Tools\ODBC Data Sources (64-bit).lnk' | Logical program group item 'Public:Start Menu\Programs\Administrative Tools\ODBC Data Sources (64-bit).lnk' | 20160716061243.877503-420 | Public:Start Menu\Programs\Administrative Tools\ODBC Data Sources (64-bit).lnk | None | 
| Logical program group item 'Public:Start Menu\Programs\Administrative Tools\Security Configuration Management.lnk' | Logical program group item 'Public:Start Menu\Programs\Administrative Tools\Security Configuration Management.lnk' | 20160716061216.266480-420 | Public:Start Menu\Programs\Administrative Tools\Security Configuration Management.lnk | None | 
| Logical program group item 'Public:Start Menu\Programs\Administrative Tools\Windows Firewall with Advanced Security.lnk' | Logical program group item 'Public:Start Menu\Programs\Administrative Tools\Windows Firewall with Advanced Security.lnk' | 20160716061005.242375-420 | Public:Start Menu\Programs\Administrative Tools\Windows Firewall with Advanced Security.lnk | None | 
| Logical program group item 'Public:Start Menu\Programs\StartUp\desktop.ini' | Logical program group item 'Public:Start Menu\Programs\StartUp\desktop.ini' | 20160716061805.225414-420 | Public:Start Menu\Programs\StartUp\desktop.ini | None | 
| Logical program group item 'Public:Start Menu\Programs\System Tools\desktop.ini' | Logical program group item 'Public:Start Menu\Programs\System Tools\desktop.ini' | 20160716061813.161954-420 | Public:Start Menu\Programs\System Tools\desktop.ini | None | 
| Logical program group item 'Public:Start Menu\Programs\System Tools\Task Manager.lnk' | Logical program group item 'Public:Start Menu\Programs\System Tools\Task Manager.lnk' | 20160716061300.245438-420 | Public:Start Menu\Programs\System Tools\Task Manager.lnk | None | 
| Logical program group item 'Public:Start Menu\Programs\VMware\VMware Tools\start VM Statistics Logging.lnk' | Logical program group item 'Public:Start Menu\Programs\VMware\VMware Tools\start VM Statistics Logging.lnk' | 20190922165619.352516-420 | Public:Start Menu\Programs\VMware\VMware Tools\start VM Statistics Logging.lnk | None | 
| Logical program group item 'HTB\Administrator:Start Menu\desktop.ini' | Logical program group item 'HTB\Administrator:Start Menu\desktop.ini' | 20190918100910.670989-420 | HTB\Administrator:Start Menu\desktop.ini | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\desktop.ini' | Logical program group item 'HTB\Administrator:Start Menu\Programs\desktop.ini' | 20190918100910.702241-420 | HTB\Administrator:Start Menu\Programs\desktop.ini | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\Accessories\desktop.ini' | Logical program group item 'HTB\Administrator:Start Menu\Programs\Accessories\desktop.ini' | 20190918100908.374093-420 | HTB\Administrator:Start Menu\Programs\Accessories\desktop.ini | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\Accessories\Notepad.lnk' | Logical program group item 'HTB\Administrator:Start Menu\Programs\Accessories\Notepad.lnk' | 20190918100908.374093-420 | HTB\Administrator:Start Menu\Programs\Accessories\Notepad.lnk | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\Administrative Tools\desktop.ini' | Logical program group item 'HTB\Administrator:Start Menu\Programs\Administrative Tools\desktop.ini' | 20190918100910.795976-420 | HTB\Administrator:Start Menu\Programs\Administrative Tools\desktop.ini | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\Startup\desktop.ini' | Logical program group item 'HTB\Administrator:Start Menu\Programs\Startup\desktop.ini' | 20190918100910.795976-420 | HTB\Administrator:Start Menu\Programs\Startup\desktop.ini | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\Command Prompt.lnk' | Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\Command Prompt.lnk' | 20190918100908.374093-420 | HTB\Administrator:Start Menu\Programs\System Tools\Command Prompt.lnk | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\computer.lnk' | Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\computer.lnk' | 20190918100908.374093-420 | HTB\Administrator:Start Menu\Programs\System Tools\computer.lnk | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\Control Panel.lnk' | Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\Control Panel.lnk' | 20190918100908.374093-420 | HTB\Administrator:Start Menu\Programs\System Tools\Control Panel.lnk | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\Default Apps.lnk' | Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\Default Apps.lnk' | 20190918100908.374093-420 | HTB\Administrator:Start Menu\Programs\System Tools\Default Apps.lnk | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\desktop.ini' | Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\desktop.ini' | 20190918100908.358468-420 | HTB\Administrator:Start Menu\Programs\System Tools\desktop.ini | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\Devices.lnk' | Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\Devices.lnk' | 20190918100908.374093-420 | HTB\Administrator:Start Menu\Programs\System Tools\Devices.lnk | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\File Explorer.lnk' | Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\File Explorer.lnk' | 20190918100908.374093-420 | HTB\Administrator:Start Menu\Programs\System Tools\File Explorer.lnk | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\Run.lnk' | Logical program group item 'HTB\Administrator:Start Menu\Programs\System Tools\Run.lnk' | 20190918100908.358468-420 | HTB\Administrator:Start Menu\Programs\System Tools\Run.lnk | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\Windows PowerShell\Windows PowerShell (x86).lnk' | Logical program group item 'HTB\Administrator:Start Menu\Programs\Windows PowerShell\Windows PowerShell (x86).lnk' | 20190918100908.358468-420 | HTB\Administrator:Start Menu\Programs\Windows PowerShell\Windows PowerShell (x86).lnk | None | 
| Logical program group item 'HTB\Administrator:Start Menu\Programs\Windows PowerShell\Windows PowerShell.lnk' | Logical program group item 'HTB\Administrator:Start Menu\Programs\Windows PowerShell\Windows PowerShell.lnk' | 20190918100908.358468-420 | HTB\Administrator:Start Menu\Programs\Windows PowerShell\Windows PowerShell.lnk | None |
```

### Win32_LogicalProgramGroupItemDataFile
```sh
WQL> SELECT * FROM Win32_LogicalProgramGroupItemDataFile
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\Accessories\\desktop.ini" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Accessories\\desktop.ini" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\Accessories\\Notepad.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Accessories\\Notepad.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\System Tools\\Command Prompt.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\Command Prompt.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\System Tools\\computer.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\computer.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\System Tools\\Control Panel.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\Control Panel.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\System Tools\\Default Apps.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\Default Apps.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\System Tools\\desktop.ini" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\desktop.ini" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\System Tools\\Devices.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\Devices.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\System Tools\\File Explorer.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\File Explorer.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\System Tools\\Run.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\Run.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell (x86).lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell (x86).lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Default:Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Default\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\desktop.ini" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\desktop.ini" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\Programs\\desktop.ini" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\desktop.ini" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\Programs\\Administrative Tools\\Active Directory PowerShell Snap-In.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools\\Active Directory PowerShell Snap-In.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\Programs\\Administrative Tools\\desktop.ini" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools\\desktop.ini" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\Programs\\Administrative Tools\\Group Policy Management.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools\\Group Policy Management.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\Programs\\Administrative Tools\\iSCSI Initiator.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools\\iSCSI Initiator.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\Programs\\Administrative Tools\\ODBC Data Sources (32-bit).lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools\\ODBC Data Sources (32-bit).lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\Programs\\Administrative Tools\\ODBC Data Sources (64-bit).lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools\\ODBC Data Sources (64-bit).lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\Programs\\Administrative Tools\\Security Configuration Management.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools\\Security Configuration Management.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\Programs\\Administrative Tools\\Windows Firewall with Advanced Security.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools\\Windows Firewall with Advanced Security.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\Programs\\StartUp\\desktop.ini" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\StartUp\\desktop.ini" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\Programs\\System Tools\\desktop.ini" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\desktop.ini" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\Programs\\System Tools\\Task Manager.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\Task Manager.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="Public:Start Menu\\Programs\\VMware\\VMware Tools\\start VM Statistics Logging.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\ProgramData\\Microsoft\\Windows\\Start Menu\\Programs\\VMware\\VMware Tools\\start VM Statistics Logging.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\desktop.ini" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\desktop.ini" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\desktop.ini" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\desktop.ini" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\Accessories\\desktop.ini" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Accessories\\desktop.ini" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\Accessories\\Notepad.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Accessories\\Notepad.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\Administrative Tools\\desktop.ini" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Administrative Tools\\desktop.ini" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\Startup\\desktop.ini" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Startup\\desktop.ini" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\System Tools\\Command Prompt.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\Command Prompt.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\System Tools\\computer.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\computer.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\System Tools\\Control Panel.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\Control Panel.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\System Tools\\Default Apps.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\Default Apps.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\System Tools\\desktop.ini" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\desktop.ini" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\System Tools\\Devices.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\Devices.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\System Tools\\File Explorer.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\File Explorer.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\System Tools\\Run.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\System Tools\\Run.lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell (x86).lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell (x86).lnk" | 
| \\FOREST\root\cimv2:Win32_LogicalProgramGroupItem.Name="HTB\\Administrator:Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell.lnk" | \\FOREST\root\cimv2:CIM_DataFile.Name="C:\\Users\\Administrator\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Windows PowerShell\\Windows PowerShell.lnk" |
```

### Win32_MemoryArray
```sh
WQL> SELECT * FROM Win32_MemoryArray 
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | StartingAddress | EndingAddress | ErrorInfo | OtherErrorDescription | CorrectableError | ErrorTime | ErrorAccess | ErrorTransferSize | ErrorData | ErrorDataOrder | ErrorAddress | SystemLevelAddress | ErrorResolution | AdditionalErrorData | ErrorGranularity | 
| Memory Array | Memory Array | None | Memory Array | None | 65535 | Win32_MemoryArray | None | True | Memory Array 0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 18446744073709551615 | None | 18446744073709551615 | None | 0 | 639 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | None | 
| Memory Array | Memory Array | None | Memory Array | None | 65535 | Win32_MemoryArray | None | True | Memory Array 1 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 18446744073709551615 | None | 18446744073709551615 | None | 1024 | 262143 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | None |
```

### Win32_MemoryArrayLocation
```sh
WQL> SELECT * FROM Win32_MemoryArrayLocation
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_PhysicalMemoryArray.Tag="Physical Memory Array 0" | \\FOREST\root\cimv2:Win32_MemoryArray.DeviceID="Memory Array 0" | 
| \\FOREST\root\cimv2:Win32_PhysicalMemoryArray.Tag="Physical Memory Array 0" | \\FOREST\root\cimv2:Win32_MemoryArray.DeviceID="Memory Array 1" |
```

### Win32_MemoryDevice
```sh
WQL> SELECT * FROM Win32_MemoryDevice
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | Access | BlockSize | ErrorMethodology | NumberOfBlocks | Purpose | StartingAddress | EndingAddress | ErrorInfo | OtherErrorDescription | CorrectableError | ErrorTime | ErrorAccess | ErrorTransferSize | ErrorData | ErrorDataOrder | ErrorAddress | SystemLevelAddress | ErrorResolution | AdditionalErrorData | ErrorGranularity | 
| Memory Device | Memory Device | None | Memory Device | None | 65535 | Win32_MemoryDevice | None | True | Memory Device 0 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 18446744073709551615 | None | 18446744073709551615 | None | 0 | 639 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | None | 
| Memory Device | Memory Device | None | Memory Device | None | 65535 | Win32_MemoryDevice | None | True | Memory Device 1 | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | 65535 | 18446744073709551615 | None | 18446744073709551615 | None | 1024 | 262143 | 65535 | None | True | None | 65535 | None | None | 65535 | 18446744073709551615 | True | 18446744073709551615 | None | None |
```

### Win32_MemoryDeviceArray
```sh
WQL> SELECT * FROM Win32_MemoryDeviceArray
| GroupComponent | PartComponent | 
| \\FOREST\root\cimv2:Win32_MemoryArray.DeviceID="Memory Array 0" | \\FOREST\root\cimv2:Win32_MemoryDevice.DeviceID="Memory Device 0" | 
| \\FOREST\root\cimv2:Win32_MemoryArray.DeviceID="Memory Array 1" | \\FOREST\root\cimv2:Win32_MemoryDevice.DeviceID="Memory Device 1" |
```

### Win32_MemoryDeviceLocation
```sh
WQL> SELECT * FROM Win32_MemoryDeviceLocation
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_PhysicalMemory.Tag="Physical Memory 0" | \\FOREST\root\cimv2:Win32_MemoryDevice.DeviceID="Memory Device 0" | 
| \\FOREST\root\cimv2:Win32_PhysicalMemory.Tag="Physical Memory 0" | \\FOREST\root\cimv2:Win32_MemoryDevice.DeviceID="Memory Device 1" |
```

### Win32_MotherboardDevice
```sh
WQL> SELECT * FROM Win32_MotherboardDevice
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | PrimaryBusType | RevisionNumber | SecondaryBusType | 
| Motherboard | Motherboard | None | Motherboard | OK | 3 | Win32_MotherBoardDevice | None | True | Motherboard | None | None | True | 65535 | Win32_ComputerSystem | FOREST | None | None | True | PCI | None | ISA |
```

### Win32_NetworkAdapter
```sh
WQL> SELECT * FROM Win32_NetworkAdapter
| Caption | Description | InstallDate | Name | Status | Availability | CreationClassName | ConfigManagerErrorCode | ConfigManagerUserConfig | DeviceID | PowerManagementCapabilities | PNPDeviceID | PowerManagementSupported | StatusInfo | SystemCreationClassName | SystemName | LastErrorCode | ErrorDescription | ErrorCleared | PermanentAddress | NetworkAddresses | Speed | MaxSpeed | AutoSense | ProductName | AdapterType | AdapterTypeId | MACAddress | ServiceName | Manufacturer | Installed | Index | InterfaceIndex | MaxNumberControlled | TimeOfLastReset | NetConnectionID | NetConnectionStatus | NetEnabled | GUID | PhysicalAdapter | 
| [00000000] Microsoft Kernel Debug Network Adapter | Microsoft Kernel Debug Network Adapter | None | Microsoft Kernel Debug Network Adapter | None | 3 | Win32_NetworkAdapter | 0 | False | 0 | None | ROOT\KDNIC\0000 | False | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | None | 18446744073709551615 | 18446744073709551615 | True | Microsoft Kernel Debug Network Adapter | None | None | None | kdnic | Microsoft | True | 0 | 3 | 0 | 20250901054812.493853-420 | None | None | None | None | False | 
| [00000001] Intel(R) 82574L Gigabit Network Connection | Intel(R) 82574L Gigabit Network Connection | None | Intel(R) 82574L Gigabit Network Connection | None | 3 | Win32_NetworkAdapter | 0 | False | 1 | None | PCI\VEN_8086&DEV_10D3&SUBSYS_07D015AD&REV_00\005056FFFFB441AF00 | False | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | None | 1000000000 | 18446744073709551615 | True | Intel(R) 82574L Gigabit Network Connection | Ethernet 802.3 | 0 | 00:50:56:94:6B:77 | e1iexpress | Intel Corporation | True | 1 | 5 | 0 | 20250901054812.493853-420 | Ethernet0 | 2 | True | {E00B7E21-EE8E-4210-8C23-A108EFC92167} | True | 
| [00000002] Microsoft ISATAP Adapter | Microsoft ISATAP Adapter | None | Microsoft ISATAP Adapter | None | 3 | Win32_NetworkAdapter | 0 | False | 2 | None | SWD\IP_TUNNEL_VBUS\ISATAP_0 | False | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | None | 100000 | 18446744073709551615 | True | Microsoft ISATAP Adapter | Tunnel | 15 | None | tunnel | Microsoft | True | 2 | 2 | 0 | 20250901054812.493853-420 | None | None | None | None | False | 
| [00000003] Microsoft Teredo Tunneling Adapter | Microsoft Teredo Tunneling Adapter | None | Microsoft Teredo Tunneling Adapter | None | 3 | Win32_NetworkAdapter | None | True | 3 | None | None | False | 65535 | Win32_ComputerSystem | FOREST | None | None | True | None | None | 18446744073709551615 | 18446744073709551615 | True | Microsoft Teredo Tunneling Adapter | None | None | None | None | None | True | 3 | 4 | 0 | 20250901054812.493853-420 | None | None | None | None | False |
```

### Win32_NetworkAdapterConfiguration
```sh
WQL> SELECT * FROM Win32_NetworkAdapterConfiguration
| SettingID | Caption | Description | GatewayCostMetric | DefaultIPGateway | DHCPEnabled | DHCPLeaseExpires | DHCPLeaseObtained | DHCPServer | Index | InterfaceIndex | IPAddress | IPSubnet | IPXAddress | MACAddress | ServiceName | IPEnabled | IPXEnabled | FullDNSRegistrationEnabled | DomainDNSRegistrationEnabled | IPConnectionMetric | DatabasePath | IPUseZeroBroadcast | ArpAlwaysSourceRoute | ArpUseEtherSNAP | DefaultTOS | DefaultTTL | DeadGWDetectEnabled | PMTUBHDetectEnabled | PMTUDiscoveryEnabled | ForwardBufferMemory | IGMPLevel | KeepAliveInterval | KeepAliveTime | MTU | NumForwardPackets | TcpMaxConnectRetransmissions | TcpMaxDataRetransmissions | TcpNumConnections | TcpUseRFC1122UrgentPointer | TcpWindowSize | IPPortSecurityEnabled | IPFilterSecurityEnabled | IPSecPermitTCPPorts | IPSecPermitUDPPorts | IPSecPermitIPProtocols | DNSHostName | DNSDomain | DNSServerSearchOrder | DNSDomainSuffixSearchOrder | DNSEnabledForWINSResolution | WINSEnableLMHostsLookup | WINSPrimaryServer | WINSSecondaryServer | WINSHostLookupFile | WINSScopeID | TcpipNetbiosOptions | IPXVirtualNetNumber | IPXNetworkNumber | IPXFrameType | IPXMediaType | 
| {D0F94394-DA53-47DE-9E02-938AF0CCD55D} | [00000000] Microsoft Kernel Debug Network Adapter | Microsoft Kernel Debug Network Adapter | None | None | True | None | None | None | 0 | 3 | None | None | None | None | kdnic | False | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | 
| {E00B7E21-EE8E-4210-8C23-A108EFC92167} | [00000001] Intel(R) 82574L Gigabit Network Connection | Intel(R) 82574L Gigabit Network Connection | 0 256  | 10.129.0.1 fe80::250:56ff:feb9:f8ec  | True | 20250902094839.000000-420 | 20250902084839.000000-420 | 10.129.0.1 | 1 | 5 | 10.129.138.203 fe80::f078:8d45:3c85:5444 dead:beef::f078:8d45:3c85:5444 dead:beef::8e  | 255.255.0.0 64 64 128  | None | 00:50:56:94:6B:77 | e1iexpress | True | None | True | False | 25 | %SystemRoot%\System32\drivers\etc | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | False |  |  |  | FOREST | .htb | 127.0.0.1  | htb.local htb  | False | True | None | None | None |  | 0 | None | None | None | None | 
| {96B97A16-1CCD-406C-818E-52A0AE4FF243} | [00000002] Microsoft ISATAP Adapter | Microsoft ISATAP Adapter | None | None | False | None | None | None | 2 | 2 | None | None | None | None | tunnel | False | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | 
| {D237B365-0ADE-4882-8122-5B874800EF32} | [00000003] Microsoft Teredo Tunneling Adapter | Microsoft Teredo Tunneling Adapter | None | None | False | None | None | None | 3 | 4 | None | None | None | None | tunnel | False | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None |
```

### Win32_NetworkAdapterSetting
```sh
WQL> SELECT * FROM Win32_NetworkAdapterSetting
| Element | Setting | 
| \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="0" | \\FOREST\root\cimv2:Win32_NetworkAdapterConfiguration.Index=0 | 
| \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="1" | \\FOREST\root\cimv2:Win32_NetworkAdapterConfiguration.Index=1 | 
| \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="2" | \\FOREST\root\cimv2:Win32_NetworkAdapterConfiguration.Index=2 | 
| \\FOREST\root\cimv2:Win32_NetworkAdapter.DeviceID="3" | \\FOREST\root\cimv2:Win32_NetworkAdapterConfiguration.Index=3 |
```

### Win32_NetworkClient
```sh
WQL> SELECT * FROM Win32_NetworkClient 
| Caption | Description | InstallDate | Name | Status | Manufacturer | 
| Workstation | LanmanWorkstation | None | Microsoft Windows Network | OK | Microsoft Corporation |
```

### Win32_NetworkLoginProfile
```sh
WQL> SELECT * FROM Win32_NetworkLoginProfile
| SettingID | Caption | Description | AccountExpires | AuthorizationFlags | BadPasswordCount | CodePage | Comment | CountryCode | Flags | FullName | HomeDirectory | HomeDirectoryDrive | LastLogoff | LastLogon | LogonHours | LogonServer | MaximumStorage | Name | NumberOfLogons | Parameters | PasswordAge | PasswordExpires | PrimaryGroupId | Privileges | Profile | ScriptPath | UnitsPerWeek | UserComment | UserId | UserType | Workstations | 
| None | NT AUTHORITY\SYSTEM | Network login profile settings for SYSTEM on NT AUTHORITY | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | NT AUTHORITY\SYSTEM | None | None | None | None | None | None | None | None | None | None | None | None | None | 
| None | NT AUTHORITY\LOCAL SERVICE | Network login profile settings for LOCAL SERVICE on NT AUTHORITY | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | NT AUTHORITY\LOCAL SERVICE | None | None | None | None | None | None | None | None | None | None | None | None | None | 
| None | NT AUTHORITY\NETWORK SERVICE | Network login profile settings for NETWORK SERVICE on NT AUTHORITY | None | None | None | None | None | None | None | None | None | None | None | None | None | None | None | NT AUTHORITY\NETWORK SERVICE | None | None | None | None | None | None | None | None | None | None | None | None | None | 
| None | sebastien | Network login profile settings for Sebastien Caron on HTB | None | 0 | 0 | 0 |  | 0 | 66113 | Sebastien Caron |  |  | **************.******+*** | 20190922152929.000000-420 | Sunday: No Limit -- Monday: No Limit -- Tuesday: No Limit -- Wednesday: No Limit -- Thursday: No Limit -- Friday: No Limit -- Saturday: No Limit | \\* | None | HTB\sebastien | 8 |  | 00002174153832.000000:000 | None | 513 | 1 |  |  | 168 |  | 1145 | Normal Account |  | 
| None | svc-alfresco | Network login profile settings for svc-alfresco on HTB | None | 0 | 0 | 0 |  | 0 | 4260353 | svc-alfresco |  |  | **************.******+*** | 20250902073300.000000-420 | Sunday: No Limit -- Monday: No Limit -- Tuesday: No Limit -- Wednesday: No Limit -- Thursday: No Limit -- Friday: No Limit -- Saturday: No Limit | \\* | None | HTB\svc-alfresco | 6 |  | 00000000000130.000000:000 | None | 513 | 1 |  |  | 168 |  | 1147 | Normal Account |  | 
| None | Administrator | Network login profile settings for Administrator on HTB | None | 0 | 0 | 0 | Built-in account for administering the computer/domain | 0 | 513 | Administrator |  |  | **************.******+*** | 20250901054943.000000-420 | Sunday: No Limit -- Monday: No Limit -- Tuesday: No Limit -- Wednesday: No Limit -- Thursday: No Limit -- Friday: No Limit -- Saturday: No Limit | \\* | None | HTB\Administrator | 143 |  | 00001463151633.000000:000 | None | 513 | 2 |  |  | 168 |  | 500 | Normal Account |  |
```

### Win32_NetworkProtocol
```sh
WQL> SELECT * FROM Win32_NetworkProtocol
| Caption | Description | InstallDate | Name | Status | ConnectionlessService | GuaranteesDelivery | GuaranteesSequencing | MaximumAddressSize | MaximumMessageSize | MessageOriented | MinimumAddressSize | PseudoStreamOriented | SupportsBroadcasting | SupportsConnectData | SupportsDisconnectData | SupportsEncryption | SupportsExpeditedData | SupportsFragmentation | SupportsGracefulClosing | SupportsGuaranteedBandwidth | SupportsMulticasting | SupportsQualityofService | 
| Tcpip | @%SystemRoot%\system32\tcpipcfg.dll,-50003 | 20190918042749.221503-420 | MSAFD Tcpip [TCP/IP] | OK | False | True | True | 16 | 0 | False | 16 | False | False | False | False | False | True | None | True | False | False | False | 
| Tcpip | @%SystemRoot%\system32\tcpipcfg.dll,-50003 | 20190918042749.221503-420 | MSAFD Tcpip [UDP/IP] | OK | True | False | False | 16 | 65527 | True | 16 | False | True | False | False | False | False | None | False | False | True | False | 
| Tcpip | @%SystemRoot%\system32\tcpipcfg.dll,-50003 | 20190918042749.221503-420 | MSAFD Tcpip [TCP/IPv6] | OK | False | True | True | 28 | 0 | False | 28 | False | False | False | False | False | True | None | True | False | False | False | 
| Tcpip | @%SystemRoot%\system32\tcpipcfg.dll,-50003 | 20190918042749.221503-420 | MSAFD Tcpip [UDP/IPv6] | OK | True | False | False | 28 | 65527 | True | 28 | False | True | False | False | False | False | None | False | False | True | False | 
| RSVP | RSVP TCPv6 Service Provider | None | RSVP TCPv6 Service Provider | None | False | True | True | 28 | 0 | False | 28 | False | False | False | False | True | True | None | True | False | False | True | 
| RSVP | RSVP TCP Service Provider | None | RSVP TCP Service Provider | None | False | True | True | 16 | 0 | False | 16 | False | False | False | False | True | True | None | True | False | False | True | 
| RSVP | RSVP UDPv6 Service Provider | None | RSVP UDPv6 Service Provider | None | True | False | False | 28 | 65527 | True | 28 | False | True | False | False | True | False | None | False | False | True | True | 
| RSVP | RSVP UDP Service Provider | None | RSVP UDP Service Provider | None | True | False | False | 16 | 65527 | True | 16 | False | True | False | False | True | False | None | False | False | True | True | 
| Hyper-V | Hyper-V RAW | None | Hyper-V RAW | None | False | True | True | 36 | 0 | False | 36 | False | False | False | False | False | False | None | True | False | False | False | 
| vSockets | vSockets DGRAM | None | vSockets DGRAM | None | True | False | False | 16 | 0 | True | 16 | False | False | False | False | False | False | None | False | False | False | False | 
| vSockets | vSockets STREAM | None | vSockets STREAM | None | False | True | True | 16 | 0 | False | 16 | False | False | False | False | False | False | None | True | False | False | False |
```

### Win32_OnBoardDevice
```sh
WQL> SELECT * FROM Win32_OnBoardDevice
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | DeviceType | Enabled | 
| On Board Device | VMware SVGA II | None | On Board Device | None | Win32_OnBoardDevice | None | None | None | None | On Board Device 0 | None | None | None | True | True | True | True | 3 | False | 
| On Board Device | ES1371 | None | On Board Device | None | Win32_OnBoardDevice | None | None | None | None | On Board Device 1 | None | None | None | True | True | True | True | 7 | False |
```

### Win32_PhysicalMemory
```sh
WQL> SELECT * FROM Win32_PhysicalMemory 
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | FormFactor | MemoryType | TotalWidth | DataWidth | Speed | Capacity | BankLabel | PositionInRow | InterleavePosition | DeviceLocator | TypeDetail | InterleaveDataDepth | Attributes | ConfiguredClockSpeed | MinVoltage | MaxVoltage | ConfiguredVoltage | SMBIOSMemoryType | 
| Physical Memory | Physical Memory | None | Physical Memory | None | Win32_PhysicalMemory | VMware Virtual RAM | None | None | 00000001 | Physical Memory 0 | None | VMW-2048MB | None | True | True | True | True | 8 | 2 | 64 | 64 | None | 2147483648 | RAM slot #0 | None | None | RAM slot #0 | 128 | None | 0 | 4800 | None | None | None | 3 |
```

### Win32_PhysicalMemoryArray
```sh
WQL> SELECT * FROM Win32_PhysicalMemoryArray
| Caption | Description | InstallDate | Name | Status | CreationClassName | Manufacturer | Model | SKU | SerialNumber | Tag | Version | PartNumber | OtherIdentifyingInfo | PoweredOn | Removable | Replaceable | HotSwappable | Height | Depth | Width | Weight | Location | Use | MemoryErrorCorrection | MaxCapacity | MaxCapacityEx | MemoryDevices | 
| Physical Memory Array | Physical Memory Array | None | Physical Memory Array | None | Win32_PhysicalMemoryArray | None | None | None | None | Physical Memory Array 0 | None | None | None | True | True | True | True | None | None | None | None | 3 | 3 | 3 | 2097152 | 2097152 | 64 |
```

### Win32_PhysicalMemoryLocation
```sh
WQL> SELECT * FROM Win32_PhysicalMemoryLocation
| GroupComponent | PartComponent | LocationWithinContainer | 
| \\FOREST\root\cimv2:Win32_PhysicalMemoryArray.Tag="Physical Memory Array 0" | \\FOREST\root\cimv2:Win32_PhysicalMemory.Tag="Physical Memory 0" | None |
```

### Win32_PnPAllocatedResource
```sh
WQL> SELECT * FROM Win32_PnPAllocatedResource
| Antecedent | Dependent | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="3758096384" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\4" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="1024" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\4" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4290772992" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\4" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4271898624" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A8" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="16384" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A8" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967293 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A8" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4270850048" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A9" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4196401152" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A9" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967292 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&A9" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4269801472" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AA" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4195352576" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AA" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967291 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AA" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4268752896" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AB" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4194304000" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AB" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967290 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AB" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4267704320" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AC" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4193255424" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AC" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967289 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AC" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4266655744" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AD" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4192206848" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AD" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967288 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AD" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4265607168" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AE" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4191158272" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AE" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967287 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AE" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4264558592" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AF" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4190109696" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AF" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967286 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&AF" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4263510016" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="12288" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B0" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967285 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B0" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4262461440" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4189061120" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B1" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967284 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4261412864" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B2" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4188012544" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B2" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967283 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B2" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4260364288" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B3" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4186963968" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B3" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967282 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B3" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4259315712" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B4" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4185915392" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B4" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967281 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B4" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4258267136" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B5" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4184866816" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B5" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967280 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B5" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4257218560" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B6" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4183818240" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B6" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967279 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B6" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4256169984" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B7" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4182769664" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B7" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967278 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B7" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4255121408" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B8" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4181721088" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B8" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967277 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B8" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4254072832" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B9" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4180672512" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B9" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967276 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&B9" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4253024256" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BA" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4179623936" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BA" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967275 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BA" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4251975680" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BB" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4178575360" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BB" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967274 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BB" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4250927104" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BC" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4177526784" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BC" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967273 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BC" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4249878528" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BD" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4176478208" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BD" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967272 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BD" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4248829952" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BE" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4175429632" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BE" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967271 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BE" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4247781376" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BF" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4174381056" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BF" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967270 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&BF" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4246732800" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C0" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4173332480" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C0" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967269 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C0" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4245684224" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4172283904" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C1" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967268 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4244635648" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C2" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4171235328" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C2" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967267 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C2" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4243587072" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C3" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4170186752" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C3" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967266 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C3" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4242538496" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C4" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4169138176" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C4" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967265 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C4" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4241489920" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C5" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4168089600" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C5" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967264 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C5" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4240441344" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C6" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4167041024" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C6" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967263 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C6" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4239392768" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C7" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4165992448" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C7" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967294 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07A0&SUBSYS_07A015AD&REV_01\\3&18D45AA6&0&C7" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4263641088" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_10D3&SUBSYS_07D015AD&REV_00\\005056FFFFB441AF00" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4263510016" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_10D3&SUBSYS_07D015AD&REV_00\\005056FFFFB441AF00" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4263837696" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_10D3&SUBSYS_07D015AD&REV_00\\005056FFFFB441AF00" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967258 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_10D3&SUBSYS_07D015AD&REV_00\\005056FFFFB441AF00" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967257 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_10D3&SUBSYS_07D015AD&REV_00\\005056FFFFB441AF00" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967256 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_10D3&SUBSYS_07D015AD&REV_00\\005056FFFFB441AF00" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967255 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_10D3&SUBSYS_07D015AD&REV_00\\005056FFFFB441AF00" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="64" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0100\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=0 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0100\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="3328" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4277141504" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4275326976" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4274061312" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4197449728" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4026531840" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="3221225472" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="655360" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="802816" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="819200" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="868352" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="884736" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="933888" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="950272" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="966656" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0A03\\2&DABA3FF&1" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="496" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="1014" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&0" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=14 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="368" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&1" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="886" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&1" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=15 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCIIDE\\IDECHANNEL\\4&39EC5D8A&0&1" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=12 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\VMW0003\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4271964160" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_1000&DEV_0054&SUBSYS_197615AD&REV_01\\4&2732702B&0&00A8" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4271898624" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_1000&DEV_0054&SUBSYS_197615AD&REV_01\\4&2732702B&0&00A8" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967260 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_1000&DEV_0054&SUBSYS_197615AD&REV_01\\4&2732702B&0&00A8" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4275044352" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0103\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="112" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0B00\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=8 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0B00\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="96" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0303\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="100" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0303\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=1 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0303\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=54 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI_HAL\\PNP0C08\\0" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=55 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI_HAL\\PNP0C08\\0" | 

---

| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=511 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI_HAL\\PNP0C08\\0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0200\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="129" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0200\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="192" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0200\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_DMAChannel.DMAChannel=4 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0200\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="16" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="36" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="40" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="44" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="46" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="48" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="52" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="56" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="60" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="80" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="114" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="128" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="144" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="164" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="168" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="172" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="176" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="184" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="188" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="1088" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="0" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="22104" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="22128" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="3312" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0C02\\1F" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4227923968" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07E0&SUBSYS_07E015AD&REV_00\\4&B70F118&0&0888" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967259 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_07E0&SUBSYS_07E015AD&REV_00\\4&B70F118&0&0888" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="65472" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0740&SUBSYS_074015AD&REV_10\\3&18D45AA6&0&3F" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4290764800" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0740&SUBSYS_074015AD&REV_10\\3&18D45AA6&0&3F" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967262 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0740&SUBSYS_074015AD&REV_10\\3&18D45AA6&0&3F" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=4294967261 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0740&SUBSYS_074015AD&REV_10\\3&18D45AA6&0&3F" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4227858432" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0790&SUBSYS_079015AD&REV_02\\3&18D45AA6&0&88" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4160749568" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0790&SUBSYS_079015AD&REV_02\\3&18D45AA6&0&88" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="4096" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0790&SUBSYS_079015AD&REV_02\\3&18D45AA6&0&88" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="97" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0800\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="8256" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0405&SUBSYS_040515AD&REV_00\\3&18D45AA6&0&78" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4026531840" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0405&SUBSYS_040515AD&REV_00\\3&18D45AA6&0&78" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="4219469824" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0405&SUBSYS_040515AD&REV_00\\3&18D45AA6&0&78" | 
| \\FOREST\root\cimv2:Win32_IRQResource.IRQNumber=16 | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0405&SUBSYS_040515AD&REV_00\\3&18D45AA6&0&78" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="944" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0405&SUBSYS_040515AD&REV_00\\3&18D45AA6&0&78" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="960" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0405&SUBSYS_040515AD&REV_00\\3&18D45AA6&0&78" | 
| \\FOREST\root\cimv2:Win32_DeviceMemoryAddress.StartingAddress="655360" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_15AD&DEV_0405&SUBSYS_040515AD&REV_00\\3&18D45AA6&0&78" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="32" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0001\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="160" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0001\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="1232" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="ACPI\\PNP0001\\4&25EE97C0&0" | 
| \\FOREST\root\cimv2:Win32_PortResource.StartingAddress="8272" | \\FOREST\root\cimv2:Win32_PnPEntity.DeviceID="PCI\\VEN_8086&DEV_7111&SUBSYS_197615AD&REV_01\\3&18D45AA6&0&39" | 
```
