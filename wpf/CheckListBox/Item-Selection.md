---
layout: post
title: Item-Selection
description: item selection
platform: wpf
control: CheckListBox
documentation: ug
---

# Item Selection

When the IsCheckOnFirstClick property is set to True, you can select an item, on the first mouse-click. The default value is True.

Here is the code for setting this property.

<table>
<tr>
<td>
[XAML]<!-- Adding CheckListBox --><syncfusion:CheckListBox Name="checkListBox" IsCheckOnFirstClick="True">    <!-- Adding CheckListBox items -->    <syncfusion:CheckListBoxItem Content="Mexico"/>    <syncfusion:CheckListBoxItem Content="Canada" />    <syncfusion:CheckListBoxItem Content="Bermuda" />    <syncfusion:CheckListBoxItem Content="Belize" />    <syncfusion:CheckListBoxItem Content="Panama" /></syncfusion:CheckListBox></td></tr>
<tr>
<td>
[C#]// Enable the IsCheckOnFirstClick property.checkListBox.IsCheckOnFirstClick = true;  </td></tr>
</table>




{{ '![](Item-Selection_images/Item-Selection_img1.jpeg)' | markdownify }}
{:.image }


