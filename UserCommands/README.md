# Managing users in Active Directory using PowerShell

## These commands can be used to manage and query users in Active Directory
## - Specifically we can do the following:
## - Create and delete users
## - Reset passwords
## - Enable/disable accounts
## - Lock/Unlock accounts
## - Edit user properties

Get user count in domain
```
(Get-ADUser -Filter *). count
```

Get use cout in specific OU
```
(Get-ADUser -Filter * -SearchBase "OU=US,DC=TEST,DC=LOCAL"). count
```
![](/images/UserCommands/CountUsers.png)

