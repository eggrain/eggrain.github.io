---
layout: post
title: "Orphan storage account"
date: 2026-06-16 01:35:00 +0000
categories: cloud
permalink: /orphan-storage-account
emoji: 🖤
mathjax: false
---

Following the documentation about migrating legacy storage accounts referenced in my last post, I used the Azure Resource Graph with the query provided in that documentation to identify one relevant resource, a storage account that was not appearing in my All Resources list.

Looking at the details of it, I couldn't see how it was being used in any way. I considered it may just be an orphan resource that was created at some point and now wasn't being used for anything or needed. I went ahead with deleting it, and was warned the dependent resources included 318 bytes of "Tables" data, however the resource details also had some text like "this resource has no tables yet" so I went ahead and deleted it.

![Modal shown when deleting the storage account](assets\screenshots\orphan-storage-account.png)

Unless this somehow has some bad side effect later, this issue Microsoft emailed me about was not much of an issue for me as I was only marginally affected. The copying over of data to a new smaller disk that has been on my mind for a while is also a completely separate issue.
