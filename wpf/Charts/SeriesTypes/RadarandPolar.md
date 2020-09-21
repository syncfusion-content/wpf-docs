---
layout: post
title: Radar and Polar Charts | SfChart | Wpf | Syncfusion
description: This section explains Radar and Polar Charts and its properties for customization in WPF Charts (SfChart)
platform: wpf
control: SfChart
documentation: ug
---

# Radar and Polar Charts in WPF Chart (SfChart)

## Radar

[`RadarSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.RadarSeries.html#) represents a collection of data, displayed by quantitative variables, represented by axes starting from the same point. The relative position and angle of the axes is not uniform. 

The following code example illustrates the use of radar series:

{% tabs %}

{% highlight xaml %}

<chart:RadarSeries ItemsSource="{Binding PlantDetails}" 

Interior="#BCBCBC"

XBindingPath="Direction"

YBindingPath="Tree" >

</chart:RadarSeries>        

{% endhighlight %}

{% highlight c# %}

RadarSeries series = new RadarSeries()
{

    ItemsSource = new ViewModel().PlantDetails,

    XBindingPath = "Direction",

    YBindingPath = "Tree",

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0XBC))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Radar chart type in WPF](Series_images/radar.png)


## Polar

[`PolarSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PolarSeries.html#) displays data points that are grouped by category, on a 360 degree circle. The following code example shows how to use polar series.

{% tabs %}

{% highlight xaml %}

<chart:PolarSeries Interior="#4A4A4A" 

ItemsSource="{Binding PlantDetails}"  

XBindingPath="Direction"

YBindingPath="Tree" />                 

{% endhighlight %}

{% highlight c# %}

PolarSeries series = new PolarSeries()
{

    ItemsSource = new ViewModel().PlantDetails,

    XBindingPath = "Direction",

    YBindingPath = "Tree",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Polar chart type in WPF](Series_images/polar.png)


The Radar and Polar charts having the following properties in common:

* [`IsClosed`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PolarRadarSeriesBase.html#Syncfusion_UI_Xaml_Charts_PolarRadarSeriesBase_IsClosed)
* [`DrawType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PolarRadarSeriesBase.html#Syncfusion_UI_Xaml_Charts_PolarRadarSeriesBase_DrawType)
* `PolarAngle`

### IsClosed

This property used to draw the closed path as below.

{% tabs %}

{% highlight xaml %}

<chart:PolarSeries x:Name="series1" Interior="#4A4A4A" 

ItemsSource="{Binding PlantDetails}"  

Label="Amount Spent" DrawType="Line" IsClosed="False" 

XBindingPath="Direction" YBindingPath="Tree" 

StrokeThickness="2" />

{% endhighlight %}

{% highlight c# %}

PolarSeries series = new PolarSeries()
{

    ItemsSource = new ViewModel().PlantDetails,

    XBindingPath = "Direction",

    YBindingPath = "Tree",

    IsClosed = false,

    DrawType = ChartSeriesDrawType.Line,

    Label = "Amount Spent",

    StrokeThickness = 2,

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Closed polar series in WPF Chart](Series_images/isclosed.png)

### DrawType

This property defines type of curve, whether its [`Line`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesDrawType.html) or [`Area`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesDrawType.html).

**DrawType** **as** **Area**

{% tabs %}

{% highlight xaml %}

<chart:PolarSeries x:Name="series1" Interior="#4A4A4A" 

ItemsSource="{Binding PlantDetails}"  

DrawType="Area" IsClosed="True" 

XBindingPath="Direction" YBindingPath="Tree" />

{% endhighlight %}

{% highlight c# %}

PolarSeries series = new PolarSeries()
{

    ItemsSource = new ViewModel().PlantDetails,

    XBindingPath = "Direction",

    YBindingPath = "Tree",

    IsClosed = True,

    DrawType = ChartSeriesDrawType.Area,

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Draw type support for polar series in WPF Chart](Series_images/drawtype_area.png)

**DrawType** **as** **Line**

{% tabs %}

{% highlight xaml %}

<chart:PolarSeries x:Name="series1" Interior="#4A4A4A" 

ItemsSource="{Binding PlantDetails}"  

DrawType="Line" IsClosed="True" 

XBindingPath="Direction" YBindingPath="Tree" 

StrokeThickness="2" />

{% endhighlight %}

{% highlight c# %}

PolarSeries series = new PolarSeries()
{

    ItemsSource = new ViewModel().PlantDetails,

    XBindingPath = "Direction",

    YBindingPath = "Tree",

    IsClosed = True,

    DrawType = ChartSeriesDrawType.Line,

    StrokeThickness = 2,

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Draw type support for polar series in WPF Chart](Series_images/drawtype_line.png)

### Polar Angle

[`Chart axis`](https://help.syncfusion.com/wpf/sfchart/axis) provides support to render polar and radar series on 0,90,180 and 270 degrees. It can be achieved by its `PolarAngle` property.The `PolarAngle` is type of `ChartPolarAngle` and its default value is `Rotate270`.`Rotate0`, `Rotate90` and `Rotate180` are another supported values of `PolarAngle`. Both the primary and secondary axes can be rotated individually based on its `PolarAngle` value.

**Rotate0**

The below snippet explains how the axes of series has been rotated when `PolarAngle` value is [`Rotate0`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPolarAngle.html),

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis  PolarAngle="Rotate0"/>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis PolarAngle="Rotate0"/>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

 chart.PrimaryAxis = new CategoryAxis()

 {

    PolarAngle = ChartPolarAngle.Rotate0

 };

chart.SecondaryAxis = new NumericalAxis()

{

    PolarAngle = ChartPolarAngle.Rotate0
            
};

{% endhighlight %}

{% endtabs %}

![Rotation support for polar series in WPF Chart](Series_images/Rotate0.png)


**Rotate90**

The below snippet explains how the axes of series has been rotated when `PolarAngle` value is [`Rotate90`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPolarAngle.html),

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis  PolarAngle="Rotate90"/>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis PolarAngle="Rotate90"/>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

 chart.PrimaryAxis = new CategoryAxis()

 {

    PolarAngle = ChartPolarAngle.Rotate90

 };

chart.SecondaryAxis = new NumericalAxis()

{

    PolarAngle = ChartPolarAngle.Rotate90
            
};

{% endhighlight %}

{% endtabs %}

![Rotation support for polar series in WPF Chart](Series_images/Rotate90.png)


**Rotate180**

The below snippet explains how the axes of series has been rotated when `PolarAngle` value is [`Rotate180`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPolarAngle.html),

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis  PolarAngle="Rotate180"/>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis PolarAngle="Rotate180"/>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

 chart.PrimaryAxis = new CategoryAxis()

 {

    PolarAngle = ChartPolarAngle.Rotate180

 };

chart.SecondaryAxis = new NumericalAxis()

{

    PolarAngle = ChartPolarAngle.Rotate180
            
};

{% endhighlight %}

{% endtabs %}

![Rotation support for polar series in WPF Chart](Series_images/Rotate180.png)


**Rotate270**

The below snippet explains how the axes of series has been rotated, when `PolarAngle` value is [`Rotate270`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPolarAngle.html),

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis  PolarAngle="Rotate270"/>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis PolarAngle="Rotate270"/>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

 chart.PrimaryAxis = new CategoryAxis()

 {

    PolarAngle = ChartPolarAngle.Rotate270

 };

chart.SecondaryAxis = new NumericalAxis()

{

    PolarAngle = ChartPolarAngle.Rotate270
            
};

{% endhighlight %}

{% endtabs %}

![Rotation support for polar series in WPF Chart](Series_images/Rotate270.png)
