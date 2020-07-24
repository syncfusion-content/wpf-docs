---
layout: post
title: Financial Charts | SfChart | Wpf | Syncfusion
description: This section explains Financial Charts and its properties for customization in WPF Charts (SfChart)
platform: wpf
control: SfChart
documentation: ug
---

# Financial Charts

The APIs present in the financial series are,

* [`High`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~High.html)-Gets or sets the string that describes high value in Y-axis.
* [`Low`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Low.html)- Gets or sets the string that describes low value in Y-axis.
* [`Open`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Open.html)-Gets or sets the string that describes open value in Y-axis.
* [`Close`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Close.html)- Gets or sets the string that describes close value in Y-axis.
* [`BearFillColor`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~BearFillColor.html)-Represents the brush color for the segments that show stock price has gone up in measured time interval.
* [`BullFillColor`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~BullFillColor.html)-Represents that brush color for the segments that show stock price has gone down in measured time interval.
* [`ComparisonMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~ComparisonMode.html) - Specifies which price need to be considered for the formation from [`High`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialPrice.html), [`Low`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialPrice.html), [`Open`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialPrice.html), [`Close`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialPrice.html) or [`None`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialPrice.html) financial price.

## OHLC

[`HiLoOpenCloseSeries`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.HiLoOpenCloseSeries.html#) displays each data point as a group of horizontal and one vertical line. The values for this series can be binded using [`High`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~High.html#), [`Low`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Low.html#), [`Open`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Open.html#) and [`Close`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Close.html#) property.

The following code example shows how to use OHLC series:

{% tabs %}

{% highlight xaml %}

<chart:HiLoOpenCloseSeries Name="series" ItemsSource="{Binding StockPriceDetails}" 

XBindingPath="Date"  High="High" Low="Low"                         

Interior="#4A4A4A"

Open="Open" Close="Close" 

Label="HiloOpenClose" />

{% endhighlight %}

{% highlight c# %}

HiLoOpenCloseSeries series = new HiLoOpenCloseSeries()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    High = "High", Low = "Low",

    Open = "Open", Close = "Close",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![HiLoOpenClose chart type in WPF](Series_images/ohlc.png)

## Candle

[`CandleSeries`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CandleSeries.html#) displays each data point as a combination of a vertical column and a vertical line. This series is most widely used in decision making places, like the stock market.

The values for this series can be bind using [`High`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~High.html#), [`Low`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Low.html#), [`Open`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Open.html#) and [`Close`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Close.html#) property and the following code example shows the usage of candle series.

{% tabs %}

{% highlight xaml %}

<chart:CandleSeries Name="series" ItemsSource="{Binding StockPriceDetails}" 

XBindingPath="Date"  High="High" Open="Open"  

Close="Close" Low="Low"  

Interior="#4A4A4A"/>

{% endhighlight %}

{% highlight c# %}

CandleSeries series = new CandleSeries()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    High = "High", Low = "Low",

    Open = "Open", Close = "Close",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0X4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Candle chart type in WPF](Series_images/candle.png)

{% tabs %}

{% highlight xaml %}

<chart:CandleSeries Name="series" ItemsSource="{Binding StockPriceDetails}" XBindingPath="Date"   
                    High="High" Open="Open"  Close="Close" Low="Low"  BearFillColor="Black"
                    BullFillColor="#BCBCBC"/>
{% endhighlight %}   

{% highlight c# %}

CandleSeries series = new CandleSeries()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    High = "High", Low = "Low",

    Open = "Open", Close = "Close",

    BearFillColor = new SolidColorBrush(Colors.Black),

    BullFillColor = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0XBC))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}               

![Candle chart type in WPF](Series_images/candle_1.png)


## Comparison Modes

[`ComparisonMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~ComparisonModeProperty.html) property of [`FinancialSeries`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase.html) is used to compare the current (High, Low, Open, and Close) values with previous (High, Low, Open, and Close) values in the series data points. 
By default, the `ComparisonMode` value is none.

**Comparing the open values**

While setting the [`ComparisonMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~ComparisonModeProperty.html) value as `Open`, the open value of current segment will be compared to open value of previous segment.

{% tabs %}

{% highlight xaml %}

<syncfusion:CandleSeries ComparisonMode="Open">

</syncfusion:CandleSeries>

{% endhighlight %}   

{% highlight c# %}

CandleSeries series = new CandleSeries();

series.ComparisonMode = Syncfusion.UI.Xaml.Charts.FinancialPrice.Open;

{% endhighlight %}

{% endtabs %}     

![Comparison Modes support in WPF](Series_images/open.png)

In the above screenshot, the second segment’s Open value is greater than the first segment’s open value. So, the stroke color is filled with bull fill color.

**Comparing the close values**

While setting the [`ComparisonMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~ComparisonModeProperty.html) value as `Close`, the close value of current segment will be compared to the close value of previous segment.

{% tabs %}

{% highlight xaml %}

<syncfusion:CandleSeries ComparisonMode="Close">

</syncfusion:CandleSeries>

{% endhighlight %}   

{% highlight c# %}

CandleSeries series = new CandleSeries();

series.ComparisonMode = Syncfusion.UI.Xaml.Charts.FinancialPrice.Close;

{% endhighlight %}

{% endtabs %}   

![Comparison Modes support in WPF](Series_images/Close.png)

 In the above screenshot, the second segment’s close value is greater than the first segment’s close value. So, the stroke color is filled with bull fill color.

**Comparing the high values**

While setting the [`ComparisonMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~ComparisonModeProperty.html) value as `High`, the high value of current segment will be compared to the high value of previous segment.

{% tabs %}

{% highlight xaml %}

<syncfusion:CandleSeries ComparisonMode="High">

</syncfusion:CandleSeries>

{% endhighlight %}   

{% highlight c# %}

CandleSeries series = new CandleSeries();

series.ComparisonMode = Syncfusion.UI.Xaml.Charts.FinancialPrice.High;

{% endhighlight %}

{% endtabs %}   

![Comparison Modes support in WPF](Series_images/high.png)

 In the above screenshot, the second segment’s high value is less than the first segment’s high value. So, the stroke color is filled with bear fill color.

 **Comparing the low values**

 While setting the [`ComparisonMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~ComparisonModeProperty.html) value as `Low`, the low value of current segment will be compared to the low value of previous segment.

 {% tabs %}

{% highlight xaml %}

<syncfusion:CandleSeries ComparisonMode="Low">

</syncfusion:CandleSeries>

{% endhighlight %}   

{% highlight c# %}

CandleSeries series = new CandleSeries();

series.ComparisonMode = Syncfusion.UI.Xaml.Charts.FinancialPrice.Low;

{% endhighlight %}

{% endtabs %}   

![Comparison Modes support in WPF](Series_images/low.png)

In the above screenshot, the second segment’s low value is greater than the first segment’s low value. So, the stroke color filled with bull fill color.