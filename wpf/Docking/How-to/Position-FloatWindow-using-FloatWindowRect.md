---
layout: post
title: How to position FloatWindow in WPF DockingManager | Syncfusion®
description: Learn here how to position floatwindow using floatwindowrect in Syncfusion® WPF Docking (DockingManager) control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# How to position FloatWindow in WPF DockingManager

FloatWindowRect is used to specify the Rect bounds for the float child that is displayed in FloatWindow.

{% tabs %}

{% highlight xaml %}

<syncfusion:DockingManager Name="DockingManager">

	<Grid Name="grid1" syncfusion:DockingManager.State="Float" syncfusion:DockingManager.FloatingWindowRect="0,0,200,200"/>

</syncfusion:DockingManager>

{% endhighlight  %}

{% highlight c# %}

DockingManager.SetFloatingWindowRect(grid1, new Rect(0, 0, 200, 200));

{% endhighlight  %}

{% endtabs %}