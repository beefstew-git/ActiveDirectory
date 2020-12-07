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
![](/images/UserCommands/UserCount.png)

Get user count in specific OU
```
(Get-ADUser -Filter * -SearchBase "OU=US,DC=TEST,DC=LOCAL").count
```
![](/images/UserCommands/OUcount.png)

