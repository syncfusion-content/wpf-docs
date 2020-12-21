---
layout: post
title: Waterfall, Box and Whisker charts | SfChart | Wpf | Syncfusion
description: This section explains Waterfall, Box and Whisker charts and its properties for customization in WPF Charts (SfChart)
platform: wpf
control: SfChart
documentation: ug
---

# Other Charts in WPF Chart (SfChart)

## Box and Whisker 

[`BoxAndWhiskerSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html) plots a combination of rectangle and lines to show the distribution of the dataset. The following code illustrates how to define the series in chart.

{% tabs %}

{% highlight xaml %}

<chart:BoxAndWhiskerSeries ItemsSource="{Binding BoxWhiskerData}"  
                          
                            XBindingPath="Department" 
                          
                            YBindingPath="Age">

</chart:BoxAndWhiskerSeries>

{% endhighlight %}

{% highlight c# %}

BoxAndWhiskerSeries boxAndWhisker = new BoxAndWhiskerSeries();

boxAndWhisker.ItemsSource = new BoxWhiskerViewModel().BoxWhiskerData;

boxAndWhisker.XBindingPath = "Department";

boxAndWhisker.YBindingPath = "Age";

boxWhiskerChart.Series.Add(boxAndWhisker);

{% endhighlight %}

{% endtabs %}

![Box and Whisker Chart type in WPF](Series_images/boxAndWhisker1.png)

N>By default, the `BoxPlotMode` property value is Exclusive.

**Customize the series Box mode**

The series box plotting mode can be changed by using [`BoxPlotMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html#Syncfusion_UI_Xaml_Charts_BoxAndWhiskerSeries_BoxPlotModeProperty) property of [`BoxAndWhiskerSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html). The plotting mode of series can be calculated as follows:

* [`Exclusive`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BoxPlotMode.html) – The quartile values are calculated by using the formula (N+1) * P (N count, P percentile) and its index value starts from 1 in the list.
* [`Inclusive`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BoxPlotMode.html) – The quartile values are calculated by using the formula (N−1) * P (N count, P percentile) and its index value starts from 0 in the list.
* [`Normal`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BoxPlotMode.html) – The quartile values are calculated by splitting the list and getting the median values.

**Normal**

The following code illustrates how to define the [`BoxPlotMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html#Syncfusion_UI_Xaml_Charts_BoxAndWhiskerSeries_BoxPlotModeProperty) value as Normal.

{% tabs %}

{% highlight xaml %}

<chart:BoxAndWhiskerSeries  BoxPlotMode="Normal">

</chart:BoxAndWhiskerSeries>

{% endhighlight %}

{% highlight c# %}

BoxAndWhiskerSeries boxAndWhisker = new BoxAndWhiskerSeries();

boxAndWhisker.BoxPlotMode = BoxPlotMode.Normal;

{% endhighlight %}

{% endtabs %}

![Series Box Mode customization support for Box and Whisker series in WPF Chart](Series_images/boxAndWhisker2.png)

**Inclusive**

The following code illustrates how to define the [`BoxPlotMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html#Syncfusion_UI_Xaml_Charts_BoxAndWhiskerSeries_BoxPlotModeProperty) value as Inclusive.

{% tabs %}

{% highlight xaml %}

<chart:BoxAndWhiskerSeries  BoxPlotMode="Inclusive">

</chart:BoxAndWhiskerSeries>

{% endhighlight %}

{% highlight c# %}

BoxAndWhiskerSeries boxAndWhisker = new BoxAndWhiskerSeries();

boxAndWhisker.BoxPlotMode = BoxPlotMode.Inclusive;

{% endhighlight %}

{% endtabs %}

![Series Box Mode customization support for Box and Whisker series in WPF Chart](Series_images/boxAndWhisker3.png)

**ShowMedian**

The Median values of given dataset is viewed by enabling the [`ShowMedian`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html#Syncfusion_UI_Xaml_Charts_BoxAndWhiskerSeries_ShowMedianProperty) property of [`BoxAndWhiskerSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html). The following code illustrates how to enable the [`ShowMedian`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html#Syncfusion_UI_Xaml_Charts_BoxAndWhiskerSeries_ShowMedianProperty) property.

{% tabs %}

{% highlight xaml %}

<chart:BoxAndWhiskerSeries ShowMedian="True">

</chart:BoxAndWhiskerSeries>

{% endhighlight %}

{% highlight c# %}

BoxAndWhiskerSeries boxAndWhisker = new BoxAndWhiskerSeries();

boxAndWhisker.ShowMedian = true;

{% endhighlight %}

{% endtabs %}

![ShowMedian support for Box and Whisker series in WPF Chart](Series_images/boxAndWhisker4.png)

### Outlier

The outlier is used to display the outlier point that lies either below the lower whisker or above the upper whisker line and it is an observation that is numerically distant from the rest of the data.

#### ShowOutlier

The outlier value in the box plot can be viewed by enabling the [`ShowOutlier`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html#Syncfusion_UI_Xaml_Charts_BoxAndWhiskerSeries_ShowOutlier) property of [`BoxAndWhiskerSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html). By default, [ShowOutlier](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html#Syncfusion_UI_Xaml_Charts_BoxAndWhiskerSeries_ShowOutlier) value is true. The following code demonstrates how to disable the [`ShowOutlier`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html#Syncfusion_UI_Xaml_Charts_BoxAndWhiskerSeries_ShowOutlier) property.

{% tabs %}

{% highlight xaml %}

<chart:BoxAndWhiskerSeries ShowOutlier="False">

</chart:BoxAndWhiskerSeries>

{% endhighlight %}

{% highlight c# %}

BoxAndWhiskerSeries boxAndWhisker = new BoxAndWhiskerSeries();

boxAndWhisker.ShowOutlier = false;

{% endhighlight %}

{% endtabs %}

![ShowOutlier support for Box and Whisker series in WPF Chart](Series_images/ShowOutlier.png)

**Outlier Template**

The default appearance of the outlier symbol can be customized by using the [`OutlierTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html#Syncfusion_UI_Xaml_Charts_BoxAndWhiskerSeries_OutlierTemplateProperty) property of [`BoxAndWhiskerSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.BoxAndWhiskerSeries.html). The following code illustrates how to customize the outlier symbol.

{% tabs %}

{% highlight xaml %}

<chart:BoxAndWhiskerSeries.OutlierTemplate>

    <DataTemplate>

        <Canvas>

                 <Path Stretch="Fill" Height="10" Width="10"  Fill="{Binding Interior}" 
                              
                         Canvas.Left="{Binding RectX}" Canvas.Top="{Binding RectY}"
      
                            Data="F1 M 145.193,54.8249L 169.315,54.8249L 169.315,
            
                                    78.9463L 145.193,78.9463L 145.193,103.074L 121.071,
            
                                    103.074L 121.071,78.9463L 96.946,78.9463L 96.946,
           
                                    54.8249L 121.071,54.8249L 121.071,
            
                                    30.6983L 145.193,30.6983L 145.193,54.8249 Z"/>

          </Canvas>

    </DataTemplate>

</chart:BoxAndWhiskerSeries.OutlierTemplate>

{% endhighlight %}

{% endtabs %}

![OutlierTemplate support for Box and Whisker series in WPF Chart](Series_images/boxAndWhisker5.png)

## Waterfall Series

[`WaterfallSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.WaterfallSeries.html) clarifies the cumulative effect of set of provided positive and negative values. The series is represented by a rectangle and a connector between the rectangles. 

The following code illustrates how to use the series in chart.

{% tabs %}

{% highlight xaml %}

<chart:WaterfallSeries ItemsSource="{Binding RevenueDetails}"  
                      
                       XBindingPath="Category" 
                      
                       YBindingPath="Value">

</chart:WaterfallSeries>

{% endhighlight %}

{% highlight c# %}

WaterfallSeries waterfallSeries = new WaterfallSeries();

waterfallSeries.ItemsSource = new ViewModel().RevenueDetails;

waterfallSeries.XBindingPath = "Category";

waterfallSeries.YBindingPath = "Value";

chart.Series.Add(waterfallSeries);


{% endhighlight %}

{% endtabs %}

![Waterfall Chart type in WPF](Series_images/waterfall1.png)

**SummarySegmentPath and SummarySegmentBrush**

[`SummaryBindingPath`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.WaterfallSeries.html#Syncfusion_UI_Xaml_Charts_WaterfallSeries_SummaryBindingPathProperty) gets or sets the string value that indicates the sum of previous segments in series. 

The summary segment can be differentiated by applying the [`SummarySegmentBrush`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.WaterfallSeries.html#Syncfusion_UI_Xaml_Charts_WaterfallSeries_SummarySegmentBrushProperty) in series.

{% tabs %}

{% highlight xaml %}

<chart:WaterfallSeries ItemsSource="{Binding RevenueDetails}"  
                                  
                                   XBindingPath="Category"
                                  
                                   YBindingPath="Value" Interior="Gray"
                                  
                                   SummaryBindingPath="IsSummary"
                                  
                                   SummarySegmentBrush="RoyalBlue">

</chart:WaterfallSeries>

{% endhighlight %}

{% highlight c# %}

WaterfallSeries waterfallSeries = new WaterfallSeries();

waterfallSeries.ItemsSource = new ViewModel().RevenueDetails;

waterfallSeries.XBindingPath = "Category";

waterfallSeries.YBindingPath = "Value";

waterfallSeries.SummaryBindingPath = "IsSummary";

waterfallSeries.SummarySegmentBrush = new SolidColorBrush(Colors.RoyalBlue);

chart.Series.Add(waterfallSeries);

{% endhighlight %}

{% endtabs %}

![Waterfall Chart type in WPF](Series_images/waterfall2.png)

**NegativeSegmentBrush**

The appearance of the negative segment can be changed by using the [`NegativeSegmentBrush`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.WaterfallSeries.html#Syncfusion_UI_Xaml_Charts_WaterfallSeries_NegativeSegmentBrushProperty) property of series.

The following code illustrates how to change the appearance of the negative segment.

{% tabs %}

{% highlight xaml %}

<chart:WaterfallSeries NegativeSegmentBrush="Red">

</chart:WaterfallSeries>

{% endhighlight %}

{% highlight c# %}


WaterfallSeries waterfallSeries = new WaterfallSeries();

waterfallSeries.NegativeSegmentBrush = new SolidColorBrush(Colors.Red);

{% endhighlight %}

{% endtabs %}

![Waterfall Chart type in WPF](Series_images/waterfall3.png)

**AllowAutoSum**

The summary segment calculation can be changed by using the [`AllowAutoSum`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.WaterfallSeries.html#Syncfusion_UI_Xaml_Charts_WaterfallSeries_AllowAutoSum) property. By default, the property is true. When disabling this property, it renders the segment by using the y value of provided ItemsSource collection.

The following code example illustrates how the AllowAutoSum property value can be set.

{% tabs %}

{% highlight xaml %}

<chart:WaterfallSeries AllowAutoSum="False"
                       
                       SummaryBindingPath="IsSummary"
                       
                       SummarySegmentBrush="RoyalBlue">
 
 </chart:WaterfallSeries>

{% endhighlight %}

{% highlight c# %}

WaterfallSeries waterfallSeries = new WaterfallSeries();

waterfallSeries.AllowAutoSum = true;

waterfallSeries.SummaryBindingPath = "IsSummary";

waterfallSeries.SummarySegmentBrush = new SolidColorBrush(Colors.RoyalBlue);

chart.Series.Add(waterfallSeries);

{% endhighlight %}

{% endtabs %}

![Waterfall Chart type in WPF](Series_images/waterfall4.png)

### ConnectorLine

The connector line of series can be enabled or disabled by using its [`ShowConnector`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.WaterfallSeries.html#Syncfusion_UI_Xaml_Charts_WaterfallSeries_ShowConnectorProperty) line property. By default, the property value  is true.

{% tabs %}

{% highlight xaml %}

<chart:WaterfallSeries ShowConnector="False">

</chart:WaterfallSeries>

{% endhighlight %}

{% highlight c# %}

WaterfallSeries waterfallSeries = new WaterfallSeries();

waterfallSeries.ShowConnector = false;

{% endhighlight %}

{% endtabs %}

![Connector Line support for Waterfall Chart in WPF](Series_images/waterfall5.png)

**Connector line customization**

The connector line can be customized by applying [`ConnectorLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.WaterfallSeries.html#Syncfusion_UI_Xaml_Charts_WaterfallSeries_ConnectorLineStyleProperty) property of the series. The following code example illustrates how to apply style for connector line.

{% tabs %}

{% highlight xaml %}

<chart:WaterfallSeries.ConnectorLineStyle>

<Style TargetType="Line">

<Setter Property="Stroke" Value="Red"/>

<Setter Property="StrokeDashArray" Value="1"/>

<Setter Property="StrokeThickness" Value="2"/>

</Style>

</chart:WaterfallSeries.ConnectorLineStyle>

{% endhighlight %}

{% highlight c# %}

Style style = new Style(typeof(Line));

style.Setters.Add(new Setter(Line.StrokeProperty, new SolidColorBrush(Colors.Red)));

style.Setters.Add(new Setter(Line.StrokeDashArrayProperty, new DoubleCollection() { 1 }));

style.Setters.Add(new Setter(Line.StrokeThicknessProperty, 2));

WaterfallSeries series = new WaterfallSeries();

series.ConnectorLineStyle = style;

{% endhighlight %}

{% endtabs %}

![Connector line customization support in WPF](Series_images/waterfall6.png)

