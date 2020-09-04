---
layout: post
title: ColorPicker with Gradient Support | ColorPicker | wpf | Syncfusion
description: This section describes the Color Picker gradient Tool which returns a Solid, Linear or Radial brush. 
platform: wpf
control: ColorPicker
documentation: ug
---

# Select gradient color with WPF ColorPicker

This section gives a brief note on how to create gradient color, modify their colors and modify their properties.

### What is a gradient color? 

A gradient color paints an area with multiple colors that blend into each other along an axis. [ColorPicker](https://www.syncfusion.com/wpf-ui-controls/colorpicker) now comes with Gradient tools which returns a brush of type Linear and Radial gradient colors. The offsets can be added or dropped dynamically and its position can be changed to produce different color combinations.

![ColorPicker with Gradient Mode](ColorPicker-with-Gradient-Support_images/ColorPicker_Gradient_Mode.png)

## Create Gradient colors using GradientStops Editor

We can add a multiple color combination for the gradient color using the `GradientStopsEditor`. We can add new gradient stops, change the offset and change the color of the gradient stops at run-time. The created gradient stops are combined together provides a gradient color.

![ColorPicker with GradientStopsEditors](ColorPicker-with-Gradient-Support_images/ColorPicker_Stopper_editing.png)

### Add or Remove GradientStops

We can add a more colors for the gradient color by using the gradient stops. Gradient stops can be added to existing gradient by clicking on the `GradientStopEditor`. 

To remove a gradient stops, select the gradient stop which want to be remove and press `Delete` key or mouse drag it away, so that it will removed from the `GradientStopsEditor`.

![ColorPicker with add and removing gradient colors](ColorPicker-with-Gradient-Support_images/ColorPicker_Stopper_Adding.gif)

### Rearrange GradientStops

We can re-arrange the color combination of the gradient color by adjusting the gradient stops. Gradient stops positions can be altered just by dragging it along the `GradientStopEditor`. The Gradient color will be generated on the basis of the order of the gradient stops arranged.

![ColorPicker with arranging the gradient colors](ColorPicker-with-Gradient-Support_images/ColorPicker_Stopper_Arranging.gif)

### Change GradientStops Colors

We can change the colors for created gradient color by changing the color of gradient stops. Color of a gradient stops changed by selecting that particular gradient stop and change the color from the color picker.

![ColorPicker with changing the gradient colors](ColorPicker-with-Gradient-Support_images/ColorPicker_Stopper_Changing.gif)

## Create Linear Gradient colors

We can create linear gradient color by programmatically using the `LinearGradientBrush` with its `LinearGradientBrush.GradientStops`, `StartPoint` and `EndPoint` properties or can create and change it at runtime by using `GradientStopsEditor` and `StartPoint`, `EndPoint` input options available in the `GradientPropertyEditor`. By default, the linear gradient colors are combined horizontally by start and end points. The default value of `StartPoint` is (0.5, 0) and `EndPoint` is (0.5, 1).

![ColorPicker with LinearGradient Editor](ColorPicker-with-Gradient-Support_images/ColorPicker_LinearGradient_Mode.png)

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
{{ '[Startpoint](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_Startpoint)' | markdownify }}</td><td>
Indicates the Start point of LinearGradientBrush.</td></tr>
<tr>
<td>
{{ '[Endpoint](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_Endpoint)' | markdownify }}</td><td>
Indicates the End point of LinearGradientBrush.</td></tr>
</table>

{% tabs %}
{% highlight C# %}

class ViewModel {
    public Brush LinearGradientBrush {get; set;}
    public ViewModel() {
        //Creating LinearGradient brush
        LinearGradientBrush LinearBrush = new LinearGradientBrush();
        LinearBrush.StartPoint = new Point(0, 1);
        LinearBrush.EndPoint = new Point(1, 1);
        LinearBrush.GradientStops.Add(new GradientStop(Colors.Yellow, 0.0));
        LinearBrush.GradientStops.Add(new GradientStop(Colors.Red, 0.25));
        LinearBrush.GradientStops.Add(new GradientStop(Colors.Blue, 0.75));
        LinearBrush.GradientStops.Add(new GradientStop(Colors.LimeGreen, 1.0));  
              
        // Assigning a created linear gradient brush to `LinearGradientBrush` property
        LinearGradientBrush = LinearBrush;
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker Brush="{Binding LinearGradientBrush}"
                        Name="colorPicker">
    <syncfusion:ColorPicker.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:ColorPicker.DataContext>
</syncfusion:ColorPicker>


{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.DataContext = new ViewModel();
colorPicker.SetBinding(ColorPicker.BrushProperty, new Binding("LinearGradientBrush"));

{% endhighlight %}
{% endtabs %}

Here, Linear Gradient created by the gradient colors and their location along the gradient axis using the `GradientStop` objects.

![ColorPicker with Horizontal Linear Gradient Editor](ColorPicker-with-Gradient-Support_images/Default_LinearGradient.png)

#### Diagonal Linear Gradient (StartPoint(0,0), EndPoint(1,1))

![ColorPicker Linear Gradient Editor](ColorPicker-with-Gradient-Support_images/LinearGradient_Example_1.png)

#### Vertical Linear Gradient (StartPoint(0, 0.5), EndPoint(1, 0.5)

![ColorPicker Linear Gradient Editor](ColorPicker-with-Gradient-Support_images/LinearGradient_Example_2.png)

## Create Radial Gradient colors

We can create radial gradient colors by programmatically using the `RadialGradientBrush ` with its `RadialGradientBrush.GradientStops`,  `GradientOrigin`, `Radius` and `Centre` properties. Radial gradient brush colors can changed at runtime using the `GradientStopsEditor` and its `GradientOrigin`, `Centre` and `Radius` can be changed at runtime using the input options available in the `GradientPropertyEditor`.

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
{{ '[GradientOrigin](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_GradientOrigin)' | markdownify }}</td><td>
Indicates the gradient origin of RadialGradientBrush.</td></tr>
<tr>
<td>
{{ '[CentrePoint](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_CentrePoint)' | markdownify }}</td><td>
Indicates the centre point of RadialGradientBrush.</td></tr>
<tr>
<td>
{{ '[RadiusX](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_RadiusX)' | markdownify }}</td><td>
Indicates the X value in Radius of RadialGradientBrush.</td></tr>
<tr>
<td>
{{ '[RadiusY](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_RadiusY)' | markdownify }}</td><td>
Indicates the Y value in Radius of RadialGradientBrush.</td></tr>
</table>

{% tabs %}
{% highlight C# %}

class ViewModel {
    public Brush RadialGradientBrush { get; set; }    
    public ViewModel() {
         //Creating Radial Gradient brush
        RadialGradientBrush radialBrush = new RadialGradientBrush();
        radialBrush.GradientOrigin = new Point(0.5, 0.5);
        radialBrush.Center = new Point(0.5, 0.5);
        radialBrush.RadiusX = 0.5;
        radialBrush.RadiusY = 0.5;
        radialBrush.GradientStops.Add(new GradientStop(Colors.Yellow, 0.0));
        radialBrush.GradientStops.Add(new GradientStop(Colors.Red, 0.25));
        radialBrush.GradientStops.Add(new GradientStop(Colors.Blue, 0.75));
        radialBrush.GradientStops.Add(new GradientStop(Colors.LimeGreen, 1.0));

        // Assigning a created radial gradient brush to `RadialGradientBrush` property
        RadialGradientBrush = radialBrush;
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker Brush="{Binding RadialGradientBrush}"
                        Name="colorPicker">
    <syncfusion:ColorPicker.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:ColorPicker.DataContext>
</syncfusion:ColorPicker>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.DataContext = new ViewModel();
colorPicker.SetBinding(ColorPicker.BrushProperty, new Binding("RadialGradientBrush"));

{% endhighlight %}
{% endtabs %}

Here, Radial Gradient created by the gradient colors and their location along the gradient axis using the `GradientStop` objects.

![ColorPicker with Radial Gradient Editor](ColorPicker-with-Gradient-Support_images/Default_RadialGradient.png)

#### Gradient Origin (0.25, 0.25)

![ColorPicker Radial Gradient Editor with Gradient Origin point](ColorPicker-with-Gradient-Support_images/RadialGradient_Origin.png)

#### Centre (0.25, 0.25)

![ColorPicker Radial Gradient Editor with Centre point](ColorPicker-with-Gradient-Support_images/RadialGradient_Centre.png)

#### Radius (0.25, 0.25)

![ColorPicker Radial Gradient Editor with Radius](ColorPicker-with-Gradient-Support_images/RadialGradient_Radius.png)

## Reverse the Gradient Colors

[ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html) comes with the reverse button which helps in changing the gradient colors upside down or in case of radial gradient inside out. 

![ColorPicker with gradient color reverse button](ColorPicker-with-Gradient-Support_images/ColorPicker_Reverse_Button_change.png)

## Show selected gradient color name

By default, the selected Gradient mode name is displayed in `ColorPicker`. If we want to display the selected gradient color name instead of the Gradient mode name, use the [GradientBrushDisplayMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_GradientBrushDisplayMode) value as `Extended`. The default value of `GradientBrushDisplayMode` property is `Default`.

{% tabs %}
{% highlight xaml %}

<Syncfusion:ColorPicker x:Name="colorPicker" GradientBrushDisplayMode="Extended"/>

{% endhighlight %}
{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.GradientBrushDisplayMode =  GradientBrushDisplayMode.Extended;

{% endhighlight %}
{% endtabs %}

![ColorPicker displays the selected gradient color name](ColorPicker-with-Gradient-Support_images/Gradient_ColorName.png)

## Show gradient color value editor

We can display the gradient property editor either in popup mode or in extended mode. By default, the gradient property editor is displayed in the extended mode. If we want display the gradient property editor only in a popup, use the [GradientPropertyEditorMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_GradientPropertyEditorMode) property value as `PopUp`. 

{% tabs %}
{% highlight xaml %}

<Syncfusion:ColorPicker x:Name="colorPicker" GradientPropertyEditorMode="Popup"/>

{% endhighlight %}
{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.GradientPropertyEditorMode =  GradientPropertyEditorMode.Popup;

{% endhighlight %}
{% endtabs %}

![Colorpicker with popup and expanded gradient property editor](ColorPicker-with-Gradient-Support_images/Colorpicker_Popup_gradientEditor.png)

## Switch between Solid, Gradient mode

We can change the brush mode from solid to gradient or vice versa at runtime as well as programmatically. By default, the `Solid` brush mode is enabled. If we want `Gradient` brush mode, use the [BrushMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorEdit.html#Syncfusion_Windows_Shared_ColorEdit_BrushMode) property value as `Gradient`.

{% tabs %}
{% highlight xaml %}

<Syncfusion: ColorPicker x:Name="colorPicker" BrushMode="Gradient"/>

{% endhighlight %}

{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();
colorPicker.BrushMode = BrushModes.Gradient;

{% endhighlight %}
{% endtabs %}

![ColorPicker is in Gradient brush mode](ColorPicker-with-Gradient-Support_images/Brush_mode.png)

Here, The `ColorPicker` is in Gradient brush mode.

### Switch between Solid, Linear and Gradient brush mode

We can change the brush mode directly by clicking on the corresponding Solid, Linear or Gradient mode buttons which are placed in the bottom right corner of the `ColorPicker`.

![ColorPicker popup gradientEditor](ColorPicker-with-Gradient-Support_images/ColorPicker_Switch_brushes.png)

## Disable Switching between Solid, Linear and Gradient brush mode at runtime

 If we want to disable the Solid, Linear and Gradient brush mode transition at runtime, use the [EnableSolidToGradientSwitch](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html#Syncfusion_Windows_Shared_ColorPicker_EnableSolidToGradientSwitch) property value as `false`. It will hide the Solid, Linear and Gradient brush buttons. The Default value of `EnableSolidToGradientSwitch` property is `true`.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker x:Name="colorPicker" EnableSolidToGradientSwitch="false"/>

{% endhighlight %}
{% highlight C# %}

ColorPicker colorPicker = new ColorPicker ();
colorPicker.EnableSolidToGradientSwitch = false;

{% endhighlight %}
{% endtabs %}

![ColorPicker Solid to Gradient brush transition is disabled](ColorPicker-with-Gradient-Support_images/ColorPicker_EnableSolidToGradientSwitch.png)

## Gradient color changed notification

Selected gradient color changed in [ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html) can be examined using [SelectedBrushChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.ColorPicker.html) event.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker SelectedBrushChanged="ColorPicker_SelectedBrushChanged"
                        Name="colorPicker"/>

{% endhighlight %}
{% highlight c# %}

ColorPicker  colorPicker = new ColorPicker();
colorPicker.SelectedBrushChanged += ColorPicker_SelectedBrushChanged;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

//Invoked when the selected brush is changed
private void ColorPicker_SelectedBrushChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    // Enter your code here
}

{% endhighlight %}
{% endtabs %}

Click [here](https://github.com/SyncfusionExamples/wpf-colorpicker-examples/tree/master/Samples/LinearGradient) to download the sample that showcases the Linear GradientBrush and its additional features.

Click [here](https://github.com/SyncfusionExamples/wpf-colorpicker-examples/tree/master/Samples/RadialGradient) to download the sample that showcases the Radial GradientBrush and its additional features.