---
layout: post
title: 3D Charts| SfChart | Wpf | Syncfusion
description: Learn how to create the 3D charts and their features such as types, axis, data binding, dynamic rotation, interactivity and depth axis.
platform: wpf
control: SfChart3D
documentation: ug
---

# Label in WPF 3D Charts (SfChart3D)  

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

| SegmentLabelContent values | Description |
|---|--|
| DateTime | Displays LabelContent.DateTime value | 
|LabelContentPath | Displays the y value|
| Percentage | Displays the percentage value of series' point among other points |
| XValue | Displays the X value of series' point|
| YofTot | Displays the value of Y of total values' point|
| YValue | Displays the Y value of series' point| 

## Label Rotation

[`LabelRotationAngle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~LabelRotationAngle.html#) property is used to define the angle to which the label has to rotate. The following code demonstrates the label rotating angle.

{% tabs %}

{% highlight xaml %}

        <chart:ColumnSeries3D  ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
        YBindingPath="Plastic">                
                <chart:ColumnSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D ShowLabel="True" LabelRotationAngle="45" LabelPosition="Outer"></chart:ChartAdornmentInfo3D>
                </chart:ColumnSeries3D.AdornmentsInfo>
        </chart:ColumnSeries3D>

{% endhighlight %}

{% highlight c# %}

        ColumnSeries3D series = new ColumnSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic",
            };

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowLabel = true,
                LabelRotationAngle=45,
                LabelPosition=AdornmentsLabelPosition.Outer
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Adornments label rotation support in WPF Chart](/3D-Charts_images/Adornments/Label_Rotation.png)

## Customizing the label

The following properties are used to customize the adornment label.

* [`BorderBrush`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~BorderBrush.html#)
* [`BorderThickness`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~BorderThickness.html#)
* [`Margin`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~Margin.html#)
* [`FontStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~FontStyle.html#)
* [`FontSize`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~FontSize.html#)
* [`Foreground`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~Foreground.html#)
* [`FontFamily`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~FontFamily.html#)
* [`Background`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~Background.html)

The following code example demonstrates the customization of label using the above properties:

{% tabs %}

{% highlight xaml %}
            <chart:ColumnSeries3D  ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">                
                    <chart:ColumnSeries3D.AdornmentsInfo>
                        <chart:ChartAdornmentInfo3D ShowLabel="True" LabelPosition="Outer"
                            Foreground="Black" Background="SkyBlue" FontFamily="Calibri" BorderBrush="Aqua"  BorderThickness="1" Margin="1" FontSize="11" FontStyle="Italic" ></chart:ChartAdornmentInfo3D>
                    </chart:ColumnSeries3D.AdornmentsInfo>
            </chart:ColumnSeries3D>

{% endhighlight %}

{% highlight c# %}

        ColumnSeries3D series = new ColumnSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic",
            };

           ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {

                ShowLabel = true,
                LabelPosition = AdornmentsLabelPosition.Outer,
                Foreground = new SolidColorBrush(Colors.Black),
                BorderBrush = new SolidColorBrush(Colors.Aqua),
                Background = new SolidColorBrush(Colors.SkyBlue),
                BorderThickness = new Thickness(1),
                Margin = new Thickness(1),
                FontStyle = FontStyles.Italic,
                FontFamily = new FontFamily("Calibri"),
                FontSize = 11

            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Adornments label content customization support in WPF Chart](/3D-Charts_images/Adornments/Label_appearance.png)

## Label Format

[`SegmentLabelFormat`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SegmentLabelFormat.html#) property allows you to provide formatting for the labels.


The following code example demonstrates the label having three decimal digits:

{% tabs %}

{% highlight xaml %}

<chart:ColumnSeries3D  ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">                
                    <chart:ColumnSeries3D.AdornmentsInfo>
                        <chart:ChartAdornmentInfo3D ShowLabel="True" LabelPosition="Outer"
                        SegmentLabelFormat="#.00" ></chart:ChartAdornmentInfo3D>
                    </chart:ColumnSeries3D.AdornmentsInfo>
        </chart:ColumnSeries3D>

{% endhighlight %}

{% highlight c# %}

        ColumnSeries3D series = new ColumnSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic",
            };

        ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
            {
                ShowLabel = true,
                AdornmentsPosition = AdornmentsPosition.Top,
                SegmentLabelFormat = "0.000"
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Adornments label format support in WPF Chart](/3D-Charts_images/Adornments/Label_Format.png)


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

![Connector Line in WPF Chart](/3D-Charts_images/Adornments/Adorn_ConnectorLine.png)

### Connector Type

[`ConnectorType`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesBase~ConnectorType.html#) property in AccumulationSeries is used to specify the connector line type such as [`Line`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ConnectorMode.html) or [`Bezier`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ConnectorMode.html). This property is only for AccumulationSeries like PieSeries and DoughnutSeries.

The following code example shows the how to specify connector type:

{% tabs %}

{% highlight xaml %}

        <chart:PieSeries3D  ItemsSource="{Binding CategoricalData}" ConnectorType="Line" 
            CircleCoefficient="0.7" EnableSmartLabels="True" LabelPosition="OutsideExtended" 
            XBindingPath="Year" YBindingPath="Plastic">
                <chart:PieSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D ShowLabel="True" SegmentLabelContent="LabelContentPath" ConnectorHeight="80" ShowConnectorLine="True" LabelPosition="Outer"></chart:ChartAdornmentInfo3D>
                </chart:PieSeries3D.AdornmentsInfo>
        </chart:PieSeries3D> 

{% endhighlight %}

{% highlight c# %}

        PieSeries3D series = new PieSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic",
                LabelPosition=CircularSeriesLabelPosition.OutsideExtended,
                ConnectorType=ConnectorMode.Line,
                CircleCoefficient=0.7,
                EnableSmartLabels=true
            };

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowLabel = true,
                SegmentLabelContent = LabelContent.LabelContentPath,
                LabelPosition=AdornmentsLabelPosition.Outer,
                ShowConnectorLine = true,
                ConnectorHeight=80
             };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

| ConnectorType | Output |
|--|--|
| Line | ![Connector Line in WPF Chart](/3D-Charts_images/Adornments/Adorn_Line.png) |
| Bezier | ![Bezier in WPF Chart](3D-Charts_images/Adornments/Adorn_Bezier.png)|

N> ConnectorType.StraightLine behavior does not applicable for 3D series.

### Customization of ConnectorLine Appearance

You can define the style for the connector line using [`ConnectorLineStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorLineStyle.html#) properties.

{% tabs %}

{% highlight xaml %}

        <Window.Resources>

            <Style TargetType="Path" x:Key="lineStyle">
                <Setter Property="StrokeDashArray" Value="10,7,5"/>
                <Setter Property="Stroke" Value="Black"/>
            </Style>
        
        </Window.Resources>

        <chart:PieSeries3D ItemsSource="{Binding CategoricalData}" ConnectorType="Line" LabelPosition="Outside" XBindingPath="Year"
            YBindingPath="Plastic">
                <chart:PieSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D ShowLabel="True" ConnectorLineStyle="{StaticResource lineStyle}" 
                           ConnectorHeight="60" ShowConnectorLine="True" LabelPosition="Outer"></chart:ChartAdornmentInfo3D>
                </chart:PieSeries3D.AdornmentsInfo>
        </chart:PieSeries3D>
  
{% endhighlight %}

{% endtabs %}

![Connector line style support in WPF Chart](/3D-Charts_images/Adornments/ConnectorLine_Customization.png)
