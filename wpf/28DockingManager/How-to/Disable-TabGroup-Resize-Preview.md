---
layout: post
title: Disable-TabGroup-Resize-Preview
description: disable tabgroup resize preview
platform: wpf
control: DockingManager
documentation: ug
---

### Disable TabGroup Resize Preview

TabGroup preview can be enabled or disabled by using the IsTabPreviewEnabled property. The default value of the TabGroup preview is true. The usage of this property is shown below.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="dockingmanager" IsTabPreviewEnabled="False" UseDocumentContainer="True"&gt;            &lt;Grid syncfusion:DockingManager.Header="tab1" syncfusion:DockingManager.State="Document"/&gt;            &lt;Grid syncfusion:DockingManager.Header="tab2" syncfusion:DockingManager.State="Document"/&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]dockingmanager.IsTabPreviewEnabled = false;</td></tr>
</table>


The above code disables the TabGroup preview, which is created by dragging and dropping the tabitems.

