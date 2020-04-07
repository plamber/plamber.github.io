---
layout: post
title:  "How do I install multiple Node versions on my Windows computer?"
author: plamber
categories: [ Development, SharePoint, Office 365 CLI ]
tags: [PowerShell, SharePoint, Office 365, Microsoft 365, Office 365 CLI]
featured: false
---
When working with Node.js you might encounter situations where you need multiple versions of Node.js on the same machine. In my case, I want to create [SPFx components for SharePoint Online](https://docs.microsoft.com/en-us/sharepoint/dev/spfx/set-up-your-development-environment) and on the same machine create components for the [Office 365 CLI](https://github.com/pnp/office365-cli).

Both solutions require different versions of Node.js. This adds the burden of manually installing or uninstalling Node versions and their global packages when switching projects. 

<div class="alert warning">
    At the time of writing SPFx runs on [Node.js v8.x and Node v10.x], while Office 365 CLI runs on [Node.js >= v12.0.0]. With Node.js v12 installed, I am not able to create SPFx components. 
</div>

Luckily, you can tackle this problem by using a project called Node Version Manager. 
- for Linux and macOS use [nwm](https://github.com/creationix/nvm). 
- for Windows use the [Node Version Manager (nwm) for Windows](https://github.com/coreybutler/nvm-windows).

### Install nvm for Windows
Before installing the latest package, ensure that you cleanup your environment first:
- Uninstall existing Node instances and remove existing installation directories
- Uninstall existing npm install location (e.g. "C:\Users\<user>\AppData\Roaming\npm")
- [Download](https://github.com/coreybutler/nvm/releases) the latest version of nvm for Windows and install it 

After installing nvm, I have to install the desired Node instances using a PowerShell command prompt <b>in an administrative context</b>. I need Node v10.19.0 for SPFx and Node v12.16.1 for Office 365 CLI. Therefore, I executing these commands.

```
# installs the node version 10.19.0
nvm install 10.19.0
nvm use 10.19.0
npm install -g yo gulp
npm install -g @microsoft/generator-sharepoint
gulp trust-dev-cert

# installs the node version 12.16.1
nvm install 12.16.1
nvm use 12.16.1
npm install -g gulp-cli
```

The commands above install the desired Node versions and the global utilities required by both Node versions.

### Using nvm for Windows
Adding multiple Node instances and switching between these is much easier with this approach.

The change of the current Node instance can be performed with the use command.

```
nvm use 12.16.1
```

Remember that the operations have to be executed in an administrative context.

