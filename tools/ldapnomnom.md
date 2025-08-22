## LDAP Ping
```sh
└─$ ./ldapnomnom -input /usr/share/seclists/Usernames/xato-net-10-million-usernames-dup.txt -parallel 16 -server 10.129.158.167
 __    ____  _____ _____                             
|  |  |    \|  _  |  _  |___ ___ _____ ___ ___ _____ 
|  |__|  |  |     |   __|   | . |     |   | . |     |
|_____|____/|__|__|__|  |_|_|___|_|_|_|_|_|___|_|_|_|


IN  SPACE  NO  ONE  CAN  HEAR  YOU  NOM  NOM  USERNAMES

mark
andy
administrator
sebastien
santi
lucinda
```

## rootDSE 
```sh
└─$ ./ldapnomnom -server 10.129.158.167 -dump
 __    ____  _____ _____                             
|  |  |    \|  _  |  _  |___ ___ _____ ___ ___ _____ 
|  |__|  |  |     |   __|   | . |     |   | . |     |
|_____|____/|__|__|__|  |_|_|___|_|_|_|_|_|___|_|_|_|


IN  SPACE  NO  ONE  CAN  HEAR  YOU  NOM  NOM  USERNAMES

[
  {
    "Response": {
      "ConfigurableSettingsEffective": null,
      "LDAPPoliciesEffective": null,
      "approximateHighestInternalObjectID": [
        "9073"
      ],
      "configurationNamingContext": [
        "CN=Configuration,DC=htb,DC=local"
      ],
      "currentTime": [
        "20250822104929.0Z"
      ],
      "dNSHostName": [
        "FOREST.htb.local"
      ],
      "databaseGuid": [
        "00000000-0000-0000-0000-000000000000"
      ],
      "defaultNamingContext": [
        "DC=htb,DC=local"
      ],
      "domainControllerFunctionality": [
        "7"
      ],
      "domainFunctionality": [
        "7"
      ],
      "dsSchemaAttrCount": [
        "3943"
      ],
      "dsSchemaClassCount": [
        "583"
      ],
      "dsSchemaPrefixCount": [
        "50"
      ],
      "dsServiceName": [
        "CN=NTDS Settings,CN=FOREST,CN=Servers,CN=Default-First-Site-Name,CN=Sites,CN=Configuration,DC=htb,DC=local"
      ],
      "dsaVersionString": null,
      "dumpLdapNotifications": null,
      "forestFunctionality": [
        "7"
      ],
      "highestCommittedUSN": [
        "6496452"
      ],
      "isGlobalCatalogReady": [
        "TRUE"
      ],
      "isSynchronized": [
        "TRUE"
      ],
      "ldapServiceName": [
        "htb.local:forest$@HTB.LOCAL"
      ],
      "msDS-Anchor": null,
      "msDS-ArenaInfo": null,
      "msDS-PortLDAP": [
        "389"
      ],
      "msDS-PortSSL": [
        "636"
      ],
      "msDS-PrefixTable": null,
      "msDS-PrincipalName": [
        "NT AUTHORITY\\ANONYMOUS LOGON"
      ],
      "msDS-ProcessLinksOperations": [
        ""
      ],
      "msDS-ReplAllInboundNeighbors": null,
      "msDS-ReplAllOutboundNeighbors": null,
      "msDS-ReplConnectionFailures": null,
      "msDS-ReplLinkFailures": null,
      "msDS-ReplPendingOps": null,
      "msDS-ReplQueueStatistics": null,
      "msDS-SegmentCacheInfo": [
        "1/0"
      ],
      "msDS-SupportedRootDSEAttributes": null,
      "msDS-SupportedRootDSEModifications": null,
      "msDS-ThreadStates": null,
      "msDS-TopQuotaUsage": null,
      "namingContexts": [
        "DC=htb,DC=local",
        "CN=Configuration,DC=htb,DC=local",
        "CN=Schema,CN=Configuration,DC=htb,DC=local",
        "DC=DomainDnsZones,DC=htb,DC=local",
        "DC=ForestDnsZones,DC=htb,DC=local"
      ],
      "netlogon": null,
      "pendingPropagations": null,
      "rootDomainNamingContext": [
        "DC=htb,DC=local"
      ],
      "schemaIndexUpdateState": [
        "3"
      ],
      "schemaNamingContext": [
        "CN=Schema,CN=Configuration,DC=htb,DC=local"
      ],
      "serverName": [
        "CN=FOREST,CN=Servers,CN=Default-First-Site-Name,CN=Sites,CN=Configuration,DC=htb,DC=local"
      ],
      "serviceAccountInfo": null,
      "spnRegistrationResult": null,
      "subschemaSubentry": [
        "CN=Aggregate,CN=Schema,CN=Configuration,DC=htb,DC=local"
      ],
      "supportedCapabilities": [
        "1.2.840.113556.1.4.800",
        "1.2.840.113556.1.4.1670",
        "1.2.840.113556.1.4.1791",
        "1.2.840.113556.1.4.1935",
        "1.2.840.113556.1.4.2080",
        "1.2.840.113556.1.4.2237"
      ],
      "supportedConfigurableSettings": [
        "DynamicObjectDefaultTTL",
        "DynamicObjectMinTTL",
        "DisableVLVSupport",
        "ADAMDisablePasswordPolicies",
        "ADAMDisableLogonAuditing",
        "ADAMLastLogonTimestampWindow",
        "RequireSecureSimpleBind",
        "RequireSecureProxyBind",
        "MaxReferrals",
        "ReferralRefreshInterval",
        "SelfReferralsOnly",
        "ADAMAllowADAMSecurityPrincipalsInConfigPartition",
        "ADAMDisableSPNRegistration",
        "ADAMDisableSSI"
      ],
      "supportedControl": [
        "1.2.840.113556.1.4.319",
        "1.2.840.113556.1.4.801",
        "1.2.840.113556.1.4.473",
        "1.2.840.113556.1.4.528",
        "1.2.840.113556.1.4.417",
        "1.2.840.113556.1.4.619",
        "1.2.840.113556.1.4.841",
        "1.2.840.113556.1.4.529",
        "1.2.840.113556.1.4.805",
        "1.2.840.113556.1.4.521",
        "1.2.840.113556.1.4.970",
        "1.2.840.113556.1.4.1338",
        "1.2.840.113556.1.4.474",
        "1.2.840.113556.1.4.1339",
        "1.2.840.113556.1.4.1340",
        "1.2.840.113556.1.4.1413",
        "2.16.840.1.113730.3.4.9",
        "2.16.840.1.113730.3.4.10",
        "1.2.840.113556.1.4.1504",
        "1.2.840.113556.1.4.1852",
        "1.2.840.113556.1.4.802",
        "1.2.840.113556.1.4.1907",
        "1.2.840.113556.1.4.1948",
        "1.2.840.113556.1.4.1974",
        "1.2.840.113556.1.4.1341",
        "1.2.840.113556.1.4.2026",
        "1.2.840.113556.1.4.2064",
        "1.2.840.113556.1.4.2065",
        "1.2.840.113556.1.4.2066",
        "1.2.840.113556.1.4.2090",
        "1.2.840.113556.1.4.2205",
        "1.2.840.113556.1.4.2204",
        "1.2.840.113556.1.4.2206",
        "1.2.840.113556.1.4.2211",
        "1.2.840.113556.1.4.2239",
        "1.2.840.113556.1.4.2255",
        "1.2.840.113556.1.4.2256",
        "1.2.840.113556.1.4.2309"
      ],
      "supportedExtension": [
        "1.3.6.1.4.1.1466.20037",
        "1.3.6.1.4.1.1466.101.119.1",
        "1.2.840.113556.1.4.1781",
        "1.3.6.1.4.1.4203.1.11.3",
        "1.2.840.113556.1.4.2212"
      ],
      "supportedLDAPPolicies": [
        "MaxPoolThreads",
        "MaxPercentDirSyncRequests",
        "MaxDatagramRecv",
        "MaxReceiveBuffer",
        "InitRecvTimeout",
        "MaxConnections",
        "MaxConnIdleTime",
        "MaxPageSize",
        "MaxBatchReturnMessages",
        "MaxQueryDuration",
        "MaxDirSyncDuration",
        "MaxTempTableSize",
        "MaxResultSetSize",
        "MinResultSets",
        "MaxResultSetsPerConn",
        "MaxNotificationPerConn",
        "MaxValRange",
        "MaxValRangeTransitive",
        "ThreadMemoryLimit",
        "SystemMemoryLimitPercent"
      ],
      "supportedLDAPVersion": [
        "3",
        "2"
      ],
      "supportedSASLMechanisms": [
        "GSSAPI",
        "GSS-SPNEGO",
        "EXTERNAL",
        "DIGEST-MD5"
      ],
      "tokenGroups": [
        "\u0001\u0001\u0000\u0000\u0000\u0000\u0000\u0005\u0007\u0000\u0000\u0000"
      ],
      "usnAtRifm": [
        "1"
      ],
      "validFSMOs": [
        "CN=Schema,CN=Configuration,DC=htb,DC=local",
        "CN=Partitions,CN=Configuration,DC=htb,DC=local",
        "DC=htb,DC=local",
        "CN=Infrastructure,DC=htb,DC=local",
        "CN=RID Manager$,CN=System,DC=htb,DC=local"
      ]
    },
    "Server": "10.129.158.167"
  }
]  
```
