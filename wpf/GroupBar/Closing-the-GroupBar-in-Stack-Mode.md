---
layout: post
title: Closing-the-GroupBar-in-Stack-Mode
description: closing the groupbar in stack mode
platform: wpf
control: GroupBar
documentation: ug
---

# Closing the GroupBar in Stack Mode

You can close the GroupBar in stack mode by enabling the close button. This is done by using the IsCloseButtonEnabled property. This dependency property sets the value indicating whether the close button is visible on the header of the item in stack mode when IsToolBarEnabled property is set to _false_. That is close button is visible only if toolbar is disabled. This property can work only in stack mode.

Use the below code snippet to set this property. 



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar --&gt;&lt;syncfusion:GroupBar Height="200" Width="230" IsCloseButtonEnabled="True" 	IsToolBarEnabled="False" VisualMode="StackMode" Name="groupBar"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem" IsSelected="True"&gt;    &lt;!-- Adding content for groupbar item using panel --&gt;    &lt;StackPanel Orientation="Vertical"&gt;      &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;      <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton Margin="4,2,2,2"  >Vertical</RadioButton>      &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;      <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>    &lt;/StackPanel&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//Setting the visual mode as stack modegroupBar.VisualMode = VisualMode.StackMode;//Enabling the close buttongroupBar.IsCloseButtonEnabled = true;//Disabling the toolbargroupBar.IsToolBarEnabled = false;</td></tr>
</table>


