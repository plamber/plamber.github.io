---
layout: post
title:  "Change the Teams client display language"
author: plamber
categories: [ Development, Teams ]
tags: [PowerShell, Teams, Office 365, Microsoft 365]
featured: false
---
I had to change the Teams client display language on my Windows machine using PowerShell.
![](../assets/images/2020-10-22-14-39-20.png)

You can perform the operation by manipulating the desktop-config.json file located on a users profile.
I finally wrote a script that performs following steps:
- Close the Teams client
- Remove two files in your %AppData% folder
- Get the Teams client settings stored in your %AppData% and manipulate the "currentWebLanguage" property
- Overwrite the Teams client settings

Start the Teams client and your interface will immediately use the new language.

The script is listed below.

<script src="https://gist.github.com/plamber/c78f88d7a656268dc6305e98c3aeaf0e.js"></script>