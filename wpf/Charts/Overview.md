---
layout: post
title: Overview of Syncfusion SfChart WPF.
description: Overview and the highlighting features of the WPF Chart (SfChart) control.
platform: wpf
control: SfChart
documentation: ug
---

# WPF Charts (SfChart) Overview

SfChart provides a perfect way to visualize data with a high level of user interactivity that focus on development,productivity and simplicity of use. SfChart also provides a wide variety of charting features that can be used to visualize large quantities of data, flexibility of binding data and user customization. 

![Overview of WPF Chart](Overview_images/Overview.png)
    

## Key features

* SfChart supports 38 different types of [series](https://help.syncfusion.com/wpf/sfchart/series), ranging from simple [bar series](https://help.syncfusion.com/wpf/sfchart/series#column-and-bar-charts) to complex [financial charts](https://help.syncfusion.com/wpf/sfchart/series#financial-charts). Each type of chart represents a unique style of representing data with more user friendly and greater UI visualization.
* Capable of rendering large amount of data within the few milliseconds (ms). 
* Allows you to map data from the specified path, by achieving [data binding](https://help.syncfusion.com/wpf/sfchart/databinding) concept.
* Interactive zooming[https://help.syncfusion.com/wpf/sfchart/interactive-features#zooming-and-panning] can be done with touch mode enabled that allows you to explore portions of large charts in more detail, with excellent performance.
* When you need more information about particular segment in a chart, a little mouse over on the series provides much more information by including [tooltip](https://help.syncfusion.com/wpf/sfchart/interactive-features#tooltip), [crosshair](https://help.syncfusion.com/wpf/sfchart/interactive-features#crosshair) and [track ball](https://help.syncfusion.com/wpf/sfchart/interactive-features#trackball) behavior.
* Supports 10 different types of [technical indicators](https://help.syncfusion.com/wpf/sfchart/technical-indicators) that determine financial, stock or economic trends by analyzing a set of recorded data. 
* Supports multiple axes that can be stacked and spanned for multiple panes.
* SfChart provides support for rendering multiple series at same time, with options to compare and visualize two different chart series simultaneously.
* User friendly and provides various options for you to customize chart features like [axis](https://help.syncfusion.com/wpf/sfchart/axis), [labels](https://help.syncfusion.com/wpf/sfchart/adornments), [legends](https://help.syncfusion.com/wpf/sfchart/legend), [series](https://help.syncfusion.com/wpf/sfchart/series) etc and visualize them accordingly. 



## Serialization

SfChart supports serialization and deserialization to save the settings of the chart and reload. 

This can be done using [`Serialize`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartBase~Serialize.html#) and [`Deserialize`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartBase~Deserialize.html#) methods as in below code example:

{% tabs %}

{% highlight xaml %}

<chart:SfChart Margin="10" x:Name="chart" Header="Defect Rates">

<chart:SfChart.Annotations>

<chart:RectangleAnnotation X1="0" X2="2" Y1="20" Y2="30" CanDrag="True" CanResize="True"/>

</chart:SfChart.Annotations>



<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis Header="X Axis" />

</chart:SfChart.PrimaryAxis>



<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis Header="Y Axis" />

</chart:SfChart.SecondaryAxis>



<chart:ColumnSeries ItemsSource="{Binding CategoricalDatas}" XBindingPath="Category"

YBindingPath="Value"  >

</chart:ColumnSeries>

</chart:SfChart>


Serialized Chart

<SfChart Header="Defect Rates" Name="chart" Margin="10,10,10,10" Width="500" Height="420"
         xmlns="https://schemas.syncfusion.com/wpf"
         xmlns:s="clr-namespace:System;assembly=mscorlib"
         xmlns:av="https://schemas.microsoft.com/winfx/2006/xaml/presentation">

<SfChart.PrimaryAxis>

    <CategoryAxis Header="X Axis">

        <CategoryAxis.StripLines>
             <ChartStripLines />
        </CategoryAxis.StripLines>

    </CategoryAxis>

</SfChart.PrimaryAxis>

<SfChart.SecondaryAxis>

    <NumericalAxis Header="Y Axis">

        <NumericalAxis.StripLines>
            <ChartStripLines />
        </NumericalAxis.StripLines>

    </NumericalAxis>

</SfChart.SecondaryAxis>

<SfChart.Behaviors>
    <ChartBehaviorsCollection />
</SfChart.Behaviors>

<SfChart.Annotations>

    <AnnotationCollection>

        <RectangleAnnotation CanDrag="True" CanResize="True">
            <RectangleAnnotation.Y2>
                <s:Int32>30</s:Int32>
            </RectangleAnnotation.Y2>
            <RectangleAnnotation.X2>
                <s:Int32>2</s:Int32>
            </RectangleAnnotation.X2>
            <RectangleAnnotation.X1>
                <s:Int32>0</s:Int32>
            </RectangleAnnotation.X1>
            <RectangleAnnotation.Y1>
                <s:Int32>20</s:Int32>
            </RectangleAnnotation.Y1>
        </RectangleAnnotation>

    </AnnotationCollection>

</SfChart.Annotations>

<SfChart.ColumnDefinitions>
    <ChartColumnDefinitions />
</SfChart.ColumnDefinitions>

<SfChart.RowDefinitions>
    <ChartRowDefinitions />
</SfChart.RowDefinitions>

<ColumnSeries YBindingPath="Value"  
              ItemsSource="{av:Binding Path=CategoricalDatas}"
              XBindingPath="Category"
              Name="series"
              xmlns="https://schemas.syncfusion.com/wpf"
              xmlns:av="https://schemas.microsoft.com/winfx/2006/xaml/presentation">

<ColumnSeries.Trendlines>
    <ChartTrendLineCollection />
</ColumnSeries.Trendlines>

<ColumnSeries.LegendIconTemplate>
    <av:DataTemplate>
        <av:Rectangle Stretch="Fill"
        Fill="{av:Binding Path=Interior}"
        Stroke="{av:Binding Path=Stroke}"
        StrokeThickness="{av:Binding Path=StrokeThickness}" />
    </av:DataTemplate>
</ColumnSeries.LegendIconTemplate>

</ColumnSeries>

</SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

chart.Header = "Defect Rates";

chart.PrimaryAxis = new CategoryAxis()
{

    Header = "X Axis"

};

chart.SecondaryAxis = new NumericalAxis()
{

    Header = "Y Axis"

};

RectangleAnnotation annotation = new RectangleAnnotation()
{

    X1 = 0, X2 = 2,

    Y1 = 20, Y2 = 30,

    CanDrag = true, CanResize = true

};

chart.Annotations.Add(annotation);

ColumnSeries columnSeries = new ColumnSeries()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "XValue",

    YBindingPath = "YValue"

};

chart.Series.Add(columnSeries);

string filePath = System.IO.Directory.GetParent(@"../").FullName + "\\chart.xml";

chart.Serialize();

{% endhighlight %}

{% endtabs %}