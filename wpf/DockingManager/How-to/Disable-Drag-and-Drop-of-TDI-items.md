---
layout: post
title: Disable-Drag-and-Drop-of-TDI-items
description: disable drag and drop of tdi items  
platform: wpf
control: DockingManager
documentation: ug
---

## Disable Drag and Drop of TDI items  

IsTDIDragDropEnabled property is used to disable the drag and drop of TDI items in DockingManager. The usage is follows: 


{% highlight html %}
<syncfusion:DockingManager Name="DockingManager" ContainerMode="TDI"IsTDIDragDropEnabled="False">   <Grid Name="grid1" syncfusion:DockingManager.State="Document"/>   <Grid Name="grid2" syncfusion:DockingManager.State="Document"/></syncfusion:DockingManager>

DockingManager.IsTDIDragDropEnabled = false;


{% endhighlight  %}