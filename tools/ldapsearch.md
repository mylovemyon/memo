```sh
└─$ ldapsearch -b 'DC=htb,DC=local' -LLL -s 'sub' -D 'svc-alfresco@htb.local' -H ldap://10.129.153.237 -w 's3rvice' '(&(sAMAccountName=svc-alfresco)(objectCategory=user))' '*'         
dn: CN=svc-alfresco,OU=Service Accounts,DC=htb,DC=local
objectClass: top
objectClass: person
objectClass: organizationalPerson
objectClass: user
cn: svc-alfresco
givenName: svc-alfresco
distinguishedName: CN=svc-alfresco,OU=Service Accounts,DC=htb,DC=local
instanceType: 4
whenCreated: 20190920005851.0Z
whenChanged: 20250925062051.0Z
displayName: svc-alfresco
uSNCreated: 26083
memberOf: CN=Service Accounts,OU=Security Groups,DC=htb,DC=local
uSNChanged: 2492177
name: svc-alfresco
objectGUID:: AhOlWHxMhkaVAtOto6+u8Q==
userAccountControl: 4260352
badPwdCount: 0
codePage: 0
countryCode: 0
badPasswordTime: 0
lastLogoff: 0
lastLogon: 132137105879311936
logonHours:: ////////////////////////////
pwdLastSet: 134032548519909895
primaryGroupID: 513
objectSid:: AQUAAAAAAAUVAAAALB4ltxV1shXFsPNPewQAAA==
adminCount: 1
accountExpires: 0
logonCount: 6
sAMAccountName: svc-alfresco
sAMAccountType: 805306368
userPrincipalName: svc-alfresco@htb.local
objectCategory: CN=Person,CN=Schema,CN=Configuration,DC=htb,DC=local
dSCorePropagationData: 20250925062115.0Z
dSCorePropagationData: 20250925062115.0Z
dSCorePropagationData: 20250925062115.0Z
dSCorePropagationData: 20250925062115.0Z
dSCorePropagationData: 16010101000000.0Z
lastLogonTimestamp: 132136663111826271
msDS-SupportedEncryptionTypes: 0

# refldap://ForestDnsZones.htb.local/DC=ForestDnsZones,DC=htb,DC=local

# refldap://DomainDnsZones.htb.local/DC=DomainDnsZones,DC=htb,DC=local

# refldap://htb.local/CN=Configuration,DC=htb,DC=local
```
