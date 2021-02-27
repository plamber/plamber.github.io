---
layout: post
title:  "Change the owner Group membership of all SharePoint Online sites"
author: plamber
categories: [ Development, PowerShell, SharePoint, PnpPowerShell ]
tags: [SharePoint, Office 365, Microsoft 365, PnpPowerShell]
---
I was required to limit the permission of all owners added to the default owner Group and assign them to the default member Group. I created this script using [PnP PowerShell](https://github.com/pnp/pnp-powershell) taking all the members of the default owner group and assigning them to the default member Group. After that I am removing the identity from the owner Group.

This script uses a `userNameOrPattern` variable to allow you to limit the operation on selected identities. 

<script src="https://gist.github.com/plamber/3fcac3dd596acf8faf8f12c0622f4f45.js"></script>

