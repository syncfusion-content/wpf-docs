---
layout: post
title: Hide-the-TDI-header-on-a-child
description: hide the tdi header on a child
platform: wpf
control: DockingManager
documentation: ug
---

### Hide the TDI header on a child

This property is used to hide the header of a TDI document when the DocumentTabControl has a TDI child.



<table>
<tr>
<td>
[XAML]<syncfusion:DockingManager Name="DockingManager"HideTDIHeaderOnSingleChild="True" UseDocumentContainer="True"><Grid Name="grid1" syncfusion:DockingManager.State="Document">   <TextBlock Text="Tab Content"/></Grid></syncfusion:DockingManager></td></tr>
<tr>
<td>
[C#]DockingManager.HideTDIHeaderOnSingleChild = true;</td></tr>
</table>


{{ '![C:/Users/Hemanth/Desktop/Documentation/Images/HideHeader.jpg](Hide-the-TDI-header-on-a-child_images/Hide-the-TDI-header-on-a-child_img1.jpeg)' | markdownify }}



