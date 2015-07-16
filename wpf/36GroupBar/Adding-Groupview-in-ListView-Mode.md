---
layout: post
title: Adding-Groupview-in-ListView-Mode
description: adding groupview in listview mode
platform: wpf
control: GroupBar
documentation: ug
---

# Adding Groupview in ListView Mode

You can arrange GroupView Items in list view mode by using the IsListViewMode property. This property is used to enable or disable the layout of items in a GroupView in the ListView mode.

You can arrange GroupView items in list view mode using the following code.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar that have visual mode is Multiple Expansion --&gt;&lt;syncfusion:GroupBar Height="300" Width="230" Name="groupBar"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1"  Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]groupview.IsListViewMode = true;</td></tr>
</table>


See Also

GroupView Orientation in Orientation topic.

