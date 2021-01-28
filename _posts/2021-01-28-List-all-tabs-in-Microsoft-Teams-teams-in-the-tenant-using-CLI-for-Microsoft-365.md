---
layout: post
title:  "List all tabs in Microsoft Teams teams in the tenant using CLI for Microsoft 365"
author: plamber
categories: [ Development, PowerShell, Teams, CLI ]
tags: [Teams, Office 365, Microsoft 365, CLI]
---
The [CLI for Microsoft 365](https://github.com/pnp/cli-microsoft365) is a solution provided by the PnP team. It allows you to manage your Microsoft 365 tenant trying to cover multiple services (e.g. SharePoint, Teams, Microsoft 365 Groups, Flow, Planner, etc.) and giving you a single experience when automating tasks in your environment. The CLI is running on every device compatible with Node, Therefore, you could consider it for any type of scripts running on almost any device or CI/CD pipelines.

This sample script shows you how to list all tabs, channels, and team information from your tenant. The inspiration was taken from the blog post written by [Veronique Lengelle](https://veronicageek.com/powershell/powershell-for-m365/get-teams-channels-tabs-and-privacy-settings-using-teams-pnp-powershell/2020/07/) using PnP PowerShell.

<script src="https://gist.github.com/plamber/783d91bee2877afad13f2cc0abc9ed70.js"></script>

