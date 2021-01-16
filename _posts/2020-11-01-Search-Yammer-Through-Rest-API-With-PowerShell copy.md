---
layout: post
title:  "Search in Yammer through the Yammer REST API with PowerShell"
author: plamber
categories: [ Development, PowerShell, Yammer ]
tags: [Yammer, Office 365, Microsoft 365]
featured: false
series: YammerRestApi
---
You can perform searches in Yammer as described [here](https://developer.yammer.com/docs/searchjson). The snippet below shows how you can perform a search. The search returns multiple objects:
- Messages
- Users
- Topics
- Uploaded files
- Users

> You can generate the baerer token (access token) as described in <a href="/Access-Yammer-API-Through-Rest">this</a> post. 

> Always consider the <a href="https://developer.yammer.com/docs/rest-api-rate-limits">REST API and Rate Limits</a> when accessing a Yammer network. 

<script src="https://gist.github.com/plamber/050680ed7496312b84880fdbee1362bf.js"></script>