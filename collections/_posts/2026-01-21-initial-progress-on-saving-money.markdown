---
layout: post
title: "Turning off 2 ASP.NET Core apps saved ~200-300 Mb of memory"
date: 2026-01-21 23:35:00 +0000
categories: cloud
permalink: /technicaldebtonoooo2
emoji: 🖤
mathjax: false
---

I finally got something working so links to my subdomains didn't go to the apps I am taking down today. Initially I tried to use DNS records, but with Namecheap to make the changes, and using Lets Encrypt digital certificates on the server, it wasn't possible to make it work for HTTPS (makes sense). Instead I accomplished it in an even better way with Apache redirecting to a post on my blog, by editing the virtual host .conf files.

Afterwards, I turned off the 2 ASP.NET Core apps, and checked the Azure portal metrics to see the available memory bytes increasing. Now I'm seeing it later and it looks like 200-300 Mb of memory was returned to the VM. I am happy my guess of 100-300 Mb per app process from the previous post was reasonable. For the graph below, imagine moving the bottom one up and to the right and connecting it on the left of the upper one.

![Graph showing available memory bytes increasing from about 2.9 Gb to 3.1 Gb](assets\azure-graph-after-turning-off-2-dotnetapps.png)