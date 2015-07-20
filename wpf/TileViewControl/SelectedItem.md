---
layout: post
title: SelectedItem
description: selecteditem
platform: wpf
control: TileView Control
documentation: ug
---

# SelectedItem

SelectedItem is a property in the TileViewControl that stores the currently selected TileViewItem in it and it is similar to SelectedItem property in ComboBox. This will help you to return the currently selected TileViewItem. Also it allows only one item to be selected at a time. 

Use Case Scenarios

This feature will be very useful who you want to get the SelectedItem.

Adding SelectedItem to an Application



[XAML]



<syncfusion:TileViewControl x:Name="TileView" Height="600" Width="800">

      <syncfusion:TileViewItem x:Name="Tile1" Header="TileViewItem 1" />

      <syncfusion:TileViewItem x:Name="Tile2" Header="TileViewItem 2" />

      <syncfusion:TileViewItem x:Name="Tile3" Header="TileViewItem 3" />

      <syncfusion:TileViewItem x:Name="Tile4" Header="TileViewItem 4" /> 

</syncfusion:TileViewControl>



[C#]



this.TileView.SelectedItem = Tile1;





Properties

_SelectedItem Property Table_

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
SelectedItem</td><td>
Stores the currently selected TileViewItem</td><td>
DependencyProperty</td><td>
Object</td><td>
</td></tr>
</table>


Events

_SelectedItem Event Table_

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
SelectedItemChanged</th><th>
This event gets fired when the Selected TileViewItem is changed.</th><th>
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



