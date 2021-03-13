---
layout: post
title:  "How do I map OneDrive with another drive?"
author: plamber
categories: [ Development, PowerShell, OneDrive ]
tags: [OneDrive, Office 365, Microsoft 365]
featured: false
---
The OneDrive for Business folder naming convention is `OneDrive - {CompanyName}`. Most applications can cope with this naming when storing data on a local drive. In a [previous blogpost](/Rename-Or-Remove-Spaces-From-OneDrive-Folder-Name) I showed how you can map a symlink path to an OneDrive folder to fool incompatible applications to write to your OneDrive.

I came across another use case where we had to ensure that a specific drive letter is mapped to an OneDrive folder. I came across this solution where you can map a drive letter with a folder.

<script src="https://gist.github.com/plamber/18c0f6c74917eecb01491e42efd489fb.js"></script>

This script takes two parameters. One is the folder name you want to create on your OneDrive. The second parameter is the drive name which will be mapped to that folder.

Please note that mapping the drive is not permanent. If you want to have this applied on every restart you have to ensure that you run subst to run on startup. You should consider creating an entry under *HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run* with your command. You can find more information [here](https://www.raymond.cc/blog/map-folder-or-directory-to-drive-letter-for-quick-and-easy-access/#:~:text=Select%20the%20drive%20letter%20from%20the%20drop%20down,Subst%20during%20startup%20to%20assign%20the%20drive%20letters).

I came with this last version which is written in PowerShell and creates the necessary startup script to map the folder on each startup.

<script src="https://gist.github.com/plamber/4e074791ca569143210decbd3d4de686.js"></script>
