---
layout: post
title: Series| SfChart | Wpf | Syncfusion
description: This section explains the different types of charts and its basic properties in WPF Chart (SfChart3D)
platform: wpf
control: SfChart3D
documentation: ug
---

# Series in WPF Chart (SfChart3D)

ChartSeries is the visual representation of the data. SfChart3D offers eight types of series. Based on your requirements and specifications, any type of Series can be added for data visualization. 

* Column
* Bar
* Stacking column 
* Stacking column 100 
* Stacking bar
* Stacking bar
* Pie
* Doughnut

The following APIs are common for the most of the series types:

* [`XBindingPath`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~XBindingPath.html) – A string property that represents the X values for the series.
* [`YBindingPath`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XyDataSeries~YBindingPath.html) – A string property that represents the Y values for the series.
Eight types of chart [`Series`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SfChart3D~Series.html).
* [`Interior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~Interior.html) – Represents the brush to fill the series.


## Column Charts

Column charts plot discrete rectangles for the given values. The following code example demonstrates the usage of [`ColumnSeries3D`]
(https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ColumnSeries3D.html)

The following code example illustrates how to use ColumnSeries3D:

% tabs %}

{% highlight xaml %}

        <chart:ColumnSeries3D Interior="LightGreen" ItemsSource="{Binding CategoricalData}"  
            XBindingPath="Year" YBindingPath="Metal"></chart:ColumnSeries3D>

{% endhighlight %}

{% highlight c# %}

   ColumnSeries3D series = new ColumnSeries3D()
        {
            ItemsSource = new CategoryDataViewModel().CategoricalData,
            XBindingPath = "Year",
            YBindingPath = "Plastic"
        };

chart3D.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Column Charts support in WPF 3D Chart](3D-Charts_images/ColumnSeries3D.png)

## Bar Charts

Bar series are similar to column series, excepts its orientation. The following code examples shows how to use [`BarSeries3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.BarSeries3D.html).

The following code example illustrates how to use BarSeries3D:

% tabs %}

{% highlight xaml %}

        <chart:BarSeries3D ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic"></chart:BarSeries3D>

{% endhighlight %}

{% highlight c# %}

    BarSeries3D series = new BarSeries3D()
        {
            ItemsSource = new CategoryDataViewModel().CategoricalData,
            XBindingPath = "Year",
            YBindingPath = "Plastic"
        };

chart3D.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Bar Charts support in WPF 3D Chart](3D-Charts_images/Bar3D.png)

## Line Charts
Line series join points on a plot by straight lines, showing data trends at equal intervals. The following code example explains how to create a simple [`LineSeries3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.LineSeries3D.html#) using given data.

% tabs %}

{% highlight xaml %}

        <chart:LineSeries3D ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic"></chart:LineSeries3D>

{% endhighlight %}

{% highlight c# %}

        LineSeries3D line = new LineSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic"
            };

chart3D.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Column Charts support in WPF 3D Chart](3D-Charts_images/LineSeries3D.png)

### Scatter Chart

[`ScatterSeries3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ScatterSeries3D.html#) is similar to bubble series when each point being represented by an ellipse with equal size. 

This size can be defined by using below properties.

* [`ScatterHeight`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ScatterSeries~ScatterHeight.html#) 
* [`ScatterWidth`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ScatterSeries~ScatterWidth.html#) properties.

% tabs %}

{% highlight xaml %}

     <chart:ScatterSeries3D ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
         YBindingPath="Plastic"></chart:ScatterSeries3D>

{% endhighlight %}

{% highlight c# %}


        ScatterSeries3D series = new ScatterSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic"
            };

        chart3D.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Scatter chart support in WPF 3D Chart](3D-Charts_images/ScatterSeries3D.png)

## Area Chart
[`AreaSeries3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.AreaSeries3D.html#) is rendered using a collection of line segments connected to form a closed loop area, filled with the specified color.

% tabs %}

{% highlight xaml %}

        <chart:AreaSeries3D ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
            YBindingPath="Plastic"></chart:AreaSeries3D>

{% endhighlight %}

{% highlight c# %}


        AreaSeries3D series = new AreaSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic"
            };

        chart3D.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Scatter chart support in WPF 3D Chart](3D-Charts_images/AreaSeries3D.png)


## Stacking Charts

### Stacking Column
[`StackingColumnSeries3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingColumnSeries3D.html#) resembles multiple types of ColumnSeries. Each series is vertically stacked one above the other. When there is only one series, then it is ColumnSeries. 

The following code example illustrates how to use StackingColumnSeries3D:

% tabs %}

{% highlight xaml %}

        <chart:StackingColumnSeries3D ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
                YBindingPath="Plastic"></chart:StackingColumnSeries3D>

        <chart:StackingColumnSeries3D ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
                YBindingPath="Iron"></chart:StackingColumnSeries3D>

        <chart:StackingColumnSeries3D ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
                YBindingPath="Metal"></chart:StackingColumnSeries3D>

{% endhighlight %}

{% highlight c# %}

        StackingColumnSeries3D stack1 = new StackingColumnSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic"
            };

        StackingColumnSeries3D stack2 = new StackingColumnSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Iron"
            };

        StackingColumnSeries3D stack3 = new StackingColumnSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Metal"
            };

        chart3D.Series.Add(stack1);
        chart3D.Series.Add(stack2);
        chart3D.Series.Add(stack3);

{% endhighlight %}

{% endtabs %}

![Stacking Charts support in WPF 3D Chart](3D-Charts_images/StackingColumn3D.png)

### Stacking Column 100

[`StackingColumn100Series3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingColumn100Series3D.html#) resembles StackingColumnSeries3D but the cumulative portion of each stacked element always comes to a total of 100%. 

The following code example illustrates how to use StackingColumn100Series3D:

% tabs %}

{% highlight xaml %}

        <chart:StackingColumn100Series3D ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
                YBindingPath="Plastic"></chart:StackingColumn100Series3D>
            
        <chart:StackingColumn100Series3D Interior="Brown" ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
                YBindingPath="Iron"></chart:StackingColumn100Series3D>

{% endhighlight %}

{% highlight c# %}

        StackingColumn100Series3D stack1 = new StackingColumn100Series3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic"
            };

        StackingColumn100Series3D stack2 = new StackingColumn100Series3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Iron",
                Interior=new SolidColorBrush(Colors.Brown)
            };

        chart3D.Series.Add(stack1);
        chart3D.Series.Add(stack2);

{% endhighlight %}

{% endtabs %}

![Stacking Charts support in WPF 3D Chart](3D-Charts_images/StackingColumn1003D.png)

### Stacking Bar

[`StackingBarSeries3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingBarSeries3D.html#) is a multiple series type of BarSeries3D. Each BarSeries3D is then stacked horizontally, side by side to each other. When there exists only one series, it resembles a simple BarSeries3D.

The following code example illustrates how to use StackingBarSeries3D:

% tabs %}

{% highlight xaml %}

            <chart:StackingBarSeries3D ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
                YBindingPath="Plastic"></chart:StackingBarSeries3D>

            <chart:StackingBarSeries3D ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
                YBindingPath="Iron"></chart:StackingBarSeries3D>

            <chart:StackingBarSeries3D ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
                YBindingPath="Metal"></chart:StackingBarSeries3D>

{% endhighlight %}

{% highlight c# %}

         StackingBarSeries3D stack1 = new StackingBarSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic"
            };

        StackingBarSeries3D stack2 = new StackingBarSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Iron"
            };

        StackingBarSeries3D stack3 = new StackingBarSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Metal"
            };

        chart3D.Series.Add(stack1);
        chart3D.Series.Add(stack2);
        chart3D.Series.Add(stack3);

{% endhighlight %}

{% endtabs %}

![Stacking bar support in WPF 3D Chart](3D-Charts_images/StackingBar3D.png)

### Stacking Bar 100

[`StackingBar100Series3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingBar100Series3D.html#) resembles a StackingBarSeries3D. StackingBar100Series3D displays multiple series as stacked bars and the cumulative portion of each stacked element is always 100%. 

The following code example illustrates how to use StackingBar100Series3D:

% tabs %}

{% highlight xaml %}

            <chart:StackingBar100Series3D ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
                               YBindingPath="Plastic"></chart:StackingBar100Series3D>

            <chart:StackingBar100Series3D ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
                               YBindingPath="Iron"></chart:StackingBar100Series3D>

{% endhighlight %}

{% highlight c# %}

        StackingBar100Series3D stack1 = new StackingBar100Series3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic"
            };

        StackingBar100Series3D stack2 = new StackingBar100Series3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Iron"
            };

        chart3D.Series.Add(stack1);
        chart3D.Series.Add(stack2);

{% endhighlight %}

{% endtabs %}

![Stacking Bar support in WPF 3D Chart](3D-Charts_images/StackingBar1003D.png)

## Pie Chart

[`PieSeries3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.PieSeries3D.html#) is divided into sectors, illustrating numerical proportion.

The following code example illustrates the PieSeries3D.

% tabs %}

{% highlight xaml %}

        <chart:PieSeries3D ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
                YBindingPath="Iron"></chart:PieSeries3D>

{% endhighlight %}

{% highlight c# %}


        PieSeries3D series = new PieSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Iron"
            };

        chart3D.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Stacking Bar support in WPF 3D Chart](3D-Charts_images/Pie3D.png)


## Doughnut

[`DoughnutSeries3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.DoughnutSeries3D.html#) is similar to PieSeries. It is used to show the relationship between parts of data and whole data. 

The DoughnutSeries3D can be added to chart as in below code example:

{% tabs %}

{% highlight xaml %}

        <chart:DoughnutSeries3D ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"                          
            YBindingPath="Iron"> </chart:DoughnutSeries3D>

{% endhighlight %}

{% highlight c# %}

        DoughnutSeries3D series = new DoughnutSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Iron"
            };

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Doughnut support in WPF 3D Chart](3D-Charts_images/Doughnut3D.png)

## Dynamic explode

This feature allows users to explode a particular segment in a circular series using [`ExplodeOnMouseClick`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.PieSeries3D~ExplodeOnMouseClick.html). This can also be achieved by setting the [`ExplodeIndex`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesBase3D~ExplodeIndex.html) or [`ExplodeAll`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesBase3D~ExplodeAll.html) property. 

The following code example illustrates how to enable dynamic explode for circular series, for data please refer series category in 3D charts.

{% highlight xaml %}
    <chart:SfChart3D EnableRotation="True"  Tilt="-30" Rotation="45"
            Depth="30" PerspectiveAngle="90" Width="500" Height="500">

            <!--PrimaryAxis-->
            <chart:SfChart3D.PrimaryAxis>
                <chart:CategoryAxis3D Header="Year"/>
            </chart:SfChart3D.PrimaryAxis>
            <!--SecondaryAxis-->
            <chart:SfChart3D.SecondaryAxis>
                <chart:NumericalAxis3D Header="Metal"/>
            </chart:SfChart3D.SecondaryAxis>           

            <!--PieSeries3D - Dynamic explode-->
            <chart:PieSeries3D  ExplodeOnMouseClick="True" ItemsSource="{Binding CategoricalData}"  XBindingPath="Year"
                               YBindingPath="Iron"></chart:PieSeries3D>

    </chart:SfChart3D>

{% endhighlight %}


![Dynamic explode support in WPF 3D Chart](3D-Charts_images/Dynamicexplode3D.png)
