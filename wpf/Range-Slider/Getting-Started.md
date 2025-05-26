---
layout: post
title: Getting Started with WPF Range Slider Control | Syncfusion®
description: Discover how to integrate and utilize the Syncfusion® WPF Range Slider (SfRangeSlider) control, including its components and features.
platform: WPF
control: SfRangeSlider 
documentation: ug
---

# Getting Started with WPF Range Slider (SfRangeSlider)

This section provides a comprehensive guide on designing an [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) control in a WPF application and gives an overview of its basic functionalities.

## Assembly Deployment

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

![Tools in WPF Range Slider](getting-started_images/wpf-range-slider-tools.png)

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

### Adding a Control Manually in Code

The following code demonstrates how to create an [SfRangeSlider](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfRangeSlider.html) in code-behind.

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

![Adding Control Manually in WPF Range Slider](getting-started_images/wpf-range-slider-add-control-manually.png)

## Theme

The SfRangeSlider supports various built-in themes. Use the following resources to apply themes:

- [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
- [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme in WPF Range Slider](getting-started_images/wpf-range-slider-theme.png)