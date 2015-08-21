---
layout: post
title: Apply-Skin-for-Hierarchy-Navigator-Control
description: apply skin for hierarchy navigator control
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

## Apply Skin for Hierarchy Navigator Control

Add the following DLLs to apply corresponding theme for the Hierarchy Navigator control. SkinStorage class is used to apply different visual style for a control, which is available in Syncfusion.Shared.WPF project.

1. Create a HierarchyNavigator instance either in XAML or code behind.

{% highlight xml %}



<syncfusion:HierarchyNavigator x:Name="hierarchyNavigator"/>

{% endhighlight  %}

Or

{% highlight c# %}



HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

{% endhighlight  %}

2. Apply Visual Style in code behind by calling the static method SetVisualStyle in SkinStorage class in Syncfusion.Shared.WPF. Here, Control name and Visual Style has to be passed in that static method arguments. The following image shows an example of Windows 7 (Default):

{% highlight c# %}


SkinStorage.SetVisualStyle(this, "Default");


{% endhighlight  %}




