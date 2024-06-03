---
layout: post
title: Getting Started with WPF color picker control | Syncfusion
description: Learn here about getting started with Syncfusion WPF color picker (ColorPicker) control, its elements and more.
platform: wpf
control: ColorPicker
documentation: ug
---

# Getting Started with WPF color picker (ColorPicker)

This section explains how to create a WPF [ColorPicker](https://www.syncfusion.com/wpf-controls/colorpicker) and explains about its structure and features.

## Structure of ColorPicker

![Structure of WPF Color Picker](getting-started_images/wpf-color-picker-structure.png)

## Assembly deployment

Refer to the [Control Dependencies](https://help.syncfusion.com/wpf/control-dependencies#colorpicker) section to get the list of assemblies or `NuGet` package that needs to be added as a reference to use the control in any application.

Refer to this [documentation](https://help.syncfusion.com/wpf/visual-studio-integration/nuget-packages) to find more details about installing nuget packages in a WPF application.

## Adding WPF ColorPicker via designer

`ColorPicker` can be added to an application by dragging it from the toolbox to a designer view. The following dependent assemblies will be added automatically:

* Syncfusion.Shared.WPF

   ![WPF Color Picker Drag and dropped from ToolBox](getting-started_images/wpf-color-picker-drag-and-dropped-from-toolbox.png)

## Adding WPF ColorPicker via XAML

To add the `ColorPicker` manually in XAML, follow these steps:

1. Create a new WPF project in Visual Studio.

2. Add the following required assembly reference to the project:

    * Syncfusion.Shared.WPF

3. Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf**, and declare the `ColorPicker` in WPF XAML page.

{% capture codesnippet1 %}
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
    <syncfusion:ColorPicker Name="colorPicker" Height="100" Width="280"/>
</Grid>

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

![WPF Color Picker Dropdown](getting-started_images/wpf-color-picker-dropdown.png)

## Adding WPF ColorPicker via C#

To add the `ColorPicker` manually in C#, follow these steps:

1. Create a new WPF application via Visual Studio.

2. Add the following required assembly references to the project:

    * Syncfusion.Shared.WPF

3. Include the required namespace.

{% capture codesnippet2 %}
{% tabs %}
{% highlight C# %}

using Syncfusion.Windows.Shared;

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}


4. Create an instance of `ColorPicker`, and add it to the window.

{% capture codesnippet3 %}
{% tabs %}
{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.Width = 300;
colorPicker.Height=100;

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet3 | OrderList_Indent_Level_1 }}


![WPF Color Picker Control](getting-started_images/wpf-color-picker-dropdown.png)

## Select a Color

We can select a solid color or gradient color from a `ColorPicker` using the [Color](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_Color) and [Brush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_Brush) properties.

### Select Solid Color

We can select the solid color by using the `Color` property.

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

We can select a linear or radial gradient color which holds the multiple colors from the `ColorPicker`.

#### Linear Gradient ####

Linear Gradient color can be selected by the multiple colors and their location along the gradient axis using the `GradientStops` objects and [StartPoint](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_Startpoint) and [EndPoint](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_Endpoint) properties. Based on the `StartPoint` and `EndPoint`, the selected colors will be combined in linear manner.

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

#### Radial Gradient ####

Radial Gradient color is similar to Linear Gradient color, except for the axis defined by the circle. Based on the [GradientOrigin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_GradientOrigin), `Center` and `RadiusPoint` properties values, the selected gradient colors are combined in a circle manner. 

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

//Creating a 
RadialGradientBrush radialGradient = new RadialGradientBrush();
radialGradient.GradientOrigin = new Point(0.5, 0.5);
radialGradient.Center = new Point(0.5, 0.5);
radialGradient.RadiusX = 0.5;
radialGradient.RadiusY = 0.5;
radialGradient.GradientStops.Add(new GradientStop(Colors.Yellow, 0.0));
radialGradient.GradientStops.Add(new GradientStop(Colors.Red, 0.25));
radialGradient.GradientStops.Add(new GradientStop(Colors.Blue, 0.75));
radialGradient.GradientStops.Add(new GradientStop(Colors.LimeGreen, 1.0));

colorPicker.Brush = radialGradient;

{% endhighlight %}
{% endtabs %}

![Choose a Radial Gradient from WPF Color Picker](getting-started_images/wpf-color-picker-radial-gradient.png)

### Change Selected Color at runtime

`ColorPicker` consist of bunch of input components to select color and edit its properties at runtime.

![Choose and edit a color from WPF Color Picker at runtime](getting-started_images/wpf-color-picker-Choose-edit-color.gif)

## Color and Brush changed notification

Selected Color and Brush changed in [ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html) can be examined using [SelectedBrushChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_SelectedBrushChanged) and [ColorChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_ColorChanged) events.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker ColorChanged="ColorPicker_ColorChanged"
                        SelectedBrushChanged="ColorPicker_SelectedBrushChanged"
                        Name="colorPicker"/>

{% endhighlight %}
{% highlight c# %}

ColorPicker  colorPicker = new ColorPicker();
colorPicker.SelectedBrushChanged += ColorPicker_SelectedBrushChanged;
colorPicker.ColorChanged += ColorPicker_ColorChanged;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

//Invoked when the selected color is changed
private void ColorPicker_ColorChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    // Enter your code here
}

//Invoked when the selected brush is changed
private void ColorPicker_SelectedBrushChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    // Enter your code here
}

{% endhighlight %}
{% endtabs %}

## Change opacity of the color

We can change the opacity of the selected color by using the A-Alpha value editor or delicate slider in the `ColorPicker`. We can hide the A-Alpha value editor and delicate slider by using the [IsAlphaVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_IsAlphaVisible) property value as `false`. The default value of the `IsAlphaVisible` property is `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker IsAlphaVisible="False" x:Name="colorPicker" />

{% endhighlight %}
{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.IsAlphaVisible = false;

{% endhighlight %}
{% endtabs %}

![WPF Color Picker hides the Alpha slider and vale editor](scrgb-color_images/wpf-color-picker-alpha-and-vale.png)

## Switch between Solid, Linear and Gradient brush mode

We can change the color selection mode directly by clicking on the corresponding Solid, Linear or Gradient brush mode buttons which are placed in the bottom right corner of the `ColorPicker`.

![WPF Color Picker popup gradient Editor](colorpicker-with-gradient-support_images/wpf-color-picker-switch-brushes.png)

### Restrict the brush mode from Solid to Gradient

 We can restrict color selection mode switching at runtime by setting the [EnableSolidToGradientSwitch](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_EnableSolidToGradientSwitch) property value as `false`.  It will hide the Solid, Linear and Gradient brush switch buttons.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker x:Name="colorPicker" EnableSolidToGradientSwitch="false"/>

{% endhighlight %}

{% highlight C# %}

ColorPicker colorPicker = new ColorPicker ();
colorPicker.EnableSolidToGradientSwitch = false;

{% endhighlight %}
{% endtabs %}

![WPF Color Picker Solid to Gradient brush transition is disabled](colorpicker-with-gradient-support_images/wpf-color-picker-gradient-transition.png)

Click [here](https://github.com/SyncfusionExamples/wpf-colorpicker-examples/tree/master/Samples/Over%20all%20features) to download the sample that showcases the `ColorPicker` overall features.

## Theme

ColorPicker supports various built-in themes. Refer to the below links to apply themes for the ColorPicker,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF Color Picker](getting-started_images/wpf-color-picker-theme-support.png)