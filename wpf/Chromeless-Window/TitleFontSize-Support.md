---
layout: post
title: Title bar Font size Support | ChromelessWindow | WPF | Syncfusion
description: This section briefly describes the ability to set Title bar font size in Syncfusion's Chromeless Window
platform: wpf
control: ChromelessWindow
documentation: ug
---
# Title bar Font size Support

The font size of the ChromelessWindow title bar can be changed by using [`TitleFontSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ChromelessWindow.html#Syncfusion_Windows_Shared_ChromelessWindow_TitleFontSize) property. By default its value is 12, to enable this functionality, change its value as desired

To set this property, use the below code

{% tabs %}

{% highlight XAML %}

<syncfusion:ChromelessWindow x:Class="Chromelesswindow.MainWindow"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
Title="ChromelessWindow" Height="350" Width="525" TitleFontSize="25" syncfusion:SkinStorage.VisualStyle="Metro"     
x:Name="_chromelessWindow" xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Shared;assembly=Syncfusion.Shared.WPF" >
<Grid>
</Grid>
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% highlight c# %}

this.TitleFontSize = 25;

{% endhighlight %}

{% highlight VB %}

Me.TitleFontSize = 25

{% endhighlight %}

{% endtabs %}

![Setting font size for the title bar text](ChromelessWindow-TitleFontSize-Support_images/ChromelessWindow-TitleFontSize-Support_img1.jpeg)
