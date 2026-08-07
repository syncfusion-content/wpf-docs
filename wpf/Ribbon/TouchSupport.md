---
layout: post
title: Touch Support in WPF Ribbon Control | Syncfusion®
description: Learn here all about Touch Support in Syncfusion® WPF Ribbon control, its elements, features, and more details.
platform: wpf
control: Ribbon
documentation: ug
---
# Touch Support in WPF Ribbon Control

The Ribbon control has touch support and it provides a Touch UI which is easy to access the element in Ribbon. 

### How to enable touch in RibbonWindow

To enable touch in the RibbonWindow, set `EnableTouch` property of the SkinStorage as `True`. The following code snippet illustrates this

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonButtonPanel.MainWindow"
Title="MainWindow" Height="350" Width="525" syncfusion:SkinStorage.VisualStyle="Office2013"  x:Name="_ribbonWindow" syncfusion:SkinStorage.EnableTouch="True"/>

{% endhighlight %}

{% highlight C# %}

SkinStorage.SetEnableTouch(_ribbonWindow, true);

{% endhighlight %}

{% highlight VB %}

SkinStorage.SetEnableTouch(_ribbonWindow, True)

{% endhighlight %}

{% endtabs %}

![WPF Ribbon with Touch Mode](TouchSupport_images/wpf-ribbon-touch-mode.jpeg)
