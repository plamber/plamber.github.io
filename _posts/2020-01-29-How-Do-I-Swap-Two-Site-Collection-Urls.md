---
layout: post
title:  "How do I rename a SharePoint Online site using PowerShell?"
author: plamber
categories: [ IT Pro, SharePoint ]
tags: [PowerShell, SharePoint, Office 365, Microsoft 365]
featured: false
---
A SharePoint Online administrator can change the SharePoint Online [site address](https://docs.microsoft.com/en-us/sharepoint/change-site-address). The interesting part of this feature is that in many situations Microsoft already considered how to limit the impact of such a change. Nevertheless, you should have a look into the [effects of changing a site address](https://docs.microsoft.com/en-us/sharepoint/change-site-address) before performing any operation. 

I created a sample script that shows you how to use PowerShell to perform a site change.

<script src="https://gist.github.com/plamber/111858beb76943a70a7588bee598460b.js"></script>

From the script, you can see that the operations are triggered by using the [Start-SPOSiteRename](https://docs.microsoft.com/en-us/powershell/module/sharepoint-online/start-spositerename?view=sharepoint-ps) command. This will queue a rename job that will be executed in the background. The command [Get-SPOSiteRenameState](https://docs.microsoft.com/en-us/powershell/module/sharepoint-online/Get-SPOSiteRenameState?view=sharepoint-ps) will return you the current status of the job. Once the job is marked as completed, you will have two sites in your tenant. You will have the site with the new URL and contents and a new site using the Template **Redirect#0**. This site will ensure that all requests pointing to the old URL will be redirected to the new URL. This site also ensures that nobody is able to request a new site with the old URL. 

In case you want to free up the old name, delete the site collection that has been created for redirection.


## Install the SharePoint Online Management Module if required
## Install-Module -Name Microsoft.Online.SharePoint.PowerShell 
## More info under https://www.nubo.eu/Connect-to-SharePoint-Online-using-PowerShell/
## Important: Execute these steps one by one

## parameters start
$tenant = "adidasgroup"
$firstSiteAlias = "WorkingProductLed"
$firstSiteNewAlias = "WorkingProductLedFuture"
$secondSiteAlias = "ProductTeamsPlaybook"
## parameters end

# Connect to SPO with admin accounts
Connect-SPOService "https://$tenant-admin.sharepoint.com"
$firstSiteUrl = "https://$tenant.sharepoint.com/sites/$firstSiteAlias"
$firstSiteNewAliasUrl = "https://$tenant.sharepoint.com/sites/$firstSiteNewAlias"
$secondSiteUrl = "https://$tenant.sharepoint.com/sites/$secondSiteAlias"

# The original site needs to be moved to a different place
Start-SPOSiteRename -Identity $firstSiteUrl -NewSiteUrl $firstSiteNewAliasUrl -Confirm:$false
# The process might take a while depending the size of the site. You can check the status using this command
Get-SPOSiteRenameState -Identity $firstSiteUrl

# Once the process is completed, perform these steps
# The previous move operation created a REDIRECTSITE#0 site on our desired spot. We have to delete first
$site = Get-SPOSite $firstSiteUrl
if ($site.Template -eq "REDIRECTSITE#0") {
    $site | Remove-SPOSite -Confirm:$false
}

# We removed the REDIRECTSITE#0 on our desired URL. Now go and perform a rename of the SharePoint site that needs the new URL
Start-SPOSiteRename -Identity $secondSiteUrl -NewSiteUrl $firstSiteUrl -Confirm:$false
# The process might take a while depending the size of the site. You can check the status using this command
Get-SPOSiteRenameState -Identity $secondSiteUrl

# The second site was moved to the new url. This rename operation created a redirect template site on the old URL
$site = Get-SPOSite $secondSiteUrl
$site.Template