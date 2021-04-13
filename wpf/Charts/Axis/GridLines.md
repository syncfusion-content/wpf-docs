---
layout: post
title: GridLines | Axis| SfChart | WPF | Syncfusion 
description: This section explains about chart axis gridlines, it's type majorgridLinestyle and minorgridlinestyle of chart axis in WPF chart
platform: wpf
control: SfChart
documentation: ug
---

# GridLines in WPF Chart

## GridLines

By default, gridlines are automatically added to the [`ChartAxis`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#) in its defined intervals. The chart axis supports customization of gridline. The visibility of the gridlines can be controlled using the [`ShowGridLines`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_ShowGridLines) property.

The following code example illustrates the [`ShowGridLines`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_ShowGridLines) property as false in the primary axis.

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300"  Palette="BlueChrome">

<chart:SfChart.PrimaryAxis>
<chart:CategoryAxis Interval="1" ShowGridLines="False" />
</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>
<chart:NumericalAxis />
</chart:SfChart.SecondaryAxis>

<chart:SfChart.Series>
<chart:ColumnSeries ItemsSource="{Binding NumericData}" XBindingPath="Month" YBindingPath="Profit"/>
</chart:SfChart.Series>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

chart.PrimaryAxis = new NumericalAxis()
{
    Interval = 1,
    ShowGridLines = false, 
};

chart.SecondaryAxis = new NumericalAxis();

ColumnSeries series = new ColumnSeries();
series.ItemsSource = (new ViewModel()).NumericalData;
series.XBindingPath = "Month";
series.YBindingPath = "Profit";
chart.Series.Add(series);
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Gridlines customization support in WPF Chart](Axis_image/WPF_Chart_Axis_ShowGridLines.png)

Style can also be applied to Major and Minor Gridlines using [`MajorGridLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_MajorGridLineStyle) and [`MinorGridLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_MinorGridLineStyle) properties.

## MajorGridLineStyle

[`MajorGridLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_MajorGridLineStyle) in chart axis is used to customize the appearance of majorgridlines. The following code example illustrates customize appearance of majorgridlines in the primary axis.

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300"  Palette="BlueChrome">

<chart:SfChart.Resources>
<Style TargetType="Line" x:Key="lineStyle">          
<Setter Property="StrokeThickness" Value="2"/>
<Setter Property="Stroke" Value="Black"/>
<Setter Property="StrokeDashArray" Value="3,3"/>  
</Style>
</chart:SfChart.Resources>
          
<chart:SfChart.PrimaryAxis>
<chart:NumericalAxis Interval="1" MajorGridLineStyle="{StaticResource lineStyle}"/>
</chart:SfChart.PrimaryAxis>
            
<chart:SfChart.SecondaryAxis>
<chart:NumericalAxis Minimum="800" Maximum="2200"/>
</chart:SfChart.SecondaryAxis>

<chart:SfChart.Series>
<chart:SplineSeries ItemsSource="{Binding NumericData}" XBindingPath="Month" YBindingPath="Profit"/>
</chart:SfChart.Series>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

chart.PrimaryAxis = new NumericalAxis()
{
    Interval = 1,
    MajorGridLineStyle = chart.Resources["lineStyle"] as Style    
};

chart.SecondaryAxis = new NumericalAxis()
{ 
    Minimum= 800,
    Maximum= 2200
};

SplineSeries series = new SplineSeries();
series.ItemsSource = (new ViewModel()).NumericalData;
series.XBindingPath = "Month";
series.YBindingPath = "Profit";
chart.Series.Add(series);
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![MajorGridLineStyle support in WPF Chart](Axis_image/WPF_Chart_Axis_MajorGridLineStyle.png)

## MinorGridLineStyle

[`MinorGridLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_MinorGridLineStyle) will be added automatically when the small tick lines is defined inside the chart area.

{% tabs %}

{% highlight xaml %}

<chart:SfChart Width="500" Height="300"  Palette="BlueChrome">

<chart:SfChart.Resources>
<Style TargetType="Line" x:Key="lineStyle">
<Setter Property="StrokeThickness" Value="1"/>
<Setter Property="Stroke" Value="DarkGray"/>
<Setter Property="StrokeDashArray" Value="3,3"/>
</Style>
</chart:SfChart.Resources>

<chart:SfChart.PrimaryAxis>
<chart:NumericalAxis Interval="1" MajorGridLineStyle="{StaticResource lineStyle}"/>
</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>
<chart:NumericalAxis Minimum="800" Maximum="2200" SmallTicksPerInterval="3" MinorGridLineStyle="{StaticResource lineStyle}"/>
</chart:SfChart.SecondaryAxis>

<chart:SfChart.Series>
<chart:SplineSeries ItemsSource="{Binding NumericData}" XBindingPath="Month" YBindingPath="Profit"/>
</chart:SfChart.Series>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart() 
{ 
    Height = 300,
    Width = 500, 
    Palette = ChartColorPalette.BlueChrome
};

chart.PrimaryAxis = new NumericalAxis()
{
    Interval = 1,
    MinorGridLineStyle = chart.Resources["lineStyle"] as Style    
};

chart.SecondaryAxis = new NumericalAxis()
{ 
    Minimum= 800,
    Maximum= 2200,
    SmallTicksPerInterval = 3,
    MinorGridLineStyle = chart.Resources["lineStyle"] as Style
};

SplineSeries series = new SplineSeries();
series.ItemsSource = (new ViewModel()).NumericalData;
series.XBindingPath = "Month";
series.YBindingPath = "Profit";
chart.Series.Add(series);
this.Content = chart;

{% endhighlight %}

{% endtabs %}

![Gridlines customization support in WPF Chart](Axis_image/WPF_Chart_Axis_MinorGridLineStyle.png)
