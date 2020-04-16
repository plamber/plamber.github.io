---
layout: post
title:  "How do I remove a site collection admin from all site collections in SharePoint Online?"
author: plamber
categories: [ Development, SharePoint ]
tags: [PowerShell, SharePoint, Office 365, Microsoft 365]
featured: false
---
I had the requirement to remove a site collection admin assigned to all SharePoint Online site collections with a script. To achieve this goal I was using [Pnp PowerShell](https://docs.microsoft.com/en-us/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). The script was executed by an account having permissions to all SharePoint Online sites.

```
$username = "putYourUserNameHere"
$password = "putYourPasswordHere"
$tenant = "putYourTenantHere"
# alternatively use the loginname. ensure you are going to change the Get-PnpUser filter
$displayName = "*putTheDisplayNameOfTheUserHere*"

[SecureString]$SecurePass = ConvertTo-SecureString $password -AsPlainText -Force 
$creds = New-Object System.Management.Automation.PSCredential($username, $SecurePass) 

Connect-PnPOnline "https://$tenant-admin.sharepoint.com" -Credentials $creds

Get-PnPTenantSite | ForEach-Object {
   $site = $_
   Write-Host "Processing $($site.Url)..."
   Connect-PnPOnline $site.Url -Credentials $creds
   Get-PnPUser | ? Title -like $displayName | Remove-PnPSiteCollectionAdmin
}
```