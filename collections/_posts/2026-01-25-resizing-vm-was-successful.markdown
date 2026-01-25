---
layout: post
title: "Resizing the VM thoughts"
date: 2026-01-25 06:50:00 -0800
categories: cloud
permalink: /technicaldebtonoooo3
emoji: 🖤
mathjax: false
---

I saw the 4 Gb VM had over 3 Gb free after the work of my last post and some additional work editing the paths of the disabled projects to project_name_DISABLED, ensuring processes wouldn't start for them even if the `systemd` service tried to when the VM restarted for example. Though I haven't checked on the PostgreSQL cluster yet, it seemed like there should have been enough memory so I proceeded with resizing the VM.

After resizing, I saw an interesting change in the available memory bytes. There was a drastic, linear decrease for a while, after which it continued to decrease somewhat at a slower rate and overnight stabilized at around ~340 MiB free. I am not exactly sure about the drastic linear decrease in the graph. Linux boots and looks at how much total RAM it has available to use, decides how much memory it wants to use in the cache for everything, and builds that amount of cache memory. If the resize involves restarting the VM, the RAM of the 4 Gb machine is lost, and after reboot it builds the cache starting from 0. So it may be due to how the Azure service averages measurements in graphs or something? The later slower decrease and stabilization is probably the true memory change as the processes warm up. 

![Graph showing available memory bytes change due to resizing the VM, there's an initial drastic decrease after there has been a gentle decrease](assets\azure-graph-resizing-vm.png)

My experience with these 2 VM sizes (B-series v2 "B2pts_v2" with the same vCPUs (2), data disks (4), and max read/write speed (3750 IOPS) and either 1 Gb or 4 Gb of RAM) was that when the only app on the machine was Anki Books (Ruby on Rails), it could just barely run on the 1 Gb RAM machine. The Ruby jobs which create Anki deck package files would cause it to fall over, especially the job to `find_each` iterate and make every Anki deck package file. But sometimes the VM was falling over at random times without me starting those jobs. So with Anki Books and Passenger using memory ruled out now, this was more a test of if it could handle my 2 relatively simpler ASP.NET Core apps, and so far it looks good.