---
layout: post
title: Handle-Navigation-Popup-Events
description: handle navigation popup events 
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

### Handle Navigation Popup Events 

Passing the argument “HierarchyNavigator item” in a method called ShowNavigationPopupItems can open the Navigation Popup for the corresponding item passed in the method.

C#



HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

hierarchyNavigator.ShowNavigationPopupItems(hierarchyitem);

#### NavigationPopupOpening

NavigationPopupOpening occurs when the navigation pop-up window is in the process of opening.

<table>
<tr>
<td>
XAML&lt;syncfusion:HierarchyNavigator NavigationPopupOpening="NavigationPopupOpening"/&gt;</td></tr>
<tr>
<td>
C#HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.NavigationPopupOpening +=new EventHandler(NavigationPopupOpening);</td></tr>
<tr>
<td>
C#private void NavigationPopupOpening(object sender, EventArgs e)<br>{<br>    //Occurs when Navigation Popup attempt to open<br>}</td></tr>
</table>
#### NavigationPopupOpened

NavigationPopupOpened occurs when the navigation pop-up window is open.

<table>
<tr>
<td>
XAML&lt;syncfusion:HierarchyNavigator NavigationPopupOpened="NavigationPopupOpened"/&gt;</td></tr>
<tr>
<td>
C#HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.NavigationPopupOpened += new EventHandler(NavigationPopupOpened);</td></tr>
<tr>
<td>
C#private void NavigationPopupOpened(object sender, EventArgs e)<br>{<br>    //Occurs when Navigation Popup is opened}</td></tr>
</table>
#### NavigationPopupClosing

NavigationPopupClosing occurs when the navigation pop-up window is closing.

<table>
<tr>
<td>
XAML&lt;syncfusion:HierarchyNavigator NavigationPopupClosing="NavigationPopupClosing"/&gt;</td></tr>
<tr>
<td>
C#HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.NavigationPopupClosing +=new EventHandler(NavigationPopupClosing);</td></tr>
<tr>
<td>
C#private void NavigationPopupClosing(object sender, EventArgs e)<br>{<br>    //Occurs when Navigation Popup is Closing}</td></tr>
</table>
#### NavigationPopupClosed 

NavigationPopupClosed occurs when the navigation pop-up window is closed.

<table>
<tr>
<td>
XAML&lt;syncfusion:HierarchyNavigator NavigationPopupClosing="NavigationPopupClosing"/&gt;</td></tr>
<tr>
<td>
C#HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.NavigationPopupClosing +=new EventHandler(NavigationPopupClosing);</td></tr>
<tr>
<td>
C#private void NavigationPopupClosing(object sender, EventArgs e)<br>{<br>    //Occurs when Navigation Popup is Closing}</td></tr>
</table>


