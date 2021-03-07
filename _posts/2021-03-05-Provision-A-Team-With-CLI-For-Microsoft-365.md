---
layout: post
title:  "How do I provision a Team using the CLI for Microsoft 365?"
author: plamber
categories: [ Development, Microsoft 365, CLI ]
tags: [Teams, Microsoft 365, CLI]
---
The [CLI for Microsoft 365](https://github.com/pnp/cli-microsoft365) is a cross-platform command-line interface used to manage or automate Microsoft 365 resources. 

This sample script shows you how to provision a Microsoft 365 team by using the CLI for Microsoft 365. You can also create a Team by using a single command like [https://pnp.github.io/cli-microsoft365/cmd/teams/team/team-add/](m365 teams team add). On the other hand, it does not allow you to control the mailnickname property (which also controls the SharePoint URL in the backend). This example might also give you some inspiration how you can teamify and manipulate and existing Unified Group.

<script src="https://gist.github.com/plamber/2e1333bff2fcb1fa6a81545b4f9f09d1.js"></script>