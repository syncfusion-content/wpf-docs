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
[XAML]&lt;!-- Adding CheckListBox --&gt;&lt;syncfusion:CheckListBox Name="checkListBox" IsCheckOnFirstClick="True"&gt;    &lt;!-- Adding CheckListBox items --&gt;    &lt;syncfusion:CheckListBoxItem Content="Mexico"/&gt;    &lt;syncfusion:CheckListBoxItem Content="Canada" /&gt;    &lt;syncfusion:CheckListBoxItem Content="Bermuda" /&gt;    &lt;syncfusion:CheckListBoxItem Content="Belize" /&gt;    &lt;syncfusion:CheckListBoxItem Content="Panama" /&gt;&lt;/syncfusion:CheckListBox&gt;</td></tr>
<tr>
<td>
[C#]// Enable the IsCheckOnFirstClick property.checkListBox.IsCheckOnFirstClick = true;  </td></tr>
</table>




{ ![](Item-Selection_images/Item-Selection_img1.jpeg) | markdownify }
{:.image }


