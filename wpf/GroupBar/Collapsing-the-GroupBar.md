---
layout: post
title: Collapsing-the-GroupBar
description: collapsing the groupbar
platform: wpf
control: GroupBar
documentation: ug
---

# Collapsing the GroupBar

Enabling this property allows the GroupBar to be collapsed when clicked. The GroupBar will collapse similar to the collapsing action in Microsoft office Outlook. AllowCollapse property is used to enable or disable the collapse button of the GroupBar.

By clicking the Navigation pane, the content of the GroupBar Items are displayed. You can resize the pop-up and also add or remove the GroupBar Item from the Toolbar using the StackItem host pop-up menu.

To enable the AllowCollapse property in GroupBar, use the following code.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar that has allow collapse property to true --&gt;&lt;syncfusion:GroupBar Height="300" Width="230" Name="groupBar" AllowCollapse="True" VisualMode="StackMode"&gt;    &lt;!-- Adding GroupBarItem --&gt;    &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;      &lt;!-- Adding content for GroupBar item using GroupView --&gt;      &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;        &lt;syncfusion:GroupViewItem Text="List View"/&gt;        &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;        &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;      &lt;/syncfusion:GroupView&gt;    &lt;/syncfusion:GroupBarItem&gt;    &lt;!-- Adding GroupBarItem --&gt;    &lt;syncfusion:GroupBarItem HeaderImageSource="Tasks.png" Name="groupBarItem2" Header="Visual Mode"&gt;      &lt;!-- Adding content for GroupBar item using GroupView --&gt;      &lt;syncfusion:GroupView&gt;        &lt;syncfusion:GroupViewItem Text="Default"/&gt;        &lt;syncfusion:GroupViewItem Text="Multiple Expansion"/&gt;        &lt;syncfusion:GroupViewItem Text="StackMode"/&gt;      &lt;/syncfusion:GroupView&gt;    &lt;/syncfusion:GroupBarItem&gt;    &lt;!-- Adding GroupBarItem --&gt;    &lt;syncfusion:GroupBarItem HeaderImageSource="Notes.png" Name="groupBarItem3" Header="State Persistence"&gt;      &lt;!-- Adding content for GroupBar item using GroupView --&gt;      &lt;syncfusion:GroupView&gt;        &lt;syncfusion:GroupViewItem Text="Save State"/&gt;        &lt;syncfusion:GroupViewItem Text="Load State"/&gt;        &lt;syncfusion:GroupViewItem Text="Reset State"/&gt;      &lt;/syncfusion:GroupView&gt;    &lt;/syncfusion:GroupBarItem&gt;  &lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]myGroupBar.AllowCollapse = true;</td></tr>
</table>




{ ![](Collapsing-the-GroupBar_images/Collapsing-the-GroupBar_img1.jpeg) | markdownify }
{:.image }




Events to handle with AllowCollapse

The event corresponding to this property is BeforeGroupBarItemPopupOpened. This event is triggered when AllowCollapse property gets changed.

> _Note: AllowCollapse property settings works only for GroupBar in StackMode._

Collapsing the GroupBar in Stack Mode

Collapsing and expanding the GroupBar in stackmode is done by using IsCollapsed property. This dependency property indicates the state of GroupBar, whether collapsed or expanded. By setting this property to _true_, groupbar is collapsed. By setting _false_, groupbar is expanded. 

Use the below code snippet to set this property.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar --&gt;&lt;syncfusion:GroupBar Height="200" Width="230" IsCollapsed="True" AllowCollapse="True" VisualMode="StackMode" Name="groupBar"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem" IsSelected="True"&gt;    &lt;!-- Adding content for GroupBar item using panel --&gt;    &lt;StackPanel Orientation="Vertical"&gt;      &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;      <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton Margin="4,2,2,2">Vertical</RadioButton>      &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;      <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>    &lt;/StackPanel&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//Set the visual mode as stack modegroupBar.VisualMode = VisualMode.StackMode;//Collapsing the GroupBar in stack modegroupBar.IsCollapsed = true;</td></tr>
</table>


See Also

Width of the Collapsed GroupBar

