---
layout: post
title: Fast Bitmap Series in WPF Charts control | Syncfusion
description: Learn here all about Fast Bitmap Series support in Syncfusion® WPF Charts (SfChart) control and more.
platform: wpf
control: SfChart
documentation: ug
---

# Fast Bitmap Series in WPF Charts (SfChart)

A fast bitmap chart displays a series of segments rendered using WritableBitmap. 

## Fast Line Bitmap 

[`FastLineBitmapSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastLineBitmapSeries.html#) displays a series of line segments rendered using WritableBitmap. The advantage of FastLineBitmapSeries renders a million data point in a fraction of seconds.

The following code example shows how to use the fast line bitmap series:

{% tabs %}

{% highlight xaml %}

<chart:FastLineBitmapSeries x:Name="FastLineSeries" ItemsSource="{Binding Data}"

XBindingPath="Date" Interior="#7F7F7F" 

YBindingPath="Value" />

{% endhighlight %}

{% highlight c# %}

FastLineBitmapSeries series = new FastLineBitmapSeries()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "Date",

    YBindingPath = "Value",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0x7F))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF FastLineBitmap Chart Type](FastChart_Images/wpf-fastlinebitmap-chart-type.png)

Like FastLineSeries, this bitmap series is also having line properties. 

N> As it was rendered using bitmap, there might be some jagged lines at edges. This is can be reduced using [`EnableAntiAliasing`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastLineBitmapSeries.html#Syncfusion_UI_Xaml_Charts_FastLineBitmapSeries_EnableAntiAliasing) property.

{% tabs %}

{% highlight xaml %}

<chart:FastLineBitmapSeries x:Name="FastLineSeries" 

XBindingPath="Date" Interior="#7F7F7F" 

StrokeDashArray="5,5"

YBindingPath="Value" EnableAntiAliasing="True"/>

{% endhighlight %}

{% highlight c# %}

FastLineBitmapSeries series = new FastLineBitmapSeries()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "Date",

    YBindingPath = "Value",

    EnableAntiAliasing =true,

    StrokeDashArray =new DoubleCollection() { 5,5},

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0x7F))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF AntiAliasing support for FastLine Chart](FastChart_Images/wpf-anti-aliasing-support-for-fastline-chart.png)


## Fast Column Bitmap

[`FastColumnBitmapSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastColumnBitmapSeries.html#) is used to boost up the performance of the ColumnSeries.

{% tabs %}

{% highlight xaml %}

<chart:FastColumnBitmapSeries Interior="#7F7F7F"

ItemsSource="{Binding List}" 

XBindingPath="Date" YBindingPath="Price" />

{% endhighlight %}

{% highlight c# %}

FastColumnBitmapSeries series = new FastColumnBitmapSeries()
{

    ItemsSource = new ViewModel().List,

    XBindingPath = "Date",

    YBindingPath = "Value",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0x7F))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF FastColumnBitmap Chart Type](FastChart_Images/wpf-fastcolumnbitmap-chart-type.png)

## Fast Bar Bitmap

[`FastBarBitmapSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastBarBitmapSeries.html) is used to boost up the performance of the series.

{% tabs %}

{% highlight xaml %}

<chart:FastBarBitmapSeries x:Name="FastBarBitmapSeries" ItemsSource="{Binding List}" 

XBindingPath="Date" YBindingPath="Price" 

Interior="#7F7F7F"/>

{% endhighlight %}

{% highlight c# %}

FastBarBitmapSeries series = new FastBarBitmapSeries()
{

    ItemsSource = new ViewModel().List,

    XBindingPath = "Date",

    YBindingPath = "Value",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0x7F))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF FastBarBitmap Chart Type](FastChart_Images/wpf-fastbarbitmap-chart-type.png)


## Fast Candle Bitmap

[`FastCandleBitmapSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastCandleBitmapSeries.html) renders using bitmap and it displays each data point as a combination of a vertical column and a vertical line, like CandleSeries. 

{% tabs %}

{% highlight xaml %}

<chart:FastCandleBitmapSeries ItemsSource="{Binding TestingModel}" 

XBindingPath="X" High="Y" 

Low="Y1" Open="Y2" Close="Y3" 

BullFillColor="#BCBCBC" 

BearFillColor="#4A4A4A"  />

{% endhighlight %}

{% highlight c# %}

FastCandleBitmapSeries series = new FastCandleBitmapSeries()
{

    ItemsSource = new ViewModel().TestingModel,

    XBindingPath = "X",

    High="Y", Low="Y1",

    Open="Y2", Close="Y3",

    BullFillColor = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC)),

    BearFillColor = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF FastCandleBitmap Chart Type](FastChart_Images/wpf-fastcandlebitmap-chart-type.png)


## Fast HiLo Bitmap

[`FastHiLoBitmapSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastHiLoBitmapSeries.html#) represents a series of line segments with high and low values rendered using WritableBitmap. 

{% tabs %}

{% highlight xaml %}

<chart:FastHiLoBitmapSeries StrokeThickness="5" ItemsSource="{Binding List}"          

Interior="#7F7F7F" XBindingPath="Date" High="Stock"     

Low="Price"/>

{% endhighlight %}

{% highlight C# %}

FastHiLoBitmapSeries series = new FastHiLoBitmapSeries()
{

    ItemsSource = new ViewModel().List,

    XBindingPath = "Date",

    High = "Stock",Low = "Price",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0X7F)),

    StrokeThickness = 5

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF FastHiLoBitmap Chart Type](FastChart_Images/wpf-fasthilobitmap-chart-type.png)

## Fast OHLC Bitmap

[`FastHiLoOpenCloseBitmapSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastHiLoOpenCloseBitmapSeries.html#) are rendered using WritableBitmap like other bitmap series. The following code example illustrates the use of OHLC bitmap series.

{% tabs %}

{% highlight xaml %}

<chart:FastHiLoOpenCloseBitmapSeries ItemsSource="{Binding TestingModel}" 

XBindingPath="X" High="Y" Low="Y1" Open="Y2"        

Close="Y3"   BullFillColor="#7F7F7F"      

BearFillColor="#4A4A4A"/>

{% endhighlight %}

{% highlight c# %}

FastHiLoOpenCloseBitmapSeries series = new FastHiLoOpenCloseBitmapSeries()
{

    ItemsSource = new ViewModel().TestingModel,

    XBindingPath = "X",

    High="Y", Low="Y1",

    Open="Y2", Close="Y3",

    BullFillColor = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC)),

    BearFillColor = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF Fast OHLC Bitmap Chart Type](FastChart_Images/wpf-fast-ohlc-bitmap-chart-type.png)

## Fast Scatter Bitmap

[`FastScatterBitmapSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastScatterBitmapSeries.html#) used to render high number scatter points. The [`ScatterHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastScatterBitmapSeries.html#Syncfusion_UI_Xaml_Charts_FastScatterBitmapSeries_ScatterHeight) and [`ScatterWidth`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastScatterBitmapSeries.html#Syncfusion_UI_Xaml_Charts_FastScatterBitmapSeries_ScatterWidth) also available as in ScatterSeries. [`ShapeType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastScatterBitmapSeries.html#Syncfusion_UI_Xaml_Charts_FastScatterBitmapSeries_ShapeType) is used to change the rendering shape of fast scatter bitmap series. The available shapes are [`Cross`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSymbol.html), [`Diamond`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSymbol.html), [`Ellipse`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSymbol.html), [`Hexagon`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSymbol.html), [`InvertedTriangle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSymbol.html), [`Pentagon`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSymbol.html), [`Plus`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSymbol.html), [`Rectangle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSymbol.html) and [`Triangle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSymbol.html).

{% tabs %}

{% highlight xaml %}

<chart:FastScatterBitmapSeries Interior="#7F7F7F"   

ItemsSource="{Binding Data}"                         

x:Name="FastScatterSeries"  XBindingPath="Date" 

YBindingPath="Value" ScatterHeight="4"  

ScatterWidth="4"/>

{% endhighlight %}

{% highlight C# %}

FastScatterBitmapSeries series = new FastScatterBitmapSeries()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "Date",

    YBindingPath = "Value",

    ScatterHeight = 4,

    ScatterWidth = 4,

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0X7F))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF FastScatterBitmap Chart Type](FastChart_Images/wpf-fastscatterbitmap-chart-type.png)


## Fast Step Line Bitmap

[`FastStepLineBitmapSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastStepLineBitmapSeries.html#) is the high performance version of StepLineSeries.

{% tabs %}

{% highlight xaml %}

<chart:FastStepLineBitmapSeries ItemsSource="{Binding Data}"

XBindingPath="Date"                                 

YBindingPath="Value" Interior="#4A4A4A" />

{% endhighlight %}

{% highlight c# %}

FastStepLineBitmapSeries series = new FastStepLineBitmapSeries()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "Date",

    YBindingPath = "Value",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF FastStepLineBitmap Chart Type](FastChart_Images/wpf-faststepline-bitmap-chart-type.png)

The anti aliasing mode can be enabled using [`EnableAntiAliasing`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastStepLineBitmapSeries.html#Syncfusion_UI_Xaml_Charts_FastStepLineBitmapSeries_EnableAntiAliasing) property of FastStepLineBitmapSeries as in below code snippet:

{% tabs %}

{% highlight xaml %}

<chart:FastStepLineBitmapSeries EnableAntiAliasing="True" ItemsSource="{Binding Data}"

x:Name="FastStepLineSeries" XBindingPath="Date" 

YBindingPath="Value" Interior="#4A4A4A"/>

{% endhighlight %}

{% highlight c# %}

FastStepLineBitmapSeries series = new FastStepLineBitmapSeries()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "Date",

    YBindingPath = "Value",

    EnableAntiAliasing = true ,

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF AntiAliasing support for FastStepLineBitmap Chart Type](FastChart_Images/wpf-antialiasing-support-for-faststeplinebitmap-chart-type.png)


## Fast Range Area

[`FastRangeAreaBitmapSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastRangeAreaBitmapSeries.html#) is the high performance version of RangeAreaSeries. 

{% tabs %}

{% highlight xaml %}

<chart:FastRangeAreaBitmapSeries ItemsSource = "{Binding Data}"

                             XBindingPath="Date" 
					 
                             High="HighTemperature" 
					 
                             Low="LowTemperature"        
					                                      
                             Interior="#7F7F7F" />

{% endhighlight %}

{% highlight c# %}

FastRangeAreaBitmapSeries fastRangeAreaBitmapSeries = new FastRangeAreaBitmapSeries();

fastRangeAreaBitmapSeries.ItemsSource = new ViewModel().Data;

fastRangeAreaBitmapSeries.XBindingPath = "Date";

fastRangeAreaBitmapSeries.High = "HighTemperature";

fastRangeAreaBitmapSeries.Low = "LowTemperature";

fastRangeAreaBitmapSeries.Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0x75));


chart.Series.Add(fastRangeAreaBitmapSeries);

{% endhighlight %}

{% endtabs %}

![WPF Chart Fast Range Area Bitmap Series](FastChart_Images/wpf-chart-fast-range-area-bitmap-series.png)

The anti-aliasing mode can be enabled using  [`EnableAntiAliasing`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FastRangeAreaBitmapSeries.html#Syncfusion_UI_Xaml_Charts_FastRangeAreaBitmapSeries_EnableAntiAliasing) property of FastRangeAreaBitmapSeries as in below code snippet:

{% tabs %}

{% highlight xaml %}

<chart:FastRangeAreaBitmapSeries ItemsSource = "{Binding Data}"

                                 XBindingPath="Date" 

                                 High="HighTemperature" 

                                 Low="LowTemperature" 

                                 EnableAntiAliasing="True" 

                                 Interior="#7F7F7F" />

{% endhighlight %}

{% highlight c# %}

FastRangeAreaBitmapSeries fastRangeAreaBitmapSeries = new FastRangeAreaBitmapSeries();

fastRangeAreaBitmapSeries.ItemsSource = new ViewModel().Data;

fastRangeAreaBitmapSeries.XBindingPath = "Date";

fastRangeAreaBitmapSeries.High = "HighTemperature";

fastRangeAreaBitmapSeries.Low = "LowTemperature";

fastRangeAreaBitmapSeries.EnableAntiAliasing = true;

fastRangeAreaBitmapSeries.Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0x75));


chart.Series.Add(fastRangeAreaBitmapSeries);

{% endhighlight %}

{% endtabs %}

![WPF Chart Fast Range Area Bitmap Series With Anit-Aliasing](FastChart_Images/wpf-chart-fast-range-area-bitmap-with-anti-aliasing.png)
