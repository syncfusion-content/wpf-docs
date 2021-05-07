---
layout: post
title: Data Label in WPF SfChart3D control | Syncfusion
description: Learn about Data Label support in Syncfusion WPF SfChart3D control and more.
platform: wpf
control: SfChart3D
documentation: ug
---

# Data Label in WPF SfChart3D

 Data points can be easily annotated with labels to help improve the readability of data.

## Define Label Content
To enable the marker in adornments you have to set the [`ShowLabel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ShowLabel) property as True. 

 [`SegmentLabelContent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SegmentLabelContent) property allows you to define the value to be displayed as adornment label.

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

|LabelContent|Output|
|--|--|
|[LabelContent.DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LabelContent.html)|![DateTime support in WPF Chart](Adornments-Images/Adorn_DateTime.png)|
|[LabelContent.LabelContentPath](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LabelContent.html)|![LabelContentPath support in WPF Chart](Adornments-Images/Adorn_LabelContent.png)|
|[LabelContent.Percentage](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LabelContent.html) |![Percentage support in WPF Chart](Adornments-Images/Adorn_Percentage.png)|
|[LabelContent.XValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LabelContent.html) |![XValue support in WPF Chart](Adornments-Images/Adorn_Xvalue.png)|
|[LabelContent.YofTot](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LabelContent.html) |![YofTot support in WPF Chart](Adornments-Images/Adorn_YofTop.png)|
|[LabelContent.YValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LabelContent.html) |![YValue support in WPF Chart](Adornments-Images/Adorn_YValue.png)|

## Customizing the label

The following properties are used to customize the adornment label.

* [`BorderBrush`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_BorderBrush) - used to change the border color.
* [`BorderThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_BorderThickness) - used to change the thickness of the border.
* [`Margin`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_Margin) - used to change the margin size for label.
* [`FontStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_FontStyle) -  used to change font family of the label.
* [`FontSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_FontSize) -  used to change font size of the label.
* [`Foreground`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_Foreground) - used to change the color of the label.
* [`FontFamily`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_FontFamily) -  used to change the font family of the label.
* [`Background`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_Background) - used to change the label background color.

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

## Label Rotation

[`LabelRotationAngle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_LabelRotationAngle) property is used to define the angle to which the label has to rotate. The following code demonstrates the label rotating angle.

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

## Label Format

[`SegmentLabelFormat`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_SegmentLabelFormat) property allows you to provide formatting for the labels.


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

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
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


## Connector Line

You can add connector line for the adornments using [`ShowConnectorLine`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ShowConnectorLine) property. Also this connector line can be customized using [`ConnectorHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ConnectorHeight), [`ConnectorLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ConnectorLineStyle) and [`ConnectorRotationAngle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ConnectorRotationAngle) properties.


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

[`ConnectorType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_ConnectorType) property in AccumulationSeries is used to specify the connector line type such as [`Line`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ConnectorMode.html) or [`Bezier`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ConnectorMode.html). This property is only for AccumulationSeries like PieSeries and DoughnutSeries.

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

| Line | Bezier |
|--|--|
| ![Connector Line in WPF Chart](Adornments-Images/Adorn_Line.png)| ![Bezier in WPF Chart](Adornments-Images/Adorn_Bezier.png)|

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

![Connector line style support in WPF Chart](Adornments-Images/ConnectorLine_Customization.png)

## Applying Series Brush

The [`UseSeriesPalette`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_UseSeriesPalette) property is used to apply the series color to background color of data marker labels.

For Accumulation like Pie, Doughnut, Funnel and Pyramid the segment interior color will be reflected in adornment background.

{% tabs %}

{% highlight xaml %}
      
        <chart:ChartAdornmentInfo3D ShowLabel="True" LabelPosition="Outer"
                UseSeriesPalette="True" ></chart:ChartAdornmentInfo3D>

{% endhighlight %}

{% highlight c# %}

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowLabel = true,
                LabelPosition = AdornmentsLabelPosition.Outer,
                UseSeriesPalette=true
            };

{% endhighlight %}

{% endtabs %}

## Smart Labels

When you have more datapoints in Pie or Doughnut series, the adornment labels might get overlap with each other. SfChart3D provides built-in support to avoid these overlapping by using [`EnableSmartLabels`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_EnableSmartLabels) property.

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

![Smart Labels in WPF Chart](Adornments-Images/SmartLabels.png)

N> For circular series, the adornment position can be changed to [`Inside`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html), [`Outside`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html) or [`OutsideExtended`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html) using the [`LabelPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CircularSeriesBase.html#Syncfusion_UI_Xaml_Charts_CircularSeriesBase_LabelPosition) property.
