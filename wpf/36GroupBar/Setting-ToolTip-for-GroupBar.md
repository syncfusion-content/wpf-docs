---
layout: post
title: Setting-ToolTip-for-GroupBar
description: setting tooltip for groupbar
platform: wpf
control: GroupBar
documentation: ug
---

# Setting ToolTip for GroupBar

ToolTip is one of the important user interactive feature available in GroupBar control. You can set the tooltip for the collapse button and expand button using the properties listed below.

_Property table_

<table>
<tr>
<td>
Property</td><td>
Description</td></tr>
<tr>
<td>
CollapseButtonToolTip</td><td>
Gets or sets the tooltip to be displayed when mouse is hovered over the collapse button.</td></tr>
<tr>
<td>
ExpandButtonToolTip</td><td>
Gets or sets the tooltip to be displayed when mouse is hovered over the expand button.</td></tr>
</table>


Use the below code snippet to set this property.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar --&gt;&lt;syncfusion:GroupBar Height="200" CollapseButtonToolTip="Expand"  VisualMode="StackMode" AllowCollapse="True"  ExpandButtonToolTip="Collapse" Width="230" Name="groupBar"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem"&gt;    &lt;!-- Adding content for GroupBar item using panel --&gt;    &lt;StackPanel Orientation="Vertical"&gt;      &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;      <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton Margin="4,2,2,2">Vertical</RadioButton>      &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;      <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>    &lt;/StackPanel&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//Setting the visual mode as StackModegroupBar.VisualMode = VisualMode.StackMode;  //Setting AllowCollapse propertygroupBar.AllowCollapse = true;//Setting the tooltip for Expand buttongroupBar.ExpandButtonToolTip = "Collapse";//Setting the tooltip for Collapse buttongroupBar.CollapseButtonToolTip = "Expand";</td></tr>
</table>


