---
layout: post
title: Adjusting-the-GroupBar-width
description: adjusting the groupbar width
platform: wpf
control: GroupBar
documentation: ug
---

# Adjusting the GroupBar width

Set the width of the GroupBar while it is collapsed by using the CollapsedWidth property. This dependency property sets the width of the collapsed groupbar. 

Use the below code snippet to set this property.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar with  AllowCollapse property = true --&gt;&lt;syncfusion:GroupBar Height="300" Width="230" Name="groupBar" CollapsedWidth="100" AllowCollapse="True" VisualMode="StackMode"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem HeaderImageSource="Tasks.png" Name="groupBarItem2" Header="Visual Mode"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView&gt;      &lt;syncfusion:GroupViewItem Text="Default"/&gt;      &lt;syncfusion:GroupViewItem Text="Multiple Expansion"/&gt;      &lt;syncfusion:GroupViewItem Text="StackMode"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem HeaderImageSource="Notes.png" Name="groupBarItem3" Header="State Persistence"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView&gt;      &lt;syncfusion:GroupViewItem Text="Save State"/&gt;      &lt;syncfusion:GroupViewItem Text="Load State"/&gt;      &lt;syncfusion:GroupViewItem Text="Reset State"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt; </td></tr>
<tr>
<td>
[C#]//Enable AllowCollapse property for GroupBargroupBar.AllowCollapse = true;//Setting the width of Collapse buttongroupBar.CollapsedWidth = 100;</td></tr>
</table>


See Also

Collapsing the GroupBar

