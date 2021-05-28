---
layout: post
title: TitleBarCustomButtons | ChromelessWindow | WPF | Syncfusion
description: How to use customs buttons on title bar of chromeless window in WPF.
platform: WPF
control: ChromelessWindow
 documentation: ug
---

#  TitleBarCustomButtons

Title bar can be customized by adding custom buttons  to the right and left side of the title bar using stack panel.  **RightCustomButtons** and **LeftCustomButtons** property is used for binding buttons to the right and left side of the Title bar respectively.  The following code snippet is used to set the custom buttons.

{% tabs %}

{% highlight XAML %}
<syncfusion:ChromelessWindow x:Class="ChromelessWindow_CustomButton1.MainWindow" x:Name="_chromelesswindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:ChromelessWindow_CustomButton1"
                            
        mc:Ignorable="d" xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
                             syncfusion:SkinStorage.VisualStyle="Office2019"
                             TitleTextAlignment="Left"
                             ShowIcon="True"
                            HorizontalContentAlignment="Left"
                  
                             RightCustomButtons="{StaticResource RightItems}"
                             LeftCustomButtons="{StaticResource LeftItems}" 
        Title="Chromeless Window Demo" Height="461.13" Width="404.063">
    <syncfusion:ChromelessWindow.Resources>

    </syncfusion:ChromelessWindow.Resources>
    <Grid>

    </Grid>
</syncfusion:ChromelessWindow>

{% endhighlight %}

{% endtabs %}

![TitleBarCustomButtons](TitleBarCustomButtons_images/TitleBarCustomButtons.png)
