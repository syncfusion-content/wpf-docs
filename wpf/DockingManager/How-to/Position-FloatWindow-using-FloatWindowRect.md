---
layout: post
title: Position-FloatWindow-using-FloatWindowRect
description: position floatwindow using floatwindowrect
platform: wpf
control: DockingManager
documentation: ug
---

### Position FloatWindow using FloatWindowRect

FloatWindowRect is used to specify the Rect bounds for the float child that is displayed in FloatWindow.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager"&gt;&lt;Grid Name="grid1" syncfusion:DockingManager.State="Float" syncfusion:DockingManager.FloatingWindowRect="0,0,200,200"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetFloatingWindowRect(grid1, new Rect(0, 0, 200, 200));</td></tr>
</table>


