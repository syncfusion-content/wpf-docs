---
layout: post
title: Getting Started with WPF Range Slider control | Syncfusion
description: Learn here about getting started with Syncfusion WPF Range Slider (SfRangeSlider) control, its elements and more.
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Getting Started with WPF Range Slider (SfRangeSlider)

This section describes how to design a [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) control in a WPF application and overview of its basic functionalities.

## Assembly deployment

 Namespace:  Syncfusion.Windows.Controls.Input

 Assembly:  Syncfusion.SfInput.WPF (in Syncfusion.SfInput.WPF.dll) 

Dependent assembly: Syncfusion.SfShared.WPF.dll


## Creating a simple application with SfRangeSlider

The [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) control can be added to an application using Visual Studio.

Create the WPF application with [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) control as follows:

1. [Creating project](#creating-the-project)
2. [Adding control via designer](#adding-control-via-designer)
3. [Adding control manually in code](#adding-control-manually-in-code)

### Creating the project

The steps to create a [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) control by using Visual Studio in C# are as follows:

1.	Open Visual Studio.

2.	On the File menu, select New -> Project. This opens the New Project Dialog box.

### Adding a control via designer

[SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) control can be added to the application by dragging it from the toolbox and dropping it in a designer view. The following required assembly references will be added automatically:

* Syncfusion.SfInput.WPF
* Syncfusion.SfShared.WPF

![Tools](GettingStarted_images/img1.png)

{% tabs %}

{% highlight XAML %}

<editors:SfRangeSlider
                    Width="500"
                    HorizontalAlignment="Center"
                    VerticalAlignment="Center"
                    Maximum="100"
                    Minimum="0"
                    Value="50" />

{% endhighlight %}

{% endtabs %}

### Adding a control manually in code

The following code sample shows how to create the [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) from code-behind.

{% tabs %}

{% highlight C# %}

SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 500,
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center,
                Minimum = 0,
                Maximum = 100,
                Value = 60
            };

{% endhighlight %}

{% endtabs %}

![RangeSlider](GettingStarted_images/img2.png)

## Theme

SfRangeSlider supports various built-in themes. Refer to the below links to apply themes for the SfRangeSlider,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF RangeSlider](GettingStarted_images/Theme.png)