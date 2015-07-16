---
layout: post
title: GroupBar-Items
description: groupbar items
platform: wpf
control: GroupBar
documentation: ug
---

# GroupBar Items

This topic illustrates the how to work with group-bar items.

## Status of the GroupBar Item

You can enable or disable the dragging of items using the DraggingItemInProgress property. This is a dependency property which gets or sets the value indicating whether the dragging of the items is in progress.

Use the below code snippet to set this property.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar --&gt;&lt;syncfusion:GroupBar Height="200" DraggingItemInProgress="True" Width="230" Name="groupBar"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem"&gt;    &lt;!-- Adding content for GroupBar item using panel --&gt;    &lt;StackPanel Orientation="Vertical"&gt;      &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;      <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton Margin="4,2,2,2">Vertical</RadioButton>      &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;      <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>    &lt;/StackPanel&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//Setting the items in progress while dragginggroupBar.DraggingItemInProgress = true; </td></tr>
</table>


See Also

Cursor Type for the GroupBar Item, Content Length of the GroupBar Item, Hidden GroupBar Item

## Cursor Type for the GroupBar Item

You can customize the cursor type of GroupBar item using the GroupBarItemCursorType property. This dependency property sets the type of cursor for the groupbar item. There are two types of built-in cursor types available for the GroupBar item. They are as follows.

* Default – default cursor type is displayed while moving the mouse over GroupBar item
* Hand – hand cursor type is displayed while moving the mouse over GroupBar item

Use the below code snippet to set this property.

<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar --&gt;&lt;syncfusion:GroupBar Height="200" GroupBarItemCursorType="Hand"  Width="230" Name="groupBar"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem"&gt;    &lt;!-- Adding content for GroupBar item using panel --&gt;    &lt;StackPanel Orientation="Vertical"&gt;      &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;      <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton Margin="4,2,2,2">Vertical</RadioButton>      &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;      <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>    &lt;/StackPanel&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;          &lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//Setting the cursor type for GroupBar itemgroupBar.GroupBarItemCursorType = ItemCursorType.Hand; </td></tr>
</table>


See Also

Status of the GroupBar Item, Content Length of the GroupBar Item, Hidden GroupBar Item

## Content Length of the GroupBar Item

You can also set the length of the content in GroupBar item. This is done using the ItemContentLength property. This dependency property sets the height or width available for the content of the selected item, i.e., it sets the height for the content, if GroupBar layout is _vertical_, and width for the content, if GroupBar layout is horizontal. 

Use the below code snippet to set this property.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar --&gt;&lt;syncfusion:GroupBar Height="200" Width="230" ItemContentLength="100" Name="groupBar"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem" IsSelected="True"&gt;    &lt;!-- Adding content for GroupBar item using panel --&gt;    &lt;StackPanel Orientation="Vertical"&gt;      &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;      <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton Margin="4,2,2,2">Vertical</RadioButton>      &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;      <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>    &lt;/StackPanel&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//Set the length of the contentgroupBar.ItemContentLength = 100;</td></tr>
</table>


See Also

Status of the GroupBar Item, Cursor Type for the GroupBar Item, Hidden GroupBar Item

## Hidden GroupBar Item

You can get the hidden GroupBar items and do some operation depending upon the visibility by using the property HiddenItemsCount. This dependency property gets the number of GroupBar items that are hidden.

Use the below code to set this property.



[C#]



int count;



//Get the hidden GroupBar items

count=groupBar.HiddenItemsCount;



See Also

Status of the GroupBar Item, Cursor Type for the GroupBar Item, Content Length of the GroupBar Item

## Setting Corner Radius for the GroupBar Item

It is now possible to set the corner radius of GroupBar Items in the GroupBar by using the GroupBarItemCornerRadius property. This helps the user to specify the degree of roundness at the tip of the GroupBar. 

The following code examples illustrate how to set this property.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:GroupBarItem HeaderText="Mailbox" GroupBarItemCornerRadius="20" ShowInGroupBar="True"&gt;</td></tr>
<tr>
<td>
[C#]// Creating an instance of GroupBar.GroupBar groupBar = new GroupBar();// Creating an instance of GroupBar Item.GroupBarItem groupBarItem = new GroupBarItem();// Setting Header Text for GroupBar Item.groupBarItem.HeaderText = "Mailbox";// Setting Corner Radius For GroupBar Item.groupBarItem.GroupBarItemCornerRadius = new CornerRadius(20d);// Setting ShowInGroupBar propety for GroupBar Item.groupBarItem.ShowInGroupBar = true;// Adding GroupBar Item to GroupBar.groupBar.Items.Add(groupBarItem);</td></tr>
</table>


Run the code. The following output is displayed.



{ ![](GroupBar-Items_images/GroupBar-Items_img1.jpeg) | markdownify }
{:.image }




