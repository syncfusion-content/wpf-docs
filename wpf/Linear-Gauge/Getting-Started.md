---
layout: post
title: Getting Started with WPF Linear Gauge control | Syncfusion
description: Learn here about getting started with Syncfusion WPF Linear Gauge (SfLinearGauge) control, its elements and more.
platform: wpf
control: SfLinearGauge
documentation: ug
---
# Getting Started with WPF Linear Gauge (SfLinearGauge)

This section explains the steps required to configure the [`SfLinearGauge`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfLinearGauge.html) control in a real-time scenario and provides a walk-through on its customization features.

## Adding gauge references

You can add gauge reference using one of the following methods:

**Method 1: Adding gauge reference from nuget.org**

Syncfusion WPF components are available in [`nuget.org`](https://www.nuget.org/). To add gauge to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.SfGauge.WPF](https://www.nuget.org/packages/Syncfusion.SfGauge.WPF), and then install it.

![Adding gauge reference from NuGet](Getting-Started_images/Adding gauge reference.png)

**Method 2: Adding gauge reference from toolbox**

You can drag the linear gauge control from the  toolbox and drop it to the designer. It will add the required assembly references automatically, and add the namespace to the page. 

**Method 3: Adding gauge assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/WPF/Assemblies

You can refer to [this](https://help.syncfusion.com/wpf/control-dependencies#sfgauge) link to know about the assemblies required for adding gauge to your project.

## Initialize gauge

Import  the [`SfLinearGauge`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfLinearGauge.html) namespace to your respective Window as in the following.

{% tabs %}

{% highlight xaml %}

xmlns:gauge="clr-namespace:Syncfusion.UI.Xaml.Gauges;assembly=Syncfusion.SfGauge.Wpf"

{% endhighlight %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Gauges;

{% endhighlight %}

{% endtabs %}

You can initialize an empty [`SfLinearGauge`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.SfLinearGauge.html) control.

{% tabs %}

{% highlight xaml %}

<gauge:SfLinearGauge/>

{% endhighlight %}

{% highlight c# %}

SfLinearGauge sfLinearGauge = new SfLinearGauge();
this.Content = sfLinearGauge;

{% endhighlight %}

{% endtabs %}

## Configuring scale

Scales is a collection of [`LinearScale`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html) which is used to indicate the numeric values. Scale bar, ticks, labels, ranges, and pointers are the sub elements of a scale.

The [`Minimum`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_Maximum) properties allow you to set the scale range.

{% tabs %}

{% highlight xaml %}

<gauge:SfLinearGauge>
    <gauge:SfLinearGauge.MainScale>
        <gauge:LinearScale ScaleBarStroke="#E0E0E0"
                           LabelStroke="#424242"
                           MajorTickStroke="Gray"
                           MajorTickSize="15"
                           MajorTickStrokeThickness="1"
                           MinorTickStroke="Gray"
                           MinorTickSize="7"
                           MinorTickStrokeThickness="1"
                           MinorTicksPerInterval="3"
                           ScaleBarLength="300"
                           ScaleBarSize="10">

        </gauge:LinearScale>
    </gauge:SfLinearGauge.MainScale>
</gauge:SfLinearGauge>


{% endhighlight %}

{% highlight c# %}

SfLinearGauge sfLinearGauge = new SfLinearGauge();
LinearScale linearScale = new LinearScale();
linearScale.LabelStroke = (SolidColorBrush)new BrushConverter().ConvertFrom("#424242");
linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);
linearScale.MajorTickSize = 15;
linearScale.MajorTickStrokeThickness = 1;
linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);
linearScale.MinorTickSize = 7;
linearScale.MinorTickStrokeThickness = 1;
linearScale.MinorTicksPerInterval = 3;
linearScale.ScaleBarStroke = (SolidColorBrush)new BrushConverter().ConvertFrom("#E0E0E0");
linearScale.ScaleBarLength = 300;
linearScale.ScaleBarSize = 10;
sfLinearGauge.MainScale = linearScale;
this.Content = sfLinearGauge;

{% endhighlight %}

{% endtabs %}

## Adding a symbol pointer

`SymbolPointer` is a shape that can be placed to mark the pointer value in gauge.

{% tabs %}

{% highlight xaml %}
 
<gauge:LinearScale.Pointers>
    <gauge:LinearPointer PointerType="SymbolPointer"
                         Value="60"
                         SymbolPointerHeight="10"
                         SymbolPointerWidth="10"
                         SymbolPointerPosition="Below"
                         SymbolPointerStroke="#757575" />
</gauge:LinearScale.Pointers>

{% endhighlight %}

{% highlight c# %}

LinearPointer linearPointer = new LinearPointer();
linearPointer.PointerType = LinearPointerType.SymbolPointer;
linearPointer.Value = 60;
linearPointer.SymbolPointerHeight = 10;
linearPointer.SymbolPointerWidth = 10;
linearPointer.SymbolPointerPosition = LinearSymbolPointersPosition.Below;
linearPointer.SymbolPointerStroke = (SolidColorBrush)new BrushConverter().ConvertFrom("#757575");
linearScale.Pointers.Add(linearPointer);

{% endhighlight %}

{% endtabs %}

## Adding a bar pointer

`BarPointer` is used to mark the scale values. This starts at the beginning of gauge and ends at the pointer value.

{% tabs %}

{% highlight xaml %}

<gauge:LinearScale.Pointers>
   <gauge:LinearPointer PointerType="BarPointer"
                        Value="50"
                        BarPointerStroke="#757575"
                        BarPointerStrokeThickness="10" />
</gauge:LinearScale.Pointers>

{% endhighlight %}

{% highlight c# %}

LinearPointer linearPointer1 = new LinearPointer();
linearPointer1.PointerType = LinearPointerType.BarPointer;
linearPointer1.Value = 50;
linearPointer1.BarPointerStroke = (SolidColorBrush)new BrushConverter().ConvertFrom("#757575");
linearPointer1.BarPointerStrokeThickness = 10;
linearScale.Pointers.Add(linearPointer1);

{% endhighlight %}

{% endtabs %}

## Adding ranges

You can categorize the scale values using the start and end values properties in [`LinearRange`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearRange.html). You can add multiple ranges for a scale using the [`Ranges`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Gauges.LinearScale.html#Syncfusion_UI_Xaml_Gauges_LinearScale_Ranges) property.

{% tabs %}

{% highlight xaml %}

<gauge:LinearScale.Ranges>
    <gauge:LinearRange StartValue="0"
                       EndValue="40"
                       RangeStroke="#27BEB7"
                       StartWidth="10"
                       EndWidth="10"
                       RangeOffset="0.4" />
    <gauge:LinearRange StartValue="40"
                       EndValue="100"
                       RangeStroke="LightCyan"
                       RangeOffset="0.4"
                       StartWidth="10"
                       EndWidth="10" />
</gauge:LinearScale.Ranges>


{% endhighlight %}

{% highlight c# %}

//Adding Range
LinearRange linearRange = new LinearRange();
linearRange.StartValue = 0;
linearRange.EndValue = 40;
linearRange.RangeStroke = (SolidColorBrush)new BrushConverter().ConvertFrom("#27BEB7");
linearRange.StartWidth = 10;
linearRange.EndWidth = 10;
linearRange.RangeOffset = 0.4;
linearScale.Ranges.Add(linearRange);

LinearRange linearRange1 = new LinearRange();
linearRange1.StartValue = 40;
linearRange1.EndValue = 100;
linearRange1.RangeStroke = new SolidColorBrush(Colors.LightCyan);
linearRange1.RangeOffset = 0.4;
linearRange1.StartWidth = 10;
linearRange1.EndWidth = 10;
linearScale.Ranges.Add(linearRange1);

{% endhighlight %}

{% endtabs %}

The following code example is the complete code of the previous configurations.

{% tabs %}

{% highlight xaml %}

<gauge:SfLinearGauge>
    <gauge:SfLinearGauge.MainScale>
        <gauge:LinearScale LabelStroke="#424242"
                           MajorTickStroke="Gray"
                           MajorTickSize="15"
                           MajorTickStrokeThickness="1"
                           MinorTickStroke="Gray"
                           MinorTickSize="7"
                           MinorTickStrokeThickness="1"
                           MinorTicksPerInterval="3"
                           ScaleBarStroke="#E0E0E0"
                           ScaleBarLength="300"
                           ScaleBarSize="10">

            <gauge:LinearScale.Pointers>
                <gauge:LinearPointer PointerType="SymbolPointer"
                                     Value="60"
                                     SymbolPointerHeight="10"
                                     SymbolPointerWidth="10"
                                     SymbolPointerPosition="Below"
                                     SymbolPointerStroke="#757575" />
                <gauge:LinearPointer PointerType="BarPointer"
                                     Value="50"
                                     BarPointerStroke="#757575"
                                     BarPointerStrokeThickness="10" />
            </gauge:LinearScale.Pointers>

            <gauge:LinearScale.Ranges>
                <gauge:LinearRange StartValue="0"
                                   EndValue="40"
                                   RangeStroke="#27BEB7"
                                   StartWidth="10"
                                   EndWidth="10"
                                   RangeOffset="0.4" />
                <gauge:LinearRange StartValue="40"
                                   EndValue="100"
                                   RangeStroke="LightCyan"
                                   RangeOffset="0.4"
                                   StartWidth="10"
                                   EndWidth="10" />
            </gauge:LinearScale.Ranges>
        </gauge:LinearScale>
    </gauge:SfLinearGauge.MainScale>
</gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

SfLinearGauge sfLinearGauge = new SfLinearGauge();
LinearScale linearScale = new LinearScale();
linearScale.LabelStroke = (SolidColorBrush)new BrushConverter().ConvertFrom("#424242");
linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);
linearScale.MajorTickSize = 15;
linearScale.MajorTickStrokeThickness = 1;
linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);
linearScale.MinorTickSize = 7;
linearScale.MinorTickStrokeThickness = 1;
linearScale.MinorTicksPerInterval = 3;
linearScale.ScaleBarStroke = (SolidColorBrush)new BrushConverter().ConvertFrom("#E0E0E0");
linearScale.ScaleBarLength = 300;
linearScale.ScaleBarSize = 10;

//Adding symbol pointer
LinearPointer linearPointer = new LinearPointer();
linearPointer.PointerType = LinearPointerType.SymbolPointer;
linearPointer.Value = 60;
linearPointer.SymbolPointerHeight = 10;
linearPointer.SymbolPointerWidth = 10;
linearPointer.SymbolPointerPosition = LinearSymbolPointersPosition.Below;
linearPointer.SymbolPointerStroke = (SolidColorBrush)new BrushConverter().ConvertFrom("#757575");
linearScale.Pointers.Add(linearPointer);

////Adding bar pointer
LinearPointer linearPointer1 = new LinearPointer();
linearPointer1.PointerType = LinearPointerType.BarPointer;
linearPointer1.Value = 50;
linearPointer1.BarPointerStroke = (SolidColorBrush)new BrushConverter().ConvertFrom("#757575");
linearPointer1.BarPointerStrokeThickness = 10;
linearScale.Pointers.Add(linearPointer1);

//Adding Range
LinearRange linearRange = new LinearRange();
linearRange.StartValue = 0;
linearRange.EndValue = 40;
linearRange.RangeStroke = (SolidColorBrush)new BrushConverter().ConvertFrom("#27BEB7");
linearRange.StartWidth = 10;
linearRange.EndWidth = 10;
linearRange.RangeOffset = 0.4;
linearScale.Ranges.Add(linearRange);

LinearRange linearRange1 = new LinearRange();
linearRange1.StartValue = 40;
linearRange1.EndValue = 100;
linearRange1.RangeStroke = new SolidColorBrush(Colors.LightCyan);
linearRange1.RangeOffset = 0.4;
linearRange1.StartWidth = 10;
linearRange1.EndWidth = 10;
linearScale.Ranges.Add(linearRange1);
sfLinearGauge.MainScale = linearScale;
this.Content = sfLinearGauge;

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates the result of the previous codes.

![Getting started image](Getting-Started_images/Getting_started_img1.png)


You can find the complete getting started sample from this [`link`](https://github.com/SyncfusionExamples/WPF-UG-getting-started-samples/tree/master/GettingStartedLinearGauge).

## Theme

LinearGauge supports various built-in themes. Refer to the below links to apply themes for the LinearGauge,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF LinearGauge](Getting-Started_images/Theme.png)

## See also

[How to apply themes for SfLinearGauge](https://www.syncfusion.com/kb/2534/how-to-apply-themes-for-sflineargauge)