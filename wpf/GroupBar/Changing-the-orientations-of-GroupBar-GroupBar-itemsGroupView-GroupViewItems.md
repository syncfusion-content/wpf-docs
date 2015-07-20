---
layout: post
title: Changing-the-orientations-of-GroupBar-GroupBar-itemsGroupView-GroupViewItems
description: changing the orientations of groupbar, groupbar items,groupview, groupviewitems
platform: wpf
control: GroupBar
documentation: ug
---

# Changing the orientations of GroupBar, GroupBar items,GroupView, GroupViewItems

You can change the layout of the entire GroupBar. GroupBar control has the Orientation property, which lets you place the contents of GroupBar either vertically or horizontally. It provides the following options.

* Horizontal: the contents of the GroupBar Item in the GroupBar control are placed horizontally.
* Vertical: the contents of the GroupBar Item in GroupBar control are placed vertically.

Use the following code snippet to set GroupBar Orientation to Horizontal.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar --&gt;&lt;syncfusion:GroupBar Height="300" Width="230" Orientation="Horizontal" Name="groupBar"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1" Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem2" Header="Visual Mode"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView&gt;      &lt;syncfusion:GroupViewItem Text="Default"/&gt;      &lt;syncfusion:GroupViewItem Text="Multiple Expansion"/&gt;      &lt;syncfusion:GroupViewItem Text="StackMode"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem4" Header="Orientation"&gt;    &lt;!-- Adding content for GroupBar item using panel --&gt;    &lt;StackPanel Orientation="Vertical"&gt;      &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;      <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton Margin="4,2,2,2">Vertical</RadioButton>      &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;      <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>    &lt;/StackPanel&gt;  &lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//Setting orientation as horizontalgroupBar.Orientation = Orientation.Horizontal;</td></tr>
</table>


{ ![](Changing-the-orientations-of-GroupBar-GroupBar-itemsGroupView-GroupViewItems_images/Changing-the-orientations-of-GroupBar-GroupBar-itemsGroupView-GroupViewItems_img1.jpeg) | markdownify }
{:.image }


Use the following code snippet to set groupbar Orientation to Vertical.



[C#]



//Setting orientation as vertical

groupBar.Orientation = Orientation.Vertical;





{ ![](Changing-the-orientations-of-GroupBar-GroupBar-itemsGroupView-GroupViewItems_images/Changing-the-orientations-of-GroupBar-GroupBar-itemsGroupView-GroupViewItems_img2.jpeg) | markdownify }
{:.image }




You can also change the orientation of the GroupView alone by using the Orientation property for GroupView. There are two types of orientation in GroupView control as in GroupBar.

* Horizontal
* Vertical



Use the following code snippet to set GroupView Orientation to Horizontal.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar --&gt;&lt;syncfusion:GroupBar Height="300" Width="230" Name="groupBar"&gt;&lt;!-- Adding GroupBarItem --&gt;&lt;syncfusion:GroupBarItem Name="groupBarItem1" Header="General"&gt;  &lt;!-- Adding content for GroupBar item using GroupView --&gt;  &lt;syncfusion:GroupView Name="groupView" Orientation="Horizontal"&gt;    &lt;syncfusion:GroupViewItem Text="List View"/&gt;    &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;    &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;  &lt;/syncfusion:GroupView&gt;&lt;/syncfusion:GroupBarItem&gt;&lt;!-- Adding GroupBarItem --&gt;&lt;syncfusion:GroupBarItem Name="groupBarItem2" Header="Visual Mode"&gt;  &lt;!-- Adding content for GroupBar item using GroupView --&gt;  &lt;syncfusion:GroupView&gt;    &lt;syncfusion:GroupViewItem Text="Default"/&gt;    &lt;syncfusion:GroupViewItem Text="Multiple Expansion"/&gt;    &lt;syncfusion:GroupViewItem Text="StackMode"/&gt;  &lt;/syncfusion:GroupView&gt;&lt;/syncfusion:GroupBarItem&gt;&lt;!-- Adding GroupBarItem --&gt;&lt;syncfusion:GroupBarItem Name="groupBarItem4" Header="Orientation"&gt;  &lt;!-- Adding content for GroupBar item using panel --&gt;  &lt;StackPanel Orientation="Vertical"&gt;    &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;    <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>    <RadioButton Margin="4,2,2,2">Vertical</RadioButton>    &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;    <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>    <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>  &lt;/StackPanel&gt;&lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//Setting the orientation of GroupView as HorizontalgroupView.Orientation = Orientation.Horizontal;</td></tr>
</table>




{ ![](Changing-the-orientations-of-GroupBar-GroupBar-itemsGroupView-GroupViewItems_images/Changing-the-orientations-of-GroupBar-GroupBar-itemsGroupView-GroupViewItems_img3.jpeg) | markdownify }
{:.image }


Use the following code snippet to set groupview Orientation to Vertical.



[C#]

//Setting the orientation of GroupView as Horizontal

groupView.Orientation = Orientation.Vertical;



{ ![](Changing-the-orientations-of-GroupBar-GroupBar-itemsGroupView-GroupViewItems_images/Changing-the-orientations-of-GroupBar-GroupBar-itemsGroupView-GroupViewItems_img4.jpeg) | markdownify }
{:.image }




Events to Handle Orientation of Groupbar

The events corresponding to this property are OrientationChanged and OrientationChanging.           

OrientationChanged Event

This event is called when the orientation of groupbar is changed and is triggered when the Orientation property is changed.

OrientationChanging Event

This event is called when orientation of groupbar is changing and is triggered when the Orientation property is changing.

