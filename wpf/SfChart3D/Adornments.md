---
layout: post
title: Adornments | SfChart | Wpf | Syncfusion
description: This section explains about adornments behavior and its customization properties in WPF Chart (SfChart3D)
platform: wpf
control: SfChart3D
documentation: ug
---

# Adornments in WPF Chart (SfChart3D)

Adornments are used to provide information about the data points to the user. Values from data point(x, y) or other custom properties from a data source can be displayed.You can add a shape and label to adorn each data point.

The following code example illustrates how to initialize the adornment.

{% tabs %}

{% highlight xaml %}

    <chart:StackingBarSeries3D ItemsSource="{Binding CategoricalDatas}" XBindingPath="Year" YBindingPath="Plastic">
                <!--AdornmentsInfo-->
        <chart:StackingBarSeries3D.AdornmentsInfo>
            <chart:ChartAdornmentInfo3D ShowLabel="True" ></chart:ChartAdornmentInfo3D>
        </chart:StackingBarSeries3D.AdornmentsInfo>
    </chart:StackingBarSeries3D>

{% endhighlight %}

{% highlight C# %}

        StackingBarSeries3D series = new StackingBarSeries3D()
            {
                ItemsSource = new ViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic"                
            };

        ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo() { ShowLabel = true };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Chart 3D support in WPF](3D-Charts_images/Chart-3D-Adornment.png)

Each adornment can be represented by the following:

    * Marker- Displays the desired symbol at the (X, Y) point.
    * Label - Displays the segment label content at the (X, Y) point.
    * ConnectorLine - Line used to connect the (X, Y) point and the label element.

## Marker

To enable the marker in adornments you have to set the [`ShowMarker`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ShowMarker.html#) property as True. By default, there is no symbol displayed, you have to add the desired symbol using Symbol property.

The following code example demonstrates the column series with [`Diamond`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSymbol.html) symbol:


{% tabs %}

{% highlight xaml %}

        <chart:ColumnSeries3D ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">
            <chart:ColumnSeries3D.AdornmentsInfo>
                 <chart:ChartAdornmentInfo3D ShowMarker="True" Symbol="Diamond" SymbolInterior="Brown"></chart:ChartAdornmentInfo3D>
            </chart:ColumnSeries3D.AdornmentsInfo>
        </chart:ColumnSeries3D>  

{% endhighlight %}

{% highlight c# %}

        ColumnSeries3D series = new ColumnSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic"
            };

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowMarker = true,
                SymbolInterior = new SolidColorBrush(Colors.Brown),
                Symbol = ChartSymbol.Diamond
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Symbol support in WPF Chart](3D-Charts_images/Adornment_Marker.png)

## Label

SfChart provides the support to customize the label content using [`SegmentLabelContent`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SegmentLabelContent.html#) property. This property allows you to define the value to be displayed as adornment label.

{% tabs %}

{% highlight xaml %}

        <chart:ColumnSeries3D ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">
                <chart:ColumnSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D ShowLabel="True" SegmentLabelContent="LabelContentPath" AdornmentsPosition="Top"></chart:ChartAdornmentInfo3D>
                </chart:ColumnSeries3D.AdornmentsInfo>
        </chart:ColumnSeries3D>  

{% endhighlight %}

{% highlight c# %}

        ColumnSeries3D series = new ColumnSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic"
            };

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowLabel = true,
                SegmentLabelContent=LabelContent.LabelContentPath,
                AdornmentsPosition=AdornmentsPosition.Top
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

| SegmentLabelContent values | Description | Output |
|---|--|---|
| DateTime | Displays LabelContent.DateTime value | ![ DateTime in Adornment](3D-Charts_images/Adorn_DateTime.png) |
|LabelContentPath | Displays the y value|![ LabelContentPath in Adornment](3D-Charts_images/Adorn_LabelContent.png)|
| Percentage | Displays the percentage value of series' point among other points |![ Percentage in Adornment](3D-Charts_images/Adorn_Percentage.png) |
| XValue | Displays the X value of series' point|![ XValue in Adornment](3D-Charts_images/Adorn_Xvalue.png) |
| YofTot | Displays the value of Y of total values' point|![ YofTot in Adornment](3D-Charts_images/Adorn_YofTop.png) |
| YValue | Displays the Y value of series' point| ![ YValue in Adornment](3D-Charts_images/Adorn_YValue.png) |


## ConnectorLine

You can add connector line for the adornments using [`ShowConnectorLine`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ShowConnectorLine.html#) property. Also this connector line can be customized using [`ConnectorHeight`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorHeight.html#), [`ConnectorLineStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorLineStyle.html#) and [`ConnectorRotationAngle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorRotationAngle.html#) properties.


The following code example shows the how to add connector line:

{% tabs %}

{% highlight xaml %}

        <chart:ColumnSeries3D ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">
                <chart:ColumnSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D ShowLabel="True" ConnectorHeight="10" ShowConnectorLine="True" LabelPosition="Outer"></chart:ChartAdornmentInfo3D>
                </chart:ColumnSeries3D.AdornmentsInfo>
        </chart:ColumnSeries3D>  

{% endhighlight %}

{% highlight c# %}

        ColumnSeries3D series = new ColumnSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic"
            };

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowLabel = true,
                LabelPosition = AdornmentsLabelPosition.Outer,
                ShowConnectorLine = true,
                ConnectorHeight = 10
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Connector Line in WPF Chart](3D-Charts_images/Adorn_ConnectorLine.png)

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
{{'[`ShowConnectorLine`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ShowConnectorLine.html)'| markdownify }}</td><td>
Gets or sets ability to show and hide the connector line for adornments.</td></tr>
<tr>
<td>
{{'[`ConnectorLineStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorLineStyle.html)'| markdownify }}</td><td>
Gets or sets the connector line style.</td></tr>
<tr>
<td>
{{'[`ConnectorRotationAngle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorRotationAngle.html)'| markdownify }}</td><td>
Gets or sets the connector line rotate angle.</td></tr>
<tr>
<td>
{{'[`ConnectorHeight`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorHeight.html)'| markdownify }}</td><td>
Gets or sets the connector height.</td></tr>
<tr>
<td>
{{'[`LabelTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~LabelTemplate.html)'| markdownify }}</td><td>
Gets or sets the adornments label template.</td></tr>
<tr>
<td>
{{'[`Symbol`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~Symbol.html)'| markdownify }}</td><td>
Enum property to get or set the symbol for adornments.</td></tr>
<tr>
<td>
{{'[`SymbolHeight`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SymbolHeight.html)'| markdownify }}</td><td>
Gets or sets the height for the symbol.</td></tr>
<tr>
<td>
{{'[`SymbolWidth`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SymbolWidth.html)'| markdownify }}</td><td>
Gets or sets the width for the symbol.</td></tr>
<tr>
<td>
{{'[`SymbolTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SymbolTemplate.html)'| markdownify }}</td><td>
Gets or sets the symbol template.</td></tr>
<tr>
<td>
{{'[`SymbolInterior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SymbolInterior.html)'| markdownify }}</td><td>
Gets or sets the interior for the symbol.</td></tr>
<tr>
<td>
{{'[`SymbolStroke`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SymbolStroke.html)'| markdownify }}</td><td>
Gets or sets the stroke for the symbol.</td></tr>
<tr>
<td>
{{'[`AdornmentsPosition`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~AdornmentsPosition.html)'| markdownify }}</td><td>
An enum property allowed to position the adornments TopAndBottom, Bottom and Top areas.</td></tr>
<tr>
<td>
{{'[`SegmentLabelContent`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SegmentLabelContent.html)'| markdownify }}</td><td>
Gets or sets the actual label content to be displayed in the label.</td></tr>
<tr>
<td>
{{'[`SegmentLabelFormat`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SegmentLabelFormat.html)'| markdownify }}</td><td>
Gets or sets the adornments label format.</td></tr>
<tr>
<td>
{{'[`ShowMarker`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ShowMarker.html)'| markdownify }}</td><td>
A Boolean property to show or hide the markers.</td></tr>
<tr>
<td>
{{'[`ShowLabel`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ShowLabel.html)'| markdownify }}</td><td>
A Boolean property to show or hide the labels</td></tr>
</table>

Refer to [`this`](https://help.syncfusion.com/wpf/sfchart3D/adornments) link  to learn more about the options to customize chart adornments.