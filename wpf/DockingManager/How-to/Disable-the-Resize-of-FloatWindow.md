---
layout: post
title: Disable-the-Resize-of-FloatWindow
description: disable the resize of floatwindow
platform: wpf
control: DockingManager
documentation: ug
---

### Disable the Resize of FloatWindow

CanResizeInFloatState is the attached property which can be applied on float state child of DockingManager to disable the manual resize of FloatWindow.  If this property is set, the float window is no longer resizable. The usage is shown below.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager&gt;&lt;Grid x:Name="grid1" syncfusion:DockingManager.State="Float" syncfusion:DockingManager.CanResizeInFloatState="False"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetCanResizeInFloatState(grid1, false);</td></tr>
</table>


