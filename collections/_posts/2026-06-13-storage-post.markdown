---
layout: post
title: "Technical debt has caught up to me again (storage)"
date: 2026-06-13 01:35:00 +0000
categories: cloud
permalink: /technicaldebtonooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo
emoji: 🖤
mathjax: false
---

I got an email from Microsoft recently that I just loved, I just loved so much 😂 (not really but I pinned it): "Retirement notice: Migrate your legacy Azure general-purpose v1 account to a general-purpose v2 account" which links [Overview of legacy blob storage account retirement](https://learn.microsoft.com/en-us/azure/storage/common/legacy-blob-storage-account-migration-overview). Microsoft, you should title this something less general. Since I will be at the Azure Portal anyway, while I am there, I will try to tackle reducing my storage bill by changing my virtual hard disk too.

> Your decision not to migrate an existing legacy blob storage account will be construed as consent for Microsoft to migrate the account on your behalf. - Microsoft

Philosophically, if I do not do something by a certain time, is that necessarily a decision? What if I had a lot going on in my life and my technical skills were too weak? (Putting my web server on the cloud VM reminds me of when I took student loans.) But I have to admit Microsoft has summarized what to do for this in that linked-to documentation nicely. I'm not sure how much migrating a legacy storage account is coupled to specific resources like the hard disk I want to retire (it may be possible to do this with no change to it) but since this involves doing inventory of your storage resources and the new storage accounts have new pricing calculators, and I want to tackle the problem of copying data from this hard disk to a smaller one to be able to detach the 64 GB one anyway (this was a problem I said I would tackle in one of my previous blog posts... about 5 months ago 😇). The deadline is October 13, 2026, so I will take my time this week and try to learn something, too.
