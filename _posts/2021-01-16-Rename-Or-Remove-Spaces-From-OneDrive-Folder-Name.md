---
layout: post
title:  "How to rename or remove spaces from OneDrive folder name?"
author: plamber
categories: [ Development, PowerShell, OneDrive ]
tags: [OneDrive, Office 365, Microsoft 365]
featured: true
---
The OneDrive for Business folder naming convention is `OneDrive - {CompanyName}`. Most applications can cope with this naming when storing data on a local drive. 

Unfortunately, there are applications not able to handle spaces or special characters in a local path. I had several occasions where I had to provide a solution to such types of applications.

> Jon Gallant provided an elegant solution to tackle the OneDrive folder renaming problem [here](https://blog.jongallant.com/2020/01/onedrive-rename-remove-spaces-from-folder-name/). I took his idea and created a script that you can run on a user's machine. 

With this script you are going to create a subfolder on the user's OneDrive and a symbolic link pointing to this folder on the user profile directory. In this way you can create folders for each application requiring this exception without providing a direct access to the whole OneDrive for Business folder.

<script src="https://gist.github.com/plamber/6f3b381c7472294910dd713aaec085b2.js"></script>

You can save the code above as a `.bat` file. Then you just have to run it using this syntax `yourbatfilename.bat yourDesiredFolder`.

