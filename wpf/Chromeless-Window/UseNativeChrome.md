---
layout: post
title: UseNativeChrome in WPF Chromeless Window | Syncfusion®
description: UseNativeChrome support in the Chromeless Window enables native window chrome behavior while preserving custom window functionality.
platform: wpf
control: ChromelessWindow
documentation: ug
---
# UseNativeChrome in WPF Chromeless Window

Windows can be arranged side by side by using the `UseNativeChrome` property, which is helpful when moving and comparing windows. To enable this docking behavior, set the `UseNativeChrome` property to `true`. This property allows the `ChromelessWindow` to behave like the standard Windows (MS Window) chrome. Windows can be docked to the left and right side of the screen to resize them to half of the screen, docked to the corners to resize to a quarter of the screen, and maximized when docked at the top of the screen.

To set this property, use the code below.

{% tabs %}

{% highlight XAML %}

<syncfusion:ChromelessWindow x:Class="Chromelesswindow.MainWindow"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
Title="ChromelessWindow" Height="350" Width="525"  UseNativeChrome="True"   syncfusion:SkinStorage.VisualStyle="Metro" 
x:Name="_chromelessWindow" xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF"  >
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% highlight c# %}

_chromelessWindow.UseNativeChrome = true;

{% endhighlight %}

{% highlight VB %}

_chromelessWindow.UseNativeChrome = True

{% endhighlight %}

{% endtabs %}
