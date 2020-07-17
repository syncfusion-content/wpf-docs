---
layout: post
title: Series customization | SfChart | Wpf | Syncfusion
description: Explains the grouping, empty points and other customization options of Series in WPF Charts (SfChart)
platform: wpf
control: SfChart
documentation: ug
---

# Series customization in WPF Charts (SfChart)

## Empty Points

The data collection that is passed to the chart can have NaN or Null values that are considered as empty points. The empty point can be defined as in the below code example.

{% highlight C# %}

    Fruits.Add(new Model() { FruitName = "Mango", People = 5 });
    Fruits.Add(new Model() { FruitName = "Apple", People = 27 });
    Fruits.Add(new Model() { FruitName = "Orange", People = Double.NaN });
    Fruits.Add(new Model() { FruitName = "Grapes", People = 15 });
    Fruits.Add(new Model() { FruitName = "Banana", People = 5 });
    Fruits.Add(new Model() { FruitName = "Blueberry", People = 20 });

{% endhighlight %}

By default, ShowEmptyPoints property is false. So the empty points will not be render as in below screenshots:

![Empty points support in WPF Chart](EmptyPoints_images/emptypoint_1.png)


![Empty points support in WPF Chart](EmptyPoints_images/emptypoint_2.png)


![Empty points support in WPF Chart](EmptyPoints_images/emptypoint_3.png)


### Display Empty Points

You can show these empty points by setting the [`ShowEmptyPoints`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~ShowEmptyPoints.html#) property as True. So we need to define the value for this empty points and that can be defined using [`EmptyPointValue`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~EmptyPointValue.html#) property.

This is an enum property having the following values: 

* [`Zero`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.EmptyPointValue.html) - Replace all the empty points with zero (0), this is the default value.
* [`Average`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.EmptyPointValue.html) - Replace all the empty points with average value.

The following code examples shows how to display the empty points:

{% tabs %}

{% highlight xaml %}

    <chart:LineSeries XBindingPath="FruitName" Interior="#BCBCBC" YBindingPath="People" 

    ShowEmptyPoints="True" ItemsSource="{Binding Fruits}" >

        <chart:LineSeries.AdornmentsInfo>

            <chart:ChartAdornmentInfo ShowLabel="True" LabelPosition="Auto"/>

        </chart:LineSeries.AdornmentsInfo>

    </chart:LineSeries>

{% endhighlight %}

{% highlight c# %}

    LineSeries series = new LineSeries()
    {   
        ItemsSource = new ViewModel().Fruits,
        XBindingPath = "FruitName",
        YBindingPath = "People",
        ShowEmptyPoints = true,
        Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC))
    };

    ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
    {
        ShowLabel = true,
        LabelPosition = AdornmentsLabelPosition.Auto
    };

    series.AdornmentsInfo = adornmentInfo;

    chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Displaying empty points in WPF Chart](EmptyPoints_images/emptypoint_4.png)


Since the [`EmptyPointValue`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~EmptyPointValue.html#) as Zero by default, it will draw a line to 0 when we set [`ShowEmptyPoint`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~ShowEmptyPoints.html#) as True.

The following code example shows the [`EmptyPointValue`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~EmptyPointValue.html#) as Average:

{% tabs %}

{% highlight xaml %}

    <chart:LineSeries XBindingPath="FruitName" Interior="#BCBCBC" YBindingPath="People" 

    ShowEmptyPoints="True" EmptyPointValue="Average" ItemsSource="{Binding Fruits}" >

        <chart:LineSeries.AdornmentsInfo>

            <chart:ChartAdornmentInfo ShowLabel="True" LabelPosition="Auto"/>

        </chart:LineSeries.AdornmentsInfo>

    </chart:LineSeries>

{% endhighlight %}

{% highlight c# %}

    LineSeries series = new LineSeries()
    {
        ItemsSource = new ViewModel().Fruits,
        XBindingPath = "FruitName",
        YBindingPath = "People",
        ShowEmptyPoints = true,
        EmptyPointValue = EmptyPointValue.Average,
        Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC))
    };

    ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
    {
        ShowLabel = true,
        LabelPosition = AdornmentsLabelPosition.Auto
    };

    series.AdornmentsInfo = adornmentInfo;
    chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Displaying empty points in WPF Chart](EmptyPoints_images/emptypoint_5.png)


### Customizing Empty Points

You can customize the empty points using [`EmptyPointStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~EmptyPointStyle.html#) property. The following are the values of EmptyPointStyle:

* [`Interior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.EmptyPointStyle.html) - Used to define the custom brush for the empty points.
* [`Symbol`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.EmptyPointStyle.html) - Used to add symbols for the empty points.
* [`SymbolAndInterior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.EmptyPointStyle.html) - This is similar to Symbol, which includes empty point brush also.

**Interior**

This option fills an interior indicating the empty points and this custom brush can be defined using the [`EmptyPointInterior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~EmptyPointInterior.html#) property.

The following code example illustrates the use of [`EmptyPointStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~EmptyPointStyle.html#) and [`EmptyPointInterior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~EmptyPointInterior.html#):

{% tabs %}

{% highlight xaml %}

    <chart:ColumnSeries  ItemsSource="{Binding EmptyPointDatas}" Interior="#bcbcbc" XBindingPath="Category" 

     YBindingPath="Value" ShowEmptyPoints="True"/>

{% endhighlight %}

{% highlight c# %}

    ColumnSeries series = new ColumnSeries()
    {
        ItemsSource = new ViewModel().EmptyPointDatas,
        XBindingPath = "Category",
        YBindingPath = "Value",
        ShowEmptyPoints = true,
        Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC))
    };

    chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Customizing empty points in WPF Chart](EmptyPoints_images/emptypoint_6.png)


N> This is the default value for [`EmptyPointStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~EmptyPointStyle.html#). So when you enable empty points using [`ShowEmptyPoints`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~ShowEmptyPoints.html#) , empty point segment render with this [`EmptyPointInterior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~EmptyPointInterior.html#).

**Symbol**

This option is used to add Symbol for the empty points as in the below code example.

{% tabs %}

{% highlight xaml %}

    <chart:LineSeries XBindingPath="FruitName" Interior="#BCBCBC" YBindingPath="People" 

    ShowEmptyPoints="True" EmptyPointValue="Average" EmptyPointStyle="Symbol" ItemsSource="{Binding Fruits}" >

        <chart:LineSeries.AdornmentsInfo>

            <chart:ChartAdornmentInfo ShowLabel="True" LabelPosition="Auto"/>

        </chart:LineSeries.AdornmentsInfo>

    </chart:LineSeries>

{% endhighlight %}

{% highlight c# %}

    LineSeries series = new LineSeries()
    {
        ItemsSource = new ViewModel().Fruits,
        XBindingPath = "FruitName",
        YBindingPath = "People",
        ShowEmptyPoints = true,
        EmptyPointValue = EmptyPointValue.Average,
        EmptyPointStyle = EmptyPointStyle.Symbol,
        Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC))
    };

    ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
    {
        ShowLabel = true,
        LabelPosition = AdornmentsLabelPosition.Auto
    };

    series.AdornmentsInfo = adornmentInfo;

    chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Adding symbol for empty points in WPF Chart](EmptyPoints_images/emptypoint_7.png)


**Symbol and Interior**

This option combines above two options, which draw a symbol with defined [`EmptyPointInterior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~EmptyPointInterior.html#). The following code example shows the use of this value.

{% tabs %}

{% highlight xaml %}

    <chart:LineSeries XBindingPath="FruitName" Interior="#BCBCBC" YBindingPath="People" 

    ShowEmptyPoints="True" EmptyPointValue="Average" EmptyPointStyle="SymbolAndInterior"

    EmptyPointInterior="Red" ItemsSource="{Binding Fruits}" >

        <chart:LineSeries.AdornmentsInfo>

            <chart:ChartAdornmentInfo ShowLabel="True" LabelPosition="Auto"/>

        </chart:LineSeries.AdornmentsInfo>

    </chart:LineSeries>

{% endhighlight %}

{% highlight c# %}

    LineSeries series = new LineSeries()
    {
        ItemsSource = new ViewModel().Fruits,
        XBindingPath = "FruitName",
        YBindingPath = "People",
        ShowEmptyPoints = true,
        EmptyPointValue = EmptyPointValue.Average,
        EmptyPointStyle = EmptyPointStyle.SymbolAndInterior,
        EmptyPointInterior = new SolidColorBrush(Colors.Red),
        Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC))
    };

    ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
    {
        ShowLabel = true,
        LabelPosition = AdornmentsLabelPosition.Auto
    };

series.AdornmentsInfo = adornmentInfo;
chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Symbol and interior support in WPF Chart](EmptyPoints_images/emptypoint_8.png)


**Custom Symbol**

You can add any custom shape for the empty point symbol. The following code example shows how to add your custom shapes:

{% tabs %}

{% highlight xaml %}

 <syncfusion:SfChart x:Name="chart">
    <syncfusion:SfChart.Resources>
        <DataTemplate x:Key="symbolTemplate">
            <Canvas>
                        <Grid Canvas.Left="{Binding X}" Canvas.Top="{Binding Y}" >
                            <Ellipse StrokeDashArray="1,1" Height="50"                                      
                                     Width="50" Stroke="Gray" StrokeThickness="2"                                      
                                     Margin="-15,-15,0,0" Fill="Transparent"/>

                            <Ellipse  StrokeDashArray="1,3" Height="35" Width="35"                                      
                                      Stroke="Gray" StrokeThickness="2" Margin="-15,-15,0,0"                                      
                                      Fill="LightGray"/>
                        </Grid>
             </Canvas>
        </DataTemplate>
     </syncfusion:SfChart.Resources>

    <syncfusion:LineSeries XBindingPath="XValue" Interior="#BCBCBC"                                    
                           YBindingPath="YValue" ShowEmptyPoints="True"                                       
                           EmptyPointValue="Average" EmptyPointStyle="Symbol"                                   
                           EmptyPointInterior="Red" ItemsSource="{Binding Data}"                                   
                           EmptyPointSymbolTemplate="{StaticResource symbolTemplate}"/>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

    LineSeries series = new LineSeries()
    {

        ItemsSource = new ViewModel().Fruits,
        XBindingPath = "FruitName",
        YBindingPath = "People",
        Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC)),
        ShowEmptyPoints = true,
        EmptyPointValue = EmptyPointValue.Average,
        EmptyPointStyle = EmptyPointStyle.Symbol,
        EmptyPointInterior =new SolidColorBrush(Colors.Red),
        EmptyPointSymbolTemplate = chart.Resources["symbolTemplate"] as DataTemplate

    };

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Custom symbol for empty points in WPF Chart](EmptyPoints_images/emptypoint_9.png)


### EmptyPoints and Series

The following section illustrates few chart types and its behavior with EmptyPoints.

**ColumnSeries** **with** **EmptyPoint** **as** **Average**

![Empty points support in WPF Chart](EmptyPoints_images/emptypoint_10.png)


**SplineSeries** **with** **EmptyPoint** **as** **Average**

![Empty points support in WPF Chart](EmptyPoints_images/emptypoint_11.png)


**Accumulation** **Series** **with** **EmptyPoint** **as** **Average**

![Empty points support in WPF Chart](EmptyPoints_images/emptypoint_12.png)

## Grouping Stacked Series

You can group the stacked similar series using [`GroupingLabel`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingSeriesBase~GroupingLabel.html#) property of stacked series. The stacked series which contains the same [`GroupingLabel`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingSeriesBase~GroupingLabel.html#) will be stacked in a single group.

The following code example shows how to group the stacking series.

{% tabs %}

{% highlight xaml %}

        <chart:StackingColumnSeries Interior="#4A4A4A" GroupingLabel="Group1" XBindingPath="Year" 
         YBindingPath="Quarter1" ItemsSource="{Binding AnnualDetails}"/>

        <chart:StackingColumnSeries Interior="#BCBCBC" GroupingLabel="Group1" XBindingPath="Year" 
          YBindingPath="Quarter2" ItemsSource="{Binding AnnualDetails}"/>

        <chart:StackingColumnSeries Interior="#7F7F7F" GroupingLabel="Group2" XBindingPath="Year"
          YBindingPath="Quarter3" ItemsSource="{Binding AnnualDetails}"/>

        <chart:StackingColumnSeries Interior="#343434" GroupingLabel="Group2" XBindingPath="Year"
          YBindingPath="Quarter4" ItemsSource="{Binding AnnualDetails}"/>

{% endhighlight %}

{% highlight c# %}

            SfChart chart = new SfChart();

            StackingColumnSeries series1 = new StackingColumnSeries()
            {
                ItemsSource = new ViewModel().AnnualDetails,
                XBindingPath = "Year",
                YBindingPath = "Quarter1",
                GroupingLabel = "Group1",
                Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))
            };

            StackingColumnSeries series2 = new StackingColumnSeries()
            {
                ItemsSource = new ViewModel().AnnualDetails,
                XBindingPath = "Year",
                YBindingPath = "Quarter2",
                GroupingLabel = "Group1",
                Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC))
            };

            StackingColumnSeries series3 = new StackingColumnSeries()
            {
                ItemsSource = new ViewModel().AnnualDetails,
                XBindingPath = "Year",
                YBindingPath = "Quarter3",
                GroupingLabel = "Group2",
                Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0x7F))
            };

            StackingColumnSeries series4 = new StackingColumnSeries()
            {
                ItemsSource = new ViewModel().AnnualDetails,
                XBindingPath = "Year",
                YBindingPath = "Quarter4",
                GroupingLabel = "Group2",
                Interior = new SolidColorBrush(Color.FromRgb(0x34, 0x34, 0x34))
            };

            chart.Series.Add(series1);
            chart.Series.Add(series2);
            chart.Series.Add(series3);
            chart.Series.Add(series4);
{% endhighlight %}

{% endtabs %}

![Grouping of stacking series in WPF Chart](Series_images/groupingstacking.png)

## Customize Series

CustomTemplate property is used to customize the chart series. It supports the following series

* BarSeries
* BubbleSeries
* ColumnSeries
* LineSeries
* ScatterSeries
* SplineSeries
* StackingBarSeries
* StackingBar100Series
* StackingColumnSeries
* StackingColumn100Series
* StepLineSeries
* FastLineSeries
* RangeColumnSeries

The respective segment of each series will be your DataTemplate context, which contains the following properties in common. This will be used to plot the custom shapes for the series.

* [`XData`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ColumnSegment~XData.html#)-Returns the actual X value of the segment.
* [`YData`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ColumnSegment~YData.html#)-Returns the actual Y value of the segment.
* [`Item`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSegment~Item.html#)-Returns the underlying model object of the segment.
* [`Interior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSegment~Interior.html#)-Returns the brush color of the segment.

The following code example illustrates the use of [`CustomTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ColumnSeries~CustomTemplate.html#) property:

{% tabs %}

{% highlight xaml %}

 <syncfusion:SfChart x:Name="chart">

     <syncfusion:SfChart.Resources>

            <local:ScatterInteriorConverter x:Key="scatterInteriorConverter"/>

            <local:ScatterAngleConverter x:Key="scatterAngleConverter"/>

            <DataTemplate x:Key="seriesTemplate">

                <Canvas>

                    <Path Fill="{Binding Converter={StaticResource scatterInteriorConverter}}"
                              
                          Stretch="Fill" Height="{Binding ScatterHeight}"
                              
                          Width="{Binding ScatterWidth}" RenderTransformOrigin="0.5,0.5"
                              
                          Canvas.Left="{Binding RectX}" Canvas.Top="{Binding RectY}"
                              
                          Data="M20.125,32L0.5,12.375L10.3125,12.375L10.3125,
                              
                              0.5L29.9375,0.5L29.9375,12.375L39.75,12.375z">

                          <Path.RenderTransform>

                                <RotateTransform Angle="{Binding Converter={StaticResource scatterAngleConverter}}"/>

                          </Path.RenderTransform>

                        </Path>

                    </Canvas>

                </DataTemplate>

    </syncfusion:SfChart.Resources>

    <syncfusion:ScatterSeries  ScatterHeight="20" ScatterWidth="20" Interior="Gray"
                                       
                                XBindingPath="Year" YBindingPath="Count" 
                                       
                                ItemsSource="{Binding Data}"
                                
                                CustomTemplate="{StaticResource seriesTemplate}"/>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

ScatterSeries series = new ScatterSeries()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "Year",

    YBindingPath = "Count",

    ScatterHeight = 20,

    ScatterWidth = 20,

    Interior = new SolidColorBrush(Colors.DarkGray),

    CustomTemplate = chart.Resources["seriesTemplate"] as DataTemplate

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Customizing series in WPF Chart](Styling-and-Customization_images/palette_9.png)

The BarSeries, BubbleSeries, ColumnSeries, LineSeries, ScatterSeries and StepLineSeries have been customized using the [`CustomTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ColumnSeries~CustomTemplate.html#) property. Refer to this [`sample`](https://github.com/SyncfusionExamples/how-to-customize-the-chart-series-in-wpf-sfchart) for complete series CustomTemplate.

![Customizing series in Syncfusion WPF SfChart](Styling-and-Customization_images/CustomTemplate.png)    