---
layout: post
title: Getting Started with WPF ColorPicker | Syncfusion®
description: Learn how to get started with the Syncfusion WPF ColorPicker control, its elements, and more details.
platform: wpf
control: ColorPicker
documentation: ug
---

# Getting Started with WPF ColorPicker

This section explains how to create a [WPF ColorPicker](https://www.syncfusion.com/wpf-controls/colorpicker) and explains about its structure and features.

## Structure of WPF ColorPicker

![Structure of WPF Color Picker](getting-started_images/wpf-color-picker-structure.png)

## Assembly deployment

Refer to the [Control Dependencies](https://help.syncfusion.com/wpf/control-dependencies#colorpicker) section to get the list of assemblies or `NuGet` package that needs to be added as a reference to use the control in any application.

Refer to this [documentation](https://help.syncfusion.com/wpf/installation/install-nuget-packages) to find more details about installing nuget packages in a WPF application.

## Adding WPF ColorPicker via designer

`WPF ColorPicker` can be added to an application by dragging it from the toolbox onto a view in the designer. The following dependent assembly will be added automatically:

* Syncfusion.Shared.WPF

![WPF Color Picker Drag and dropped from ToolBox](getting-started_images/wpf-color-picker-drag-and-dropped-from-toolbox.png)

## Adding WPF ColorPicker via XAML

To add the `WPF ColorPicker` manually in XAML, follow these steps:

1. Create a new WPF project in Visual Studio.

2. Add the following required assembly reference to the project:

    * Syncfusion.Shared.WPF

3. Import the Syncfusion<sup>®</sup> WPF schema **http://schemas.syncfusion.com/wpf** and declare the `WPF ColorPicker` on the XAML page.

{% capture codesnippet1 %}
{% tabs %}
{% highlight XAML %}

<Window x:Class="ColorPickerSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <syncfusion:ColorPicker Name="colorPicker" Height="100" Width="280"/>
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

![WPF Color Picker Dropdown](getting-started_images/wpf-color-picker-dropdown.png)

## Adding WPF ColorPicker via C#

To add the `WPF ColorPicker` manually in C#, follow these steps:

1. Create a new WPF application in Visual Studio.

2. Add the following required assembly reference to the project:

    * Syncfusion.Shared.WPF

3. Include the required namespace and create an instance of the `WPF ColorPicker`.

{% capture codesnippet2 %}
{% tabs %}
{% highlight C# %}

// Required usings:
// using Syncfusion.Windows.Shared;

ColorPicker colorPicker = new ColorPicker();
colorPicker.Width = 300;
colorPicker.Height = 100;

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}


![WPF Color Picker Control](getting-started_images/wpf-color-picker-dropdown.png)

## Select a Color

You can select a solid color or a gradient color from `WPF ColorPicker` using the [Color](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_Color) and [Brush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_Brush) properties. The default value of `Color` is `Transparent`, and the default value of `Brush` is `null`.

### Select Solid Color

You can select a solid color by using the `Color` property.

{% tabs %}
{% highlight xaml %}

 <syncfusion:ColorPicker x:Name="colorPicker"
                         Color="Yellow"/>

{% endhighlight %}
{% highlight c# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.Color = Colors.Yellow;

{% endhighlight %}
{% endtabs %}

![Choose a color from WPF Color Picker](getting-started_images/wpf-color-picker-select-color.png)

### Select a Gradient Color

You can select a linear or radial gradient brush that contains multiple colors from the `WPF ColorPicker`.

#### Linear Gradient

A linear gradient can be configured with multiple colors and their locations along the gradient axis using `GradientStop` objects and the [StartPoint](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_Startpoint) and [EndPoint](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_Endpoint) properties. The selected colors are combined in a linear manner based on `StartPoint` and `EndPoint`.

{% tabs %}
{% highlight xaml %}

 <syncfusion:ColorPicker x:Name="colorPicker" Width="200">
   <syncfusion:ColorPicker.Brush>
        <LinearGradientBrush StartPoint="0,0" EndPoint="1,1">
             <GradientStop Color="Yellow" Offset="0.0" />
             <GradientStop Color="Red" Offset="0.25" />
             <GradientStop Color="Blue" Offset="0.75" />
             <GradientStop Color="LimeGreen" Offset="1.0" />
        </LinearGradientBrush>
    </syncfusion:ColorPicker.Brush>
 </syncfusion:ColorPicker>
{% endhighlight %}
{% highlight c# %}

//Creating the linear gradient brush
LinearGradientBrush linearGradient = new LinearGradientBrush();
linearGradient.StartPoint = new Point(0, 0);
linearGradient.EndPoint = new Point(1, 1);
linearGradient.GradientStops.Add(new GradientStop(Colors.Yellow, 0.0));
linearGradient.GradientStops.Add(new GradientStop(Colors.Red, 0.25));
linearGradient.GradientStops.Add(new GradientStop(Colors.Blue, 0.75));
linearGradient.GradientStops.Add(new GradientStop(Colors.LimeGreen, 1.0));

//Assigning a linear gradient brush to ColorPicker
ColorPicker colorPicker= new ColorPicker();
colorPicker.Brush = linearGradient;

{% endhighlight %}
{% endtabs %}

![Choose a Linear Gradient from WPF Color Picker](getting-started_images/wpf-color-picker-linear-gradient.png)

#### Radial Gradient

A radial gradient is similar to a linear gradient, except that the axis is defined by a circle. The selected gradient colors are combined in a circular manner based on the [GradientOrigin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_GradientOrigin), `Center`, and `RadiusPoint` property values.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker x:Name="colorPicker" Width="200">
    <syncfusion:ColorPicker.Brush>
        <RadialGradientBrush GradientOrigin="0.5,0.5" Center="0.5,0.5" RadiusX="0.5" RadiusY="0.5">
            <GradientStop Color="Yellow" Offset="0" />
            <GradientStop Color="Red" Offset="0.25" />
            <GradientStop Color="Blue" Offset="0.75" />
            <GradientStop Color="LimeGreen" Offset="1" />
        </RadialGradientBrush>
    </syncfusion:ColorPicker.Brush>
</syncfusion:ColorPicker>
{% endhighlight %}
{% highlight c# %}

// Required usings:
// using System.Windows;
// using System.Windows.Media;
// using Syncfusion.Windows.Shared;

//Creating a radial gradient brush
RadialGradientBrush radialGradient = new RadialGradientBrush();
radialGradient.GradientOrigin = new Point(0.5, 0.5);
radialGradient.Center = new Point(0.5, 0.5);
radialGradient.RadiusX = 0.5;
radialGradient.RadiusY = 0.5;
radialGradient.GradientStops.Add(new GradientStop(Colors.Yellow, 0.0));
radialGradient.GradientStops.Add(new GradientStop(Colors.Red, 0.25));
radialGradient.GradientStops.Add(new GradientStop(Colors.Blue, 0.75));
radialGradient.GradientStops.Add(new GradientStop(Colors.LimeGreen, 1.0));

//Assigning the radial gradient brush to ColorPicker
colorPicker.Brush = radialGradient;

{% endhighlight %}
{% endtabs %}

![Choose a Radial Gradient from WPF Color Picker](getting-started_images/wpf-color-picker-radial-gradient.png)

### Change Selected Color at runtime

The selected color and brush in the [WPF ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html) can be observed using the [SelectedBrushChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_SelectedBrushChanged) and [ColorChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_ColorChanged) events.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker ColorChanged="ColorPicker_ColorChanged"
                        SelectedBrushChanged="ColorPicker_SelectedBrushChanged"
                        Name="colorPicker"/>

{% endhighlight %}
{% highlight c# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.SelectedBrushChanged += ColorPicker_SelectedBrushChanged;
colorPicker.ColorChanged += ColorPicker_ColorChanged;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

//Invoked when the selected color is changed
private void ColorPicker_ColorChanged(DependencyObject d, DependencyPropertyChangedEventArgs e) {
    //Read the new and old color
    Color newColor = (Color)e.NewValue;
    Color oldColor = (Color)e.OldValue;
}

//Invoked when the selected brush is changed
private void ColorPicker_SelectedBrushChanged(DependencyObject d, DependencyPropertyChangedEventArgs e) {
    //Read the new and old brush
    Brush newBrush = (Brush)e.NewValue;
    Brush oldBrush = (Brush)e.OldValue;
}

{% endhighlight %}
{% endtabs %}

## Change opacity of the color

You can change the opacity of the selected color using the A (alpha) value editor or the alpha slider in the `WPF ColorPicker`. You can hide the alpha value editor and the slider by setting the [IsAlphaVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_IsAlphaVisible) property to `false`. The default value of `IsAlphaVisible` is `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker IsAlphaVisible="False" x:Name="colorPicker" />

{% endhighlight %}
{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.IsAlphaVisible = false;

{% endhighlight %}
{% endtabs %}

![WPF Color Picker hides the Alpha slider and value editor](scrgb-color_images/wpf-color-picker-alpha-and-vale.png)

## Switch between Solid, Linear and Gradient brush mode

You can switch the color-selection mode by clicking the corresponding Solid, Linear, or Gradient button placed in the bottom-right corner of the `WPF ColorPicker`. The default brush mode is `Solid`.

![WPF Color Picker popup gradient Editor](colorpicker-with-gradient-support_images/wpf-color-picker-switch-brushes.png)

### Hide the brush mode switch buttons

You can hide the Solid, Linear, and Gradient brush-mode switch buttons by setting the [EnableSolidToGradientSwitch](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_EnableSolidToGradientSwitch) property to `false`. The default value of `EnableSolidToGradientSwitch` is `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker x:Name="colorPicker" EnableSolidToGradientSwitch="false"/>

{% endhighlight %}

{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.EnableSolidToGradientSwitch = false;

{% endhighlight %}
{% endtabs %}

![WPF Color Picker Solid to Gradient brush transition is disabled](colorpicker-with-gradient-support_images/wpf-color-picker-gradient-transition.png)

Click [here](https://github.com/SyncfusionExamples/wpf-colorpicker-examples/tree/master/Samples/Over%20all%20features) to download the sample that showcases the `WPF ColorPicker` overall features.

## Theme

The WPF ColorPicker supports various built-in themes. Refer to the links below to apply themes,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF Color Picker](getting-started_images/wpf-color-picker-theme-support.png)