---
layout: post
title: Add Syncfusion Controls | WPF | Syncfusion
description: common supports
platform: wpf
control: Add Syncfusion Controls
documentation: ug
---
## Through XAML

The following steps help you add a required Essential WPF Control through XAML Code, like DockingManager.

1. Create a WPF project in Visual Studio and refer the following assemblies.
  * Syncfusion.Tools.Wpf
  * Syncfusion.Shared.Wpf
2. Include an xml namespace for the above assemblies to the Main window.
{% highlight xml %}

<Window

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusion=[http://schemas.syncfusion.com/wpf](http://schemas.syncfusion.com/wpf# "") />



{% endhighlight %}

3. Now, Add the Docking Manager control with a required optimal name, using the included namespace.

{% highlight xml %}

<syncfusion:DockingManager x:Name="SyncDockingManager" />



{% endhighlight %}

