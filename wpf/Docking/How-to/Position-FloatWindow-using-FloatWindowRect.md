---
layout: post
title: How to position FloatWindow in DockingManager in WPF Data Grid
description: Learn How to position FloatWindow in DockingManager in WPF Data Grid using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: WPF
control: DockingManager
documentation: ug
---

# How to position FloatWindow in DockingManager in WPF Data Grid

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