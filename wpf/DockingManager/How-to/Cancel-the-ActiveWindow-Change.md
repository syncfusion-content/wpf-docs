---
layout: post
title: Cancel-the-ActiveWindow-Change
description: cancel the activewindow change
platform: wpf
control: DockingManager
documentation: ug
---

### Cancel the ActiveWindow Change

ActiveWindowChanging event is used to cancel the ActiveWindow change. This event will be triggered before the new window is set as activewindow, the usage is shown below.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager UseDocumentContainer="True"     ActiveWindowChanging="DockingManager_ActiveWindowChanging"&gt;            &lt;Grid Name="grid1" syncfusion:DockingManager.Header="grid1" syncfusion:DockingManager.State="Document"/&gt;            &lt;Grid Name="grid2" syncfusion:DockingManager.Header="grid2" syncfusion:DockingManager.State="Document"/&gt;            &lt;Grid Name="grid3" syncfusion:DockingManager.Header="grid3" syncfusion:DockingManager.State="Document"/&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]private void DockingManager_ActiveWindowChanging(FrameworkElement sender, Syncfusion.Windows.Tools.Controls.ActiveWindowChangingEventArgs e){     if (sender.Name == "grid1")     {         e.Cancel = true;     }}</td></tr>
</table>


