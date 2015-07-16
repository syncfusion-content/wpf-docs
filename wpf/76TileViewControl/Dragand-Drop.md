---
layout: post
title: Dragand-Drop
description: drag–and-drop
platform: wpf
control: TileView Control
documentation: ug
---

# Drag–and-Drop

Drag-and-Drop enables you to drag the TileViewItems in TileViewControl in a normal state. Once the TileViewItem is dragged, the other items in the TileViewControl moves to the corresponding positions in accordance to the dragging item. This can be enabled and disabled by using the AllowItemsRepositioning property.

Adding Dragging Items to an Application 

The Dragging items can be added to an application by using either XAML or C# code.

Adding through XAML

The following code example illustrates how to add the Dragging Items to an application through XAML.



[XAML]



<syncfusion:TileViewControl Name="tileViewCntrl" 

                            AllowItemRepositioning="True"/>





Adding through C#

The following code example illustrates how to add the Dragging Items to an application through C#.



[C#]



tileViewCntrl.AllowItemRepositioning = true;   





Properties

_MinimizedItemTemplate / MaximizedItemTemplate Properties Table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td><td>
Reference links </td></tr>
<tr>
<td>
AllowItemRepositioning</td><td>
Enables or disables the TileViewItems from dragging.</td><td>
DependencyProperty</td><td>
True</td><td>
</td></tr>
</table>


Events

_AllowItemRepositioningChanged Table_

<table>
<tr>
<th>
Event </th><th>
Description </th><th>
Arguments </th><th>
Type </th><th>
Reference links </th></tr>
<tr>
<th>
AllowItemRepositioningChanged</th><th>
The event gets fired when the dragging items feature is enabled or disabled.</th><th>
</th><th>
</th><th>
</th></tr>
</table>


Sample Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio XX.X.X.XX -> Dashboard.
2. Select Run Locally Installed Samples in WPF Button.
3. Now expand the DragAndDropManagerDemo tree-view item in the Sample Browser.
4. Choose any one of the samples listed under it to launch. 



