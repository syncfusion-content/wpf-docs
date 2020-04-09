---
layout: post
title: Themes | Button control | WPF | Syncfusion
description: This section explains about different themes for button control and how to implement those themes to the control.
platform: WPF
control: ButtonAdv
documentation: ug
---

# Themes

Button supports various themes which can be applied using [SfSkinManager](https://help.syncfusion.com/wpf/themes/getting-started) and also provided support to create custom theme using [Theme Studio](https://help.syncfusion.com/wpf/themes/theme-studio).

## Applying themes using SkinManager

The appearance of Button control can be customized by using [VisualStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSkinManager.WPF~Syncfusion.SfSkinManager.VisualStyles.html) attached property of the [SfSkinManager](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSkinManager.WPF~Syncfusion.SfSkinManager.SfSkinManager.html). The list of available themes and assemblies can be referred in the below documentation [link](https://help.syncfusion.com/wpf/themes/getting-started).

Below example explains how to apply blend theme for button using `SfSkinManager` in an existing application.

* Add references like **Syncfusion.SfSkinManager.Wpf.dll** and **Syncfusion.Themes.Blend.Wpf.dll** assembly to the project.

 * Import **SfSkinManager** namespace and set **SfSkinManager.VisualStyle** attached property either to the Window or the Button control. Setting [VisualStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfSkinManager.WPF~Syncfusion.SfSkinManager.VisualStyles.html) property to the Window will apply blend theme for all controls inside the Window.

{% tabs %}
{% highlight xaml %}

    <Window x:Class="Button_Sample.MainWindow"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
            xmlns:local="clr-namespace:Button_Sample"
            xmlns:Syncfusion="http://schemas.microsoft.com/netfx/2009/xaml/presentation"
            xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
            mc:Ignorable="d"
            xmlns:skinManager="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
            Title="MainWindow" Height="450" Width="800">
        <Grid>
            <syncfusion:ButtonAdv x:Name="button" skinManager:SfSkinManager.VisualStyle="Blend"  Label="Log-in Syncfusion Employee" Sizemode="Large" LargeIcon="image\employee.png"/>
        </Grid> 
    </Window>

{% endhighlight %}
{% highlight C# %}

    SfSkinManager.SetVisualStyle(button, VisualStyles.Blend); 

{% endhighlight %}
{% endtabs %}

Now run the application and can see the blend theme applied for Button control respectively.

![Theme](Theme-Support_images/Theme-Support_img1.png)


## Applying themes using Theme studio

Button control themes can be customized using theme studio. Refer the documentation [link](https://help.syncfusion.com/wpf/themes/theme-studio) for more information.