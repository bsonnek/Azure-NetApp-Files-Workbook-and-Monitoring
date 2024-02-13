## Issues Discovered While Deploying and Using Deployed Resources


### Azure Automation Account

#### PowerShell 5.1 Modules and Dependencies

Sometimes the Az.Account and Az.NetAppFiles  PowerShell 5.1 Modules do not install correctly in the deployment. The Az.NetAppFiles module has a dependecy on the Az.Accounts module. 
If the Az.Account Module is not at version 2.12.4 it will not install the Az.NetAppFiles version 0.12.0 module.  We are now testing Az.Account 2.15.1 with Az.NetAppFiles 0.15.0  5.1 PowerShell.
Following this guide to manage your modules will typically fix any issues:
https://learn.microsoft.com/en-us/azure/automation/automation-update-azure-modules#update-az-modules
##### Steps:
1. Add Module Az.Accounts 2.15.1 - PowerShell 5.1
2. Delete Failed Az.NetAppFiles Module
3. Add Module Az.NetAppFiles 0.15.0 - PowerShell 5.1
4. Then continue with the Troubleshooting guide to add the Environmental variables to the Automation Account. These variables are used in the PowerShell script to write logs and trigger logic apps.

 ARM Template Version Control
![image](https://github.com/bsonnek/Azure-NetApp-Files-Workbook-and-Monitoring/assets/10324197/f6b3bf7d-0814-4eeb-8629-69bd8035a14c)

Manage Modules from Here:
![image](https://github.com/bsonnek/Azure-NetApp-Files-Workbook-and-Monitoring/assets/10324197/2df6212c-17d7-42a3-ba0a-867fd63a978a)


How to Add Module:
![image](https://github.com/bsonnek/Azure-NetApp-Files-Workbook-and-Monitoring/assets/10324197/00bc3bb9-c75c-4611-9c37-957c828ea49e)


