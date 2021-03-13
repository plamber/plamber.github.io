---
layout: post
title:  "How do I delete all my Microsoft 365 Groups and SharePoint Online sites in my development environment?"
author: plamber
categories: [ Development, PowerShell, SharePoint, Groups]
tags: [SharePoint, Office 365, Microsoft 365]
featured: false
---
The [CLI for Microsoft 365](https://github.com/pnp/cli-microsoft365) is a cross-platform command-line interface used to manage or automate Microsoft 365 resources. It is a PnP and community-driven initiative that is growing rapidly over time. 

I am actively working on our Microsoft 365 governance tool [EasyLife365](https://www.easylife365.cloud). We are creating thousands of Microsoft 365 Groups and SharePoint Online sites during development and testing. On some occasions, we want to clean up our environment and start fresh.

This sample script shows you how you can enumerate all Microsoft 365 Groups in your test tenant and delete these Groups. Afterward, it also processes all SPO sites and deletes them permanently. 

Please execute this script carefully. 

<script src="https://gist.github.com/plamber/eb504e417412f03e86e6f9b8269ac342.js"></script>