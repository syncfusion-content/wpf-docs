---
layout: post
title: Getting Started | ColorPicker | wpf | Syncfusion
description: This section discusses how to build a ColorPicker control and explains its basic features and structure.
platform: wpf
control: ColorPicker
documentation: ug
---


# Getting Started with ColorPicker

This section explains how to create a WPF [ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker.html) and explains about its structure.

## Structure of ColorPicker

The various elements of ColorPicker are illustrated in the following screenshot.

![Structure of WPF ColorPicker](Getting-Started_images/ColorPicker_Structure.png)

## Assembly deployment

Refer to the [Control Dependencies](https://help.syncfusion.com/wpf/control-dependencies#colorpicker) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

Refer to this [documentation](https://help.syncfusion.com/wpf/visual-studio-integration/nuget-packages) to find more details about installing nuget packages in a WPF application.

## Adding WPF ColorPicker via designer

1) [ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker.html) / [ColorEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit.html) can be added to an application by dragging it from the toolbox to a designer view. The following dependent assemblies will be added automatically:

* Syncfusion.Shared.WPF

   ![ColorPicker Drag and dropped from ToolBox](Getting-Started_images/ColorPicker_Drag_and_dropped_from_ToolBox.png)

2. Set the properties for the ColorPicker in the design mode, using the Smart Tag feature.

## Adding WPF ColorPicker via XAML

To add the [ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker.html) / [ColorEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit.html) manually in XAML, follow these steps:

1) Create a new WPF project in Visual Studio.

2) Add the following required assembly references to the project:

* Syncfusion.Shared.WPF

3) Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf**, and declare the ColorPicker in XAML page.

{% tabs %}

{% highlight XAML %}

<Window x:Class="ColorPicker_sample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:ColorPicker_sample"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">

<Grid Name="grid">
    <syncfusion:ColorPicker Name="colorPicker" Height="100" Width="280" />
</Grid>

{% endhighlight %}

{% endtabs %}

![ColorPicker Dropdown](Getting-Started_images/ColorPicker_Dropdown.png)

## Adding WPF ColorPicker via C#

To add the ColorPicker manually in C#, follow these steps:

1) Create a new WPF application via Visual Studio.

2) Add the following required assembly references to the project:

* Syncfusion.Shared.WPF

3) Include the required namespace.

{% tabs %}

{% highlight C# %}

using Syncfusion.Windows.Shared;

{% endhighlight %}

{% endtabs %}

4) Create an instance of [ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker.html) / [ColorEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit.html), and add it to the window.

{% tabs %}

{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();

colorPicker.Width = 300;

grid.Children.Add(colorPicker); 

{% endhighlight %}

{% endtabs %}

![ColorPicker Control](Getting-Started_images/ColorPicker_Dropdown.png)

## Bind to a color

 [ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker.html) and [ColorEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit.html) can be easily binded to [Color](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~Color.html) as well as [Brush](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~Brush.html) .

 {% tabs %}
{% highlight xaml %}

 <Button  Background="{Binding ElementName=colorPicker, Path=Brush}" ></Button>
<syncfusion:ColorPicker Name="colorPicker" Width="300" HorizontalAlignment="Center" VerticalAlignment="Center"/>

{% endhighlight %}
{% endtabs %}

## Choose a Color

[ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker.html) consist of delicate input components to select color, such as slider with **Hue Spectrum**,Color selection palette with saturation range, updown controls to get or set color value runtime.

![Choose a color from ColorPicker](Getting-Started_images/ColorPicker_Choose_a_color.gif)

## Color changed notification

Color changed in [ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker.html) can be examined using [SelectedBrushChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~SelectedBrushChanged_EV.html) and [ColorChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~ColorChanged_EV.html).


 {% tabs %}
{% highlight c# %}

colorPicker.SelectedBrushChanged += ColorPicker_SelectedBrushChanged;

  private void ColorPicker_SelectedBrushChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
 {
         // code here
 }

{% endhighlight %}
{% endtabs %}

## Gradient Brush

ColorPicker supports Linear and Radial brush selection along with their property editors.

![WPF ColorPicker Linear Gradient](Getting-Started_images/ColorPicker_Linear_Gradient.png)

![WPF ColorPicker Radial Gradient](Getting-Started_images/ColorPicker_Radial_Gradient.png)