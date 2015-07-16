---
layout: post
title: Disable-Drag-and-Drop-of-TDI-items
description: disable drag and drop of tdi items  
platform: wpf
control: DockingManager
documentation: ug
---

### Disable Drag and Drop of TDI items  

IsTDIDragDropEnabled property is used to disable the drag and drop of TDI items in DockingManager. The usage is follows: 



<table>
<tr>
<td>
[XAML]<syncfusion:DockingManager Name="DockingManager" ContainerMode="TDI"IsTDIDragDropEnabled="False">   &lt;Grid Name="grid1" syncfusion:DockingManager.State="Document"/&gt;   &lt;Grid Name="grid2" syncfusion:DockingManager.State="Document"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.IsTDIDragDropEnabled = false;</td></tr>
</table>


