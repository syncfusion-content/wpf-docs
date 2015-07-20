---
layout: post
title: Unpin-all-AutoHide-window
description: unpin all autohide window
platform: wpf
control: DockingManager
documentation: ug
---

### Unpin all AutoHide window

You can Unpin all AutoHidden windows by using the method UnPinAutoHide().This can be shown below:



<table>
<tr>
<td>
[XAML]  &lt;syncfusion:DockingManager Name="DockingManager"&gt;            &lt;Grid syncfusion:DockingManager.State="AutoHidden"/&gt;            &lt;Grid syncfusion:DockingManager.State="AutoHidden"/&gt;            &lt;Grid syncfusion:DockingManager.State="AutoHidden"/&gt;            &lt;Grid syncfusion:DockingManager.State="AutoHidden"/&gt;  &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager. UnPinAllAutoHide();  </td></tr>
</table>


