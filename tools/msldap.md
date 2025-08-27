```sh
[DC=htb,DC=local]> help

Documented commands:
====================

?                                                                        
addallowedtoactonbehalfofotheridentity <target_dn> <other_identity_sid>  Adds a SID to the msDS-AllowedToActOnBehalfOfOtherIdentity protperty of target_dn
addcerttemplatenameflagaltname <certtemplatename> [flags=None]           Modifyies the msPKI-Certificate-Name-Flag value of the specified certificate template and enables ENROLLEE_SUPPLIES_SUBJECT_ALT_NAME bit. If 'flags' is present then it will assign that value.
addcomputer  [computername=None] [password=None]                         Adds a new computer account
addenrollmentright <certtemplatename> <user_dn>                          Grants enrollment rights to a user (by DN) for the specified certificate template.
addhostname <user_dn> <hostname>                                         Adds additional hostname to computer account
addprivaddmember <user_dn> <group_dn>                                    Adds AddMember rights to the user on the group specified by group_dn
addprivdcsync <user_dn> [forest=None]                                    Adds DCSync rights to the given user by modifying the forest's Security Descriptor to add GetChanges and GetChangesAll ACE
addspn <user_dn> <spn>                                                   Adds an SPN entry to the users account
adduser <user_dn> <password>                                             Creates a new domain user with password
addusertogroup <user_dn> <group_dn>                                      Adds user to specified group. Both user and group must be in DN format!
adinfo  [show=True]                                                      Prints detailed Active Driectory info
aiacas  [to_print=True]                                                  Lists AIA CA certificates
allschemaentry                                                           Feteches all schema object entry objects
asrep                                                                    Fetches ASREP-roastable user accounts
bindtree <newtree>                                                       Changes the LDAP TREE for future queries. MUST be DN format eg. 'DC=test,DC=corp'
cat  [attributes='*'] [dn='']                                            Print attributes of object. Without arguments it will cat the current DN
cd <path>                                                                Change current work directory
certify  [cmd=None] [username=None]                                      ADCA security test
certtemplates  [name=None] [to_print=True]                               Lists certificate templates
changeowner <new_owner_sid> <target_dn> [target_attribute=None]          Changes the owner in a Security Descriptor to the new_owner_sid on an LDAP object or on an LDAP object's attribute identified by target_dn and target_attribute. target_attribute can be omitted to change the target_dn's SD's owner
changesamaccountname <dn> <newname>                                      Changes the sAMAccountName of a given DN
changeuserpw <user_dn> <newpass> [oldpass=None]                          Changes user password, if you are admin then old pw doesnt need to be supplied
computeraddr                                                             Fetches all computer accounts
constrained                                                              Lists all constrained delegation objects
dadms                                                                    Lists all members of the domain administrators group
delspn <user_dn> <spn>                                                   Removes an SPN entry to the users account
deluser <user_dn>                                                        Deletes the user! This action is irrecoverable (actually domain admins can do that but probably will shout with you)
deluserfromgroup <user_dn> <group_dn>                                    Removes user from specified group. Both user and group must be in DN format!
disableuser <user_dn>                                                    Unlock user by flipping useraccountcontrol bits
dn2sam <dn>                                                              Fetches the sAMAccountName of an object based on the DN
dn2sid <dn>                                                              Fetches the objectSid of an object based on the DN
dnsdump  [zone=None]                                                     
dnszones                                                                 Lists all DNS zones
dump                                                                     Fetches ALL user and machine accounts from the domain with a LOT of attributes
enableuser <user_dn>                                                     Unlock user by flipping useraccountcontrol bits
enrollmentservices  [to_print=True]                                      Lists AIA CA certificates
exit                                                                     Exit the prompt
genschema                                                                Generates schema data. This will take a long time.
getsd <dn> [opts=' ']                                                    Feteches security info for a given DN
gmsa                                                                     Lists all managed service accounts (MSA). If user has permissions it retrieves the password as well
gpos                                                                     Feteches security info for a given DN
groupmembers <dn> [recursive=True]                                       Returns all member users in a group specified by DN
groupmembership <dn>                                                     Feteches names all groupnames the user is a member of for a given DN
help                                                                     
laps                                                                     Feteches all laps passwords
ldapinfo  [show=True]                                                    Prints detailed LDAP connection info (DSA)
login  [url=None]                                                        Performs connection and login
ls  [fullpath=False]                                                     Print objects in current work directory
machine <samaccountname>                                                 Feteches a machine object based on the sAMAccountName of the machine
modify <dn> <attribute> <value>                                          Modify an attribute of object. Only works with string data types!
nocb                                                                     Disables channel binding
nosig                                                                    Disables signing
ntcas  [to_print=True]                                                   Lists NT CA certificates
nullcb                                                                   Sets incorrect channel binding data
pre2000                                                                  Lists potentially abusable machine accounts created with pre windows-2000 flag
query <query> [attributes='-']                                           Performs a raw LDAP query against the server. Secondary parameter is the requested attributes SEPARATED WITH COMMA (,)
quit                                                                     Exit the prompt
rootcas  [to_print=True]                                                 Lists Root CA certificates
s4u2proxy                                                                Lists all S4U2Proxy objects
sam2dn <sAMAccountName>                                                  Fetches the DN of an object based on the sAMAccountName
schemaentry <cn>                                                         Feteches a schema object entry object based on the DN of the object (must start with CN=)
setsd <target_dn> <sddl>                                                 Updates the security descriptor of an object
sid2dn <sid>                                                             Fetches the DN of an object based on the objectSid
sidresolv <sid> [to_print=True]                                          Returns the domain and username for SID
spns                                                                     Fetches kerberoastable user accounts
test                                                                     testing, dontuse
tree  [dn=None] [level=1]                                                Prints a tree from the given DN (if not set, the top) and with a given depth (default: 1)
trusts                                                                   Feteches gives back domain trusts
unconstrained                                                            Lists all unconstrained delegation objects
unlockuser <user_dn>                                                     Unlock user by setting lockoutTime to 0
user <samaccountname> [to_print=True]                                    Feteches a user object based on the sAMAccountName of the user
whoami                                                                   Full whoami
whoamiraw                                                                Simple whoami
```
