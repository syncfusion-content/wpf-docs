---
layout: post
title: How to disable resize of FloatWindow in WPF Docking | Syncfusion®
description: Learn here how to disable the resize of floatwindow in Syncfusion® WPF Docking (DockingManager) control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# How to disable resize of FloatWindow in WPF Docking

CanResizeInFloatState is the attached property which can be applied on float state child of DockingManager to disable the manual resize of FloatWindow.  If this property is set, the float window is no longer resizable. The usage is shown below.

{% tabs %}

{% highlight xaml %}

<syncfusion:DockingManager>

	<Grid x:Name="grid1" syncfusion:DockingManager.State="Float" syncfusion:DockingManager.CanResizeInFloatState="False"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight c# %}

DockingManager.SetCanResizeInFloatState(grid1, false);

{% endhighlight %}

{% endtabs %}

