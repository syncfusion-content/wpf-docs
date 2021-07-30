---
layout: post
title: Pie and Doughnut Chart in WPF Charts control | Syncfusion
description: Learn here all about Pie and Doughnut Chart support in Syncfusion WPF Charts (SfChart) control and more.
platform: wpf
control: SfChart
documentation: ug
---

# Pie and Doughnut in WPF Charts (SfChart)

## Pie Chart

[`PieSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PieSeries.html#) is divided into sectors, illustrating numerical proportion. The following code example illustrates the PieSeries.

{% tabs %}

{% highlight xaml %}

<chart:PieSeries  XBindingPath="Category" 

                 ItemsSource="{Binding Tax}" 

                  YBindingPath="Percentage"/>

{% endhighlight %}

{% highlight c# %}

PieSeries series = new PieSeries()
{

    ItemsSource = new ViewModel().Tax,

    XBindingPath = "Category",

    YBindingPath = "Percentage"

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF Pie Chart](Series_images/wpf-pie-chart.png)

The rendering size of the PieSeries can be controlled using [`PieCoefficient`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PieSeries.html#Syncfusion_UI_Xaml_Charts_PieSeries_PieCoefficient) property as in below code example.

{% tabs %}

{% highlight xaml %}

<chart:PieSeries PieCoefficient="0.9" 

XBindingPath="Category" 

ItemsSource="{Binding Tax}" 

YBindingPath="Percentage"/>

{% endhighlight %}

{% highlight c# %}

PieSeries series = new PieSeries()
{

    ItemsSource = new ViewModel().Tax,

    XBindingPath = "Category",

    YBindingPath = "Percentage",

    PieCoefficient = 0.9

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF Chart with PieCoefficient](Series_images/wpf-chart-with-pie-coefficient.png)

### Group small data points into “others”
The small segments in the pie chart can be grouped into the “others” category using the [`GroupTo`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_GroupTo) and [`GroupMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_GroupMode) properties of PieSeries.

 The [`GroupMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_GroupMode) property is used to specify the grouping type based on slice [`Angle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PieGroupMode.html), actual data point [`Value`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PieGroupMode.html), or [`Percentage`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PieGroupMode.html), and the [`GroupTo`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_GroupTo) property is used to set the limit to group data points into a single slice. The grouped segment is labeled as “Others” in legend and toggled as other segment. The default value of the [`GroupTo`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_GroupTo) property is [`double.NAN`], and the default value of the [`GroupMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_GroupMode) property is Value.

**Pie series without grouping**

![WPF Pie Chart without Grouping](Series_images/wpf-chart-non-grouping-pie.png)

**Pie series with grouping (Mode - Value)**

{% tabs %}

{% highlight xaml %}

            <chart:PieSeries ItemsSource="{Binding Data}" XBindingPath="Country" YBindingPath="Count"
				   GroupMode="Value" GroupTo="1000" >

                <chart:PieSeries.AdornmentsInfo>
                    <chart:ChartAdornmentInfo ShowConnectorLine="True" 
                                              ConnectorHeight="80" 
                                              ShowLabel="True" 
                                              LabelTemplate="{StaticResource DataLabelTemplate}"  
                                              SegmentLabelContent="LabelContentPath">
                    </chart:ChartAdornmentInfo>
                </chart:PieSeries.AdornmentsInfo>
            </chart:PieSeries>

{% endhighlight %}

{% highlight c# %}

            pieSeries.GroupMode = PieGroupMode.Value;
            pieSeries.GroupTo = 1000;

            ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
            {
                ShowConnectorLine = true,
                ShowLabel = true,
                ConnectorHeight = 80,
                LabelTemplate = this.RootGrid.Resources["DataLabelTemplate"] as DataTemplate,
                SegmentLabelContent = LabelContent.LabelContentPath,
            };

            pieSeries.AdornmentsInfo = adornmentInfo;

{% endhighlight %}

{% endtabs %}

![WPF Pie Chart with Grouping](Series_images/wpf-pie-chart-grouping.png)

**Pie series with grouping (Mode - Angle)**

{% tabs %}

{% highlight xaml %}

<chart:PieSeries ItemsSource="{Binding Data}" XBindingPath="Country" YBindingPath="Count" 
                 GroupMode="Angle" GroupTo="30">
                 
    <chart:PieSeries.AdornmentsInfo>
        <chart:ChartAdornmentInfo ShowConnectorLine="True" 
                                  ConnectorHeight="80" 
                                  ShowLabel="True" 
                                  LabelTemplate="{StaticResource DataLabelTemplate}"  
                                  SegmentLabelContent="LabelContentPath">
        </chart:ChartAdornmentInfo>
    </chart:PieSeries.AdornmentsInfo>
</chart:PieSeries>

{% endhighlight %}

{% highlight c# %}

pieSeries.GroupMode = PieGroupMode.Angle;
pieSeries.GroupTo = 30;

ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
    {
        ShowConnectorLine = true,
        ShowLabel = true,
        ConnectorHeight = 80,
        LabelTemplate = this.RootGrid.Resources["DataLabelTemplate"] as DataTemplate,
        SegmentLabelContent = LabelContent.LabelContentPath,
    };

pieSeries.AdornmentsInfo = adornmentInfo;

{% endhighlight %}

{% endtabs %}

![WPF Pie Chart with Grouping in Angle Mode](Series_images/wpf-pie-chart-grouping.png)

**Pie series with grouping (Mode - Percentage)**

{% tabs %}

{% highlight xaml %}

<chart:PieSeries ItemsSource="{Binding Data}" XBindingPath="Country" YBindingPath="Count"                
                 GroupMode="Percentage" GroupTo="10" >

    <chart:PieSeries.AdornmentsInfo>
        <chart:ChartAdornmentInfo ShowConnectorLine="True" 
                                  ConnectorHeight="80" 
                                  ShowLabel="True" 
                                  LabelTemplate="{StaticResource DataLabelTemplate}"  
                                  SegmentLabelContent="LabelContentPath">
        </chart:ChartAdornmentInfo>
    </chart:PieSeries.AdornmentsInfo>
</chart:PieSeries>


{% endhighlight %}

{% highlight c# %}

pieSeries.GroupMode = PieGroupMode.Percentage;
pieSeries.GroupTo = 10;

ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
    {
        ShowConnectorLine = true,
        ShowLabel = true,
        ConnectorHeight = 80,
        LabelTemplate = this.RootGrid.Resources["DataLabelTemplate"] as DataTemplate,
        SegmentLabelContent = LabelContent.LabelContentPath,
    };

pieSeries.AdornmentsInfo = adornmentInfo;

{% endhighlight %}

{% endtabs %}

![WPF Pie Chart with Grouping in Percentage Mode](Series_images/wpf-pie-chart-grouping.png)

N> You can explore our [WPF Pie Chart](https://www.syncfusion.com/wpf-controls/charts/wpf-pie-chart) feature tour page for its groundbreaking features. You can also explore our [WPF Pie Chart example](https://github.com/syncfusion/wpf-demos/blob/master/chart/Views/Circular%20Charts/PieChart.xaml) to know how to render and configure the pie chart.

## Doughnut Chart

[`DoughnutSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#) is similar to PieSeries. It is used to show the relationship between parts of data and whole data. 

The DoughnutSeries can be added to chart as in below code example:

{% tabs %}

{% highlight xaml %}

<chart:DoughnutSeries XBindingPath="Category"

                      ItemsSource="{Binding Tax}" 

                      YBindingPath="Percentage"/>

{% endhighlight %}

{% highlight c# %}

DoughnutSeries series = new DoughnutSeries()
{

    ItemsSource = new ViewModel().Tax,

    XBindingPath = "Category",

    YBindingPath = "Percentage"
};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF Doughnut Chart](Series_images/wpf-doughnut-chart.png)

The Doughnut also having coefficient property, [`DoughnutCoefficient`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#Syncfusion_UI_Xaml_Charts_DoughnutSeries_DoughnutCoefficient) which defines the inner circle. Also it has [`DoughnutSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#Syncfusion_UI_Xaml_Charts_DoughnutSeries_DoughnutSize), used to define the size for this series like [`PieCoefficient`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PieSeries.html#Syncfusion_UI_Xaml_Charts_PieSeries_PieCoefficient) in PieSeries.

{% tabs %}

{% highlight xaml %}

<chart:DoughnutSeries DoughnutCoefficient="0.7"                    

XBindingPath="Category" ItemsSource="{Binding Tax}" 

YBindingPath="Percentage" />

{% endhighlight %}

{% highlight c# %}

DoughnutSeries series = new DoughnutSeries()
{

    ItemsSource = new ViewModel().Tax,

    XBindingPath = "Category",

    YBindingPath = "Percentage",

    DoughnutCoefficient = 0.9
};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF Chart with Doughnut Coefficient](Series_images/wpf-chart-with-doughnut-coefficient.png)

**Size**

The size of doughnut series can be customized by using its [`DoughnutSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#Syncfusion_UI_Xaml_Charts_DoughnutSeries_DoughnutSizeProperty) property. The following code illustrates how to use the property in series.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart>

<syncfusion:DoughnutSeries DoughnutSize="0.8"/>
       
<syncfusion:DoughnutSeries DoughnutSize="0.8"/ >

</syncfusion:SfChart>


{% endhighlight %}

{% highlight c# %}

DoughnutSeries doughnut = new DoughnutSeries();

doughnut.DoughnutSize = 0.8;

chart.Series.Add(doughnut);

DoughnutSeries doughnut1 = new DoughnutSeries();

doughnut1.DoughnutSize = 0.8;

chart.Series.Add(doughnut1);

{% endhighlight %}

{% endtabs %}

![Customizing Doughnut Size in WPF Chart](Series_images/wpf-chart-doughnut-size.png)

**Hole Size**

[`DoughnutHoleSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#Syncfusion_UI_Xaml_Charts_DoughnutSeries_DoughnutHoleSizeProperty) is an attachable property. It gets or sets the double value, which is used to customize the doughnut hole size. Its value ranges from 0 to 1, and it can be set as shown in the following code example.

{% tabs %}

{% highlight xaml %}

<Chart:SfChart Chart:DoughnutSeries.DoughnutHoleSize="0.2">
    
</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

DoughnutSeries.SetDoughnutHoleSize(chart, 0.2);

{% endhighlight %}

{% endtabs %}

![Customizing Doughnut HoleSize in WPF Chart](Series_images/wpf-chart-doughnut-hole-size.png)


## Semi Pie and Doughnut

By using custom [`StartAngle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_StartAngle) and [`EndAngle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_EndAngle) properties, you can draw pie series in different shapes such as semicircular or quarter circular series.

{% tabs %}

{% highlight xaml %}

<syncfusion:PieSeries x:Name="PieSeries" StartAngle="180" EndAngle="360"    

XBindingPath="Utilization" 

YBindingPath="ResponseTime"

ItemsSource="{Binding}"/>

{% endhighlight %}

{% highlight c# %}

PieSeries series = new PieSeries()
{

    ItemsSource = new ViewModel().Value,

    XBindingPath = "Utilization",

    YBindingPath = "ResponseTime",

    StartAngle = 180,

    EndAngle = 360

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF Semi Pie Chart](Series_images/wpf-semipie-chart.png)

{% tabs %}

{% highlight xaml %}

<syncfusion:DoughnutSeries StartAngle="180" EndAngle="360" 

XBindingPath="Utilization"

YBindingPath="ResponseTime" 

ItemsSource="{Binding}"/>

{% endhighlight %}

{% highlight c# %}

DoughnutSeries series = new DoughnutSeries()
{

    ItemsSource = new ViewModel().Value,

    XBindingPath = "Utilization",

    YBindingPath = "ResponseTime",

    StartAngle = 180,

    EndAngle = 360

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF Semi Doughnut Chart](Series_images/wpf-semi-doughnut-chart.png)

## Stacked doughnut

Doughnut segments can be separated as individual circles using the [`IsStackedDoughnut`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#Syncfusion_UI_Xaml_Charts_DoughnutSeries_IsStackedDoughnut) property. The following properties are used to customize the stacked doughnut chart:

•	[`CapStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#Syncfusion_UI_Xaml_Charts_DoughnutSeries_CapStyle) - Specifies the shapes of the start and end points of a circular segment. The supported values are [`BothFlat`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutCapStyle.html), [`BothCurve`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutCapStyle.html), [`StartCurve`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutCapStyle.html), and [`EndCurve`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutCapStyle.html). The default value of the this property is BothFlat.
•	[`SegmentSpacing`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#Syncfusion_UI_Xaml_Charts_DoughnutSeries_SegmentSpacing) - Changes the spacing between two individual segments. The default value of spacing is 0, and the value ranges from 0 to 1. Here, 1 represents 100%, and 0 represents 0% of the available space.
•	[`MaximumValue`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#Syncfusion_UI_Xaml_Charts_DoughnutSeries_SegmentSpacing) - Represents the entire span of an individual circle. The default value of the this property is double.NaN.
•	[`TrackColor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#Syncfusion_UI_Xaml_Charts_DoughnutSeries_TrackColor) - Changes the color of the track area.
•	[`TrackBorderColor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#Syncfusion_UI_Xaml_Charts_DoughnutSeries_TrackBorderColor) - Changes the color of the track border.
•	[`TrackBorderWidth`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#Syncfusion_UI_Xaml_Charts_DoughnutSeries_TrackBorderWidth) - Changes the width of the track border.

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
    …
    <chart:DoughnutSeries XBindingPath="Category" YBindingPath="Expenditure" ItemsSource="{Binding ExpenditureData}"
                          IsStackedDoughnut="True" CapStyle="BothCurve" SegmentSpacing="0.2"
                          MaximumValue="100">
    </chart:DoughnutSeries>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

DoughnutSeries doughnutSeries = new DoughnutSeries()
{
    XBindingPath = "Category",
    YBindingPath = "Expenditure",
    ItemsSource = new ViewModel().ExpenditureData,
    IsStackedDoughnut = true,
    CapStyle = DoughnutCapStyle.BothCurve,
    SegmentSpacing = 0.2,
    MaximumValue = 100
};

chart.Series.Add(doughnutSeries);

{% endhighlight %}

{% endtabs %}

![WPF Stacked Doughnut Chart](Series_images/wpf-stacked-doughnut-chart.png)

### Add content to the center of doughnut chart
You can add any content to the center of the doughnut chart using the [`CenterView`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#Syncfusion_UI_Xaml_Charts_DoughnutSeries_CenterView) property of [`DoughnutSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html). The binding context of the [`CenterView`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#Syncfusion_UI_Xaml_Charts_DoughnutSeries_CenterView) will be the respective [`DoughnutSeries`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoughnutSeries.html).

{% tabs %}

{% highlight xaml %}

<chart:SfChart>
    …
    <chart:DoughnutSeries XBindingPath="Category" YBindingPath="Expenditure" ItemsSource="{Binding ExpenditureData}"
                          IsStackedDoughnut="True" CapStyle="BothCurve" SegmentSpacing="0.2"
                          MaximumValue="100">

        <chart:DoughnutSeries.CenterView>
            <ContentControl HorizontalAlignment="Center" VerticalAlignment="Center" >
                <Image Source="/Image/Person.png" Width="164" Height="164"/>
            </ContentControl>
        </chart:DoughnutSeries.CenterView>
								  
    </chart:DoughnutSeries>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

ContentControl centerView = new ContentControl()
{
    Content = new Image()
    {
        HorizontalAlignment = HorizontalAlignment.Center,
        VerticalAlignment = VerticalAlignment.Center,
        Source = new BitmapImage(new Uri("Image/Person.png", UriKind.Relative)),
        Width = 164,
        Height = 164
    }
};

doughnutSeries.CenterView = centerView;

{% endhighlight %}

{% endtabs %}	

![WPF Stacked Doughnut Chart with Center View](Series_images/wpf-stacked-doughnut-chart-center-view.png)

## Explode Segments

The following properties are used to explode the individual segments in Pie and Doughnut.

* [`ExplodeAll`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AccumulationSeriesBase.html#Syncfusion_UI_Xaml_Charts_AccumulationSeriesBase_ExplodeAll)  - Used to explode all the segments of these series.
* [`ExplodeIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AccumulationSeriesBase.html#Syncfusion_UI_Xaml_Charts_AccumulationSeriesBase_ExplodeIndex) - Used to explode any specific segment.
* [`ExplodeRadius`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_ExplodeRadius) - Used to define the explode distance.
* [`ExplodeOnMouseClick`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AccumulationSeriesBase.html#Syncfusion_UI_Xaml_Charts_AccumulationSeriesBase_ExplodeOnMouseClick) -Used to explode the segment when segment is clicked.

**Explode** **Index**

{% tabs %}

{% highlight xaml %}

<syncfusion:PieSeries x:Name="PieSeries" ItemsSource="{Binding}"          

ExplodeIndex="2"

ExplodeRadius="10"

XBindingPath="Utilization" 

YBindingPath="ResponseTime" />

{% endhighlight %}

{% highlight c# %}

PieSeries series = new PieSeries()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "Utilization",

    YBindingPath = "ResponseTime",

    ExplodeIndex = 2,

    ExplodeRadius = 10

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF Chart displays Exploded Segment of Accumulation Series](Series_images/wpf-pie-chart-exploded-segment.png)

N> We have defined ExplodeRadius as 30, by default its value is zero. So you need to define explode, when you set ExplodeIndex or ExplodeAll.

**Explode** **All**

{% tabs %}

{% highlight xaml %}

<chart:PieSeries  ExplodeAll="True"

ExplodeRadius="15"

XBindingPath="Category" 

ItemsSource="{Binding Tax}" 

YBindingPath="Percentage">

{% endhighlight %}

{% highlight c# %}

PieSeries series = new PieSeries()
{

    ItemsSource = new ViewModel().Tax,

    XBindingPath = "Category",

    YBindingPath = "Percentage",

    ExplodeAll = true,

    ExplodeRadius = 15

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![WPF Chart displays Exploded Segments of Accumlation Series](Series_images/wpf-chart-exploded-segments.png)

## See also

[`How to create Pie Chart in C# WPF`](https://www.syncfusion.com/kb/10789/how-to-create-pie-chart-in-c-wpf)
