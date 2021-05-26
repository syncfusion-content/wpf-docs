---
layout: post
title: Data Marker in WPF SfChart3D control | Syncfusion
description: Learn about Data Marker support in Syncfusion Essential Studio WPF SfChart3D control, its elements and more.
platform: wpf
control: SfChart3D
 documentation: ug
---

# Data Marker in WPF SfChart3D

Data Marker is used to mark the data points with built-in available shapes.

## Define Data Marker

To enable the marker in adornments you have to set the [`ShowMarker`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ShowMarker) property as True. By default, there is no symbol displayed, you have to add the desired symbol using Symbol property.

The following code example demonstrates the column series with [`Diamond`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartSymbol.html) symbol:


{% tabs %}

{% highlight xaml %}

        <chart:ColumnSeries3D ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">
            <chart:ColumnSeries3D.AdornmentsInfo>
                   <chart:ChartAdornmentInfo3D SymbolStroke="White" Symbol="Diamond" 
                        UseSeriesPalette="True" ShowMarker="True"></chart:ChartAdornmentInfo3D>
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
                SymbolInterior = new SolidColorBrush(Colors.White),
                Symbol = ChartSymbol.Diamond,
                UseSeriesPalette=true
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Symbol support in WPF Chart](Adornments-Images/Adornment_Marker.png)

### Customization of Symbol

SfChart3D provides support more customization for symbol in adornments.

* [`SymbolHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SymbolHeight) - used to change the height of the symbol.
* [`SymbolWidth`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SymbolWidth) - used to change the width of the symbol.
* [`SymbolInterior`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SymbolInterior) - used to change the color of symbol.
* [`SymbolStroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SymbolStroke) - used to change the stroke color of symbol.
* [`SymbolTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SymbolTemplate) - used to customize the appearance of symbol.

The following code example demonstrates the basic customization of symbol size and appearance.

{% tabs %}

{% highlight xaml %}

        <chart:LineSeries3D ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">
            <chart:LineSeries3D.AdornmentsInfo>
                <chart:ChartAdornmentInfo3D AdornmentsPosition="Top" ShowMarker="True" SymbolHeight="15" SymbolWidth="15" 
                          SymbolInterior="Brown" SymbolStroke="DarkGray" Symbol="Triangle" />
            </chart:LineSeries3D.AdornmentsInfo>
        </chart:LineSeries3D>  

{% endhighlight %}

{% highlight c# %}

        LineSeries3D series = new LineSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic"
            };

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowMarker = true,
                SymbolInterior = new SolidColorBrush(Colors.Brown),
                SymbolStroke=new SolidColorBrush(Colors.White),
                Symbol = ChartSymbol.Triangle,
                AdornmentsPosition = AdornmentsPosition.Top,
                SymbolHeight = 15,
                SymbolWidth = 15,
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![ Custom Symbol in Adornment](Adornments-Images/SymblBasic.png) 

**Symbol Template**

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

![ Custom Symbol in Adornment](Adornments-Images/SymbolCustom.png) 

