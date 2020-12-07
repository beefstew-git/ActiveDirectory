# Managing users in Active Directory using PowerShell

These commands can be used to manage and query users in Active Directory
Specifically we can do the following:
- Create and delete users
- Reset passwords
- Enable/disable accounts
- Lock/Unlock accounts
- Edit user properties


### Queries
Get user count in domain
```
(Get-ADUser -Filter *).count
```
![](/UserCommands/images/UserCount.png)

Get user count in specific OU
```
(Get-ADUser -Filter * -SearchBase "OU=IT,OU=US,DC=TEST,DC=LOCAL").count
```
![](/UserCommands/images/OUcount.png)

Get users with name like "dan" and return Name, Username, and DistinguishedName
```
Get-ADUser -Filter {name -like "*dan*"} | select Name,SamAccountName,DistinguishedName | Format-Table
```
![](/UserCommands/images/UsersLike.png)

Get user properties and return specific ones
```
Get-ADUser j.booi -Properties * | Select Created,Enabled,LastLogonDate,LogonCount
```
![](/UserCommands/images/UserProperties.png)


### Account status and passwords
Find disabled user accounts
```
Search-ADAccount -AccountDisabled -UsersOnly | Select Name, SamAccountName
```
![](/UserCommands/images/FindDisabled.png)

Enable user account
```
Enable-ADAccount -Identity j.booi
```
![](/UserCommands/images/EnableAccount.png)

Disable user account
```
Disable-ADAccount -Identity j.booi
```
![](/UserCommands/images/DisableAccount.png)

Find locked accounts
```
Search-ADAccount -LockedOut -UsersOnly | Select Name, SamAccountName
```
![](/UserCommands/images/Locked.png)

Unlock account
```
Unlock-ADAccount -Identity j.booi
```
![](/UserCommands/images/Unlocked.png)

