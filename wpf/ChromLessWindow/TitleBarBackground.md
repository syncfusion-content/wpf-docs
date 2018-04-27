---
layout: post
title: TitleBarBackground
description: TitleBarBackground
platform: wpf
control: ChromelessWindow
documentation: ug
---
# TitleBarBackground

The **TitleBarBackground** property can help to set the Background for the TitleBar. By setting the value for this property, user can create custom TitleBars.

{% tabs %}

{% highlight XAML %}

<syncfusion:ChromelessWindow x:Class="Chromelesswindow.MainWindow"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
Title="MainWindow" Height="350" Width="525"  TitleBarBackground="Red"   x:Name="_chromelessWindow"  
syncfusion:SkinStorage.VisualStyle="Metro"  
xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF" >
<Grid>
</Grid>
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% highlight c# %}

this.TitleBarBackground = new SolidColorBrush(Colors.Red);

{% endhighlight %}

{% highlight VB %}

Me.TitleBarBackground = New SolidColorBrush(Colors.Red)

{% endhighlight %}

{% endtabs %}

The following screen shots illustrate the title bar background changes.

![](TitleBarBackground_images/TitleBarBackground_img1.jpeg)
