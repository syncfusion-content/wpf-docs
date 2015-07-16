---
layout: post
title: Rotating-the-GroupBar
description: rotating the groupbar
platform: wpf
control: GroupBar
documentation: ug
---

# Rotating the GroupBar

You can rotate the GroupBar in any direction by setting a suitable angle to the RotationAngle property. This dependency property sets the angle of displaying GroupBar. It returns the angle of rotation used for displaying the GroupBar. The default value is _0_.

Use the below code snippet to set this property.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar --&gt;&lt;syncfusion:GroupBar Height="200" Width="230" RotationAngle="45" Name="groupBar"&gt;&lt;!-- Adding GroupBarItem --&gt;&lt;syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem"&gt;  &lt;!-- Adding content for groupbar item using panel --&gt;  &lt;StackPanel Orientation="Vertical"&gt;    &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;    <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>    <RadioButton Margin="4,2,2,2">Vertical</RadioButton>    &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;    <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>    <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>  &lt;/StackPanel&gt;&lt;/syncfusion:GroupBarItem&gt;&lt;!-- Adding GroupBarItem --&gt;&lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;  &lt;!-- Adding content for GroupBar item using GroupView --&gt;  &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;    &lt;syncfusion:GroupViewItem Text="List View"/&gt;    &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;    &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;  &lt;/syncfusion:GroupView&gt;&lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//Set the rotation anglegroupBar.RotationAngle = 45; </td></tr>
</table>


See Also

Rotating the Content in the GroupBar

