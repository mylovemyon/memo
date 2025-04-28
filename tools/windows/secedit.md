```
The syntax of this command is:

secedit [/configure | /analyze | /import | /export | /validate | /generaterollback]
```

## export
```
Allows you to export security settings stored in a database.

The syntax of this command is:

secedit /export [/db filename] [/mergedpolicy] /cfg filename [/areas area1 area2...] [/log filename]

            /db filename - Specifies the database to export data from. If not specified, system security database will be used.

            /cfg filename - Specifies a security template to export the database contents to.

            /mergedpolicy - Merges and exports domain and local policy security settings.

            /areas - Specifies the security areas to export. If this parameter is not specified, all security settings defined in the database are exported. To export specific areas, separate each area by a space.  The following security areas are exported:

                        SECURITYPOLICY - Includes Account Policies, Audit Policies, Event Log Settings and Security Options.
                        GROUP_MGMT - Includes Restricted Group settings
                        USER_RIGHTS - Includes User Rights Assignment
                        REGKEYS - Includes Registry Permissions
                        FILESTORE - Includes File System permissions
                        SERVICES - Includes System Service settings

            /log filename - Specifies a file in which to log the status of the export process.  If not specified, export processing information is logged in the scesrv.log file which is located in the %windir%\security\logs directory.

Example:

secedit /export /db hisecws.sdb /cfg hisecws.inf /log hisecws.log

For all filenames, the current directory is used if no path is specified.
```
