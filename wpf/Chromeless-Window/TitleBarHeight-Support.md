---
layout: post
title: Title bar Height Support | ChromelessWindow | WPF | Syncfusion
description: This section briefly describes the ability to set Title bar height in Syncfusion's Chromeless Window
platform: wpf
control: ChromelessWindow
documentation: ug
---

# Title bar Height Support

ChromelessWindow now supports changing the title bar font size and height directly with the  `TitleFontSize` and `TitleBarHeight` respectively and there is no need to edit the full template to change this.

`TitleBarHeight` is a property, which is used to change the height of the Title bar. By default its value is 30 and we can change this default value as desired 

Here is the code example for setting the `TitleBarHeight` Property

{% tabs %}

{% highlight XAML %}

<syncfusion:ChromelessWindow x:Class="Chromelesswindow.MainWindow"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
Title="ChromelessWindow" Height="350" Width="525" TitleBarHeight="60" TitleBarBackground="Pink" 
syncfusion:SkinStorage.VisualStyle="Metro"  x:Name="_chromelessWindow"  
xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF" >
<Grid>
</Grid>
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% highlight c# %}

this.TitleBarHeight = 60;

{% endhighlight %}

{% highlight VB %}

  Me.TitleBarHeight = 60
  
{% endhighlight %}

{% endtabs %}

![Setting title bar height](TitleBarHeight-Support_images/TitleBarHeight-Support_img1.jpeg)
