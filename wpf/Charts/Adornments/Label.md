---
layout: post
title: Data Label in WPF Charts control | Syncfusion
description: Learn here all about Data Label support in Syncfusion WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---

# Data Label in WPF Charts (SfChart)

Data points can be easily annotated with labels to help improve the readability of data. 

## Define Data Label 

To enable the Label in adornments you have to set the [`ShowLabel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ShowLabel) property of [`ChartAdornmentInfo`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfo.html). 

[`SegmentLabelContent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SegmentLabelContent) property allows you to define the value to be displayed as adornment label.

The following code example demonstrates about define the value to be displayed as adornment label.

{% tabs %}

{% highlight xaml %}

            <syncfusion:ChartAdornmentInfo SegmentLabelContent="YValue" ShowLabel="True" LabelPosition="Outer"></syncfusion:ChartAdornmentInfo>

{% endhighlight %}

{% highlight c# %}
        
            ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
            {
               ShowLabel = true,
               SegmentLabelContent=LabelContent.YValue
            };

{% endhighlight %}

{% endtabs %}

| SegmentLabelContent values | Description | Output |
|---|--|---|
| DateTime | Displays LabelContent.DateTime value | ![WPF Chart DateTime in Adornment](adornments_images/wpf-chart-datetime.png) |
|LabelContentPath | Without using a LabelTemplate, it displays the y value by default. If we use LabelTemplate for Adornment, we must specify this in to get the underlying data model as DataContext. |![WPF Chart LabelContentPath in Adornment](adornments_images/wpf-chart-label-content-path.png)|
| Percentage | Displays the percentage value of series' point among other points |![WPF Chart Percentage in Adornment](adornments_images/wpf-chart-percentage.png) |
| XValue | Displays the X value of series' point|![WPF Chart XValue in Adornment](adornments_images/wpf-chart-Xvalue.png) |
| YofTot | Displays the value of Y of total values' point|![WPF Chart YofTot in Adornment](Adornments_images/YofTot.png) |
| YValue | Displays the Y value of series' point| ![WPF Chart YValue in Adornment](adornments_images/wpf-chart-YValue.png) |

## Customizing Labels

The following properties are used to customize the adornment label.

* [`BorderBrush`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_BorderBrush)- used to change the border color.
* [`BorderThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_BorderThickness)- used to change the thickness of the border.
* [`Margin`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_Margin)- used to change the margin size for label.
* [`FontStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_FontStyle)-  used to change font family of the label.
* [`FontSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_FontSize) -  used to change font size of the label.
* [`Foreground`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_Foreground)- used to change the color of the label.
* [`FontFamily`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_FontFamily)-  used to change the font family of the label.
* [`Background`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_Background)- used to change the label background color.

The following code example demonstrates the customization of label using the above properties:

{% tabs %}

{% highlight xaml %}

        <syncfusion:ColumnSeries.AdornmentsInfo>
            <syncfusion:ChartAdornmentInfo LabelPosition="Outer" Foreground="Black" FontSize="11" FontFamily="Calibri" BorderBrush="Black" BorderThickness="1" Margin="1" FontStyle="Italic"  Background="DarkGray" ShowLabel="True">                        
            </syncfusion:ChartAdornmentInfo>
        </syncfusion:ColumnSeries.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

        ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
            {

                ShowLabel = true,
                LabelPosition = AdornmentsLabelPosition.Outer,
                Foreground = new SolidColorBrush(Colors.Black),
                BorderBrush = new SolidColorBrush(Colors.Black),
                Background = new SolidColorBrush(Colors.DarkGray),
                BorderThickness = new Thickness(1),
                Margin = new Thickness(1),
                FontStyle = FontStyles.Italic,
                FontFamily = new FontFamily("Calibri"),
                FontSize = 11
            };


{% endhighlight %}

{% endtabs %}

![Adornments label content customization support in WPF Chart](adornments_images/wpf-chart-custom-Label.png)

## Label Template

The default appearance of the label can be customized using [`LabelTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_LabelTemplate) property and along with [`SegmentLabelContent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SegmentLabelContent) property value as `LabelContentPath` as in the below code example:

{% tabs %}

{% highlight xaml %}

    <Window.Resources>
        <DataTemplate x:Key="adornmentTemplate">
            <StackPanel Orientation="Vertical">               
                <Path Grid.Row="0"  Stretch="Uniform" Fill="#FF0F0E0E"                              
                           Width="15" Height="15" Margin="0,0,0,0"                              
                           RenderTransformOrigin="0.5,0.5">
                    <Path.Data>
                        <PathGeometry FillRule="Nonzero" Figures="M22.5,15.8899993896484L37.5,                                
                                              30.8899993896484 7.5,30.8899993896484 22.5,15.8899993896484z" />
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
                <TextBlock Grid.Row="1" Text="{Binding Item.Value}" FontSize="11" Foreground="Black"></TextBlock>
            </StackPanel>
        </DataTemplate>
    </Window.Resources>

     <Grid>
        <chart:SfChart Width="400" Height="300">
         ...
            <syncfusion:ColumnSeries Interior="#777777" ItemsSource="{Binding Demands}" XBindingPath="Category" YBindingPath="Value">
                <syncfusion:ColumnSeries.AdornmentsInfo>
                    <syncfusion:ChartAdornmentInfo ShowLabel="True" LabelTemplate="{StaticResource adornmentTemplate}"
                        LabelPosition="Outer" SegmentLabelContent="LabelContentPath"></syncfusion:ChartAdornmentInfo>
                </syncfusion:ColumnSeries.AdornmentsInfo>
            </syncfusion:ColumnSeries>
        ...
        </chart:SfChart>
    </Grid>

{% endhighlight %}

{% highlight c# %}

        ColumnSeries series = new ColumnSeries()
            {
                ItemsSource = new ViewModel().Demands,
                XBindingPath = "Category",
                YBindingPath = "Value",
                 Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))
            };

            ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
            {
                ShowLabel = true,
                LabelPosition = AdornmentsLabelPosition.Outer,
                LabelTemplate = this.Resources["adornmentTemplate"] as DataTemplate
            };
        series.AdornmentsInfo = adornmentInfo;

{% endhighlight %}

{% endtabs %}

![LabelTemplate support for adornments in WPF Chart](adornments_images/wpf-chart-label-template.png)

## Label Format

[`SegmentLabelFormat`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SegmentLabelFormat) property allows you to provide formatting for the labels.

The following code example demonstrates the y value having three decimal digits.

{% tabs %}

{% highlight xaml %}

        <syncfusion:ChartAdornmentInfo ShowLabel="True" SegmentLabelFormat="#.000" AdornmentsPosition="Top">
        </syncfusion:ChartAdornmentInfo>

{% endhighlight %}

{% highlight c# %}

        ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
        {
             ShowLabel = true,
            SegmentLabelFormat = "0.000"
        };

{% endhighlight %}

{% endtabs %}

In the following image, you can see the decimal position will be rounded off to two digits by default.

![Adornments label format support in WPF Chart](adornments_images/wpf-chart-label-format.png)

## Label Rotation

[`LabelRotationAngle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_LabelRotationAngle) property is used to define the angle to which the label has to rotate. The following code demonstrates the label rotating angle.

{% tabs %}

{% highlight xaml %}

        <syncfusion:ColumnSeries.AdornmentsInfo>
             <syncfusion:ChartAdornmentInfo LabelPosition="Outer" LabelRotationAngle="45" ShowLabel="True"></syncfusion:ChartAdornmentInfo>
        </syncfusion:ColumnSeries.AdornmentsInfo>
{% endhighlight %}

{% highlight c# %}

            ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
            {
                ShowLabel = true,
                LabelRotationAngle = 45,
                LabelPosition=AdornmentsLabelPosition.Outer          
            };
{% endhighlight %}

{% endtabs %}

![Adornments label rotation support in WPF Chart](adornments_images/wpf-chart-label-rotation.png)

## Connector Line

This feature is used to connect label and data point using a line. It can be enabled for any chart types but this is often used with Pie and Doughnut chart types. You can add connector line for the adornments using [`ShowConnectorLine`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ShowConnectorLine) property. 

The connector line can be customized using the below properies.

* [`ConnectorHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ConnectorHeight)
* [`ConnectorLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ConnectorLineStyle) 
* [`ConnectorRotationAngle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ConnectorRotationAngle)
* [`ConnectorLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ConnectorLineStyle)

The following code example shows the customization options for connector line:

{% tabs %}

{% highlight xaml %}

    <Window.Resources>

        <Style TargetType="Path" x:Key="lineStyle">
            <Setter Property="StrokeDashArray" Value="10,7,5"/>
            <Setter Property="Stroke" Value="Black"/>
        </Style>

    </Window.Resources>

    <Grid>
        <chart:SfChart Width="400" Height="400">
         ...

        <syncfusion:PieSeries Interior="#777777" ItemsSource="{Binding Demands}" XBindingPath="Category" YBindingPath="FloatValue" LabelPosition="OutsideExtended">
                <syncfusion:PieSeries.AdornmentsInfo>
                    <syncfusion:ChartAdornmentInfo ShowLabel="True" ConnectorLineStyle="{StaticResource lineStyle}"ShowConnectorLine="True" LabelPosition="Outer"></syncfusion:ChartAdornmentInfo>
                </syncfusion:PieSeries.AdornmentsInfo>
        </syncfusion:PieSeries>

        ...
        </chart:SfChart>
    </Grid>

{% endhighlight %}

{% highlight c# %}

        PieSeries series = new PieSeries()
            {
                ItemsSource = new ServerViewModel().Performance,
                XBindingPath = "Year",
                YBindingPath = "Plastic",
                LabelPosition = CircularSeriesLabelPosition.OutsideExtended,
                Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))
            };

        ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
            {
                ShowLabel = true,
                ShowConnectorLine = true,
                UseSeriesPalette = true,
                ConnectorLineStyle=this.Resources["lineStyle"] as Style
                LabelPosition =AdornmentsLabelPosition.Outer,
            };
        series.AdornmentsInfo = adornmentInfo;

{% endhighlight %}

{% endtabs %}

![Connector line for adornments support in WPF Chart](adornments_images/wpf-chart-connector-line.png)

**Connector Type**

[`ConnectorType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_ConnectorType) property in AccumulationSeries is used to specify the connector line type such as [`Line`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ConnectorMode.html) or [`Bezier`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ConnectorMode.html). This property is only for AccumulationSeries like PieSeries, DoughnutSeries, PyramidSeries and FunnelSeries.


{% tabs %}

{% highlight xaml %}

        <chart:PieSeries Interior="#777777" ItemsSource="{Binding Performance}" XBindingPath="ServerLoad"
            YBindingPath="Server1" EnableSmartLabels="True" ConnectorType="Bezier" LabelPosition="OutsideExtended">
                <chart:PieSeries.AdornmentsInfo>
                    <chart:ChartAdornmentInfo HorizontalAlignment="Center"
                                              VerticalAlignment="Center"    ShowConnectorLine="True" 
                                              ConnectorHeight="80" ShowLabel="True" />
                </chart:PieSeries.AdornmentsInfo>
        </chart:PieSeries>

{% endhighlight %}

{% highlight c# %}

        PieSeries series = new PieSeries()
            {
                ItemsSource = new ServerViewModel().Performance,
                XBindingPath = "Year",
                YBindingPath = "Plastic",
                EnableSmartLabels = true,
                ExplodeAll = true,
                ExplodeRadius = 3,
                ConnectorType=ConnectorMode.Bezier,
                LabelPosition = CircularSeriesLabelPosition.OutsideExtended,
                Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))
            };

        ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
            {
                ShowLabel = true,
                ShowConnectorLine = true,
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center,
                ConnectorHeight= 80
            };

    {% endhighlight %}

{% endtabs %}

 **Line** 
 
 ![Connector Line in WPF Chart](adornments_images/wpf-chart-line.png) 

 **Bezier**
 
  ![Bezier in WPF Chart](adornments_images/wpf-chart-bezier.png)

   **Straight Line**

![Connector line with StraightLine type in WPF Chart](Adornments_images/wpf-chart-straight-line.png)

## Applying Series Brush

[`UseSeriesPalette`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_UseSeriesPalette) property is used to set the interior of the series to the adornment background. 

>N For Accumulation like Pie, Doughnut, Funnel and Pyramid the segment interior color will be reflected in adornment background.

{% tabs %}

{% highlight xaml %}

        <syncfusion:ChartAdornmentInfo ShowLabel="True" UseSeriesPalette="True">

        </syncfusion:ChartAdornmentInfo>

{% endhighlight %}

{% highlight c# %}

        ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
        {
            ShowLabel = true,
            UseSeriesPalette = true
        };

{% endhighlight %}

{% endtabs %}

## Smart Labels

When you have more datapoints in Pie or Doughnut series, the adornment labels might get overlap with each other. SfChart provides built-in support to avoid these overlapping by using [`EnableSmartLabels`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_EnableSmartLabels) property.

The following code example demonstrates the EnableSmartLabels property:

{% tabs %}

{% highlight xaml %}

            <chart:PieSeries Interior="#777777" ItemsSource="{Binding CategoricalData}" ConnectorType="Bezier" XBindingPath="Year"
            YBindingPath="Plastic" EnableSmartLabels="True" LabelPosition="OutsideExtended" ExplodeAll="True" ExplodeRadius="3">
                <chart:PieSeries.AdornmentsInfo>
                    <chart:ChartAdornmentInfo ShowLabel="True" HorizontalAlignment="Center" VerticalAlignment="Center" ShowConnectorLine="True"></chart:ChartAdornmentInfo>
                </chart:PieSeries.AdornmentsInfo>
            </chart:PieSeries>

{% endhighlight %}

{% highlight c# %}

            PieSeries series = new PieSeries()
            {
                ItemsSource = new ViewModel().Tax,
                XBindingPath = "Year",
                YBindingPath = "Plastic",
                EnableSmartLabels = true,
                ExplodeAll = true,
                ExplodeRadius = 3,
                Palette = ChartColorPalette.Custom,
                LabelPosition=CircularSeriesLabelPosition.OutsideExtended,
                Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))
            };

            ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
            {
                ShowLabel = true,
                ShowConnectorLine = true,
                UseSeriesPalette = true,
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center
            };
            series.AdornmentsInfo = adornmentInfo;

{% endhighlight %}

{% endtabs %}

![Smart labels for adornments in WPF Chart](adornments_images/wpf-chart-smart-label.png)

N> For circular series, the adornment position can be changed to [`Inside`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html), [`Outside`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html) or [`OutsideExtended`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html) using the [`LabelPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_LabelPosition) property.
