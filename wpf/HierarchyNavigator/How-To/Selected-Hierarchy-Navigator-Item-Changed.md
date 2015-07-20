---
layout: post
title: Selected-Hierarchy-Navigator-Item-Changed
description: selected hierarchy navigator item changed
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

### Selected Hierarchy Navigator Item Changed

Users can handle selected item changed by using the methods Command (ICommand) property or HierarchyNavigatorSelectedItemChanged event in Hierarchy Navigator control.

<table>
<tr>
<td>
XAML&lt;syncfusion:HierarchyNavigator HierarchyNavigatorSelectedItemChanged="HierarchyNavigatorSelectedItemChanged" /&gt;</td></tr>
<tr>
<td>
C#HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.HierarchyNavigatorSelectedItemChanged += new HierarchyNavigatorSelectedItemChangedEventHandler(HierarchyNavigatorSelectedItemChanged);</td></tr>
<tr>
<td>
C#private void HierarchyNavigatorSelectedItemChanged(object sender, HierarchyNavigatorSelectedItemChangedEventArgs e){<br>     //Occurs when Selected Item Changed}</td></tr>
</table>


Passing the argument “HierarchyNavigator item” in a method called SelectNavigationItem can change the selected item.

C#



HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

hierarchyNavigator.SelectNavigationItem(hierarchyitem);



