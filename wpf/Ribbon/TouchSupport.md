---
layout: post
title: Touch support in Syncfusion Ribbon control
description: This section briefly describes the functionalities of touch mode support in Syncfusion 'sRibbon control for WPF.
platform: wpf
control: Ribbon
documentation: ug
---
# Touch Support in WPF Ribbon    

Ribbon control have touch support and it provides Touch UI which is easy to access the element in Ribbon. 

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

![Enabling touch mode for ribbon](TouchSupport_images/TouchSupport_img1.jpeg)
