---
layout: post
title: Stacked Chart in WPF Charts control | Syncfusion
description: Learn here all about Stacked Chart support in Syncfusion® WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---

# Stacked in WPF Charts (SfChart)

## Stacked Line Chart

[`StackingLineSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StackingLineSeries.html) resembles multiple types of series of the [`LineSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineSeries.html). Each series is vertically stacked one above the other. When there is only one series, then it is [`LineSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineSeries.html). 

The following code example illustrates how to use [`StackingLineSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StackingLineSeries.html):

{% tabs %}

{% highlight xaml %}

<chart:StackingLineSeries  

XBindingPath="MonthlyExpenses"    

YBindingPath="Father" 

Interior="#4A4A4A"

ItemsSource="{Binding Data}"/>

<chart:StackingLineSeries

XBindingPath="MonthlyExpenses" 

YBindingPath="Mother"

Interior="#BCBCBC"

ItemsSource="{Binding Data}"/> 

<chart:StackingLineSeries 

XBindingPath="MonthlyExpenses" 

YBindingPath="Son"

Interior="#7F7F7F"

ItemsSource="{Binding Data}" />

{% endhighlight %}

{% highlight c# %}

StackingLineSeries series1 = new StackingLineSeries()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "MonthlyExpenses",

    YBindingPath ="Father",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

StackingLineSeries series2 = new StackingLineSeries()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "MonthlyExpenses",

    YBindingPath = "Mother",

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0XBC))

};

StackingLineSeries series3 = new StackingLineSeries()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "MonthlyExpenses",

    YBindingPath = "Son",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0X7F))

};

chart.Series.Add(series1);

chart.Series.Add(series2);

chart.Series.Add(series3);

{% endhighlight %}

{% endtabs %}

![WPF Stacked Line Chart](Series_images/wpf-stacking-line-chart.png)

N> You can explore our [WPF Stacked Line Chart](https://www.syncfusion.com/wpf-controls/charts/wpf-stacked-line-chart) feature tour page for its groundbreaking features. You can also explore our [WPF Stacked Line Chart example](https://github.com/syncfusion/wpf-demos/blob/master/chart/Views/Stacked%20Charts/StackingLineChart.xaml) to know how to represent time-dependent data, showing trends in data at equal intervals.

## Stacked Line100 Chart

[`StackingLine100Series`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StackingLine100Series.html) resembles [`StackingLinenSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StackingLineSeries.html) but the cumulative portion of each stacked element always comes to a total of 100%. 

{% tabs %}

{% highlight xaml %}

<chart:StackingLine100Series ItemsSource="{Binding Data}" 

XBindingPath="MonthlyExpenses" 

YBindingPath="Father" 

Interior="#4A4A4A"
/>

<chart:StackingLine100Series ItemsSource="{Binding Data}"

XBindingPath="MonthlyExpenses"  

YBindingPath="Mother"

Interior="#BCBCBC"/>

<chart:StackingLine100Series ItemsSource="{Binding Data}"

XBindingPath="MonthlyExpenses" 

YBindingPath="Son"

Interior="#7F7F7F"/>

{% endhighlight %}

{% highlight c# %}

StackingLine100Series series1 = new StackingLine100Series()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "MonthlyExpenses",

    YBindingPath = "Father",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

StackingLine100Series series2 = new StackingLine100Series()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "MonthlyExpenses",

    YBindingPath = "Mother",

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0XBC))

};

StackingLine100Series series3 = new StackingLine100Series()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "MonthlyExpenses",

    YBindingPath = "Son",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0X7F))

};

chart.Series.Add(series1);

chart.Series.Add(series2);

chart.Series.Add(series3);

{% endhighlight %}

{% endtabs %}

![WPF Stacked Line100 Chart](Series_images/wpf-stacking-line-100-chart.png)

N> You can explore our [WPF 100% Stacked Line Chart](https://www.syncfusion.com/wpf-controls/charts/wpf-stacked-line-100-chart) feature tour page for its groundbreaking features. You can also explore our [WPF 100% Stacked Line Chart example](https://github.com/syncfusion/wpf-demos/blob/master/chart/Views/Stacked%20Charts%20100/StackingLine.xaml) to know how to represent time-dependent data, showing trends in data at equal intervals.

## Stacked Column Chart

[`StackingColumnSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StackingColumnSeries.html#) resembles multiple types of ColumnSeries. Each series is vertically stacked one above the other. When there is only one series, then it is ColumnSeries. 

The following code example illustrates how to use StackingColumnSeries:

{% tabs %}

{% highlight xaml %}

<chart:StackingColumnSeries  

XBindingPath="CountryName"    

YBindingPath="GoldMedals" 

Interior="#4A4A4A"

ItemsSource="{Binding MedalDetails}"/>

<chart:StackingColumnSeries 

Interior="#BCBCBC"

XBindingPath="CountryName" 

YBindingPath="SilverMedals"

ItemsSource="{Binding MedalDetails}"/> 

<chart:StackingColumnSeries 

Interior="#7F7F7F"

XBindingPath="CountryName" 

YBindingPath="BronzeMedals" />

{% endhighlight %}

{% highlight c# %}

StackingColumnSeries series1 = new StackingColumnSeries()
{

    ItemsSource = new ViewModel().MedalDetails,

    XBindingPath = "CountryName",

    YBindingPath ="GoldMedals",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

StackingColumnSeries series2 = new StackingColumnSeries()
{

    ItemsSource = new ViewModel().MedalDetails,

    XBindingPath = "CountryName",

    YBindingPath = "SilverMedals",

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0XBC))

};

StackingColumnSeries series3 = new StackingColumnSeries()
{

    ItemsSource = new ViewModel().MedalDetails,

    XBindingPath = "CountryName",

    YBindingPath = "BronzeMedals",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0X7F))

};

chart.Series.Add(series1);

chart.Series.Add(series2);

chart.Series.Add(series3);

{% endhighlight %}

{% endtabs %}

![WPF Stacked Column Chart](Series_images/wpf-stacking-column-chart.png)

N> You can explore our [WPF Stacked Column Chart](https://www.syncfusion.com/wpf-controls/charts/wpf-stacked-column-chart) feature tour page for its groundbreaking features. You can also explore our [WPF Stacked Column Chart example](https://github.com/syncfusion/wpf-demos/blob/master/chart/Views/Stacked%20Charts/StackingColumnChart.xaml) to know how to represent time-dependent data, showing trends in data at equal intervals.

## Stacked Column100 Chart

[`StackingColumn100Series`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StackingColumn100Series.html#) resembles StackingColumnSeries but the cumulative portion of each stacked element always comes to a total of 100%. 

{% tabs %}

{% highlight xaml %}

<chart:StackingColumn100Series  XBindingPath="CountryName" 

YBindingPath="GoldMedals" Interior="#4A4A4A"

ItemsSource="{Binding MedalDetails}"/>

<chart:StackingColumn100Series ItemsSource="{Binding MedalDetails}"

XBindingPath="CountryName"  

YBindingPath="SilverMedals"

Interior="#BCBCBC"/>

{% endhighlight %}

{% highlight c# %}

StackingColumn100Series series1 = new StackingColumn100Series()
{

    ItemsSource = new ViewModel().MedalDetails,

    XBindingPath = "CountryName",

    YBindingPath = "GoldMedals",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

StackingColumn100Series series2 = new StackingColumn100Series()
{

    ItemsSource = new ViewModel().MedalDetails,

    XBindingPath = "CountryName",

    YBindingPath = "SilverMedals",

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0XBC))

};

StackingColumn100Series series3 = new StackingColumn100Series()
{

    ItemsSource = new ViewModel().MedalDetails,

    XBindingPath = "CountryName",

    YBindingPath = "BronzeMedals",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0X7F))

};

chart.Series.Add(series1);

chart.Series.Add(series2);

chart.Series.Add(series3);

{% endhighlight %}

{% endtabs %}

![WPF Stacked Column100 Chart](Series_images/wpf-stacking-column-100-chart.png)

N> You can explore our [WPF 100% Stacked Column Chart](https://www.syncfusion.com/wpf-controls/charts/wpf-stacked-column-100-chart) feature tour page for its groundbreaking features. You can also explore our [WPF 100% Stacked Column Chart example](https://github.com/syncfusion/wpf-demos/blob/master/chart/Views/Stacked%20Charts%20100/StackedColumn.xaml) to know how to represent time-dependent data, showing trends in data at equal intervals.

## Stacked Bar Chart

[`StackingBarSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StackingBarSeries.html#) is a multiple series type of BarSeries. Each BarSeries is then stacked horizontally, side by side to each other. When there exists only one series, it resembles a simple BarSeries. 

{% tabs %}

{% highlight xaml %}

<chart:StackingBarSeries XBindingPath="CountryName"        

Interior="#BCBCBC"

YBindingPath="GoldMedals" 

ItemsSource="{Binding MedalDetails}" >

</chart:StackingBarSeries>

<chart:StackingBarSeries Interior="#4A4A4A"

XBindingPath="CountryName" 

YBindingPath="SilverMedals" 

ItemsSource="{Binding MedalDetails}">

</chart:StackingBarSeries>

<chart:StackingBarSeries Interior="#7F7F7F"

XBindingPath="CountryName" 

YBindingPath="BronzeMedals"

ItemsSource="{Binding MedalDetails}" >

</chart:StackingBarSeries>

{% endhighlight %}

{% highlight c# %}

StackingBarSeries series1 = new StackingBarSeries()
{

    ItemsSource = new ViewModel().MedalDetails,

    XBindingPath = "CountryName",

    YBindingPath = "GoldMedals",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

StackingBarSeries series2 = new StackingBarSeries()
{

    ItemsSource = new ViewModel().MedalDetails,

    XBindingPath = "CountryName",

    YBindingPath = "SilverMedals",

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0XBC))

};

StackingBarSeries series3 = new StackingBarSeries()
{

    ItemsSource = new ViewModel().MedalDetails,

    XBindingPath = "CountryName",

    YBindingPath = "BronzeMedals",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0X7F))

};

chart.Series.Add(series1);

chart.Series.Add(series2);

chart.Series.Add(series3);

{% endhighlight %}

{% endtabs %}

![WPF Stacked Bar Chart](Series_images/wpf-stacked-bar-chart.png)

N> You can explore our [WPF Stacked Bar Chart](https://www.syncfusion.com/wpf-controls/charts/wpf-stacked-bar-chart) feature tour page for its groundbreaking features. You can also explore our [WPF Stacked Bar Chart example](https://github.com/syncfusion/wpf-demos/blob/master/chart/Views/Stacked%20Charts/StackingBarChart.xaml) to know how to displays multiple series of data as stacked bars.

## Stacked Bar100 Chart

[`StackingBar100Series`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StackingBar100Series.html#) resembles a StackingBarSeries. StackingBar100Series displays multiple series as stacked bars and the cumulative portion of each stacked element is always 100%. 

{% tabs %}

{% highlight xaml %}

<chart:StackingBar100Series Interior="#BCBCBC"

XBindingPath="CountryName" 

YBindingPath="GoldMedals" 

ItemsSource="{Binding MedalDetails}" />

<chart:StackingBar100Series Interior="#4A4A4A" 

XBindingPath="CountryName"                          

YBindingPath="SilverMedals" 

ItemsSource="{Binding MedalDetails}" />

<chart:StackingBar100Series Interior="#7F7F7F" 

XBindingPath="CountryName" 

YBindingPath="BronzeMedals" 

ItemsSource="{Binding MedalDetails}" />

{% endhighlight %}

{% highlight c# %}

StackingBar100Series series1 = new StackingBar100Series()
{

    ItemsSource = new ViewModel().MedalDetails,

    XBindingPath = "CountryName",

    YBindingPath = "GoldMedals",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

StackingBar100Series series2 = new StackingBar100Series()
{

    ItemsSource = new ViewModel().MedalDetails,

    XBindingPath = "CountryName",

    YBindingPath = "SilverMedals",

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0XBC))

};

StackingBar100Series series3 = new StackingBar100Series()
{

    ItemsSource = new ViewModel().MedalDetails,

    XBindingPath = "CountryName",

    YBindingPath = "BronzeMedals",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0X7F))

};

chart.Series.Add(series1);

chart.Series.Add(series2);

chart.Series.Add(series3);

{% endhighlight %}

{% endtabs %}

![WPF Stacked Bar100 Chart](Series_images/wpf-stacked-bar-100-chart.png)

## Stacked Area Chart

[`StackingAreaSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StackingAreaSeries.html#) is representing areas stacked vertically one above the other. 

{% tabs %}

{% highlight xaml %}

<chart:StackingAreaSeries Interior="#BCBCBC" 

XBindingPath="Month" YBindingPath="Bus" 

ItemsSource="{Binding Accidents}" />

<chart:StackingAreaSeries Interior="#4A4A4A"                  

XBindingPath="Month" YBindingPath="Car" 

ItemsSource="{Binding Accidents}" />

<chart:StackingAreaSeries  Interior="#7F7F7FC"                     

XBindingPath="Month" 

YBindingPath="Truck" 

ItemsSource="{Binding Accidents}" />

{% endhighlight %}

{% highlight c# %}

StackingAreaSeries series1 = new StackingAreaSeries()
{

    ItemsSource = new ViewModel().Accidents,

    XBindingPath = "Month",

    YBindingPath = "Bus",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

StackingAreaSeries series2 = new StackingAreaSeries()
{

    ItemsSource = new ViewModel().Accidents,

    XBindingPath = "Month",

    YBindingPath = "Car",

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0XBC))

};

StackingAreaSeries series3 = new StackingAreaSeries()
{

    ItemsSource = new ViewModel().Accidents,

    XBindingPath = "Month",

    YBindingPath = "Truck",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0X7F))

};

chart.Series.Add(series1);

chart.Series.Add(series2);

chart.Series.Add(series3);

{% endhighlight %}

{% endtabs %}

![WPF Stacked Area Chart](Series_images/wpf-stacked-area-chart.png)

N> You can explore our [WPF Stacked Area Chart](https://www.syncfusion.com/wpf-controls/charts/wpf-stacked-area-chart) feature tour page for its groundbreaking features. You can also explore our [WPF Stacked Area Chart example](https://github.com/syncfusion/wpf-demos/blob/master/chart/Views/Stacked%20Charts/StackingAreaChart.xaml) to know how to displays multiple series of data as stacked area.

## Stacked Area100 Chart

StackingArea100Series is similar to StackingAreaSeries, but the cumulative portion of each stacked element always totals 100%. 

The following code example shows the way to add stacking area 100 series:

{% tabs %}

{% highlight xaml %}

<chart:StackingArea100Series Interior="#BCBCBC" 

XBindingPath="Month"         

YBindingPath="Bus" 

ItemsSource="{Binding Accidents}" 

/>

<chart:StackingArea100Series Interior="#4A4A4A" 

XBindingPath="Month" YBindingPath="Car" 

ItemsSource="{Binding Accidents}" />

<chart:StackingArea100Series Interior="#7F7F7F" 

XBindingPath="Month" 

YBindingPath="Truck" 

ItemsSource="{Binding Accidents}" />

{% endhighlight %}

{% highlight c# %}

StackingArea100Series series1 = new StackingArea100Series()
{

    ItemsSource = new ViewModel().Accidents,

    XBindingPath = "Month",

    YBindingPath = "Bus",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

StackingArea100Series series2 = new StackingArea100Series()
{

    ItemsSource = new ViewModel().Accidents,

    XBindingPath = "Month",

    YBindingPath = "Car",

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0XBC))

};

StackingArea100Series series3 = new StackingArea100Series()
{

    ItemsSource = new ViewModel().Accidents,

    XBindingPath = "Month",

    YBindingPath = "Truck",

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0X7F))

};

chart.Series.Add(series1);

chart.Series.Add(series2);

chart.Series.Add(series3);

{% endhighlight %}

{% endtabs %}

![WPF Stacked Area100 Chart](Series_images/wpf-stacked-area-100-chart.png)

You can draw open curve like Area using this [`IsClosed`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StackingAreaSeries.html#Syncfusion_UI_Xaml_Charts_StackingAreaSeries_IsClosed) property.

{% tabs %}

{% highlight xaml %}

<chart:StackingAreaSeries  Interior="#BCBCBC" Stroke="Black" StrokeThickness="3"

IsClosed="False" XBindingPath="Month" 

YBindingPath="Bus" 

ItemsSource="{Binding Accidents}"/>

<chart:StackingAreaSeries  Interior="#777777" Stroke="White" StrokeThickness="3"

IsClosed="False"  XBindingPath="Month"             

YBindingPath="Car"

ItemsSource="{Binding Accidents}"/>

<chart:StackingAreaSeries  Interior="#7F7F7F" Stroke="Black"   

StrokeThickness="3" IsClosed="False"   

XBindingPath="Month" 

YBindingPath="Truck" 

ItemsSource="{Binding Accidents}" />

{% endhighlight %}

{% highlight c# %}

StackingAreaSeries series1 = new StackingAreaSeries()
{

    ItemsSource = new ViewModel().Accidents,

    XBindingPath = "Month",

    YBindingPath = "Bus",

    Stroke = new SolidColorBrush(Colors.Black),

    StrokeThickness = 3,

    IsClosed = false,

    Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0XBC))

};

StackingAreaSeries series2 = new StackingAreaSeries()
{

    ItemsSource = new ViewModel().Accidents,

    XBindingPath = "Month",

    YBindingPath = "Car",

    Stroke = new SolidColorBrush(Colors.White),

    StrokeThickness = 3,

    IsClosed = false,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0X77))

};

StackingAreaSeries series3 = new StackingAreaSeries()
{

    ItemsSource = new ViewModel().Accidents,

    XBindingPath = "Month",

    YBindingPath = "Truck",

    Stroke = new SolidColorBrush(Colors.Black),

    StrokeThickness = 3,

    IsClosed = false,

    Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0X7F))

};

chart.Series.Add(series1);

chart.Series.Add(series2);

chart.Series.Add(series3);

{% endhighlight %}

{% endtabs %}

![WPF Chart with Closed Stacked area](Series_images/wpf-chart-stacked-closed-area.png)

N> You can explore our [WPF Stacked Area 100 Chart](https://www.syncfusion.com/wpf-controls/charts/wpf-stacked-area-100-chart) feature tour page for its groundbreaking features. You can also explore our [WPF Stacked Area 100 Chart example](https://github.com/syncfusion/wpf-demos/blob/master/chart/Views/Stacked%20Charts%20100/StackingArea.xaml) to know how to displays multiple series of data as stacked area.