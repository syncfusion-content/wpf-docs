---
layout: post
title: Positioning Data Markers in WPF SfChart3D control | Syncfusion
description: Learn about Positioning Data Markers support in Syncfusion WPF SfChart3D control and more.
platform: wpf
control: SfChart3D
documentation: ug
---

# Positioning Data Markers in WPF SfChart3D

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
                    <chart:ChartAdornmentInfo3D ShowMarker="True" SymbolHeight="10" SymbolWidth="10" Symbol="Diamond" AdornmentsPosition="TopAndBottom" SymbolInterior="#FF64B5F6"></chart:ChartAdornmentInfo3D>
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
                AdornmentsPosition=AdornmentsPosition.TopAndBottom,
                SymbolHeight=10,
                SymbolWidth=10
            };

        series.AdornmentsInfo = adornmentInfo;
        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![TopAndBottom Position in WPF Chart](Adornments-Images/Adorn_TopAndBottom.png)

## Label Position

SfChart3D provides additional customization option to position the adornments smartly based on series types using [`LabelPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_LabelPosition) property.

The following section shows few examples for this LabelPosition behavior with respect to the series.

**Auto**

The [`Auto`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AdornmentsLabelPosition.html) position of Labels with respect to [`ColumnSeries3D`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ColumnSeries3D.html) and [`LineSeries3D`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineSeries3D.html#).

 {% tabs %}

{% highlight xaml %}

         <chart:ChartAdornmentInfo3D  UseSeriesPalette="True" LabelPosition="Auto"
            ShowLabel="True" BorderBrush="White" BorderThickness="1"></chart:ChartAdornmentInfo3D>

{% endhighlight %}

{% highlight c# %}

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowMarker = true,
                BorderBrush = new SolidColorBrush(Colors.White),
                LabelPosition=AdornmentsLabelPosition.Auto,
                UseSeriesPalette=true,              
                BorderThickness = new Thickness(1),
            };

{% endhighlight %}

{% endtabs %}

|Column Series|Line Series|
|--|--|
|![Auto Position in WPF Chart](Adornments-Images/Label_Auto_Column.png) |![Auto Position in WPF Chart](Adornments-Images/Label_Auto_Line.png)|

**Inner**

The [`Inner`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AdornmentsLabelPosition.html) position of Labels with respect to [`ColumnSeries3D`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ColumnSeries3D.html) and [`LineSeries3D`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineSeries3D.html#).

 {% tabs %}

{% highlight xaml %}

         <chart:ChartAdornmentInfo3D  UseSeriesPalette="True" LabelPosition="Inner"
            ShowLabel="True" BorderBrush="White" BorderThickness="1"></chart:ChartAdornmentInfo3D>

{% endhighlight %}

{% highlight c# %}

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowMarker = true,
                BorderBrush = new SolidColorBrush(Colors.White),
                LabelPosition=AdornmentsLabelPosition.Inner,
                UseSeriesPalette=true,              
                BorderThickness = new Thickness(1),
            };

{% endhighlight %}

{% endtabs %}

|Column Series|Line Series|
|--|--|
|![Inner Position in WPF Chart](Adornments-Images/Label_Inner_Column.png)| ![Inner Position in WPF Chart](Adornments-Images/Label_Inner_Line.png)|

**Outer**

The [`Outer`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AdornmentsLabelPosition.html) position of Labels with respect to [`ColumnSeries3D`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ColumnSeries3D.html) and [`LineSeries3D`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineSeries3D.html#).

 {% tabs %}

{% highlight xaml %}

         <chart:ChartAdornmentInfo3D  UseSeriesPalette="True" LabelPosition="Outer"
            ShowLabel="True" BorderBrush="White" BorderThickness="1"></chart:ChartAdornmentInfo3D>

{% endhighlight %}

{% highlight c# %}

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowMarker = true,
                BorderBrush = new SolidColorBrush(Colors.White),
                LabelPosition=AdornmentsLabelPosition.Outer,
                UseSeriesPalette=true,              
                BorderThickness = new Thickness(1),
            };

{% endhighlight %}

{% endtabs %}

|Column Series|Line Series|
|--|--|
|![Outer Position in WPF Chart](Adornments-Images/Label_Outer_Column.png) | ![Auto Position in WPF Chart](Adornments-Images/Label_Outer_Line.png)|

**Center**

The [`Center`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AdornmentsLabelPosition.html) position of Labels with respect to [`ColumnSeries3D`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ColumnSeries3D.html) and [`LineSeries3D`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineSeries3D.html#).

 {% tabs %}

{% highlight xaml %}

         <chart:ChartAdornmentInfo3D  UseSeriesPalette="True" LabelPosition="Center"
            ShowLabel="True" BorderBrush="White" BorderThickness="1"></chart:ChartAdornmentInfo3D>

{% endhighlight %}

{% highlight c# %}

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowMarker = true,
                BorderBrush = new SolidColorBrush(Colors.White),
                LabelPosition=AdornmentsLabelPosition.Center,
                UseSeriesPalette=true,              
                BorderThickness = new Thickness(1),
            };

{% endhighlight %}

{% endtabs %}

|Column Series|Line Series|
|--|--|
|![Auto Position in WPF Chart](Adornments-Images/Label_Center_Column.png)| ![Auto Position in WPF Chart](Adornments-Images/Label_Center_Line.png)|

