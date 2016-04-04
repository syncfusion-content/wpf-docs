---
layout: post
title: Adornments| SfChart | Wpf | Syncfusion
description: adornments
platform: wpf
control: SfChart
documentation: ug
---

# Adornments

Chart adornments are used to display values related to a chart segment element. Values from data point(x, y) or other custom properties from a data source can be displayed. 

You can initialize the adornment as in the below code snippet:

{% highlight xaml %}

<syncfusion:ColumnSeries  Interior="#777777"

ItemsSource="{Binding Demands}"  

XBindingPath="Demand" 

YBindingPath="Year2011">

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo></syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

</syncfusion:ColumnSeries>

{% endhighlight %}


Each adornment can be represented by the following:

* Marker- Displays the desired symbol at the (X, Y) point.
* Label - Displays the segment label content at the (X, Y) point.
* ConnectorLine - Line used to connect the (X, Y) point and the label element.

The following topics discuss briefly about various adornment customization.

## Marker

To enable the marker in adornments you have to set the [`ShowMarker`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ShowMarker.html#) property as True. By default, there is no symbol displayed, you have to add the desired symbol using Symbol property.

The following code example demonstrates the column series with Diamond symbol:

{% highlight xaml %}

<syncfusion:ColumnSeries  Interior="#777777"

ItemsSource="{Binding Demands}"  

XBindingPath="Demand" 

YBindingPath="Year2011">

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo SymbolInterior="Black" Symbol="Diamond"></syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

</syncfusion:ColumnSeries>    

{% endhighlight %}

![](Adornments_images/marker_1.png)


### Customization

SfChart provide support more customization for markers in adornments. 

You can customize the marker size using [`SymbolHeight`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SymbolHeight.html#) and [`SymbolWidth`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SymbolWidth.html#) property. Also the marker fill color and stroke can be customized using [`SymbolInterior`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SymbolInterior.html#) and [`SymbolStroke`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SymbolStroke.html#).

{% highlight xaml %}

<syncfusion:LineSeries  Interior="#777777"

ItemsSource="{Binding Demands}"  

XBindingPath="Demand" 

YBindingPath="Year2011">

<syncfusion:LineSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo SymbolStroke="Black"

SymbolInterior="DarkGray"

SymbolWidth="10"                                                   

SymbolHeight="10"

Symbol="Ellipse"></syncfusion:ChartAdornmentInfo>

</syncfusion:LineSeries.AdornmentsInfo>

</syncfusion:LineSeries>   

{% endhighlight %}

![](Adornments_images/marker_2.png)


**Custom Template**

You can also provide the template for the symbol using `SymbolTemplate` property as in the below code snippet.

{% highlight xaml %}

<syncfusion:ColumnSeries  Label="2011" Interior="#777777"

ItemsSource="{Binding Demands}"  

XBindingPath="Demand" 

YBindingPath="Year2011">

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo AdornmentsPosition="Top"  >

<syncfusion:ChartAdornmentInfo.SymbolTemplate>

<DataTemplate>

<Grid>

<Grid Name="backgroundGrid" Width="24" Height="24" Visibility="Visible">

<Ellipse Fill="#FFE2DBDB" Name="Fill" Visibility="Visible" />

</Grid>

<Path Stretch="Uniform" Fill="#FF0F0E0E" Width="24" Height="24" Margin="0,0,0,0" RenderTransformOrigin="0.5,0.5">

<Path.Data>

<PathGeometry FillRule="Nonzero" 

Figures="M23.9296875,10.6165618896484L20.759765625,11.2200794219971 18.09375,13.0306243896484 16.283203125,15.6966400146484 15.6796875,18.8665618896484 16.283203125,22.0423431396484 18.09375,24.7259368896484 20.759765625,26.5540618896484 23.9296875,27.1634368896484 27.1025371551514,26.5540618896484 29.77734375,24.7259368896484 31.5966796875,22.0423431396484 32.203125,18.8665618896484 31.5966796875,15.6966400146484 29.77734375,13.0306243896484 27.1025371551514,11.2200794219971 23.9296875,10.6165618896484z M25.265625,7.35874938964844L26.6953125,9.86656188964844 29.3671875,8.64781188964844 29.765625,11.4837493896484 32.7421875,11.2728118896484 32.015625,14.1790618896484 34.921875,14.9759368896484 33.1875,17.4134368896484 35.578125,19.1478118896484 33.140625,20.7884368896484 34.640625,23.3665618896484 31.8046875,23.9759368896484 32.3203125,26.9759368896484 29.4375,26.5540618896484 28.921875,29.4837493896484 26.25,27.9603118896484 24.75,30.4681243896484 22.8046875,28.2181243896484 20.5078125,30.0228118896484 19.5703125,27.1634368896484 16.640625,28.0306243896484 16.875,25.1009368896484 13.875,24.7728118896484 15.140625,22.1478118896484 12.421875,20.7415618896484 14.5546875,18.6790618896484 12.4921875,16.5228118896484 15.2578125,15.3040618896484 14.203125,12.5384368896484 17.1328125,12.3978118896484 17.1328125,9.42124938964844 19.921875,10.4056243896484 

21.046875,7.61656188964844 23.296875,9.49156188964844 25.265625,7.35874938964844z" />

</Path.Data>

<Path.RenderTransform>

<TransformGroup>

<TransformGroup.Children>

<RotateTransform Angle="0" />

<ScaleTransform ScaleX="1" ScaleY="1" />

</TransformGroup.Children>

</TransformGroup>

</Path.RenderTransform>

</Path>

</Grid>

</DataTemplate>

</syncfusion:ChartAdornmentInfo.SymbolTemplate>

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

</syncfusion:ColumnSeries>

{% endhighlight %}

![](Adornments_images/custom_template.png)


## Label

Label represents the text in the adornments which helps to identify the segment based on it y or x value. You can enable the label by setting [`ShowLabel`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ShowLabel.html#) property as true as in the below code example.

{% highlight xaml %}

<syncfusion:ColumnSeries  Label="2011" Interior="#777777"

ItemsSource="{Binding Demands}"  

XBindingPath="Demand" 

YBindingPath="Year2011">

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo AdornmentsPosition="Top" ShowLabel="True" >

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

</syncfusion:ColumnSeries>

{% endhighlight %}

![](Adornments_images/label_1.png)


### Defining the Label Content

SfChart provides the support to customize the label content using [`SegmentLabelContent`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SegmentLabelContent.html#) property. This property allows you to define the value to be displayed as adornment label.

**XValue**

{% highlight xaml %}

<syncfusion:ColumnSeries  Label="2011" Interior="#777777"

ItemsSource="{Binding Demands}"  

XBindingPath="Demand" 

YBindingPath="Year2011">

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo AdornmentsPosition="Top" SegmentLabelContent="XValue" ShowLabel="True" >

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

</syncfusion:ColumnSeries>

{% endhighlight %}

![](Adornments_images/label_2.png)


N>For CategoryAxis, the x values will be taken as the index since it is an indexed based axis. If it is a numerical axis or date time the corresponding x value will be displayed.

**Percentage**

{% highlight xaml %}

<syncfusion:ColumnSeries  Label="2011" Interior="#777777"

ItemsSource="{Binding Demands}"  

XBindingPath="Demand" 

YBindingPath="Year2011">

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo AdornmentsPosition="Top" SegmentLabelContent="Percentage" ShowLabel="True" >

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

</syncfusion:ColumnSeries>

{% endhighlight %}

![](Adornments_images/label_3.png)


**YofTot**


{% highlight xaml %}

<syncfusion:ColumnSeries  ItemsSource="{Binding Demands}"  

XBindingPath="Demand" 

YBindingPath="Year2011">

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo AdornmentsPosition="Top" SegmentLabelContent="YofTot" ShowLabel="True" >

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

</syncfusion:ColumnSeries>

{% endhighlight %}

![](Adornments_images/label_4.png)


**DateTime**

{% highlight xaml %}

<syncfusion:ColumnSeries ItemsSource="{Binding Demands}"   XBindingPath="Date"  

YBindingPath="Year2011">

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo ShowLabel="True" 

SegmentLabelContent="DateTime" >

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

</syncfusion:ColumnSeries>

{% endhighlight %}

{% highlight C# %}

{% endhighlight %}

![](Adornments_images/label_5.png)


N> If you are having DateTimeAxis then the corresponding date time value will be displayed. In case of category or numerical axis the value will be converted to OADate.

**LabelContentPath**

LabelContentPath property by default displays the y value. If you need to specify the value other than y value you can define the `LabelTemplate` where you can retrieve the adornment value of every segment. 

The following code example demonstrates displaying the string value which is taken as x values.

{% tabs %}

{% highlight xaml %}

<syncfusion:PieSeries ItemsSource="{Binding Demands}" XBindingPath="Demand"  YBindingPath="Year2011">

<syncfusion:PieSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo ShowLabel="True"  ShowConnectorLine="True" 

SegmentLabelContent="LabelContentPath"

LabelPosition="Auto"

Foreground="Black"  >

<syncfusion:ChartAdornmentInfo.LabelTemplate>

<DataTemplate >

<Border CornerRadius="2" BorderBrush="Black" BorderThickness="1" Background="LightGray" >

<TextBlock HorizontalAlignment="Center" FontSize="11" Foreground="Black" Text="{Binding Converter={StaticResource con}}"></TextBlock>

</Border>

</DataTemplate>

</syncfusion:ChartAdornmentInfo.LabelTemplate>

</syncfusion:ChartAdornmentInfo>

</syncfusion:PieSeries.AdornmentsInfo>

</syncfusion:PieSeries>

{% endhighlight %}

{% highlight C# %}

public class convert : IValueConverter

{

public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)

{

ChartPieAdornment adornment= value as ChartPieAdornment;

return (adornment.Item as GoldDemand).Demand ;

}

public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)

{

throw new NotImplementedException();

}

}

{% endhighlight %}

{% endtabs %}


![](Adornments_images/label_5.png)


**Label Rotation**

[`LabelRotationAngle`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~LabelRotationAngle.html#) property is used to define the angle to which the label has to rotate. The following code demonstrates the label rotating angle.

{% highlight xaml %}

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo  ShowLabel="True" LabelPosition="Outer" LabelRotationAngle="45" >

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

{% endhighlight %}

![](Adornments_images/label_rotation.png)

### Customization

The following properties are used to customize the adornment label.

* [`BorderBrush`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~BorderBrush.html#)
* [`BorderThickness`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~BorderThickness.html#)
* [`Margin`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~Margin.html#)
* [`FontStyle`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~FontStyle.html#)
* [`FontSize`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~FontSize.html#)
* [`Foreground`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~Foreground.html#)
* [`FontFamily`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~FontFamily.html#)

The following code example demonstrates the customization of label using the above properties:

{% highlight xaml %}

<syncfusion:ColumnSeries  Label="2011"

Interior="#777777"

ItemsSource="{Binding Demands}" 

XBindingPath="Date"  

YBindingPath="Year2011">

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo ShowLabel="True" LabelPosition="Outer" 

Foreground="Black" 

FontSize="11"

Background="DarkGray"

FontFamily="Calibri"

BorderBrush="Black"

BorderThickness="1"

Margin="1"

FontStyle="Italic" 

>

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

</syncfusion:ColumnSeries>

{% endhighlight %}

![](Adornments_images/custom_label.png)


## Applying Series Brush

[`UseSeriesPalette`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~UseSeriesPalette.html#) property is used to set the interior of the series to the adornment background. 

For Accumulation like Pie, Doughnut, Funnel and Pyramid the segment interior color will be reflected in adornment background.

{% highlight xaml %}

<syncfusion:PieSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo ShowLabel="True" Foreground="White" UseSeriesPalette="True" ShowConnectorLine="True" ConnectorHeight="20">

</syncfusion:ChartAdornmentInfo>

</syncfusion:PieSeries.AdornmentsInfo>

{% endhighlight %}

![](Adornments_images/series_palette.png)


The default appearance of the label can be customized using `LabelTemplate` property as in the below code example:

{% highlight xaml %}

<syncfusion:ColumnSeries  Label="2011"

Interior="#777777"

ItemsSource="{Binding Demands}" 

XBindingPath="Demand"  

YBindingPath="Year2011">

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo ShowLabel="True" LabelPosition="Outer">

<syncfusion:ChartAdornmentInfo.LabelTemplate>

<DataTemplate>

<Grid>

<Grid.RowDefinitions>

<RowDefinition Height="15" ></RowDefinition>

<RowDefinition Height="15"></RowDefinition>

</Grid.RowDefinitions>

<Grid Name="backgroundGrid" Width="24" Height="24" Visibility="Collapsed" />



<Path Grid.Row="0"  Stretch="Uniform" Fill="#FF0F0E0E" Width="24" Height="24" Margin="0,0,0,0" RenderTransformOrigin="0.5,0.5">

<Path.Data>

<PathGeometry FillRule="Nonzero" Figures="M22.5,15.8899993896484L37.5,30.8899993896484 7.5,30.8899993896484 22.5,15.8899993896484z" />

</Path.Data>

<Path.RenderTransform>

<TransformGroup>

<TransformGroup.Children>

<RotateTransform Angle="0" />

<ScaleTransform ScaleX="1" ScaleY="1" />

</TransformGroup.Children>

</TransformGroup>

</Path.RenderTransform>



</Path>

<TextBlock Grid.Row="1" Text="{Binding}" FontSize="11" Foreground="Black"></TextBlock>

</Grid>

</DataTemplate>

</syncfusion:ChartAdornmentInfo.LabelTemplate>

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

</syncfusion:ColumnSeries>

{% endhighlight %}

![](Adornments_images/label_template.png)


## Label Format

[`SegmentLabelFormat`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SegmentLabelFormat.html#) property allows you to provide formatting for the labels.

In the following image, you can see the decimal position will be rounded off to two digits by default.

![](Adornments_images/label_format.png)


The following code example demonstrates the rounding off the y value to three decimal digits:


{% highlight xaml %}

<syncfusion:ColumnSeries  Label="2011"

Interior="#777777"

ItemsSource="{Binding Demands}" 

XBindingPath="Demand"  

YBindingPath="Year2011">

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo ShowLabel="True" SegmentLabelFormat="0.##" AdornmentsPosition="Top">

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

</syncfusion:ColumnSeries>

{% endhighlight %}


## Adding Connector Line to Adornments

You can add connector line for the adornments using [`ShowConnectorLine`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ShowConnectorLine.html#) property. Also this connector line can be customized using [`ConnectorHeight`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorHeight.html#), [`ConnectorLineStyle`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorLineStyle.html#) and [`ConnectorRotationAngle`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorRotationAngle.html#) properties.

The following code example shows the customization option for connector line:

{% highlight xaml %}

<syncfusion:PieSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo ShowLabel="True"  ShowConnectorLine="True" >

</syncfusion:ChartAdornmentInfo>

</syncfusion:PieSeries.AdornmentsInfo>

{% endhighlight %}

![](Adornment_images/connectorline_1.png)


### Connector Height and Rotation

You can customize the connector line height and also line can be rotated to any specified angle.

### Connector Line Style

You can define the style for the connector line using [`ConnectorLineStyle`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorLineStyle.html#) properties.


{% highlight xaml %}

<syncfusion:ChartAdornmentInfo.ConnectorLineStyle>

<Style TargetType="Path">

<Setter Property="StrokeDashArray" Value="10,7,5"/>

<Setter Property="Stroke" Value="Black"/>

</Style>

</syncfusion:ChartAdornmentInfo.ConnectorLineStyle>

{% endhighlight %}

![](Adornments_images/connectorline_2.png)


### Connector Type

[`ConnectorType`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesBase~ConnectorType.html#) property in AccumulationSeries is used to determine the type of line for the connector. This property is only for AccumulationSeries like PieSeries, DoughnutSeries, PyramidSeries and FunnelSeries.

**Line**

![](Adornments_images/connectorline_3.png)

**Bezier**

{% highlight xaml %}

<syncfusion:PieSeries ConnectorType="Bezier" LabelPosition="Outside"

ItemsSource="{Binding Demands}"   

XBindingPath="Demand"  EnableSmartLabels="True"

YBindingPath="Year2011">

<syncfusion:PieSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo ShowLabel="True" ConnectorHeight="17" ShowConnectorLine="True" >

</syncfusion:ChartAdornmentInfo>

</syncfusion:PieSeries.AdornmentsInfo>

</syncfusion:PieSeries>

{% endhighlight %}

![](Adornments_images/connectorline_4.png)


## Positioning the Adornments

The positioning of adornments inside the series is defined using [`AdornmentPosition`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~AdornmentsPosition.html#) property. 

* Top- Positions the Adornment at the top edge point of a chart segment.
* Bottom- Positions the Adornment at the bottom edge point of a chart segment.
* TopandBottom- Positions the Adornment at the center point of a chart segment.

N> This behavior varies based on the type chart series.

The following code example explains the positioning of adornments in the middle of the segment.

{% highlight xaml %}

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo AdornmentsPosition="TopAndBottom" 

ShowMarker="True" Symbol="Ellipse">

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

{% endhighlight %}

![](Adornments_images/adornment_pos_1.png)

Also you can define the label alignment using  [`HorizontalAlignment`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~HorizontalAlignment.html#) and [`VerticalAlignment`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~VerticalAlignment.html#) properties and the following code example demonstrates the labels positioned using horizontal and vertical alignment.

{% highlight xaml %}

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo  ShowLabel="True" LabelPosition="Default" HorizontalAlignment="Right" VerticalAlignment="Top">

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

{% endhighlight %}

![](Adornments_images/adornment_pos_2.png)

### Advanced Positioning

Other than the above positioning options, SfChart providing additional customization option to position the adornments smartly based on series types using [`LabelPosition`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~LabelPosition.html#) property.

The following are the values for this property: 

* Default
* Auto
* Inner
* Outer
* Center

The following section shows few examples for this LabelPosition behavior with respect to the series.

**Column Series**

LabelPosition as Center

{% highlight xaml %}

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo  ShowLabel="True" LabelPosition="Center">

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

{% endhighlight %}

![](Adornments_images/adornment_pos_3.png)


LabelPosition as Inner

{% highlight xaml %}

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo  ShowLabel="True" LabelPosition="Inner">

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

{% endhighlight %}

![](Adornments_images/adornment_pos_4.png)


LabelPosition as Outer

{% highlight xaml %}

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo  ShowLabel="True" LabelPosition="Outer">

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

{% endhighlight %}

![](Adornments_images/adornment_pos_5.png)


**Line Series**

LabelPosition as Auto

{% highlight xaml %}

<syncfusion:SplineSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo  ShowLabel="True" LabelPosition="Auto">

</syncfusion:ChartAdornmentInfo>

</syncfusion:SplineSeries.AdornmentsInfo>

{% endhighlight %}

![](Adornments_images/adornment_pos_6.png)

LabelPosition as Inner

{% highlight xaml %}

<syncfusion:SplineSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo  ShowLabel="True" LabelPosition="Inner">

</syncfusion:ChartAdornmentInfo>

</syncfusion:SplineSeries.AdornmentsInfo>

{% endhighlight %}

![](Adornments_images/adornment_pos_7.png)


LabelPosition as Outer

{% highlight xaml %}

<syncfusion:SplineSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo  ShowLabel="True" LabelPosition="Outer">

</syncfusion:ChartAdornmentInfo>

</syncfusion:SplineSeries.AdornmentsInfo>

{% endhighlight %}

![](Adornments_images/adornment_pos_8.png)

LabelPosition as Center

{% highlight xaml %}

<syncfusion:SplineSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo  ShowLabel="True" LabelPosition="Center">

</syncfusion:ChartAdornmentInfo>

</syncfusion:SplineSeries.AdornmentsInfo>

{% endhighlight %}

![](Adornments_images/adornment_pos_9.png)


## Smart Labels for Accumulation Series

When you have more datapoints in Pie or Doughnut series, the adornment labels might get overlap with each other. SfChart provides built-in support to avoid these overlapping by using [`EnableSmartLabels`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesBase~EnableSmartLabels.html#) property.

The following code example demonstrates the EnableSmartLabels property:

{% highlight xaml %}

<chart:PieSeries EnableAnimation="False" x:Name="DouughnutSeries" 

ExplodeAll="True" ExplodeRadius="3" Palette="Custom"

EnableSmartLabels="True"

XBindingPath="Category" ItemsSource="{Binding Tax}" 

Label="Tax" YBindingPath="Percentage">

<chart:PieSeries.AdornmentsInfo>

<chart:ChartAdornmentInfo HorizontalAlignment="Center"

VerticalAlignment="Center" ShowLabel="True" ShowConnectorLine="True" UseSeriesPalette="True"

>

</chart:ChartAdornmentInfo>

</chart:PieSeries.AdornmentsInfo>

{% endhighlight %}

![](Adornments_images/smartlabel.png)


