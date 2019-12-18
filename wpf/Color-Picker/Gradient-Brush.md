---
layout: post
title: ColorPicker with Gradient Support | ColorPicker | wpf | Syncfusion
description: This section describes the Color Picker gradient Tool which returns a Solid, Linear or Radial brush. 
platform: wpf
control: ColorPicker
documentation: ug
---

## What is a gradient brush? 

A gradient brush paints an area with multiple colors that blend into each other along an axis. Color Picker now comes with Gradient tool which returns a brush of type Linear and Radial. The offsets can be added or dropped dynamically and its position can be changed to produce different color combinations.

![ColorPicker with Gradient Mode](ColorPicker-with-Gradient-Support_images/ColorPicker_Gradient_Mode.png)

## Gradient Stops

[ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker.html) has gradient editor similar to that of VisualStudio brush editor. Adding new gradient stops, altering the offset and changing the color of the gradient stops can be done run-time.

![ColorPicker with Gradient Mode](ColorPicker-with-Gradient-Support_images/ColorPicker_Stopper_editing.gif)

### Add remove stops

Gradient stops can be added or removed in existing GradientBrush runtime, 

### Slide stops

### Change color of a stop

### Reverse stops


## Configure linear gradient

Start and end point of the selected [Linear Gradient brush](https://docs.microsoft.com/en-us/dotnet/api/system.windows.media.lineargradientbrush?view=netframework-4.8) can be edited runtime through the input options as well as with their properties listed in below table.

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
{{ '[Startpoint](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit~Startpoint.html)' | markdownify }}</td><td>
Indicates Start point of LinearGradientBrush.</td></tr>
<tr>
<td>
{{ '[Endpoint](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit~Endpoint.html)' | markdownify }}</td><td>
Indicates End point of LinearGradientBrush.</td></tr>

</table>

![ColorPicker Linear Gradient Editor](ColorPicker-with-Gradient-Support_images/ColorPicker_LinearGradient_Editor.png)

## Configure radial gradient

Gradient origin, Centre and Radius of the selected [Radial Gradient brush](https://docs.microsoft.com/en-us/dotnet/api/system.windows.media.radialgradientbrush?view=netframework-4.8) can be edited runtime through the input options as well as with their properties listed in below table.

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
{{ '[GradientOrigin](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit~GradientOrigin.html)' | markdownify }}</td><td>
Indicates gradient origin of RadialGradientBrush.</td></tr>
<tr>
<td>
{{ '[CentrePoint](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit~CentrePoint.html)' | markdownify }}</td><td>
Indicates centre point of RadialGradientBrush.</td></tr>
<tr>
<td>
{{ '[RadiusX](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit~RadiusX.html)' | markdownify }}</td><td>
Indicates X value in Radius of RadialGradientBrush.</td></tr>
<tr>
<td>
{{ '[RadiusY](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit~RadiusY.html)' | markdownify }}</td><td>
Indicates Y value in Radius of RadialGradientBrush.</td></tr>
</table>

![ColorPicker Radial Gradient Editor](ColorPicker-with-Gradient-Support_images/ColorPicker_RadialGradient_Editor.png)

## Hide gradient property editor

[GradientPropertyEditorMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~GradientPropertyEditorMode.html) property specifies whether Gradient Editor should be displayed as a Popup or in extended mode.

{% tabs %}
{% highlight xaml %}

<Syncfusion:ColorPicker x:Name="colorPicker"    GradientPropertyEditorMode="Popup" ></ Syncfusion: ColorPicker >
<Syncfusion: ColorPicker x:Name="colorPicker"  GradientPropertyEditorMode="Extended"  ></Syncfusion: ColorPicker >

{% endhighlight %}
{% highlight C# %}

ColorPicker colorPicker = new ColorPicker ();
colorPicker.GradientPropertyEditorMode =  GradientPropertyEditorMode.Popup;
colorPicker. GradientPropertyEditorMode =  GradientPropertyEditorMode.Extended;

{% endhighlight %}
{% endtabs %}

The GradientEditor is displayed accordingly.

![Colorpicker Extended gradientEditor](ColorPicker-with-Gradient-Support_images/Colorpicker_Extended_gradientEditor.png)

![Colorpicker popup gradientEditor](ColorPicker-with-Gradient-Support_images/Colorpicker_Popup_gradientEditor.png)

## Switch between Solid, Linear, Gradient mode

Brush type can be switched between solid to gradient or vice versa, runtime as well as programmatically. This can be switched using [BrushMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~BrushMode.html) property.

{% tabs %}
{% highlight xaml %}

<Syncfusion: ColorPicker x:Name="colorPicker" BrushMode="Gradient"   ></  Syncfusion: ColorPicker >

{% endhighlight %}

{% highlight C# %}

ColorPicker colorPicker = new ColorPicker ();
colorPicker.BrushMode = BrushModes.Gradient;

{% endhighlight %}
{% endtabs %}

![ColorPicker with Gradient Mode](ColorPicker-with-Gradient-Support_images/ColorPicker_BrushMode.png)
