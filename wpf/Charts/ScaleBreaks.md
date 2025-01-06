---
layout: post
title: Scale Breaks in WPF Charts control | Syncfusion
description: Learn here all about Scale Breaks support in Syncfusion® WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---
# Scale Breaks in WPF Charts (SfChart)

Scale break is a stripe drawn in the chart area to denote the break in the continuity of data points. Scale breaks are useful when there is a large difference in the data points. Scale break allows you to have different ranges on the same axis to visualize the data effectively.

## Positioning the Breaks

SfChart provides [`Start`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisScaleBreak.html#Syncfusion_UI_Xaml_Charts_ChartAxisScaleBreak_Start) and [`End`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisScaleBreak.html#Syncfusion_UI_Xaml_Charts_ChartAxisScaleBreak_End) properties for defining the scale break range (ranges that needs to be skipped). These values are based on axis values. 

The following image has data points with both greater and smaller magnitude, but the segments with smaller values is not visualized properly.

![WPF Chart displays ScaleBreaks Position](ScaleBreak_images/wpf-chart-scalebreak-position.jpeg)


Applying scale breaks helps in proper visualization of all the data points.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis>                                

<chart:NumericalAxis.AxisScaleBreaks>                     

<chart:ChartAxisScaleBreak Start="300"

End="8500">

</chart:ChartAxisScaleBreak>

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

NumericalAxis axis = new NumericalAxis();

ChartAxisScaleBreak scaleBreak = new ChartAxisScaleBreak();

scaleBreak.Start = 300;

scaleBreak.End = 8500;

axis.AxisScaleBreaks.Add(scaleBreak);

chart.SecondaryAxis = axis;

{% endhighlight %}

{% endtabs %}

![WPF Chart displays ScaleBreaks Position based on Axis Value](ScaleBreak_images/wpf-chart-scalebreak-based-on-axis.jpeg)


## Break Position Customization

For the defined break range, its position in the chart area can be customized using the [`BreakPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.NumericalAxis.html#Syncfusion_UI_Xaml_Charts_NumericalAxis_BreakPosition) property in numerical axis.

Break position is determined based on the following factors:

### Data Count

Based on the number of data points that fall in axis ranges (other than break range) scale break will be positioned.

In the below image the range [0,350] contains maximum number of data compared to the range 

[8000, 10000] hence the break is positioned in such a way that allocates more space to the range [0,350].

Range [0,350] takes nearly 4/5th of the axis height and the range [8000,10000] takes 1/5th.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis x:Name="axis" BreakPosition="DataCount">                                

<chart:NumericalAxis.AxisScaleBreaks>                     

<chart:ChartAxisScaleBreak Start="350"

End="8000">  

</chart:ChartAxisScaleBreak>

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

NumericalAxis axis = new NumericalAxis();

axis.BreakPosition = ScaleBreakPosition.DataCount;

ChartAxisScaleBreak scaleBreak = new ChartAxisScaleBreak();

scaleBreak.Start = 350;

scaleBreak.End = 8000;

axis.AxisScaleBreaks.Add(scaleBreak);

chart.SecondaryAxis = axis;

{% endhighlight %}

{% endtabs %}

![WPF Chart displays ScaleBreak Position based on Data Count](ScaleBreak_images/wpf-chart-scalebreak-position-based-on-data.jpeg)


### Scale

[`Scale`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ScaleBreakPosition.html) option allows you to position the breaks based on the delta of each axis range relative to the other.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis x:Name="axis" BreakPosition="Scale">                                

<chart:NumericalAxis.AxisScaleBreaks>                     

<chart:ChartAxisScaleBreak Start="350"

End="8000">  

</chart:ChartAxisScaleBreak>

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

NumericalAxis axis = new NumericalAxis();

axis.BreakPosition = ScaleBreakPosition.Scale;

ChartAxisScaleBreak scaleBreak = new ChartAxisScaleBreak();

scaleBreak.Start = 350;

scaleBreak.End = 8000;

axis.AxisScaleBreaks.Add(scaleBreak);

chart.SecondaryAxis = axis;

{% endhighlight %}

{% endtabs %}

![WPF Chart displays ScaleBreak Position based on Scale](ScaleBreak_images/wpf-chart-scalebreak-based-on-scale.jpeg)


### Percent

Percent option allows to position the breaks at the specified percentage of the axis available height.

Percentage can be specified using [`BreakPercent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisScaleBreak.html#Syncfusion_UI_Xaml_Charts_ChartAxisScaleBreak_BreakPercent) property. Default BreakPercent value is 50.

In the below image, each break is given percent value as 50. First break is positioned at the 50% of the axis, and the next break is positioned at 50% of the remaining space and so on.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis x:Name="axis" BreakPosition="Percent ">                                

<chart:NumericalAxis.AxisScaleBreaks>                     

<chart:ChartAxisScaleBreak Start="300"

End="8000" BreakPercent="50"> 

</chart:ChartAxisScaleBreak>                     

<chart:ChartAxisScaleBreak Start="12500"

End="19000" BreakPercent="50"> 

</chart:ChartAxisScaleBreak>

</chart:NumericalAxis.AxisScaleBreaks>

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

NumericalAxis axis = new NumericalAxis();

axis.BreakPosition = ScaleBreakPosition.Percent;

ChartAxisScaleBreak scaleBreak1 = new ChartAxisScaleBreak();

scaleBreak1.Start = 300;

scaleBreak1.End = 8000;

scaleBreak1.BreakPercent = 50;

axis.AxisScaleBreaks.Add(scaleBreak1);

ChartAxisScaleBreak scaleBreak2 = new ChartAxisScaleBreak();

scaleBreak2.Start = 12500;

scaleBreak2.End = 19000;

scaleBreak2.BreakPercent = 50;

axis.AxisScaleBreaks.Add(scaleBreak2);

chart.SecondaryAxis = axis;

{% endhighlight %}

{% endtabs %}

![WPF Chart displays ScaleBreak Position based on Percentage](ScaleBreak_images/wpf-chart-scalebreak-based-on-percentage.jpeg)


## Multiple Breaks

Multiple breaks can be included in the chart.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis>                                

<chart:NumericalAxis.AxisScaleBreaks>                     

<chart:ChartAxisScaleBreak Start="300"

End="8000"> 

</chart:ChartAxisScaleBreak>                   

<chart:ChartAxisScaleBreak Start="12500"

End="19000"> 

</chart:ChartAxisScaleBreak>

</chart:NumericalAxis.AxisScaleBreaks>

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

NumericalAxis axis = new NumericalAxis();

ChartAxisScaleBreak scaleBreak1 = new ChartAxisScaleBreak();

scaleBreak1.Start = 300;

scaleBreak1.End = 8000;

axis.AxisScaleBreaks.Add(scaleBreak1);

ChartAxisScaleBreak scaleBreak2 = new ChartAxisScaleBreak();

scaleBreak2.Start = 12500;

scaleBreak2.End = 19000;

axis.AxisScaleBreaks.Add(scaleBreak2);

chart.SecondaryAxis = axis;

{% endhighlight %}

{% endtabs %}

![Multiple ScaleBreaks in WPF Chart](ScaleBreak_images/wpf-chart-multiple-scale-breaks.jpeg)


## Customization

The following are the customizing options for scale break.

Line type such as [`Wave`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BreakLineType.html) or [`StraightLine`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BreakLineType.html), background, spacing, stroke, stroke thickness of the scale break can be customized using [`LineType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisScaleBreak.html#Syncfusion_UI_Xaml_Charts_ChartAxisScaleBreak_LineType), [`Fill`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisScaleBreak.html#Syncfusion_UI_Xaml_Charts_ChartAxisScaleBreak_Fill), [`BreakSpacing`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisScaleBreak.html#Syncfusion_UI_Xaml_Charts_ChartAxisScaleBreak_BreakSpacing), [`Stroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisScaleBreak.html#Syncfusion_UI_Xaml_Charts_ChartAxisScaleBreak_Stroke), [`StrokeThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisScaleBreak.html#Syncfusion_UI_Xaml_Charts_ChartAxisScaleBreak_StrokeThickness) properties respectively.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis>                                

<chart:NumericalAxis.AxisScaleBreaks>                     

<chart:ChartAxisScaleBreak Start="300"  BreakSpacing="12"

End="8500" LineType="Wave" 

Fill="PaleTurquoise"

Stroke="Black" StrokeThickness="1.2" >  

</chart:ChartAxisScaleBreak>

</chart:NumericalAxis.AxisScaleBreaks> 

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

NumericalAxis axis = new NumericalAxis();

ChartAxisScaleBreak scaleBreak = new ChartAxisScaleBreak();

scaleBreak.Start = 300;

scaleBreak.End = 8500;

scaleBreak.LineType = BreakLineType.Wave;

scaleBreak.BreakSpacing = 12;

scaleBreak.Fill = new SolidColorBrush(Colors.PaleTurquoise);

scaleBreak.Stroke = new SolidColorBrush(Colors.Black);

scaleBreak.StrokeThickness = 1.2;

axis.AxisScaleBreaks.Add(scaleBreak);

chart.SecondaryAxis = axis;

{% endhighlight %}

{% endtabs %}

![Customization of ScaleBreaks in WPF Chart](ScaleBreak_images/wpf-chart-scalebreak-customization.jpeg)


N> You can refer to our [WPF Charts](https://www.syncfusion.com/wpf-controls/charts) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Charts example](https://github.com/syncfusion/wpf-demos) to knows various chart types and how to easily configured with built-in support for creating stunning visual effects.