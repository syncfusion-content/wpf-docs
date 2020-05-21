---
layout: post
title: 3D Charts| SfChart | Wpf | Syncfusion
description: Learn how to create the 3D charts and their features such as types, axis, data binding, dynamic rotation, interactivity and depth axis.
platform: wpf
control: SfChart3D
documentation: ug
---

# Label in WPF 3D Chart (SfChart3D)  

SfChart provides the support to customize the label content using [`SegmentLabelContent`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SegmentLabelContent.html#) property. This property allows you to define the value to be displayed as adornment label.

{% tabs %}

{% highlight xaml %}

        <chart:ColumnSeries3D ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">
                <chart:ColumnSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D ShowLabel="True" SegmentLabelContent="DateTime" AdornmentsPosition="Top"></chart:ChartAdornmentInfo3D>
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
                SegmentLabelContent=LabelContent.DateTime,
                AdornmentsPosition=AdornmentsPosition.Top
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

**DateTime**

[LabelContent.DateTime](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.LabelContent.html) displays LabelContent.DateTime value.

![DateTime support in WPF Chart](Adornments-Images/Adorn_DateTime.png)

**LabelContentPath**

[LabelContent.LabelContentPath](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.LabelContent.html) displays the y value by default.

![LabelContentPath support in WPF Chart](Adornments-Images/Adorn_LabelContent.png)

**Percentage**

[LabelContent.Percentage](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.LabelContent.html) displays the percentage value of series' point among other points.

![Percentage support in WPF Chart](Adornments-Images/Adorn_Percentage.png)

**XValue**

[LabelContent.XValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.LabelContent.html) displays the X value of series' point

![XValue support in WPF Chart](Adornments-Images/Adorn_Xvalue.png)

**YofTot**

[LabelContent.YofTot](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.LabelContent.html) displays the value of Y of total values' point

![YofTot support in WPF Chart](Adornments-Images/Adorn_YofTop.png)

**YValue**

[LabelContent.YValue](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.LabelContent.html) Displays the Y value of series' point.

![YValue support in WPF Chart](Adornments-Images/Adorn_YValue.png)


## Label Rotation

[`LabelRotationAngle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~LabelRotationAngle.html#) property is used to define the angle to which the label has to rotate. The following code demonstrates the label rotating angle.

{% tabs %}

{% highlight xaml %}

        <chart:ColumnSeries3D  ItemsSource="{Binding Demands}" XBindingPath="Category"
        YBindingPath="Value">                
                <chart:ColumnSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D LabelRotationAngle="45" UseSeriesPalette="True" ShowLabel="True" BorderBrush="White" BorderThickness="1"></chart:ChartAdornmentInfo3D>
                </chart:ColumnSeries3D.AdornmentsInfo>
        </chart:ColumnSeries3D>

{% endhighlight %}

{% highlight c# %}

        ColumnSeries3D series = new ColumnSeries3D()
            {
                ItemsSource = new StockViewModel().Demands,
                XBindingPath = "Category",
                YBindingPath = "Value",
            };

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowLabel = true,
                LabelRotationAngle=45,
                LabelPosition=AdornmentsLabelPosition.Outer,
                UseSeriesPalette=true,
                BorderBrush = new SolidColorBrush(Colors.White),
                BorderThickness = new Thickness(1),
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Adornments label rotation support in WPF Chart](Adornments-Images/Label_Rotation.png)

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

            <chart:ColumnSeries3D  ItemsSource="{Binding Demands}" XBindingPath="Category"
            YBindingPath="Value">                 
                    <chart:ColumnSeries3D.AdornmentsInfo>
                        <chart:ChartAdornmentInfo3D  ShowLabel="True" FontStyle="Italic" FontFamily="Segoe UI" Background="DarkGray" BorderBrush="LightGray" Foreground="White" BorderThickness="1">                   
                    </chart:ChartAdornmentInfo3D>
                    </chart:ColumnSeries3D.AdornmentsInfo>
            </chart:ColumnSeries3D>

{% endhighlight %}

{% highlight c# %}

        ColumnSeries3D series = new ColumnSeries3D()
            {
                ItemsSource = new StockViewModel().Demands,
                XBindingPath = "Category",
                YBindingPath = "Value",
            };

           ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowLabel = true,
                LabelPosition = AdornmentsLabelPosition.Outer,
                Foreground = new SolidColorBrush(Colors.White),
                BorderBrush = new SolidColorBrush(Colors.LightGray),
                Background = new SolidColorBrush(Colors.DarkGray),
                BorderThickness = new Thickness(1),
                FontStyle = FontStyles.Italic,
                FontFamily = new FontFamily("Segoe UI"),
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Adornments label content customization support in WPF Chart](Adornments-Images/Label_appearance.png)

## Label Format

[`SegmentLabelFormat`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~SegmentLabelFormat.html#) property allows you to provide formatting for the labels.


The following code example demonstrates the label having three decimal digits:

{% tabs %}

{% highlight xaml %}

<chart:ColumnSeries3D  ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">                
                    <chart:ColumnSeries3D.AdornmentsInfo>
                        <chart:ChartAdornmentInfo3D ShowLabel="True" LabelPosition="Outer"
                        SegmentLabelFormat="#.###" ></chart:ChartAdornmentInfo3D>
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
                SegmentLabelFormat = "#.###"
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Adornments label format support in WPF Chart](Adornments-Images/Label_Format.png)


## ConnectorLine

You can add connector line for the adornments using [`ShowConnectorLine`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ShowConnectorLine.html#) property. Also this connector line can be customized using [`ConnectorHeight`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorHeight.html#), [`ConnectorLineStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorLineStyle.html#) and [`ConnectorRotationAngle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~ConnectorRotationAngle.html#) properties.


The following code example shows the how to add connector line:

{% tabs %}

{% highlight xaml %}

        <chart:PieSeries3D ItemsSource="{Binding Demands}" XBindingPath="Category"
            YBindingPath="Value" LabelPosition="OutsideExtended">
                <chart:PieSeries3D.AdornmentsInfo>
                   <chart:ChartAdornmentInfo3D ShowConnectorLine="True" ConnectorHeight="15" UseSeriesPalette="True" ShowLabel="True" BorderBrush="White" BorderThickness="1"></chart:ChartAdornmentInfo3D>
                </chart:PieSeries3D.AdornmentsInfo>
        </chart:PieSeries3D>  

{% endhighlight %}

{% highlight c# %}

        ColumnSeries3D series = new ColumnSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic",
                pie.LabelPosition=CircularSeriesLabelPosition.OutsideExtended
            };

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowLabel = true,              
                ShowConnectorLine = true,
                ConnectorHeight = 15,
                UseSeriesPalette=true,
                BorderBrush = new SolidColorBrush(Colors.White),
                BorderThickness = new Thickness(1)
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Connector Line in WPF Chart](Adornments-Images/Adorn_ConnectorLine.png)

### Connector Type

[`ConnectorType`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesBase~ConnectorType.html#) property in AccumulationSeries is used to specify the connector line type such as [`Line`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ConnectorMode.html) or [`Bezier`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ConnectorMode.html). This property is only for AccumulationSeries like PieSeries and DoughnutSeries.

The following code example shows the how to specify connector type:

{% tabs %}

{% highlight xaml %}

         <chart:PieSeries3D Palette="BlueChrome" ItemsSource="{Binding DataPoints}"  
            XBindingPath="Year" ConnectorType="Line" LabelPosition="OutsideExtended" YBindingPath="India">
                <chart:PieSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D ShowConnectorLine="True"
                                                UseSeriesPalette="True" ShowLabel="True" ></chart:ChartAdornmentInfo3D>
                </chart:PieSeries3D.AdornmentsInfo>
            </chart:PieSeries3D>

{% endhighlight %}

{% highlight c# %}

        PieSeries3D series = new PieSeries3D()
            {
                ItemsSource = new ViewModel().DataPoints,
                XBindingPath = "Year",
                YBindingPath = "India",
                LabelPosition=CircularSeriesLabelPosition.OutsideExtended,
                ConnectorType=ConnectorMode.Line
            };

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowLabel = true,
                ShowConnectorLine = true
             };

        series.AdornmentsInfo = adornmentInfo;
        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

 **Line** 
 
 ![Connector Line in WPF Chart](Adornments-Images/Adorn_Line.png) 

 **Bezier**
 
  ![Bezier in WPF Chart](Adornments-Images/Adorn_Bezier.png)|

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

![Connector line style support in WPF Chart](Adornments-Images/ConnectorLine_Customization.png)
