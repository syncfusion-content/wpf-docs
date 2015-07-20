---
layout: post
title: Setting-the-FlowDirection-for-GroupBar
description: setting the flowdirection for groupbar
platform: wpf
control: GroupBar
documentation: ug
---

# Setting the FlowDirection for GroupBar

Flow Direction of the GroupBar is set by using the FlowDirection property. 

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Description</td></tr>
<tr>
<td>
FlowDirection</td><td>
Sets the flow direction for the GroupBar control. The options provided are as follows.* LeftToRight* RightToLeft</td></tr>
</table>



Use the following code snippet to set this property.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar that has flow direction as left to right --&gt;&lt;syncfusion:GroupBar Height="300" Width="230" Name="groupBar" FlowDirection="RightToLeft"&gt;&lt;!-- Adding GroupBarItem --&gt;&lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;  &lt;!-- Adding content for GroupBar item using GroupView --&gt;  &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;    &lt;syncfusion:GroupViewItem Text="List View"/&gt;    &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;    &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;  &lt;/syncfusion:GroupView&gt;&lt;/syncfusion:GroupBarItem&gt;&lt;!-- Adding GroupBarItem --&gt;&lt;syncfusion:GroupBarItem HeaderImageSource="Tasks.png" Name="groupBarItem2" Header="Visual Mode"&gt;  &lt;!-- Adding content for GroupBar item using GroupView --&gt;  &lt;syncfusion:GroupView&gt;    &lt;syncfusion:GroupViewItem Text="Default"/&gt;    &lt;syncfusion:GroupViewItem Text="Multiple Expansion"/&gt;    &lt;syncfusion:GroupViewItem Text="StackMode"/&gt;  &lt;/syncfusion:GroupView&gt;&lt;/syncfusion:GroupBarItem&gt;&lt;!-- Adding GroupBarItem --&gt;&lt;syncfusion:GroupBarItem HeaderImageSource="Notes.png" Name="groupBarItem3" Header="State Persistence"&gt;  &lt;!-- Adding content for GroupBar item using GroupView --&gt;  &lt;syncfusion:GroupView&gt;    &lt;syncfusion:GroupViewItem Text="Save State"/&gt;    &lt;syncfusion:GroupViewItem Text="Load State"/&gt;    &lt;syncfusion:GroupViewItem Text="Reset State"/&gt;  &lt;/syncfusion:GroupView&gt;&lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]// Setting flow direction as RightToLeftgroupBar.FlowDirection = FlowDirection.RightToLeft;  </td></tr>
</table>


