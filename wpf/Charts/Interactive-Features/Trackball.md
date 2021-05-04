---
layout: post
title: Trackball in WPF Charts control | Syncfusion
description: Learn here all about Trackball support in Syncfusion WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---

# Trackball in WPF Charts (SfChart)

The [`ChartTrackBallBehavior`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#) allows you to track a data point closer to the cursor position. The x values are determined from the position of the vertical line in the axis and y values are determined from the points touching the vertical line in the series.

## Adding TrackBall to the SfChart

You can create an instance [`ChartTrackBallBehavior`](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#) and add it to the [`Behaviors`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_Behaviors) collection.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior>                                                  

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior();

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

To view the TrackBall in the particular Axis, you have to enable the ShowTrackBallInfo property in that axis as in the following code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis  ShowTrackBallInfo="True" />

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior();

chart.Behaviors.Add(behavior);

chart.PrimaryAxis = new CategoryAxis()
{

    ShowTrackBallInfo = true

};

{% endhighlight %}

{% endtabs %}

The default appearance of the trackball in primary axis (CategoryAxis).

![TrackBall support in WPF Chart](Interactive-Features_images/Interactive-Features_img7.jpeg)


The Trackball is composed of the following parts:

1. Vertical Line

2. Symbol

3. Axis Label

4. Series Label

## Vertical Line

The vertical line in the trackball is visible when you initialize the TrackBallBehavior.If you want to collapse the visibility of the trackball line, then you have to set ShowLine to false.

The following code snippet explains how to collapse the visibility of trackball line.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior ShowLine="False" />

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

    ShowLine = false

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![TrackBall support in WPF Chart](Interactive-Features_images/Interactive-Features_img8.jpeg)


**Customization of TrackBall Line**

SfChart allows you to customize the appearance of  trackball vertical line using the [`LineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_LineStyle) property.

The following code snippet explains the customization of trackball line.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <Style TargetType="Line" x:Key="lineStyle">

            <Setter Property="StrokeDashArray" Value="5,1,2"/>

            <Setter Property="Stroke" Value="Red"/>

            <Setter Property="StrokeThickness" Value="1.2"/>

        </Style>

    </syncfusion:SfChart.Resources>

    <syncfusion:SfChart.Behaviors>

        <syncfusion:ChartTrackBallBehavior LineStyle="{StaticResource lineStyle}"/>

    </syncfusion:SfChart.Behaviors>
            
</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior trackball = new ChartTrackBallBehavior()
{

    LineStyle = chart.Resources["lineStyle"] as Style

};

chart.Behaviors.Add(trackball);

{% endhighlight %}

{% endtabs %}

![TrackBall line customization in WPF Chart](Interactive-Features_images/Interactive-Features_img9.jpeg)


## Symbol

By default, the trackball symbol is displayed as ellipse to change the default style of the symbol using [`ChartTrackBallStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_ChartTrackBallStyle) property.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <Style TargetType="syncfusion:ChartTrackBallControl" x:Key="trackballStyle">

            <Setter Property="Background" Value="red"></Setter>

        </Style>

    </syncfusion:SfChart.Resources>

    <syncfusion:SfChart.Behaviors>

        <syncfusion:ChartTrackBallBehavior ChartTrackBallStyle="{StaticResource trackballStyle}"/>

    </syncfusion:SfChart.Behaviors>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

ChartTrackBallBehavior trackball = new ChartTrackBallBehavior()
{

    ChartTrackBallStyle = chart.Resources["trackballStyle"] as Style

};

chart.Behaviors.Add(trackball);

{% endhighlight %}

{% endtabs %}

![Symbol for trackball in WPF Chart](Interactive-Features_images/Interactive-Features_img10.jpeg)


## Axis Label

The axis label will be viewed when the ShowTrackBallInfo property is set to true. If you want to collapse the visibility of axis label in trackball then you have to set ShowTrackballInfo as false.

N>By default the value of ShowTrackBallInfo is false.

**Alignment** **of** **Axis** **Label**

The alignment of the axis label while moving trackball can be defined using [`AxisLabelAlignment`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_AxisLabelAlignment) property.

Auto –Axis label is aligned in Near/Far positions based on the trackball movement.

Far-Axis label is positioned far from the position of trackball.

Near- Axis label is near to the position of trackball.

Center-Axis label is aligned to the center of the trackball. By default, the axis label will positioned in center.

**Far**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior AxisLabelAlignment="Far">

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

    AxisLabelAlignment = ChartAlignment.Far

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Alignment support for trackball axis label in WPF Chart](Interactive-Features_images/Interactive-Features_img11.jpeg)


**Near**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior AxisLabelAlignment="Near"  >       

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

    AxisLabelAlignment = ChartAlignment.Near

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Alignment support for trackball axis label in WPF Chart](Interactive-Features_images/Interactive-Features_img12.jpeg)


### Customization of axis label

You can change the default appearance of the axis label in trackball using [`TrackballLabelTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_TrackBallLabelTemplate) property in ChartAxis as in the below code snippet.

{% tabs %}

{% highlight xaml %}

 <syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <DataTemplate x:Key="labelTemplate">

            <Border CornerRadius="4" BorderThickness="1" BorderBrush="Black"
                            
                    Background="BlueViolet" Margin="8">

                    <TextBlock Foreground="White" Text="{Binding ValueX}"/>

            </Border>

        </DataTemplate>

    </syncfusion:SfChart.Resources>

    <syncfusion:SfChart.Behaviors>

            <syncfusion:ChartTrackBallBehavior />

    </syncfusion:SfChart.Behaviors>

    <syncfusion:SfChart.PrimaryAxis>

            <syncfusion:CategoryAxis ShowTrackBallInfo="True" 
                                         
                                     LabelTemplate="{StaticResource labelTemplate}"/>

    </syncfusion:SfChart.PrimaryAxis>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

chart.PrimaryAxis = new NumericalAxis()
{

    ShowTrackBallInfo = true,

    TrackBallLabelTemplate = chart.Resources["labelTemplate"] as DataTemplate

};

{% endhighlight %}

{% endtabs %}

![Customization support for trackball axis label in WPF Chart](Interactive-Features_images/Interactive-Features_img13.jpeg)


### Series Label

When the trackball is hovered over, you can view the label is also displayed over the series in addition the axis label.

**ShowTrackballInfo**

The `ShowTrackballInfo` property of [`Cartesian Series`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CartesianSeries.html) allows user to enable or disable the [`trackball`](https://help.syncfusion.com/wpf/sfchart/interactive-features#trackball) label for corresponding series. By default, `ShowTrackballInfo` property is true. The property can be set as shown in the below code example:

{% tabs %}

{% highlight xaml %}

 <syncfusion:SfChart >
            <syncfusion:SplineSeries Interior="#4a4a4a"/>    
            <syncfusion:SplineSeries Interior="#7f7f7f" ShowTrackballInfo="False"/>
            <syncfusion:SplineSeries Interior="#bcbcbc"/>
 </syncfusion:SfChart>
 
{% endhighlight %}

{% highlight c# %}

  SplineSeries series1 = new SplineSeries()
  {
      Interior = new SolidColorBrush(Color.FromArgb(0, 0x4a, 0x4a, 0x4a))
  };
  chart.Series.Add(series1);
  SplineSeries series2 = new SplineSeries()
  {
      Interior = new SolidColorBrush(Color.FromArgb(0, 0x7f, 0x7f, 0x7f)),
      ShowTrackballInfo = false
  };
  chart.Series.Add(series2);
  SplineSeries series3 = new SplineSeries()
  {
      Interior = new SolidColorBrush(Color.FromArgb(0, 0xbc, 0xbc, 0xbc))
  };
  chart.Series.Add(series3);

{% endhighlight %}

{% endtabs %}

![TrackBall series label in WPF Chart](Interactive-Features_images/ShowTrackball.png)



**Alignment** **of** **Series** **Label**

The trackball label displayed over the series can be aligned using the [`LabelHorizontalAlignment`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_LabelHorizontalAlignment) and [`LabelVerticalAlignment`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_LabelVerticalAlignment) properties. By default, the series label will be horizontally aligned to the left and vertically to the top.

The following code snippet explains how to align the series label to the center of the trackball.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior LabelHorizontalAlignment="Center" 

LabelVerticalAlignment="Center">

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

    LabelHorizontalAlignment = ChartAlignment.Center,

    LabelVerticalAlignment = ChartAlignment.Center

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Alignment support for trackball series label in WPF Chart](Interactive-Features_images/Interactive-Features_img14.jpeg)


### Label Display Mode

When there is a multiple series, by default, the trackball series label will be displayed only for the nearest point. If you want to display all the y values with respect to the x value then the [`LabelDisplayMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_LabelDisplayMode) property is set to [`FloatAllPoints`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.TrackballLabelDisplayMode.html).

**FloatAllPoints**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior LabelDisplayMode="FloatAllPoints" >

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

    LabelDisplayMode = TrackballLabelDisplayMode.FloatAllPoints

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![LabelDisplayMode support for trackball in WPF Chart](Interactive-Features_images/Interactive-Features_img15.jpeg)


**NearestPoint**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior LabelDisplayMode="NearestPoint" >

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

    LabelDisplayMode = TrackballLabelDisplayMode.NearestPoint

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![LabelDisplayMode support for trackball in WPF Chart](Interactive-Features_images/Interactive-Features_img16.jpeg)

**GroupAllPoints**

[`ChartTrackBallBehavior`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html) supports to group the multiple selected trackball points, and allows to display the trackball points in a single trackball label. It can be achieved by setting the [`LabelDisplayMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_LabelDisplayModeProperty) property of [`ChartTrackBallBehavior`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html) as GroupAllPoints.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior LabelDisplayMode="GroupAllPoints" >

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

    LabelDisplayMode = TrackballLabelDisplayMode.GroupAllPoints

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates the trackball label for multiple series, when the [`LabelDisplayMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_LabelDisplayModeProperty) property value is GroupAllPoints.

![LabelDisplayMode support for trackball in WPF Chart](Interactive-Features_images/grouping1.png)

The following screenshot illustrates the trackball label for financial series, when the [`LabelDisplayMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_LabelDisplayModeProperty) property value is GroupAllPoints.

![LabelDisplayMode support for trackball in WPF Chart](Interactive-Features_images/grouping2.png)


## TrackBall for Technical Indicators

In trackball label, the data point value of the technical indicator also can be displayed by enabling [`ShowTrackballInfo`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FinancialTechnicalIndicator.html#Syncfusion_UI_Xaml_Charts_FinancialTechnicalIndicator_ShowTrackballInfoProperty) of technical indicator. It is shown in the following code example.

{% tabs %}

{% highlight xaml %}

 <chart:SfChart.Behaviors>

                <chart:ChartTrackBallBehavior />

 </chart:SfChart.Behaviors>  

<chart:SfChart.TechnicalIndicators>

                <chart:AverageTrueRangeIndicator ShowTrackballInfo="True" >

                </chart:AverageTrueRangeIndicator>

 </chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior();

chart.Behaviors.Add(behavior);

AverageTrueRangeIndicator average = new AverageTrueRangeIndicator();

average.ShowTrackballInfo = true;

chart.TechnicalIndicators.Add(average);

{% endhighlight %}

{% endtabs %}

![TrackBall for Technical Indicators support in WPF](Interactive-Features_images/indicator.png)

N> By default, [`ShowTrackballInfo`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.FinancialTechnicalIndicator.html#Syncfusion_UI_Xaml_Charts_FinancialTechnicalIndicator_ShowTrackballInfoProperty) value of technical indicators is false.

### TrackBall Label Template

[`TrackBallLabelTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_TrackBallLabelTemplate) property in [`ChartSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#) allows you to customize the appearance of series label in trackball.

{% tabs %}

{% highlight xaml %}

  <syncfusion:SfChart x:Name="chart">

        <syncfusion:SfChart.Resources>

            <DataTemplate x:Key="labelTemplate">

                <Border CornerRadius="5" BorderThickness="1" 
                            
                        BorderBrush="Black" Background="BlueViolet" Margin="8">

                    <TextBlock Foreground="White" Text="{Binding ValueY}"/>

                </Border>

            </DataTemplate>

         </syncfusion:SfChart.Resources>

        <syncfusion:SfChart.Behaviors>

                <syncfusion:ChartTrackBallBehavior />

        </syncfusion:SfChart.Behaviors>

        <syncfusion:ColumnSeries Label="2010"  Interior="#4A4A4A"     

                                 ItemsSource="{Binding Demands}" 

                                 XBindingPath="Demand" 
                                     
                                 YBindingPath="Year2010"
                                 
                                 TrackBallLabelTemplate="{StaticResource labelTemplate}"/>
          
</syncfusion:SfChart>


{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

ChartTrackBallBehavior trackball = new ChartTrackBallBehavior();

chart.Behaviors.Add(trackball);

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    TrackBallLabelTemplate = chart.Resources["labelTemplate"] as DataTemplate,

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Trackball templte support for trackball in WPF Chart](Interactive-Features_images/Interactive-Features_img17.jpeg)


**Applying** **Palette** **to** **the** **Series** **Label**

Palette or interior color of the Series is applied to the series label by setting [`UseSeriesPalette`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_UseSeriesPalette) to True as shown in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior UseSeriesPalette="True" >

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

     UseSeriesPalette = true

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Applying palette to the trackball series label in WPF Chart](Interactive-Features_images/Interactive-Features_img18.jpeg)


## Events

The following events are available in ChartTrackBallBehavior:

**PositionChanging**

The [`PositionChanging`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html) event occurs when the [`trackball`](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#) position is changing from current mouse position to new mouse position. This argument contains the following information.

* [`Cancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PositionChangingEventArgs.html#Syncfusion_UI_Xaml_Charts_PositionChangingEventArgs_Cancel) - Gets or sets a value that indicates whether to show the trackball on new mouse pointer position.
* [`PointInfos`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PositionChangingEventArgs.html#Syncfusion_UI_Xaml_Charts_PositionChangingEventArgs_PointInfos) - Gets or sets the current [`ChartPointInfo`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html).

**PositionChanged**

The [`PositionChanged`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html) event occurs when the [`trackball`](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#) position is changed from current mouse position to new mouse position. This argument contains the following information.

* [`PreviousPointInfos`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PositionChangedEventArgs.html#Syncfusion_UI_Xaml_Charts_PositionChangedEventArgs_PreviousPointInfos) - Gets or sets the previous [`ChartPointInfo`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html).
* [`CurrentPointInfos`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PositionChangedEventArgs.html#Syncfusion_UI_Xaml_Charts_PositionChangedEventArgs_CurrentPointInfos) - Gets or sets the current [`ChartPointInfo`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html).

The [`ChartPointInfo`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html) class contains the following properties to customize the appearance of trackball label:

* [`Axis`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Axis) - Gets the associated axis in which the trackball is activated.
* [`BaseX`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_BaseX) - Gets the x-initial coordinate of the trackball label. 
* [`BaseY`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_BaseY) - Gets the y-initial coordinate of the trackball label.
* [`BorderBrush`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_BorderBrush) - Gets or sets the border color of the trackball label.
* [`Close`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Close) - Gets the close value of the trackball label when it is applicable.
* [`Foreground`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Foreground) - Gets or sets the foreground color of the trackball label.
* [`High`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_High) - Gets the high value of the trackball label when it is applicable.
* [`Interior`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Interior) - Gets or sets the interior color of the trackball label.
* [`Item`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Item) - Gets the respective underlying object of the data in which the trackball is activated.
* [`Low`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Low) - Gets the low value of the trackball label when it is applicable.
* [`LowerLine`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_LowerLine) - Gets the y-value of the lower line in indicator. 
* [`Median`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Median) - Gets the median value when it is applicable.
* [`Open`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Open) - Gets the open value of the trackball label when it is applicable.
* [`PolygonPoints`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_PolygonPoints) - Gets the point collection to render trackball.
* [`Series`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Series) - Gets the associated series in which the trackball is activated.
* [`SeriesValues`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_SeriesValues) - Gets the SeriesValues in which the trackball is activated.
* [`SignalLine`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_SignalLine) - Gets the y-value of the signal line in indicator. 
* [`UpperLine`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_UpperLine) - Gets the y-value of the upper line in indicator. 
* [`ValueX`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_ValueX) - Gets the x-value of the trackball label.
* [`ValueY`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_ValueY) - Gets the y-value of the trackball label.
* [`X`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_X) - Gets the x-coordinate of the trackball label.
* [`Y`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Y) - Gets the y-coordinate of the trackball label.

## See also

[`How to disable a trackball for a specific series`](https://www.syncfusion.com/kb/11291/how-to-disable-a-trackball-for-a-specific-series)

[`How to customize the trackball appearance in WPF Chart`](https://www.syncfusion.com/kb/11020/how-to-customize-the-trackball-appearance-in-wpf-chart)

[`How to apply label formatting to the trackball labels`](https://www.syncfusion.com/kb/5362/how-to-apply-label-formatting-to-the-trackball-labels)
