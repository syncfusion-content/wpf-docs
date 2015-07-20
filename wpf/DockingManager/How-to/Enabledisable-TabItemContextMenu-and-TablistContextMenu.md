---
layout: post
title: Enabledisable-TabItemContextMenu-and-TablistContextMenu
description: enable/disable tabitemcontextmenu and tablistcontextmenu
platform: wpf
control: DockingManager
documentation: ug
---

### Enable/disable TabItemContextMenu and TablistContextMenu

ShowTabItemContextMenu is the property that is used to disable the showing of Context Menu when right-clicked on the document tab. Simlarly, ShowTabListContextMenu is used to disable the showing of Context Menu list when clicked on the tabcontrol menu toggle button. The usages are given below:



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager" ShowTabItemContextMenu="False" ShowTabListContextMenu="False" UseDocumentContainer="True" ContainerMode="TDI"&gt;        &lt;Grid Name="grid1" syncfusion:DockingManager.State="Document"/&gt;        &lt;Grid Name="grid2" syncfusion:DockingManager.State="Document"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]//Disables the tabitem context menu.DockingManager.ShowTabItemContextMenu = false;//Disables the tablist context menu.DockingManager.ShowTabListContextMenu = false;</td></tr>
</table>


