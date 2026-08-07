---
layout: post
title: How to disable resize of FloatWindow in Docking in WPF Data Grid
description: Learn How to disable resize of FloatWindow in Docking in WPF Data Grid using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: WPF
control: DockingManager
documentation: ug
---

# How to disable resize of FloatWindow in Docking in WPF Data Grid

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

