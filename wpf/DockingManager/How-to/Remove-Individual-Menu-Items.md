---
layout: post
title: Remove-Individual-Menu-Items
description: remove individual menu items
platform: wpf
control: DockingManager
documentation: ug
---

## Remove Individual Menu Items

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



{% highlight html %}
<syncfusion:DockingManager>     <Grid Name="grid1" syncfusion:DockingManager.ShowTabbedMenuItem="False"/>  </syncfusion:DockingManager>

DockingManager.SetShowTabbedMenuItem(grid1, false);</td></tr>
{% endhighlight  %}


![](Remove-Individual-Menu-Items_images/Remove-Individual-Menu-Items_img1.png)



Similarly you can use other properties to disable corresponding MeniItems.

