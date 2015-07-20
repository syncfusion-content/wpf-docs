---
layout: post
title: Creating-Tab-Groups
description: creating tab groups
platform: wpf
control: DocumentContainer
documentation: ug
---

# Creating Tab Groups

To create tab groups programmatically in DocumentContainer, two methods are used; they are 

CreateHorizontalTabGroup() and CreateVerticalTabGroup(). Their usages are given below.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DocumentContainer  Name="documentcontainer1" Mode="TDI"&gt;            &lt;Grid Name="grid1"/&gt;            &lt;Grid Name="grid2"/&gt;        &lt;/syncfusion:DocumentContainer&gt;</td></tr>
<tr>
<td>
[C#]//To create horizontal tab groupdocumentcontainer1.CreateHorizontalTabGroup(grid1);//To create vertical tab group  documentcontainer1.CreateVerticalTabGroup(grid1);</td></tr>
</table>


