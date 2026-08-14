---
layout: post
title: How to remove Menu Items in WPF Docking | Syncfusion®
description: Learn here how to remove individual menu items in Syncfusion® WPF Docking (DockingManager) control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# How to remove Menu Items in WPF Docking

We can remove individual MenuItem in ContextMenu using the following properties.  The removal can be done by right clicking on it.

* ShowHiddenMenuItem
* ShowFloatingMenuItem
* ShowFloatingMenuItem
* ShowDockableMenuItem
* ShowTabbedMenuItem
* ShowTabbedMenuItem
* ShowAutoHiddenMenuItem
* ShowDocumentMenuItem
* ShowCloseMenuItem
* ShowHorizontalTabGroupMenuItem
* ShowVerticalTabGroupMenuItem
* ShowMovetoNextTabGroupMenuItem
* ShowMovetoPreviousTabGroupMenuItem
* ShowRestoreMenuItem
* ShowMoveMenuItem
* ShowResizeMenuItem
* ShowMinimizeMenuItem
* ShowMaximizedMenuItem

The below code shows how to disable Tabbed menu item using ShowTabbedMenuItem attached property

{% tabs %}

{% highlight xaml %}

<syncfusion:DockingManager>    

	<Grid Name="grid1" syncfusion:DockingManager.ShowTabbedMenuItem="False"/>  

</syncfusion:DockingManager>

{% endhighlight  %}

{% highlight c# %}

DockingManager.SetShowTabbedMenuItem(grid1, false);

{% endhighlight  %}

{% endtabs %}

![Remove-Individual-Menu-Items_in_WPF_DockingManager](Remove-Individual-Menu-Items_images/Remove-Individual-Menu-Items_img1.png)

Similarly you can use other properties to disable corresponding MenuItems.