---
layout: post
title: Sorting in WPF Charts control | Syncfusion
description: Learn here all about Sorting support in Syncfusion WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---

# Sorting in WPF Charts (SfChart)

Chart provides the support for sorting the data point either in ascending or descending based on X or Y axis.

### Enable Sorting
This [`IsSortData`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_IsSortData) property used to enable the sorting in series.

### Changing sorting direction

The [`SortDirection`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_SortDirection) property defines the direction of sorting either in [`Ascending`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Direction.html) or [`Descending`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Direction.html) based on x or y value.

### Changing sorting axis

This [`SortBy`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_SortBy) property decides whether sorting should be done based on [`X`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SortingAxis.html) or [`Y`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SortingAxis.html) values.


The following example illustrates a simple chart (without apply sorting):

![WPF Chart Axis without Sorting](sorting_chart_images/wpf-chart-axis-without-sorting.png)


## Sorting for category(non-linear) axis

**Sorting x axis in ascending order**:

{% tabs %}

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="X"  
	
	                     SortDirection="Ascending"

                         ItemsSource="{Binding Demands}" Interior="#4A4A4A"

                         XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.X,

    SortDirection = Direction.Ascending,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![WPF Chart Axis with Sorting](sorting_chart_images/wpf-chart-axis-with-sorting.png)


**Sorting x axis in descending order**:

{% tabs %}

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="X"  
	 
	                     SortDirection="Descending"

                         ItemsSource="{Binding Demands}" Interior="#4A4A4A"

                         XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.X,

    SortDirection = Direction.Descending,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![WPF Chart Sorting X-axis in Descending Order](sorting_chart_images/wpf-chart-sorting-X-axis-in-descending-order.png)


**Sorting y axis in ascending order**:

{% tabs %}

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="Y" 
	                   
					     SortDirection="Ascending"

                         ItemsSource="{Binding Demands}" Interior="#4A4A4A"

                         XBindingPath="Demand"  YBindingPath="Year2011"/>


{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.Y,

    SortDirection = Direction.Ascending,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![WPF Chart Sorting Y-axis in Ascending Order](sorting_chart_images/wpf-chart-sorting-y-axis-in-ascending-order.png)


**Sorting y axis in descending order**:

{% tabs %}

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="Y"  
	
	                     SortDirection="Descending"

                         ItemsSource="{Binding Demands}" Interior="#4A4A4A"

                         XBindingPath="Demand"  YBindingPath="Year2011"/>


{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.X,

    SortDirection = Direction.Descending,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![WPF Chart Sorting y-axis in Descending Order](sorting_chart_images/wpf-chart-sorting-y-axis-in-descending-order.png)

N> This feature is primarily applicable for indexed (non-linear) axis like CategoryAxis. For linear axis like NumericalAxis, only the order of rendering will be sorted. i.e., the order in which the data point is being rendered.


## Sorting for linear axis

As mentioned above, the sorting for the linear axis is different from CategoryAxis. Here the rendering order of the data point (x or y) will be sorted.

This will be useful especially when we have one or more values added in same data point. Also this rendering order will be captured by applying Palette to each point.

The following example illustrates a simple chart having AutumnBrights palette (without apply sorting):

![WPF Chart Linear Axis with Sorting](sorting_chart_images/wpf-chart-linear-axis-with-sorting.png)

**Sorting x axis in ascending order**

{% tabs %}

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="X" Palette="AutumnBrights"

                         SortDirection="Ascending"

                         ItemsSource="{Binding Demands}" 

                         XBindingPath="Position"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.X,

    SortDirection = Direction.Ascending,

    Palette = ChartColorPalette.AutumnBrights,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Position",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![WPF Chart Sorting Linear x-axis in Ascending Order](sorting_chart_images/wpf-chart-sorting-linear-x-axis-in-ascending-order.png)

**Sorting x axis in descending order**

{% tabs %}

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="X" 
	
	                     Palette="AutumnBrights"

                         SortDirection="Descending"

                         ItemsSource="{Binding Demands}" 

                         XBindingPath="Position"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.X,

    SortDirection = Direction.Descending,

    Palette = ChartColorPalette.AutumnBrights,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Position",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![WPF Chart Sorting Linear x-axis in Descending Order](sorting_chart_images/wpf-chart-sorting-linear-x-axis-in-descending-order.png)

**Sorting y axis in ascending order**

{% tabs %}

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="Y" 
	
	                     Palette="AutumnBrights"

                         SortDirection="Ascending"

                         ItemsSource="{Binding Demands}" 

                         XBindingPath="Position"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.Y,

    SortDirection = Direction.Ascending,

    Palette = ChartColorPalette.AutumnBrights,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Position",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![WPF Chart Sorting y-axis in Ascending Order](sorting_chart_images/wpf-chart-sorting-linear-y-axis-in-ascending-order.png)

**Sorting y axis in descending order**

{% tabs %}

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="Y" 
	
	                     Palette="AutumnBrights"

                         SortDirection="Descending"

                         ItemsSource="{Binding Demands}" 

                         XBindingPath="Position"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.Y,

    SortDirection = Direction.Descending,

    Palette = ChartColorPalette.AutumnBrights,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Position",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![WPF Chart Sorting y-axis in Descending Order](sorting_chart_images/wpf-chart-sorting-linear-y-axis-in-descending-order.png)


