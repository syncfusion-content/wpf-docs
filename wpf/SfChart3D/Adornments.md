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

Each adornment can be represented by the following:

    * Marker- Displays the desired symbol at the (X, Y) point.
    * Label - Displays the segment label content at the (X, Y) point.
    * ConnectorLine - Line used to connect the (X, Y) point and the label element.

    
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

![Chart 3D support in WPF](3D-Charts_images/Adornments/Chart-3D-Adornment.png)

## Marker

To enable the marker in adornments you have to set the [`ShowMarker`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ShowMarker) property as True. By default, there is no symbol displayed, you have to add the desired symbol using Symbol property.

The following code example demonstrates the column series with [`Diamond`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSymbol.html) symbol:


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

![Symbol support in WPF Chart](3D-Charts_images/Adornments/Adornment_Marker.png)

### Customization of Symbol

SfChart3D provides support more customization for symbol in adornments.

* [`SymbolHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SymbolHeight) 
* [`SymbolWidth`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SymbolWidth) 
* [`SymbolInterior`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SymbolInterior) 
* [`SymbolStroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SymbolStroke)
* [`SymbolTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SymbolTemplate)

The following code example demonstrates the basic customization of symbol size and appearance.

{% tabs %}

{% highlight xaml %}

        <chart:ColumnSeries3D ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">
            <chart:ColumnSeries3D.AdornmentsInfo>
                <chart:ChartAdornmentInfo3D AdornmentsPosition="Top" ShowMarker="True" SymbolHeight="15" SymbolWidth="15" 
                          SymbolInterior="Brown" SymbolStroke="DarkGray" Symbol="Triangle" />
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
                SymbolStroke=new SolidColorBrush(Colors.DarkGray),
                Symbol = ChartSymbol.Triangle,
                AdornmentsPosition = AdornmentsPosition.Top,
                SymbolHeight = 15,
                SymbolWidth = 15,
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![ Custom Symbol in Adornment](3D-Charts_images/Adornments/SymblBasic.png) 

**SymbolTemplate**

The following code example demonstrates how to use SymbolTemplate.

{% tabs %}

{% highlight xaml %}

<Window.Resources>
        <DataTemplate x:Key="symbolTemplate">
            <Grid>
                <Grid Name="backgroundGrid" Width="24" Height="24" Visibility="Visible">
                    <Ellipse Fill="#FFE2DBDB" Name="Fill" Visibility="Visible" />
                </Grid>

                <Path Stretch="Uniform" Fill="Brown" Stroke="Green" Width="24" Height="24" RenderTransformOrigin="0.5,0.5">
                    <Path.Data>
                        <PathGeometry FillRule="Nonzero" Figures="M23.9296875,10.6165618896484L20.759765625,11.2200794219971 18.09375,
                            13.0306243896484 16.283203125,15.6966400146484 15.6796875,18.8665618896484 16.283203125,
                            22.0423431396484 18.09375,24.7259368896484 20.759765625,26.5540618896484 23.9296875,27.1634368896484 27.1025371551514,
                            26.5540618896484 29.77734375,24.7259368896484 31.5966796875,22.0423431396484 32.203125,18.8665618896484 31.5966796875,
                            15.6966400146484 29.77734375,13.0306243896484 27.1025371551514,11.2200794219971 23.9296875,10.6165618896484z M25.265625,
                            7.35874938964844L26.6953125,9.86656188964844 29.3671875,8.64781188964844 29.765625,11.4837493896484 32.7421875,
                            11.2728118896484 32.015625,14.1790618896484 34.921875,14.9759368896484 33.1875,17.4134368896484 35.578125,
                            19.1478118896484 33.140625,20.7884368896484 34.640625,23.3665618896484 31.8046875,23.9759368896484 32.3203125,
                            26.9759368896484 29.4375,26.5540618896484 28.921875,29.4837493896484 26.25,27.9603118896484 24.75,
                            30.4681243896484 22.8046875,28.2181243896484 20.5078125,30.0228118896484 19.5703125,27.1634368896484 16.640625,
                            28.0306243896484 16.875,25.1009368896484 13.875,24.7728118896484 15.140625,22.1478118896484 12.421875,
                            20.7415618896484 14.5546875,18.6790618896484 12.4921875,16.5228118896484 15.2578125,15.3040618896484 14.203125,
                            12.5384368896484 17.1328125,12.3978118896484 17.1328125,9.42124938964844 19.921875,10.4056243896484 21.046875,
                            7.61656188964844 23.296875,9.49156188964844 25.265625,7.35874938964844z" />
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

    </Window.Resources>
    
<Grid>
        <chart:SfChart3D  Width="500" Height="500" >

    ...
        <chart:ColumnSeries3D  ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">
                <chart:ColumnSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D AdornmentsPosition="Top" ShowMarker="True"
                        SymbolTemplate="{StaticResource symbolTemplate}" ></chart:ChartAdornmentInfo3D>
                </chart:ColumnSeries3D.AdornmentsInfo>
        </chart:ColumnSeries3D>

    ...
        </chart:SfChart3D>
</Grid>

{% endhighlight %}

{% endtabs %}

![ Custom Symbol in Adornment](3D-Charts_images/Adornments/SymbolCustom.png) 

## Label

SfChart provides the support to customize the label content using [`SegmentLabelContent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SegmentLabelContent) property. This property allows you to define the value to be displayed as adornment label.

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
| DateTime | Displays LabelContent.DateTime value | ![ DateTime in Adornment](3D-Charts_images/Adornments/Adorn_DateTime.png) |
|LabelContentPath | Displays the y value|![ LabelContentPath in Adornment](3D-Charts_images/Adornments/Adorn_LabelContent.png)|
| Percentage | Displays the percentage value of series' point among other points |![ Percentage in Adornment](3D-Charts_images/Adornments/Adorn_Percentage.png) |
| XValue | Displays the X value of series' point|![ XValue in Adornment](3D-Charts_images/Adornments/Adorn_Xvalue.png) |
| YofTot | Displays the value of Y of total values' point|![ YofTot in Adornment](3D-Charts_images/Adornments/Adorn_YofTop.png) |
| YValue | Displays the Y value of series' point| ![ YValue in Adornment](3D-Charts_images/Adornments/Adorn_YValue.png) |

### Label Rotation

[`LabelRotationAngle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_LabelRotationAngle) property is used to define the angle to which the label has to rotate. The following code demonstrates the label rotating angle.

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

![Adornments label rotation support in WPF Chart](3D-Charts_images/Adornments/Label_Rotation.png)

### Customization

The following properties are used to customize the adornment label.

* [`BorderBrush`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_BorderBrush)
* [`BorderThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_BorderThickness)
* [`Margin`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_Margin)
* [`FontStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_FontStyle)
* [`FontSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_FontSize)
* [`Foreground`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_Foreground)
* [`FontFamily`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_FontFamily)
* [`Background`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_Background)

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

![Adornments label content customization support in WPF Chart](3D-Charts_images/Adornments/Label_appearance.png)

## Applying Series Brush

[`UseSeriesPalette`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_UseSeriesPalette) property is used to set the interior of the series to the adornment background. 

For Accumulation like Pie, Doughnut, Funnel and Pyramid the segment interior color will be reflected in adornment background.

{% tabs %}

{% highlight xaml %}

        <chart:ColumnSeries3D  ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">                
                    <chart:ColumnSeries3D.AdornmentsInfo>
                        <chart:ChartAdornmentInfo3D ShowLabel="True" LabelPosition="Outer"
                        UseSeriesPalette="True" ></chart:ChartAdornmentInfo3D>
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
                UseSeriesPalette=true
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Series brush for adornments background support in WPF Chart](3D-Charts_images/Adornments/Label_palette.png)

## Label Format

[`SegmentLabelFormat`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SegmentLabelFormat) property allows you to provide formatting for the labels.


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

![Adornments label format support in WPF Chart](3D-Charts_images/Adornments/Label_Format.png)


## ConnectorLine

You can add connector line for the adornments using [`ShowConnectorLine`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ShowConnectorLine) property. Also this connector line can be customized using [`ConnectorHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ConnectorHeight), [`ConnectorLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ConnectorLineStyle) and [`ConnectorRotationAngle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ConnectorRotationAngle) properties.


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

![Connector Line in WPF Chart](3D-Charts_images/Adornments/Adorn_ConnectorLine.png)

### Connector Type

[`ConnectorType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_ConnectorType) property in AccumulationSeries is used to specify the connector line type such as [`Line`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ConnectorMode.html) or [`Bezier`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ConnectorMode.html). This property is only for AccumulationSeries like PieSeries and DoughnutSeries.

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
| Line | ![Connector Line in WPF Chart](3D-Charts_images/Adornments/Adorn_Line.png) |
| Bezier | ![Bezier in WPF Chart](3D-Charts_images/Adornments/Adorn_Bezier.png)|

N> ConnectorType.StraightLine behavior does not applicable for 3D series.

### Customization of ConnectorLine Appearance

You can define the style for the connector line using [`ConnectorLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ConnectorLineStyle) properties.

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

![Connector line style support in WPF Chart](3D-Charts_images/Adornments/ConnectorLine_Customization.png)

## Positioning the Adornments

The positioning of adornments inside the series is defined using [`AdornmentPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_AdornmentsPosition) property. 

* [`Top`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AdornmentsPosition.html) - Positions the Adornment at the top edge point of a chart segment.
* [`Bottom`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AdornmentsPosition.html) - Positions the Adornment at the bottom edge point of a chart segment.
* [`TopAndBottom`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AdornmentsPosition.html) - Positions the Adornment at the center point of a chart segment.

N> This behavior varies based on the chart series type.

The following code example shows the how to specify connector type:

{% tabs %}

{% highlight xaml %}

        <chart:ColumnSeries3D  ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">
                <chart:ColumnSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D ShowMarker="True" SymbolHeight="10" SymbolWidth="10" Symbol="Diamond" AdornmentsPosition="Top" SymbolInterior="Brown"></chart:ChartAdornmentInfo3D>
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
                ShowMarker = true,
                SymbolInterior = new SolidColorBrush(Colors.Brown),
                Symbol = ChartSymbol.Diamond,
                AdornmentsPosition=AdornmentsPosition.Top,
                SymbolHeight=10,
                SymbolWidth=10
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

| AdornmentsPosition | Output |
|--|--|
| Top | ![Top Position in WPF Chart](3D-Charts_images/Adornments/Adorn_Top.png) |
| Bottom | ![Bottom Position in WPF Chart](3D-Charts_images/Adornments/Adorn_Bottom.png) |
| TopAndBottom | ![TopAndBottom Position in WPF Chart](3D-Charts_images/Adornments/Adorn_TopAndBottom.png) |

### Advanced Positioning

Other than the above positioning options, SfChart providing additional customization option to position the adornments smartly based on series types using [`LabelPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_LabelPosition) property.

The following are the values for this property: 

* [`Default`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AdornmentsLabelPosition.html)
* [`Auto`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AdornmentsLabelPosition.html)
* [`Inner`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AdornmentsLabelPosition.html)
* [`Outer`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AdornmentsLabelPosition.html)
* [`Center`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AdornmentsLabelPosition.html)

The following section shows few examples for this LabelPosition behavior with respect to the series.

| LabelPosition | Column Series | Line Series|
|--|--|--|
| Auto | ![Auto Position in WPF Chart](3D-Charts_images/Adornments/Label_Auto_Column.png) | ![Auto Position in WPF Chart](3D-Charts_images/Adornments/Label_Auto_Line.png) |
| Inner | ![Inner Position in WPF Chart](3D-Charts_images/Adornments/Label_Inner_Column.png) | ![Auto Position in WPF Chart](3D-Charts_images/Adornments/Label_Inner_Line.png) |
| Outer | ![Outer Position in WPF Chart](3D-Charts_images/Adornments/Label_Outer_Column.png) | ![Auto Position in WPF Chart](3D-Charts_images/Adornments/Label_Outer_Line.png) |
| Center | ![Auto Position in WPF Chart](3D-Charts_images/Adornments/Label_Center_Column.png) | ![Auto Position in WPF Chart](3D-Charts_images/Adornments/Label_Center_Line.png) |


## Smart Labels

When you have more datapoints in Pie or Doughnut series, the adornment labels might get overlap with each other. SfChart provides built-in support to avoid these overlapping by using [`EnableSmartLabels`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_EnableSmartLabels) property.

The following code example demonstrates the EnableSmartLabels property:

{% tabs %}

{% highlight xaml %}

        <chart:PieSeries3D  ItemsSource="{Binding CategoricalData}" ConnectorType="Bezier" XBindingPath="Year"
            YBindingPath="Plastic" EnableSmartLabels="True" LabelPosition="OutsideExtended" ExplodeAll="True" ExplodeRadius="3">
                <chart:PieSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D ShowLabel="True" HorizontalAlignment="Center" VerticalAlignment="Center" ShowConnectorLine="True"></chart:ChartAdornmentInfo3D>
                </chart:PieSeries3D.AdornmentsInfo>
        </chart:PieSeries3D>

{% endhighlight %}

{% highlight c# %}

        PieSeries3D series = new PieSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic",
                LabelPosition = CircularSeriesLabelPosition.OutsideExtended,
                ConnectorType = ConnectorMode.StraightLine,                
                EnableSmartLabels = true,
                ExplodeAll=true,
                ExplodeRadius=3
            };

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowLabel = true,
                ShowConnectorLine = true,
                HorizontalAlignment=HorizontalAlignment.Center,
                VerticalAlignment=VerticalAlignment.Center
            };

        series.AdornmentsInfo = adornmentInfo;
        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Smart Labels in WPF Chart](3D-Charts_images/Adornments/SmartLabels.png)

N> For circular series, the adornment position can be changed to [`Inside`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html), [`Outside`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html) or [`OutsideExtended`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html) using the [`LabelPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_LabelPosition) property.
