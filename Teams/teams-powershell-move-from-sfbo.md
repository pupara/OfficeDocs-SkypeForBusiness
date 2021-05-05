---
title: Migrating from Skype for Business Online Connector to the Teams PowerShell module
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection: 
  - M365-collaboration
description: Learn how to move from Skype for Business Online Connector to the Teams PowerShell module to manage Teams.
appliesto: 
  - Microsoft Teams
---

# Migrating from Skype for Business Online Connector to the Teams PowerShell module

Teams PowerShell Module provides a complete set of cmdlets for managing Teams directly from the PowerShell command line. Administrators do not require Skype For Business Online Connector for their Teams administration. 

> [!NOTE]
> Teams administrator were notified through Message center post (MC244740, dated March 16, 2021; MC250940, dated April 16 2021) about this change.

> [!WARNING]
> Customers who have migrated to Teams must use Teams Powershell Module. Connection orginating from Skype for Business online connector will be rejected starting May 17, 2021.
>
> All customers must migrate to Teams PowerShell Module no later than July 31 2021. 


## How to Migrate
Migrating from using Skype for Business Online Connector to  Teams PowerShell module is easy and simple. This article explains how to do this.

1. Install the latest Teams PowerShell module. For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).
2. Uninstall Skype For Business Online Connector. To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**. 
3. In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from 
```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.

    For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.
4. When using Teams PowerShell Module 2.0 or later, change New-csOnlineSession to Connect-MicrosoftTeams. 

```powershell
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## Online support

Save time by starting your service request online. We'll help you find a solution or connect you to technical support.

1. Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. If you get a message that says you don't have permission to access this page or perform this action, then you aren't an admin. [Who has admin permissions in my business?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview?#who-has-admin-permissions-in-my-business)

2. Select the **Need help?** button.

3. In the **Need help?** pane, tell us what you need help with, and then press **Enter**.

4. If the results don't help, select **Contact support**.

5. Enter a description of your issue, confirm your contact number and email address, select your preferred contact method, and then select **Contact me**. The expected wait time is indicated in the **Need help?** pane.



## Related topics

[Install Microsoft Teams Powershell](teams-powershell-install.md)

[Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md)

[Teams PowerShell release notes](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet reference](/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet reference](/powershell/skype/intro?view=skype-ps)
