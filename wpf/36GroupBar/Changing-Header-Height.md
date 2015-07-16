---
layout: post
title: Changing-Header-Height
description: changing header height
platform: wpf
control: GroupBar
documentation: ug
---

# Changing Header Height

Header Height of the GroupBar Item

The height of the each GroupBar item header is set using the ItemHeaderHeight property. This dependency property sets the height for each groupbar items header.

Use the below code to set this property.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar --&gt;&lt;syncfusion:GroupBar Height="200" Width="230" ItemHeaderHeight="50" Name="groupBar"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem" IsSelected="True"&gt;    &lt;!-- Adding content for GroupBar item using panel --&gt;    &lt;StackPanel Orientation="Vertical"&gt;      &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;      <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton Margin="4,2,2,2">Vertical</RadioButton>      &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;      <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>    &lt;/StackPanel&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//Set the height of GroupBar item headergroupBar.ItemHeaderHeight = 50; </td></tr>
</table>




Height of the Container that hosts the Selected Header 

HeaderHeight is a dependency property, which gets or sets the height of the topmost container that hosts the selected header.

Use the below code snippet to set this property.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar --&gt;&lt;syncfusion:GroupBar Height="200" HeaderHeight="20" Width="230" VisualMode="StackMode" Name="groupBar"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem" IsSelected="True"&gt;    &lt;!-- Adding content for GroupBar item using panel --&gt;    &lt;StackPanel Orientation="Vertical"&gt;      &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;      <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton Margin="4,2,2,2">Vertical</RadioButton>      &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;      <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>    &lt;/StackPanel&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]groupBar.HeaderHeight = 20; </td></tr>
</table>


