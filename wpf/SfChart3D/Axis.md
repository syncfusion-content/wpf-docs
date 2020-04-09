---
layout: post
title: Axis| SfChart | Wpf | Syncfusion 
description: Explains the parts of axis, types of axis, it's behavior and customization options in WPF Chart (SfChart3D)
platform: wpf
control: SfChart3D
documentation: ug
---

# Axis in WPF Chart (SfChart3D)

[`ChartAxis`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxis.html#) is used to locate a data point inside the chart area. Charts typically have two axes that are used to measure and categorize data: a vertical (Y) axis and a horizontal (X) axis. 

* [`PrimaryAxis`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SfChart3D~PrimaryAxis.html) – Gets or sets the horizontal x axis for the chart.
* [`SecondaryAxis`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SfChart3D~SecondaryAxis.html) – Gets or sets the vertical y axis for the chart.

Additionally, SfChart3D have horizontal (z) Axis called Depth Axis.

* [`DepthAxis`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SfChart3D~DepthAxis.html#) - Gets or sets the horizontal z axis for the chart.


## Types of Axis

ChartAxis supports the following types.

* NumericalAxis
* CategoryAxis
* DateTimeAxis
* TimeSpanAxis
* LogarithmicAxis

### Numerical Axis

[`NumericalAxis3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.NumericalAxis3D.html#) is used to plot numerical values to the chart and can be defined for both PrimaryAxis and SecondaryAxis.


{% tabs %}

{% highlight xaml %}

    <chart:SfChart3D>

            <!--PrimaryAxis-->
            <chart:SfChart3D.PrimaryAxis>
                <chart:NumericalAxis3D/>
            </chart:SfChart3D.PrimaryAxis>

            <!--SecondaryAxis-->
            <chart:SfChart3D.SecondaryAxis>
                <chart:NumericalAxis3D />
            </chart:SfChart3D.SecondaryAxis>

    </chart:SfChart3D>

{% endhighlight %}

{% highlight C# %}

        SfChart3D Chart3D = new SfChart3D()
            {
                PrimaryAxis = new NumericalAxis3D(),

                SecondaryAxis = new NumericalAxis3D()               
            };

{% endhighlight %}

{% endtabs %}

### Category Axis

[`CategoryAxis3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CategoryAxis3D.html#) - it is an indexed based axis that plots values based on the index of the data point collection. The points are equally spaced here.

{% tabs %}

{% highlight xaml %}

    <chart:SfChart3D>

            <!--PrimaryAxis-->
            <chart:SfChart3D.PrimaryAxis>
                <chart:CategoryAxis3D/>
            </chart:SfChart3D.PrimaryAxis>

    </chart:SfChart3D>

{% endhighlight %}

{% highlight C# %}

        SfChart3D Chart3D = new SfChart3D()
            {
                PrimaryAxis = new CategoryAxis3D()               
            };

{% endhighlight %}

{% endtabs %}

### DateTime Axis

[`DateTimeAxis3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.DateTimeAxis3D.html#) - it is used to plot DateTime values and  it is widely used to make financial charts in places like the Stock Market, where index plotting is done every day.

{% tabs %}

{% highlight xaml %}

    <chart:SfChart3D>

            <!--PrimaryAxis-->
            <chart:SfChart3D.PrimaryAxis>
                <chart:DateTimeAxis3D/>
            </chart:SfChart3D.PrimaryAxis>

    </chart:SfChart3D>

{% endhighlight %}

{% highlight C# %}

        SfChart3D Chart3D = new SfChart3D()
            {
                PrimaryAxis = new DateTimeAxis3D()               
            };

{% endhighlight %}

{% endtabs %}

### Logarithmic Axis

[`LogarithmicAxis3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.LogarithmicAxis3D.html#) - it is used to plot the logarithmic scale for the chart. The Logarithmic values will be plotted based on the logarithmic base value as 10.

{% tabs %}

{% highlight xaml %}

    <chart:SfChart3D>

            <!--SecondaryAxis-->
            <chart:SfChart3D.SecondaryAxis>
                <chart:LogarithmicAxis3D />
            </chart:SfChart3D.SecondaryAxis>

    </chart:SfChart3D>

{% endhighlight %}

{% highlight C# %}

       SfChart3D Chart3D = new SfChart3D()
            {
                SecondaryAxis = new LogarithmicAxis3D()               
            };

{% endhighlight %}

{% endtabs %}

### TimeSpan Axis

[`TimeSpanAxis3D`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.TimeSpanAxis3D.html#) - it is used to plot the time span values in the PrimaryAxis. TimeSpanAxis has the advantage of plotting data with milliseconds difference. The limitation of TimeSpanAxis is that it can only accept timespan values (hh:mm:ss) and date time values are not accepted.

{% tabs %}

{% highlight xaml %}

    <chart:SfChart3D>

            <!--PrimaryAxis-->
            <chart:SfChart3D.PrimaryAxis>
                <chart:TimeSpanAxis3D/>
            </chart:SfChart3D.PrimaryAxis>

    </chart:SfChart3D>

{% endhighlight %}

{% highlight C# %}

        SfChart3D Chart3D = new SfChart3D()
            {
                PrimaryAxis = new TimeSpanAxis3D()               
            };

{% endhighlight %}

{% endtabs %}

## Depth Axis
[`DepthAxis`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SfChart3D~DepthAxis.html#) is horizontal axis(Z) for the SfChart3D (3D Chart with X, Y and Z Axis).

The following code example illustrates how to create Depth Axis.

{% tabs %} 

{% highlight xaml %}

    <chart:SfChart3D EnableRotation="True" Rotation="43" Tilt="10"
                         Width="500" Height="500">

            <!--PrimaryAxis-->
            <chart:SfChart3D.PrimaryAxis>
                <chart:CategoryAxis3D/>
            </chart:SfChart3D.PrimaryAxis>
            <!--SecondaryAxis-->
            <chart:SfChart3D.SecondaryAxis>
                <chart:NumericalAxis3D />
            </chart:SfChart3D.SecondaryAxis>
            <!--DepthAxis-->
            <chart:SfChart3D.DepthAxis>
                <chart:NumericalAxis3D/>
            </chart:SfChart3D.DepthAxis>

            <chart:ColumnSeries3D ItemsSource="{Binding CategoricalData}"  
            XBindingPath="Year" YBindingPath="Plastic" ZBindingPath="Iron" ></chart:ColumnSeries3D>

    </chart:SfChart3D>

{% endhighlight %}

{% highlight C# %} 

        SfChart3D Chart3D = new SfChart3D()
            {
                PrimaryAxis = new DateTimeAxis3D(),

                SecondaryAxis = new NumericalAxis3D(),

                DepthAxis=new NumericalAxis3D()
            };


{% endhighlight %}

{% endtabs %}

![Depth Axis in WPF 3D Chart](3D-Charts_images/Axis/DepthAxis.png)