---
layout: post
title:  "Retrieve all site collection owners using the CLI for Microsoft 365"
author: plamber
categories: [ Development, PowerShell, SharePoint, CLI ]
tags: [SharePoint, Office 365, Microsoft 365, CLI]
---
The [CLI for Microsoft 365](https://github.com/pnp/cli-microsoft365) is a solution provided by the PnP team. It allows you to manage your Microsoft 365 tenant trying to cover multiple services (e.g. SharePoint, Teams, Microsoft 365 Groups, Flow, Planner, etc.) and giving you a single experience when automating tasks in your environment. The CLI is running on every device compatible with Node, Therefore, you could consider it for any type of scripts running on almost any device or CI/CD pipelines.

This sample shows how to list all site collection owners using the CLI. It assumes that you run the script with a user having enough priviledges to read this information. 

<script src="https://gist.github.com/plamber/6e327e9260853d2d816fe355da27cf2d.js"></script>

