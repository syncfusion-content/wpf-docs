---
layout: post
title: UseNativeChrome in WPF Chromeless Window control | Syncfusion
description: Learn about UseNativeChrome support in Syncfusion WPF Chromeless Window control and more.
platform: wpf
control: ChromelessWindow
documentation: ug
---
# UseNativeChrome in WPF Chromeless Window

Windows can be arranged side by side by using **UseNativeChrome** property, which is very helpful while moving and comparing the windows .To enable this docking behavior, set UseNativeChrome property to **True****.** This property allows the ChromelessWindow to behave like the MS Window .Windows can be docked to the left and right side of the Window to resize them to half of the screen. Also it supports the window maximization when docked at the top of the screen.

To set this property, use the below code.

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
