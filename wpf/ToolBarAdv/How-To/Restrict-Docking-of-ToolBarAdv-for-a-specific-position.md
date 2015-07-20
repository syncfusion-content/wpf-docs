---
layout: post
title: Restrict-Docking-of-ToolBarAdv-for-a-specific-position
description: restrict docking of toolbaradv for a specific position
platform: wpf
control: ToolBarAdv
documentation: ug
---

### Restrict Docking of ToolBarAdv for a specific position

You can restrict docking of ToolBarAdv by setting the following properties. Each will restrict docking at corresponding positions in ToolBarManager.

* CanDockAtLeft—restricts docking at the left.
* CanDockAtTop—restricts docking at the left.
* CanDockAtRight—restricts docking at the left.
* CanDockAtBottom—restricts docking at the left.



Following code restricts docking at the top:



[XAML]

<shared:ToolBarManager x:Name="toolBarManager" CanDockAtTop="False"

                               >&lt;/shared:ToolBarManager&gt;





[C#]

ToolBarManager toolBarManager = new ToolBarManager();

            toolBarManager.CanDockAtTop = false;



                * 
