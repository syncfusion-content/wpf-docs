---
layout: post
title: Remove Individual Menu Items | DockingManager | wpf | Syncfusion®
description: Remove individual menu items in Syncfusion® Essential Studio® WPF DockingManager control, its elements and more.
platform: WPF
control: DockingManager
documentation: ug
---

# Remove Individual Menu Items in WPF DockingManager

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