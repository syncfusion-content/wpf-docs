---
layout: post
title: Syncfusion InteractiveFeatures.
description: How to show the functionality of WPF Chart with available interaction options such as zooming, selecting, and tracking the data points.
platform: wpf
control: SfChart
documentation: ug
---

# Interactive features

SfChart provides interactive features such as zooming, selection, and tracking data points.

The following interactive features are supported in SfChart:

* ToolTip
* TrackBall
* Visual Data Editing
* Zoom and Pan
* Selection
* Resizing Scrollbar
* CrossHair

## ToolTip

The ToolTip feature allows you to display any information over a [`ChartSeries`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeries.html#). It is used in conjunction with the pointer. It appears when the mouse hovers over any chart segment. It is set to display the metadata of the particular segment or data point.

By default, a small box containing the data points y values are displayed as the ToolTip. The y values vary depending on the [`ChartSeries`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeries.html#). For example, a single y value is usually displayed in Column and [`BarSeries`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.BarSeries.html#). In the [`FinancialSeries`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase.html#), high, low, open, and close values are displayed in ToolTip. 

The tooltip will be visible if you enable [`ShowTooltip`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~ShowTooltip.html) property as in the below code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:ColumnSeries  ShowTooltip="True"                                                  

ItemsSource="{Binding Demands}" 

XBindingPath="Demand"  YBindingPath="Year2010"/>

<syncfusion:ColumnSeries ItemsSource="{Binding Demands}" 

ShowTooltip="True"                           

XBindingPath="Demand"  YBindingPath="Year2011"/>           

{% endhighlight %}

{% highlight c# %}

ColumnSeries series1 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true

};

ColumnSeries series2 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    ShowTooltip = true

};

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Tooltip support in WPF Chart](Interactive-Features_images/Interactive-Features_img1.jpeg)


### Aligning the ToolTip

The tooltip can be aligned with respect to the cursor position using the [`HorizontalAlignment`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTooltip_members.html#) and [`VerticalAlignment`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTooltip_members.html#) properties.

**HorizontalAlignment**

The following code example explains the positioning of tooltip to the left of the cursor.

{% tabs %}

{% highlight xaml %}

<Chart:ColumnSeries ShowTooltip="True" ItemsSource="{Binding Demands}"  

Chart:ChartTooltip.HorizontalAlignment="Left"

XBindingPath="Demand"  YBindingPath="Year2010" />

<Chart:ColumnSeries ItemsSource="{Binding Demands}" 

Chart:ChartTooltip.HorizontalAlignment="Left" ShowTooltip="True"

XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series1 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true
    
};

ChartTooltip.SetHorizontalAlignment(series1, HorizontalAlignment.Left);

ColumnSeries series2 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    ShowTooltip = true

};

ChartTooltip.SetHorizontalAlignment(series2, HorizontalAlignment.Left);

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Tooltip alignment support in WPF Chart](Interactive-Features_images/Interactive-Features_img2.jpeg)

N> By default the horizontal alignment is center for the tooltip.

**VerticalAlignment**

The following code example explains the positioning of tooltip to the bottom of the cursor.

{% tabs %}

{% highlight xaml %}

<Chart:ColumnSeries ShowTooltip="True" ItemsSource="{Binding Demands}"  

Chart:ChartTooltip.VerticalAlignment="Bottom"

XBindingPath="Demand" YBindingPath="Year2010" />

<Chart:ColumnSeries ItemsSource="{Binding Demands}"

Chart:ChartTooltip.VerticalAlignment="Bottom"

ShowTooltip="True" XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series1 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true
    
};

ChartTooltip.SetVerticalAlignment(series1, VerticalAlignment.Bottom);

ColumnSeries series2 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    ShowTooltip = true

};

ChartTooltip.SetVerticalAlignment(series2, VerticalAlignment.Bottom);

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Tooltip alignment support in WPF Char](Interactive-Features_images/Interactive-Features_img3.jpeg)


**ToolTipMargin**

You can also set the distance for the margin to be positioned from the cursor using the ToolTipMargin property as in the following code snippet.

{% tabs %}

{% highlight xaml %}

<Chart:ColumnSeries Label="2010" ShowTooltip="True"

ItemsSource="{Binding Demands}"   Interior="#777777"

Chart:ChartTooltip.TooltipMargin="25"

XBindingPath="Demand" YBindingPath="Year2010" />

<Chart:ColumnSeries Label="2011"  ItemsSource="{Binding Demands}"

Interior="#4A4A4A"

Chart:ChartTooltip.TooltipMargin="25"

ShowTooltip="True" XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series1 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

ChartTooltip.SetTooltipMargin(series1, new Thickness(25));

ColumnSeries series2 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A)),

    Label = "2011"

};

ChartTooltip.SetTooltipMargin(series2, new Thickness(25));

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Margin for tooltip in WPF Char](Interactive-Features_images/Interactive-Features_img4.jpeg)


N>By default, the VerticalAlignment of the Tooltip is Top.

**VerticalOffset and HorizontalOffset**

The tooltip can be positioned at a particular distance from the cursor horizontally using the [`HorizontalOffset`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTooltip~SetHorizontalOffset.html#) and vertically using [`VerticalOffset`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTooltip~SetVerticalOffset.html#) properties.

{% tabs %}

{% highlight xaml %}

<Chart:ColumnSeries ShowTooltip="True"

ItemsSource="{Binding Demands}" 

Chart:ChartTooltip.HorizontalOffset="40"

Chart:ChartTooltip.VerticalOffset="40"

XBindingPath="Demand" YBindingPath="Year2010" />

<Chart:ColumnSeries ItemsSource="{Binding Demands}"

Chart:ChartTooltip.HorizontalOffset="40"

Chart:ChartTooltip.VerticalOffset="40" ShowTooltip="True"

XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series1 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

ChartTooltip.SetHorizontalOffset(series1, 40);

ChartTooltip.SetVerticalOffset(series1, 40);

ColumnSeries series2 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A)),

    Label = "2011"

};

ChartTooltip.SetHorizontalOffset(series2, 40);

ChartTooltip.SetVerticalOffset(series2, 40);

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![VerticalOffset and HorizontalOffset support for tooltip in WPF Chart](Interactive-Features_images/Interactive-Features_img5.jpeg)

### ToolTip duration

This property [`ShowDuration`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTooltip~SetShowDuration.html#) in [`ChartToolTip`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTooltip.html#) sets the duration time for tooltip to be displayed in milliseconds.

The following code example demonstrates the duration of the tooltip set as 5 seconds.

{% tabs %}

{% highlight xml %}

<Chart:ColumnSeries ShowTooltip="True"  

Chart:ChartTooltip.ShowDuration="5000"                                          

ItemsSource="{Binding Demands}" Interior="#777777"                                     

XBindingPath="Demand"  YBindingPath="Year2010">                                   

</Chart:ColumnSeries>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

ChartTooltip.SetShowDuration(series, 5000);

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

N> The tooltip by default will be displayed for 1000 milliseconds.

**Show delay**

ToolTip also has support to delay the time to display by setting the [`SetInitialShowDelay`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTooltip~SetInitialShowDelay.html#) property in milliseconds.

The following code example demonstrates the tooltip will be delayed for 1 second at the before display.

{% tabs %}

{% highlight xml %}

<Chart:ColumnSeries Label="2010" ShowTooltip="True"  

Chart:ChartTooltip.InitialShowDelay="1000"                                          

ItemsSource="{Binding Demands}" Interior="#777777"                                     

XBindingPath="Demand"  YBindingPath="Year2010" />                                   

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

ChartTooltip.SetInitialShowDelay(series, 1000);

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

### Animation for ToolTip

You can also provide animation effects for tooltip by setting the [`EnableAnimation`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTooltip~SetEnableAnimation.html#) property to true as shown in the following code snippet.

{% tabs %}

{% highlight xml %}

<Chart:ColumnSeries Label="2010" ShowTooltip="True"  

Chart:ChartTooltip.EnableAnimation="True"                                          

ItemsSource="{Binding Demands}" Interior="#777777"                                     

XBindingPath="Demand"  YBindingPath="Year2010">                                   

</Chart:ColumnSeries>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

ChartTooltip.SetEnableAnimation(series, true);

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

### Customizing the Tooltip

The [`ToolTipTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~TooltipTemplate.html#) property allows you to customize the default appearance of the tooltip as explained in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:ColumnSeries ShowTooltip="True"

ItemsSource="{Binding Demands}"

TooltipTemplate="{StaticResource tooltip}"

XBindingPath="Demand" YBindingPath="Year2010" />

<syncfusion:ColumnSeries  ItemsSource="{Binding Demands}"

TooltipTemplate="{StaticResource tooltip}"

ShowTooltip="True" XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series1 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    Label = "2010",

    ShowTooltip = true,

    TooltipTemplate = chart.Resources["tooltipTemplate"] as DataTemplate,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

ColumnSeries series2 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Label = "2011",

    ShowTooltip = true,

    TooltipTemplate = chart.Resources["tooltipTemplate"] as DataTemplate,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Tooltip customization support in WPF Chart](Interactive-Features_images/Interactive-Features_img6.jpeg)

## TrackBall

The [`ChartTrackBallBehavior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#) allows you to track a data point closer to the cursor position. The x values are determined from the position of the vertical line in the axis and y values are determined from the points touching the vertical line in the series.

### Adding TrackBall to the SfChart

You can create an instance [`ChartTrackBallBehavior`](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#) and add it to the [`Behaviors`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SfChart~Behaviors.html) collection.

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

### Vertical Line

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

SfChart allows you to customize the appearance of  trackball vertical line using the [`LineStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior~LineStyle.html#) property.

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


### Symbol

By default, the trackball symbol is displayed as ellipse to change the default style of the symbol using [`ChartTrackBallStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior~ChartTrackBallStyle.html#) property.

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


### Axis Label

The axis label will be viewed when the ShowTrackBallInfo property is set to true. If you want to collapse the visibility of axis label in trackball then you have to set ShowTrackballInfo as false.

N>By default the value of ShowTrackBallInfo is false.

**Alignment** **of** **Axis** **Label**

The alignment of the axis label while moving trackball can be defined using [`AxisLabelAlignment`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior~AxisLabelAlignment.html#) property.

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

You can change the default appearance of the axis label in trackball using [`TrackballLabelTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxis~TrackBallLabelTemplate.html#) property in ChartAxis as in the below code snippet.

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

The `ShowTrackballInfo` property of [`Cartesian Series`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CartesianSeries.html) allows user to enable or disable the [`trackball`](https://help.syncfusion.com/wpf/sfchart/interactive-features#trackball) label for corresponding series. By default, `ShowTrackballInfo` property is true. The property can be set as shown in the below code example:

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

The trackball label displayed over the series can be aligned using the [`LabelHorizontalAlignment`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior~LabelHorizontalAlignment.html#) and [`LabelVerticalAlignment`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior~LabelVerticalAlignment.html#) properties. By default, the series label will be horizontally aligned to the left and vertically to the top.

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


### LabelDisplayMode

When there is a multiple series, by default, the trackball series label will be displayed only for the nearest point. If you want to display all the y values with respect to the x value then the [`LabelDisplayMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior~LabelDisplayMode.html#) property is set to [`FloatAllPoints`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.TrackballLabelDisplayMode.html).

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

[`ChartTrackBallBehavior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html) supports to group the multiple selected trackball points, and allows to display the trackball points in a single trackball label. It can be achieved by setting the [`LabelDisplayMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior~LabelDisplayModeProperty.html) property of [`ChartTrackBallBehavior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html) as GroupAllPoints.

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

The following screenshot illustrates the trackball label for multiple series, when the [`LabelDisplayMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior~LabelDisplayModeProperty.html) property value is GroupAllPoints.

![LabelDisplayMode support for trackball in WPF Chart](Interactive-Features_images/grouping1.png)

The following screenshot illustrates the trackball label for financial series, when the [`LabelDisplayMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior~LabelDisplayModeProperty.html) property value is GroupAllPoints.

![LabelDisplayMode support for trackball in WPF Chart](Interactive-Features_images/grouping2.png)


### TrackBall for Technical Indicators

In trackball label, the data point value of the technical indicator also can be displayed by enabling [`ShowTrackballInfo`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialTechnicalIndicator~ShowTrackballInfoProperty.html) of technical indicator. It is shown in the following code example.

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

N> By default, [`ShowTrackballInfo`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialTechnicalIndicator~ShowTrackballInfoProperty.html) value of technical indicators is false.

### TrackBallLabelTemplate

[`TrackBallLabelTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~TrackBallLabelTemplate.html#) property in [`ChartSeries`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#) allows you to customize the appearance of series label in trackball.

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

Palette or interior color of the Series is applied to the series label by setting [`UseSeriesPalette`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior~UseSeriesPalette.html#) to True as shown in the following code snippet.

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


### Events

The following events are available in ChartTrackBallBehavior:

**PositionChanging**

The [`PositionChanging`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior~PositionChanging_EV.html) event occurs when the [`trackball`](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#) position is changing from current mouse position to new mouse position. This argument contains the following information.

* [`Cancel`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.PositionChangingEventArgs~Cancel.html) - Gets or sets a value that indicates whether to show the trackball on new mouse pointer position.
* [`PointInfos`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.PositionChangingEventArgs~PointInfos.html) - Gets or sets the current [`ChartPointInfo`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo.html).

**PositionChanged**

The [`PositionChanged`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior~PositionChanged_EV.html) event occurs when the [`trackball`](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#) position is changed from current mouse position to new mouse position. This argument contains the following information.

* [`PreviousPointInfos`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.PositionChangedEventArgs~PreviousPointInfos.html) - Gets or sets the previous [`ChartPointInfo`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo.html).
* [`CurrentPointInfos`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.PositionChangedEventArgs~CurrentPointInfos.html) - Gets or sets the current [`ChartPointInfo`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo.html).

The [`ChartPointInfo`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo.html) class contains the following properties to customize the appearance of trackball label:

* [`Axis`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~Axis.html) - Gets the associated axis in which the trackball is activated.
* [`BaseX`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~BaseX.html) - Gets the x-initial coordinate of the trackball label. 
* [`BaseY`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~BaseY.html) - Gets the y-initial coordinate of the trackball label.
* [`BorderBrush`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~BorderBrush.html) - Gets or sets the border color of the trackball label.
* [`Close`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~Close.html) - Gets the close value of the trackball label when it is applicable.
* [`Foreground`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~Foreground.html) - Gets or sets the foreground color of the trackball label.
* [`High`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~High.html) - Gets the high value of the trackball label when it is applicable.
* [`Interior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~Interior.html) - Gets or sets the interior color of the trackball label.
* [`Item`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~Item.html) - Gets the respective underlying object of the data in which the trackball is activated.
* [`Low`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~Low.html) - Gets the low value of the trackball label when it is applicable.
* [`LowerLine`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~LowerLine.html) - Gets the y-value of the lower line in indicator. 
* [`Median`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~Median.html) - Gets the median value when it is applicable.
* [`Open`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~Open.html) - Gets the open value of the trackball label when it is applicable.
* [`PolygonPoints`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~PolygonPoints.html) - Gets the point collection to render trackball.
* [`Series`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~Series.html) - Gets the associated series in which the trackball is activated.
* [`SeriesValues`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~SeriesValues.html) - Gets the SeriesValues in which the trackball is activated.
* [`SignalLine`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~SignalLine.html) - Gets the y-value of the signal line in indicator. 
* [`UpperLine`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~UpperLine.html) - Gets the y-value of the upper line in indicator. 
* [`ValueX`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~ValueX.html) - Gets the x-value of the trackball label.
* [`ValueY`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~ValueY.html) - Gets the y-value of the trackball label.
* [`X`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~X.html) - Gets the x-coordinate of the trackball label.
* [`Y`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartPointInfo~Y.html) - Gets the y-coordinate of the trackball label.

## Visual data editing

SfChart has a feature that allows you to edit an entire series or a single data point at run time by dragging the single point or the series as a whole.

### Segment dragging

Segment Dragging defines the dragging a particular point or segment based on the series type. The segment dragging can be enabled using the [`EnableSegmentDragging`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~EnableSegmentDragging.html#) property to true.

**Line Series**

{% tabs %}

{% highlight xml %}

<syncfusion:LineSeries Label="2010" EnableSegmentDragging="True"

XBindingPath="Demand"   Interior="#777777"

ItemsSource="{Binding Demands}"                                   

YBindingPath="Year2010">

</syncfusion:LineSeries>

{% endhighlight %}

{% highlight c# %}

LineSeries series = new LineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

chart.Series.Add(series)

{% endhighlight %}

{% endtabs %}

![Segment dragging support in WPF Chart](Interactive-Features_images/Interactive-Features_img19.jpg)


**Column Series**

{% tabs %}

{% highlight xml %}

<syncfusion:ColumnSeries Label="2010" EnableDragTooltip="True" EnableSegmentDragging="True"

XBindingPath="Demand"   Interior="#777777"

ItemsSource="{Binding Demands}"                                   

YBindingPath="Year2010">

</syncfusion:ColumnSeries>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    EnableDragTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

chart.Series.Add(series)

{% endhighlight %}

{% endtabs %}

![Segment dragging support in WPF Chart](Interactive-Features_images/Interactive-Features_img20.jpg)

**Scatter Series**

This series supports dragging in both the x and y co-ordinates. The dragging co-ordinates can be set by using the enum property [`DragDirection`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ScatterSeries~DragDirection.html).

{% tabs %}

{% highlight xml %}

<syncfusion:ScatterSeries ItemsSource="{Binding Data}" XBindingPath="Index" 

                          YBindingPath="Value"  Interior="#777777"

                          EnableSegmentDragging="True" DragDirection="XY" >

 </syncfusion:ScatterSeries>

{% endhighlight %}

{% highlight c# %}

ScatterSeries series = new ScatterSeries()
            
{
                
ItemsSource = new ViewModel().Data,
                
XBindingPath = "Index",
                
YBindingPath = "Value",
                
Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),
                
EnableSegmentDragging = true,

DragDirection = DragType.XY
            
};

chart.Series.Add(series)

{% endhighlight %}

{% endtabs %}

![Segment dragging support in WPF Chart](Interactive-Features_images/Interactive-Features_img55.jpg)

N> By default, the DragDirection of the scatter series is XY.

### Series dragging

SfChart provides support to drag the LineSeries and SplineSeries. This allows the series to move to a new position by dragging. To enable the series dragging, you have to set [`EnableSeriesDragging`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySeriesDraggingBase~EnableSeriesDragging.html#) property to true.

The following code snippet explains the series dragging feature in LineSeries.

{% tabs %}

{% highlight xaml %}

<syncfusion:LineSeries Label="2010" EnableDragTooltip="True" EnableSeriesDragging="True"

XBindingPath="Demand"   Interior="#777777" ItemsSource="{Binding Demands}"

YBindingPath="Year2010"/>

{% endhighlight %}

{% highlight c# %}

LineSeries series = new LineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSeriesDragging = true,

    EnableDragTooltip = true ,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Segment dragging support in WPF Chart](Interactive-Features_images/Interactive-Features_img21.jpeg)


N>In line and Spline Series, if segment and series dragging is enabled, the series dragging is having higher priority over segment dragging.

### Adding ToolTip for dragging

While the series or segment is dragged by default you can view the tooltip showing the new y value. To disable the tooltip while dragging you have to set the [`EnableDragToolTip`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~EnableDragTooltip.html) as false.

{% tabs %}

{% highlight xml %}

<syncfusion:LineSeries Label="2010"  EnableSegmentDragging="True" EnableDragTooltip="False"

XBindingPath="Demand"   Interior="#777777"

Focusable="False"

ItemsSource="{Binding Demands}"                                   

</syncfusion:LineSeries>

{% endhighlight %}

{% highlight c# %}

LineSeries series = new LineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSeriesDragging = true,

    EnableDragTooltip = true ,

    Focusable = false,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

chart.Series.Add(series);


{% endhighlight %}

{% endtabs %}

![Adding tooltip for dragging in WPF Chart](Interactive-Features_images/Interactive-Features_img22.jpeg)


**Drag Tooltip Template**

[`DragTooltipTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~DragTooltipTemplate.html#)  property allows you to customize the default appearance of the tooltip while dragging.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <DataTemplate x:Key="tooltipTemplate">

            <Border CornerRadius="4" BorderBrush="Black"
                            
                    BorderThickness="1" Background="CadetBlue" 
                    
                    Margin="0,0,0,15">

                <TextBlock  FontSize="12" Text="{Binding NewValue}" 
                                    
                            Width="35" Foreground="White" Margin="2">
                
                </TextBlock>

            </Border>

        </DataTemplate>

    </syncfusion:SfChart.Resources>

    <syncfusion:LineSeries Label="2010" EnableSegmentDragging="True" 
                                   
                           Interior="#777777"
                                   
                           Focusable="False" 

                           XBindingPath="Demand" 
                                   
                           ItemsSource="{Binding Demands}"          
                                   
                           YBindingPath="Year2010"
                                   
                           DragTooltipTemplate="{StaticResource tooltipTemplate }">

    </syncfusion:LineSeries>
            
</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    Focusable = false,

    EnableSegmentDragging = true,

    DragTooltipTemplate = chart.Resources["tooltipTemplate"] as DataTemplate,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Customizing tooltip while dragging in WPF Chart](Interactive-Features_images/Interactive-Features_img23.jpg)

**Drag Tooltip Style**

The dragging tooltip can be customized by using the [`DragTooltipStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~DragTooltipStyle.html) property of the series.

The following are the API’s in `ChartDragTooltipStyle`.

[`FontFamily`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle~FontFamily.html) – Gets or sets the font family for dragging tooltip text.

[`FontSize`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle~FontSize.html) – Gets or sets the font size for dragging tooltip text.

[`FontStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle~FontStyle.html) – Gets or sets the font style for dragging tooltip text.

[`Foreground`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle~Foreground.html) – Gets or sets the brush for dragging tooltip text.

[`Background`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle~Background.html) – Gets or sets the background brush for dragging tooltip.

{% tabs %}

{% highlight xml %}

<syncfusion:LineSeries.DragTooltipStyle>
                    
<syncfusion:ChartDragTooltipStyle FontFamily="Calibri" FontSize="14" 
                                                     
                                  FontStyle="Italic" Background="DarkGray" 
                                                      
                                  Foreground="Black" />

</syncfusion:LineSeries.DragTooltipStyle>

{% endhighlight %}

{% highlight c# %}

series.DragTooltipStyle = new ChartDragTooltipStyle()
            
{
                
    FontFamily = new FontFamily("Calibri"),
                
    FontSize = 14,
                
    FontStyle = FontStyles.Italic,
                
    Background = new SolidColorBrush(Colors.DarkGray),
                
    Foreground = new SolidColorBrush(Colors.Black)
            
};

{% endhighlight %}

{% endtabs %}

![Customizing tooltip while dragging in WPF Chart](Interactive-Features_images/Interactive-Features_img56.jpg)

**Rounding** **Off** **the** **Dragged** **Value**

To round off the dragged values, you have to set the [`SnapToPoint`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~SnapToPoint.html#) and [`RoundToDecimal`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~RoundToDecimal.html#) properties. The following code snippet explains rounding the dragged y value to 2 decimal digits.

{% tabs %}

{% highlight xml %}

<syncfusion:SplineSeries   EnableSegmentDragging="True"

SnapToPoint="Round" RoundToDecimal="2" YBindingPath = "Year2010"

UpdateSource="True" XBindingPath="Demand"   Interior="#777777"

ItemsSource="{Binding Demands}"                                   

</syncfusion:SplineSeries>

{% endhighlight %}

{% highlight c# %}

SplineSeries series = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    UpdateSource = true ,

    RoundToDecimal = 2,

    SnapToPoint = SnapToPoint.Round,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

### Updating the Dragged Values to the Source

When dragging the series or segment at run time, to update the underlying data based on the values you have to set the [`UpdateSource`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~UpdateSource.html#) property to true as in the following code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SplineSeries   EnableSegmentDragging="True" UpdateSource="True"

XBindingPath="Demand"   Interior="#777777"

ItemsSource="{Binding Demands}"                                   

YBindingPath="Year2010">

</syncfusion:SplineSeries>

{% endhighlight %}

{% highlight c# %}

SplineSeries series = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    UpdateSource = true ,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

### Drag Cancel using KeyModifiers

While you are dragging you can set the KeyModifiers to cancel the drag by setting [`DragCancelKeyModifier`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~DragCancelKeyModifiers.html#) property as in the below code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SplineSeries  

EnableSegmentDragging="True" 

DragCancelKeyModifiers="Alt"  

UpdateSource="True"

XBindingPath="Demand"                                   

ItemsSource="{Binding Demands}"                                   

YBindingPath="Year2010">

</syncfusion:SplineSeries>

{% endhighlight %}

{% highlight c# %}

SplineSeries series = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    DragCancelKeyModifiers = ModifierKeys.Alt,

    UpdateSource = true ,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}


### Events

Series with visual data editing has support for following events:

* [`DragStart`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~DragStart_EV.html#)- Occurs when segment/series drag started. 
* [`DragDelta`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~DragDelta_EV.html#)- Occurs when segment/series dragging.
* [`DragEnd`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~DragEnd_EV.html#)- Occurs when segment/series drag end. 
* [`PreviewDragEnd`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~PreviewDragEnd_EV.html#)- Occurs before drag end triggered. 
* [`SegmentEnter`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~SegmentEnter_EV.html#)- Occurs when mouse enters in segment. 


## Zoom and Pan

SfChart allows you to zoom the chart area with the help of the zoom feature. This behavior is mostly used to view the data point in the specific area, when there are a number of data points inside the chart.

Zooming and panning provides you to take a close-up look of the data point plotted in the series

### Adding Zooming/Panning to the SfChart

You can create an instance ChartZoomPanBehavior and add it to the Behaviors collection.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior >                                             

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior();

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}


### Zooming the ChartArea

**Zooming** **by** **setting** **ZoomFactor** **and** **ZoomPosition**

[`ZoomFactor`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~ZoomFactor.html#) defines the percentage of visible range from the total range of axis values. [`ZoomPosition`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~ZoomPosition.html#) defines the ranges of values that need to be displayed as a result of [`ZoomFactor`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~ZoomFactor.html#). 

The following code example demonstrates the zooming the chart axis by setting zoom position and zoom factor.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis 

ShowGridLines="False"

ZoomFactor="0.3" ZoomPosition="0.1" />

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    ShowGridLines = false,

    ZoomFactor = 0.1,

    ZoomPosition = 0.3

};

{% endhighlight %}

{% endtabs %}

![Zooming support in WPF Chart](Interactive-Features_images/Interactive-Features_img24.jpeg)

**Mouse** **Wheel** **Zooming**

Zooming can be performed by mouse wheel action by setting [`EnableMouseWheelZooming`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~EnableMouseWheelZooming.html#) property to true.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableMouseWheelZooming="True" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableMouseWheelZooming = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

**Pinch** **Zooming**

If you want to zoom using fingers by touch, then you have to set [`EnablePinchZooming`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~EnablePinchZooming.html#) property to true as shown in the below code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnablePinchZooming="True" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnablePinchZooming = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

**Zooming** **Relative** **to** **Cursor**

To enable the zooming relative to cursor position you can set [`ZoomRelativeToCursor`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~ZoomRelativeToCursor.html#) property to true. This support is applicable only for mouse wheel zooming.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior ZoomRelativeToCursor="True" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    ZoomRelativeToCursor = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

**SelectionZooming**

SelectionZooming helps us to zoom a particular area by selecting the region using  rectangle.To enable the selection ,you have to set [`EnableSelectionZooming`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~EnableSelectionZooming.html#) property to true.

The following code snippet demonstrated selection zooming.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Selection zooming support in WPF Chart](Interactive-Features_images/Interactive-Features_img25.jpeg)


**Customization** **of** **Selection** **Rectangle**

Selection Rectangle can be customized by setting the following properties 

* [`Fill`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~Fill.html#)-Represents the brush filled in selection rectangle. 
* [`Stroke`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~Stroke.html#)- Represents the outer line color of selection rectangle.
* [`StrokeThickness`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~StrokeThickness.html#)- Represents the selection rectangle outer line thickness. 

The following code example demonstrates the customization of selection rectangle

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" 

Fill="LightBlue" Stroke="Blue" StrokeThickness="2" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true,

    Fill = new SolidColorBrush(Colors.LightBlue),

    Stroke = new SolidColorBrush(Colors.Blue),

    StrokeThickness = 2

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Customizing selection rectangle support in WPF Chart](Interactive-Features_images/Interactive-Features_img26.jpeg)


**Zooming** **Mode**

The zooming can be done both horizontally and vertically. The zooming direction is defined using [`ZoomMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~ZoomMode.html#) property.

Zooming along [`X`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ZoomMode.html) axis

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" ZoomMode="X">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true,

    ZoomMode = ZoomMode.X

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Zoom mode support in WPF Chart](Interactive-Features_images/Interactive-Features_img27.jpeg)


Zooming along Y axis

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" ZoomMode="Y">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true,

    ZoomMode = ZoomMode.Y

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Zoom mode support in WPF Chart](Interactive-Features_images/Interactive-Features_img28.jpeg)

**Maximum** **Zoom** **Level**

You can also limit the zooming by setting [`MaximumZoomLevel`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~MaximumZoomLevel.html#) property as shown in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" MaximumZoomLevel="100">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true,

    MaximumZoomLevel = 100

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

### Zooming Toolbar

Zooming Toolbar encompassed with buttons for performing actions like Zoom In/Out, Reset, Pan, etc. You can add the zooming toolbar to the chart area by setting [`EnableZoomingToolBar`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~EnableZoomingToolBar.html#) property to True.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableZoomingToolBar="True">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableZoomingToolBar = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

The following image depicts the default view of the zooming toolbar.

![Zooming toolbar in WPF Chart](Interactive-Features_images/Interactive-Features_img29.jpeg)


**Positioning** **the** **zooming** **toolbar**

Zooming Toolbar can be positioned using the [`HorizontalPosition`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~HorizontalPosition.html#) and [`VerticalPosition`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~VerticalPosition.html#) properties.The following code demonstrates the positioning of the toolbar.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableZoomingToolBar="True" HorizontalPosition="Left" VerticalPosition="Bottom">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableZoomingToolBar = true,

    HorizontalPosition = HorizontalAlignment.Left,

    VerticalPosition = VerticalAlignment.Bottom

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Positioning the zooming toolbar in WPF Chart](Interactive-Features_images/Interactive-Features_img30.jpeg)


**Customization** **of** **Zooming** **Toolbar**

Zooming Toolbar can be customized using the following APIs:

* [`ToolBarBackground`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~ToolBarBackground.html#)- Represents the zooming toolkit background.
* [`ToolBarItems`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~ToolBarItems.html#)- Collection value that contains zooming toolkit items. 
* [`ToolBarItemMargin`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~ToolBarItemMargin.html#)-Represents the margin for the toolbar item.
* [`ToolBarItemWidth`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~ToolBarItemWidth.html#) -Represents the width of the toolbar item
* [`ToolBarItemHeight`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~ToolBarItemHeight.html#)-Represents the height of the toolbar item

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableZoomingToolBar="True" ToolBarItemHeight="15" 

ToolBarItemWidth="15" ToolBarBackground="Black" 

ToolBarItems="All" ToolBarItemMargin="10">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableZoomingToolBar = true,

    ToolBarBackground = new SolidColorBrush(Colors.Black),

    ToolBarItemHeight = 15,

    ToolBarItemWidth = 15,

    ToolBarItemMargin = new Thickness(10),

    ToolBarItems = ZoomToolBarItems.All

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Customization of zooming toolbar in WPF Chart](Interactive-Features_images/Interactive-Features_img31.jpeg)


**Orientation** **of** **Zooming** **Toolbar**

Zooming toolbar orientation is horizontal by default.You can change the orientation to vertical by setting 

[`ToolBarOrientation`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~ToolBarOrientation.html#) property to Vertical.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableZoomingToolBar="True" 

ToolBarOrientation="Vertical">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableZoomingToolBar = true,

    ToolBarOrientation = Orientation.Vertical

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Orientation of zooming toolbar in WPF Chart](Interactive-Features_images/Interactive-Features_img32.jpeg)


### Panning the ChartArea

Panning feature allows moving the visible area of the chart when it is zoomed in. To enable panning, you have to set [`EnablePanning`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~EnablePanning.html#) property to true.

{% tabs %}

{% highlight xml %}
<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableMouseWheelZooming="True" EnablePanning="True">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableMouseWheelZooming = true,

    EnablePanning = true
     
};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

The following image demonstrates the cursor panning in the left direction.

![Panning support in WPF Chart](Interactive-Features_images/Interactive-Features_img33.jpeg)


### Resetting the Zooming/Panning

SfChart provides support to reset to the default view when you double tap the chart area by setting [`ResetOnDoubleTap`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior~ResetOnDoubleTap.html#) property to true.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior  ResetOnDoubleTap="True">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    ResetOnDoubleTap = true
     
};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}


### Events

The following events are available in SfChart for ChartZoomPanBehavior:

* [`ZoomChanging`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SfChart~ZoomChanging_EV.html#)- Occurs when zoom started in chart area.
* [`ZoomChanged`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SfChart~ZoomChanged_EV.html#)- Occurs when zooming done in chart area.
* [`SelectionZoomingStart`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SfChart~SelectionZoomingStart_EV.html#)- Occurs when selection zooming started. 
* [`SelectionZoomingDelta`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SfChart~SelectionZoomingDelta_EV.html#)- Occurs when selection zooming.
* [`SelectionZoomingEnd`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SfChart~SelectionZoomingEnd_EV.html#)- Occurs when selection zooming end. 
* [`ResetZooming`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SfChart~ResetZooming_EV.html#)- Occurs when zooming get reset in chart area.


## Selection

SfChart supports selection that allows you to select a segment in a series or series itself by using [`ChartSelectionBehavior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior.html#). 

### Adding Selection Behavior to SfChart

You can create an instance [`ChartSelectionBehavior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior.html#) and add it to the Behaviors collection.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior >

</syncfusion:ChartSelectionBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior();

chart.Behaviors.Add(selection);

{% endhighlight %}

{% endtabs %}

### SegmentSelection

Segment Selection allows you to highlight a segment in a chart series. To enable a segment selection in a chart series, you have to set the [`EnableSegmentSelection`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior~EnableSegmentSelection.html#) property to True.For highlighting a segment the  brush color can be set using [`SegmentSelectionBrush`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ColumnSeries~SegmentSelectionBrush.html#) property.

**ColumnSeries**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior   EnableSegmentSelection="True" >

</syncfusion:ChartSelectionBehavior>

</syncfusion:SfChart.Behaviors>

<syncfusion:ColumnSeries Label="2011" SegmentSelectionBrush="Green" Interior="#777777"

ItemsSource="{Binding Demands}" XBindingPath="Demand" YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    EnableSegmentSelection = true

};

chart.Behaviors.Add(selection);

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    Label ="2011",

    SegmentSelectionBrush = new SolidColorBrush(Colors.Green),

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Segment selection support in WPF Chart](Interactive-Features_images/Interactive-Features_img34.jpeg)

**SplineSeries**

In Linear type series the segment selection can be viewed by changing the adornments symbol interior.

The following code example demonstrates the spline series segment selection by changing the adornments interior.

{% tabs %}

{% highlight xml %}

<syncfusion:SplineSeries SegmentSelectionBrush="Red"

ItemsSource="{Binding Demands}" Interior="#4A4A4A"

XBindingPath="Demand"

YBindingPath="Year2010">

<syncfusion:SplineSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo ShowMarker="True" Symbol="Ellipse" HighlightOnSelection="True"></syncfusion:ChartAdornmentInfo>

</syncfusion:SplineSeries.AdornmentsInfo>

</syncfusion:SplineSeries>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    EnableSegmentSelection = true

};

chart.Behaviors.Add(selection);

SplineSeries series = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    SegmentSelectionBrush = new SolidColorBrush(Colors.Red),

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
{

    ShowMarker = true,

    HighlightOnSelection = true,

    Symbol = ChartSymbol.Ellipse

};

series.AdornmentsInfo = adornmentInfo;

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Segment selection support in WPF Chart](Interactive-Features_images/Interactive-Features_img35.jpeg)

### Series Selection

Series selection is used in case of multiple series when you want to highlight a particular series.Series Selection can be enabled by setting [`EnableSeriesSelection`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior~EnableSeriesSelection.html#)  property to True. The [`SeriesSelectionBrush`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~SeriesSelectionBrush.html#) property is used to set the brush color to highlight the series.

The following code example demonstrates highlighting a series.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior EnableSegmentSelection="False" EnableSeriesSelection="True"/>

</syncfusion:SfChart.Behaviors>   

<syncfusion:ScatterSeries Label="2010"  SeriesSelectionBrush="Green"

ItemsSource="{Binding Demands}" Interior="#4A4A4A"

XBindingPath="Demand"

YBindingPath="Year2010">

</syncfusion:ScatterSeries>

<syncfusion:ScatterSeries Label="2011" SeriesSelectionBrush="Green" Interior="#777777"

ItemsSource="{Binding Demands}" XBindingPath="Demand" 

YBindingPath="Year2011"/>    

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    EnableSegmentSelection = true,

    EnableSeriesSelection = true

};

chart.Behaviors.Add(selection);

ScatterSeries series1 = new ScatterSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    Label = "2010",

    SegmentSelectionBrush = new SolidColorBrush(Colors.Green),

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

ScatterSeries series2 = new ScatterSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Label = "2011",

    SegmentSelectionBrush = new SolidColorBrush(Colors.Green),

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Series selection support in WPF Chart](Interactive-Features_images/Interactive-Features_img36.jpeg)

N>By default the segment selection is true, so for selecting series you have to set the EnableSegmentSelection property to false.

### Selection Mode

SfChart provides support to select using mouse move or mouse click. By default the selection will take place in mouse click. The selection mode can be defined using [`SelectionMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior~SelectionMode.html#) property for segment and series selection.

The following code snippet demonstrates the selection mode using [`MouseMove`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SelectionMode.html).

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior SelectionMode="MouseMove" EnableSeriesSelection="True">

</syncfusion:ChartSelectionBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    SelectionMode = Syncfusion.UI.Xaml.Charts.SelectionMode.MouseMove,

    EnableSeriesSelection = true

};

chart.Behaviors.Add(selection);

{% endhighlight %}

{% endtabs %}

### Selection Style

SfChart allows you to select single or multiple segment /series using [`SelectionStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior~SelectionStyle.html#) property. By default the SelectionStyle is [`Single`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SelectionStyle.html).

The following code snippet demonstrates multiple segment selection.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior SelectionStyle="Multiple" EnableSegmentSelection="True">

</syncfusion:ChartSelectionBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    SelectionStyle = SelectionStyle.Multiple,

    EnableSegmentSelection = true

};

chart.Behaviors.Add(selection);

{% endhighlight %}

{% endtabs %}

![Selection style support in WPF Chart](Interactive-Features_images/Interactive-Features_img37.jpeg)


### Changing Cursor while Selection

[`SelectionCursor`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior~SelectionCursor.html#) property allows you to define the cursor when mouse is hovered over the segment with segment or series selection enabled.

The following code snippet demonstrates hand cursor in segment selection.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior SelectionCursor="Hand"  EnableSegmentSelection="True">

</syncfusion:ChartSelectionBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    SelectionCursor = Cursors.Hand,

    EnableSegmentSelection = true

};

chart.Behaviors.Add(selection);

{% endhighlight %}

{% endtabs %}

![Changing cursor while selection support in WPF Chart](Interactive-Features_images/Interactive-Features_img38.jpeg)


### Adornment Selection:

SfChart provides selection for adornments by defining [`HighlightOnSelection`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~HighlightOnSelection.html#) property which allows you to select the segment or series with the corresponding adornments.

**HighlightOnSelection**

**Segment** **Selection**

The following code example demonstrates the segment selection with adornments 

{% tabs %}

{% highlight xaml %}

<syncfusion:ColumnSeries Interior="#4A4A4A"

ItemsSource="{Binding Demands}" XBindingPath="Demand"

SegmentSelectionBrush="Green"

YBindingPath="Year2010">

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo UseSeriesPalette="True" ShowConnectorLine="True"

ConnectorHeight="30" ShowLabel="True" HighlightOnSelection="True">

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    EnableSegmentSelection = true

};

chart.Behaviors.Add(selection);

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    SegmentSelectionBrush = new SolidColorBrush(Colors.Green),

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
{

    ShowLabel = true,

    ShowConnectorLine = true,

    HighlightOnSelection = true,

    UseSeriesPalette = true,

    ConnectorHeight = 30

};

series.AdornmentsInfo = adornmentInfo;

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Segments selection with adornments in WPF Chart](Interactive-Features_images/Interactive-Features_img39.jpeg)

**Series** **Selection**

The following code example demonstrates the series selection with adornments. 

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior EnableSegmentSelection="False" 

EnableSeriesSelection="True"/>

</syncfusion:SfChart.Behaviors>

<syncfusion:SplineSeries ItemsSource="{Binding Demands}" SeriesSelectionBrush="Green"

XBindingPath="Demand" 

YBindingPath="Year2010">

<syncfusion:SplineSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo Symbol="Ellipse"

ShowMarker="True"

HighlightOnSelection="True">                                            

</syncfusion:ChartAdornmentInfo>

</syncfusion:SplineSeries.AdornmentsInfo>

</syncfusion:SplineSeries>

<syncfusion:SplineSeries Label="2010" Interior="#4A4A4A" 

ItemsSource="{Binding Demands}" SeriesSelectionBrush="Green"

XBindingPath="Demand"

YBindingPath="Year2011">

<syncfusion:SplineSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo Symbol="Ellipse"

ShowMarker="True"

HighlightOnSelection="True">

</syncfusion:ChartAdornmentInfo>

</syncfusion:SplineSeries.AdornmentsInfo>

</syncfusion:SplineSeries>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    EnableSegmentSelection = false,

    EnableSeriesSelection = true

};

chart.Behaviors.Add(selection);

SplineSeries series1 = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    SeriesSelectionBrush = new SolidColorBrush(Colors.Green)

};

ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
{

    ShowMarker = true,

    Symbol = ChartSymbol.Ellipse

};

series1.AdornmentsInfo = adornmentInfo;

SplineSeries series2 = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    SeriesSelectionBrush = new SolidColorBrush(Colors.Green),

    Interior = new SolidColorBrush(Color.FromRgb(0x4A,0x4A,0x4A))

};

ChartAdornmentInfo adornmentInfo1 = new ChartAdornmentInfo()
{

    ShowMarker = true,

    Symbol = ChartSymbol.Ellipse,

    HighlightOnSelection = true

};

series2.AdornmentsInfo = adornmentInfo1;

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Series selection with adornments in WPF Chart](Interactive-Features_images/Interactive-Features_img40.jpeg)


### Events

The following events are available in SfChart for ChartSelectionBehavior,

* [`SelectionChanging`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartBase~SelectionChanging_EV.html#)- Occurs when selection changing in chart area.
* [`SelectionChanged`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartBase~SelectionChanged_EV.html#)- Occurs when selection changed in chart area. 


## Resizable Scrollbar

The resizable scrollbar is a type of scrollbar that can be resized within the track area by adjusting the scrolling thumbs. In the SfChart, a resizable scrollbar is used for zooming and panning across different chart segments.

### Adding ScrollBar to the Axis

[`EnableScrollBar`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~EnableScrollBar.html#) property allows you to add the scrollbar for the particular axis. The following code snippet illustrates the scrollbar in the primary axis.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" />

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true

};

{% endhighlight %}

{% endtabs %}

![Adding scrollbar to axis in WPF Chart](Interactive-Features_images/Interactive-Features_img41.jpeg)


**Deferred** **Scrolling**

SfChart provides support to suspend the value updates for every thumb values. This can be done using [`DeferredScrolling`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~DeferredScrolling.html#) property in chart axis.The following code snippet demonstrates the deferred scrolling.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" DeferredScrolling="True"/>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true,

    DeferredScrolling = true,

};

{% endhighlight %}

{% endtabs %}

**Resizing** **the** **scrollbar**

SfChart allows you to resize the scrollbar using [`EnableScrollBarResizing`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~EnableScrollBarResizing.html#) property to true. By default the EnableScrollBarResizing property is true. The following code example and image demonstrates scrollbar without resizing option.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" EnableScrollBarResizing="False"/>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true,

    EnableScrollBarResizing = false,

};

{% endhighlight %}

{% endtabs %}

![Resizing the scrollbar in WPF Chart](Interactive-Features_images/Interactive-Features_img42.jpeg)


### Scrollbar for Touch Mode

Scrollbar provides a touch mode style by enabling [`EnableTouchMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~EnableTouchMode.html#) property to true as in the below code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" EnableTouchMode="True"/>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true,

    EnableTouchMode = true

};

{% endhighlight %}

{% endtabs %}

![Scrollbar for touch mode support in WPF Chart](Interactive-Features_images/Interactive-Features_img43.jpeg)


**Thumb** **Label**

In touch mode while resizing or dragging the scrollbar to view thumb labels the [`ThumbLabelVisibility`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxis~ThumbLabelVisibility.html#) is set to true.

The following code example demonstrates the thumb labels in scrollbar.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" ThumbLabelVisibility="Visible" EnableTouchMode="True"/>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true,

    EnableTouchMode = true,

    ThumbLabelVisibility = Visibility.Visible

};

{% endhighlight %}

{% endtabs %}

![Thumb label for scrollbar in WPF Chart](Interactive-Features_images/Interactive-Features_img44.jpeg)


**ThumbLabelTemplate**

[`ThumbLabelTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxis~ThumbLabelTemplate.html#) property provides the custom template for the scroll bar thumb

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <DataTemplate x:Key="labelTemplate">

            <Grid>

                <Border BorderBrush="Black" Background="Pink" 
                                
                        BorderThickness="2">

                    <TextBlock Text="{Binding}" FontSize="15"/>

                </Border>

            </Grid>

        </DataTemplate>

    </syncfusion:SfChart.Resources>

    <syncfusion:SfChart.PrimaryAxis>

        <syncfusion:CategoryAxis EnableTouchMode="True" EnableScrollBar="True"
                                         
                                 ThumbLabelVisibility="Visible"
                                         
                                 ThumbLabelTemplate="{StaticResource labelTemplate}"/>

    </syncfusion:SfChart.PrimaryAxis>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableTouchMode = true,

    EnableScrollBar = true,

    ThumbLabelVisibility = Visibility.Visible,

    ThumbLabelTemplate = chart.Resources["labelTemplate"] as DataTemplate

};

{% endhighlight %}

{% endtabs %}

![Label template support for scrollbar thumb in WPF Chart](Interactive-Features_images/Interactive-Features_img45.jpeg)

## CrossHair

ChartCrossHairBehavior is used to view the values at mouse point or touch contact point. By moving these lines horizontally, you can get the X values and by moving these lines vertically, you can get the Y values.

### Adding CrossHairBehavior to SfChart

You can create an instance [`ChartCrossHairBehavior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior.html#) and add it to the Behaviors collection.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior />

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior();

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

To view the axis labels then set the [`ShowTrackBallInfo`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxis~ShowTrackBallInfo.html#) property to true as in the below code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis  ShowTrackBallInfo="True"/>

</syncfusion:SfChart.PrimaryAxis>

<syncfusion:SfChart.SecondaryAxis>

<syncfusion:NumericalAxis  ShowTrackBallInfo="True"/>

</syncfusion:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior();

chart.Behaviors.Add(behavior);

chart.PrimaryAxis = new CategoryAxis()
{

    ShowTrackBallInfo = true

};

chart.SecondaryAxis = new NumericalAxis()
{

    ShowTrackBallInfo = true

};

{% endhighlight %}

{% endtabs %}

![Cross hair support in WPF Chart](Interactive-Features_images/Interactive-Features_img46.jpeg)


Cross hair is composed of the following parts:

1. Vertical and horizontal line

2. Axis Labels

### Vertical and Horizontal Line

If you add [`ChartCrossHairBehavior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior.html#) to chart you can see horizontal and vertical lines.The horizontal and vertical lines can be customized using [`HorizontalLineStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior~HorizontalLineStyle.html#) and [`VerticalLineStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior~VerticalLineStyle.html#) properties.

**HorizontalLineStyle**

The following code snippet demonstrates the line style for horizontal line in cross hair.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <Style TargetType="Line" x:Key="lineStyle">

            <Setter Property="Stroke" Value="Green"></Setter>

            <Setter Property="StrokeThickness" Value="1"></Setter>

        </Style>
                
    </syncfusion:SfChart.Resources>

    <syncfusion:SfChart.Behaviors>

        <syncfusion:ChartCrossHairBehavior HorizontalLineStyle="{StaticResource lineStyle}"/>

    </syncfusion:SfChart.Behaviors>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior crosshair = new ChartCrossHairBehavior()
{

    HorizontalLineStyle = chart.Resources["lineStyle"] as Style

};

chart.Behaviors.Add(crosshair);

{% endhighlight %}

{% endtabs %}

![Cross hair line style in WPF Chart](Interactive-Features_images/Interactive-Features_img47.jpeg)


**VerticalLineStyle**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <Style TargetType="Line" x:Key="lineStyle">

            <Setter Property="StrokeDashArray" Value="10,5"/>

            <Setter Property="Stroke" Value="Red"/>

             <Setter Property="StrokeThickness" Value="1"/>

        </Style>
                
    </syncfusion:SfChart.Resources>

     <syncfusion:SfChart.Behaviors>

                <syncfusion:ChartCrossHairBehavior VerticalLineStyle="{StaticResource lineStyle}"/>

    </syncfusion:SfChart.Behaviors>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior crosshair = new ChartCrossHairBehavior()
{

    VerticalLineStyle = chart.Resources["lineStyle"] as Style

};

chart.Behaviors.Add(crosshair);

{% endhighlight %}

{% endtabs %}

![Cross hair line style in WPF Chart](Interactive-Features_images/Interactive-Features_img48.jpeg)


### Horizontal axis label

The vertical line in contact with the x axes shows axis label. The horizontal axis label can be aligned using [`HorizontalAxisLabelAlignment`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior~HorizontalAxisLabelAlignment.html#) property.

Axis Label can be aligned by Near, Far, Center, Auto and None Options.

* [`Auto`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAlignment.html) – Axis label is aligned in Near/Far positions based on the movement of vertical line.

* [`Far`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAlignment.html) - Axis label is positioned far from the position of vertical line in cross hair.

* [`Near`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAlignment.html) - Axis label is near to the position of trackball.

* [`Center`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAlignment.html) - Axis label is aligned to the center of the vertical line. By default the axis label will positioned in center.

The following image demonstrates the horizontal axis label positioned center to the vertical line.

![Axis label alignment support for cross hair in WPF Chart](Interactive-Features_images/Interactive-Features_img49.jpeg)


**Far**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior HorizontalAxisLabelAlignment="Far ">

</syncfusion:ChartCrossHairBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior()
{

    HorizontalAxisLabelAlignment = ChartAlignment.Far

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Axis label alignment support for cross hair in WPF Chart](Interactive-Features_images/Interactive-Features_img50.jpeg)


**Near**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior HorizontalAxisLabelAlignment="Near ">

</syncfusion:ChartCrossHairBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior()
{

    HorizontalAxisLabelAlignment = ChartAlignment.Near

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Axis label alignment support for cross hair in WPF Chart](Interactive-Features_images/Interactive-Features_img51.jpeg)


### Vertical axis label

Vertical axis label is displayed when the horizontal line in contact with x axis.The label can be aligned using [`VerticalAxisLabelAlignment`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior~VerticalAxisLabelAlignment.html#) property.

Axis Label can be aligned by Near, Far, Center, Auto, and None Options.

The following image demonstrates the horizontal axis label positioned center to the vertical line.

![Axis label alignment support for cross hair in WPF Chart](Interactive-Features_images/Interactive-Features_img52.jpeg)


**Near**

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior VerticalAxisLabelAlignment="Near">

</syncfusion:ChartCrossHairBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior()
{

    VerticalAxisLabelAlignment = ChartAlignment.Near

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Axis label alignment support for cross hair in WPF Chart](Interactive-Features_images/Interactive-Features_img53.jpeg)

**Far**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior VerticalAxisLabelAlignment="Far"  >

</syncfusion:ChartCrossHairBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior()
{

    VerticalAxisLabelAlignment = ChartAlignment.Far

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Axis label alignment support for cross hair in WPF Chart](Interactive-Features_images/Interactive-Features_img54.jpeg)

**Customization of Crosshair axis labels**

The default appearance of the crosshair axis labels can be customized by using the [`CrosshairLabelTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxis~CrosshairLabelTemplateProperty.html) property of chart axis. It can be set as shown in the following code example.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>
    
    <chart:CategoryAxis ShowTrackBallInfo="True">
        
        <chart:CategoryAxis.CrosshairLabelTemplate>
                
            <DataTemplate>
                            
                 <Border Background="Orange" 
                                   
                         CornerRadius="4" 
                                    
                          BorderThickness="1" BorderBrush="Black">

                 <TextBlock Margin="2" Text="{Binding ValueX}"/>
                            
                </Border>
                
            </DataTemplate>
             
        </chart:CategoryAxis.CrosshairLabelTemplate>
                
    </chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>
                
       <chart:NumericalAxis ShowTrackBallInfo="True">
                    
            <chart:NumericalAxis.CrosshairLabelTemplate>
                        
                <DataTemplate>
                            
                    <Border Background="Orange" 
                                   
                            CornerRadius="4" 
                            
                             BorderThickness="1" 
                             
                             BorderBrush="Black">

                    <TextBlock  Margin="2" Text="{Binding ValueY}"/>
                   
                    </Border>
                        
                </DataTemplate>
            
            </chart:NumericalAxis.CrosshairLabelTemplate>
       
       </chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

<chart:SfChart.Behaviors>
       
    <chart:ChartCrossHairBehavior />
    
</chart:SfChart.Behaviors>

{% endhighlight %}

{% endtabs %}

![Crosshair axis labels customization in WPF](Interactive-Features_images/crossHairTemplate.png)