---
layout: post
title: How to remove Menu Items in Docking in WPF Data Grid | Syncfusion
description: Learn How to remove Menu Items in Docking in WPF Data Grid using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: WPF
control: DockingManager
documentation: ug
---

# How to remove Menu Items in Docking in WPF Data Grid

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