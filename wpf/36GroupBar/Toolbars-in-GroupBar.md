---
layout: post
title: Toolbars-in-GroupBar
description: toolbars in groupbar
platform: wpf
control: GroupBar
documentation: ug
---

# Toolbars in GroupBar

We can hide the toolbar that is displayed in the GroupBar using the IsToolBarEnabled property. This dependency property sets the value indicating whether to hide the toolbar and items in stacked mode. It returns the bool value that indicates the state of toolbar that is hidden or visible. This property works only in stacked mode. 

The following code snippet will help you to set this property.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar --&gt;&lt;syncfusion:GroupBar Height="200" Width="230" IsToolBarEnabled="True" VisualMode="StackMode" Name="groupBar"&gt;&lt;!-- Adding GroupBarItem --&gt;&lt;syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem" IsSelected="True"&gt;  &lt;!-- Adding content for GroupBar item using panel --&gt;  &lt;StackPanel Orientation="Vertical"&gt;    &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;    <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>    <RadioButton Margin="4,2,2,2">Vertical</RadioButton>    &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;    <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>    <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>  &lt;/StackPanel&gt;&lt;/syncfusion:GroupBarItem&gt;&lt;!-- Adding GroupBarItem --&gt;&lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;  &lt;!-- Adding content for GroupBar item using GroupView --&gt;  &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;    &lt;syncfusion:GroupViewItem Text="List View"/&gt;    &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;    &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;  &lt;/syncfusion:GroupView&gt;&lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//Enable the ToolBargroupBar.IsToolBarEnabled = true;</td></tr>
</table>


