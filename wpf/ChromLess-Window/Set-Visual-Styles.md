---
layout: post
title: Set Visual Styles
description: Set Visual Styles
platform: wpf
control: ChromelessWindow
documentation: ug
---
# Set Visual Styles

The visual style for the ChromelessWindow control is set using the VisualStyle property. ChromelessWindow supports the following built-in visual styles.

* Blend
* Office2003
* Office2007Blue
* Office2007Black
* Office2007Silver
* Office2010Blue
* Office2010Black
* Office2010Silver
* Default
* Transparent
* Metro

In the below code example, metro theme is applied to the ChromelessWindow control.

{% tabs %}

{% highlight XAML %}

<syncfusion:ChromelessWindow x:Class="Chromelesswindow.MainWindow"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
Title="MainWindow" Height="350" Width="525" syncfusion:SkinStorage.VisualStyle="Metro"    
xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF" >
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% endtabs %} 

{% tabs %}

{% highlight c# %}

SkinStorage.SetVisualStyle(this, "Metro");

{% endhighlight %}

{% highlight VB %}

SkinStorage.SetVisualStyle(Me, "Metro")

{% endhighlight %}

{% endtabs %} 

![](Set-Visual-Styles_images/Set-Visual-Styles_img1.jpeg)

N> Metro theme supports customization of Brushes and fonts. For example to change the Background color of the Window Icon ,use SetMetroBrush method
