---
layout: post
title: Interactivity in WPF Range Selector control | Syncfusion
description: Learn here all about Interactivity support in Syncfusion WPF Range Selector (SfDateTimeRangeNavigator) control and more.
platform: wpf
control: SfDateTimeRangeNavigator
 documentation: ug
---

# Interactivity in WPF Range Selector (SfDateTimeRangeNavigator)

The date-time range navigator control provides interactive features such as zooming and panning. This control has a resizable scrollbar, which is used to zoom in large amount of data and navigate to particular timespan by moving the scroll bar.

The ZoomPosition and ZoomFactor properties of the chart axis can be bound with the SfDateTimeRangeNavigator.

## Properties

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
{{'[`ZoomPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfRangeNavigator_ZoomPosition)'| markdownify }}</td><td>
Represents the zoom position of the selected range.</td></tr>
<tr>
<td>
{{'[`ZoomFactor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfRangeNavigator_ZoomFactor)'| markdownify }}</td><td>
Represents the zoom factor of the selected range.</td></tr>
<tr>
<td>
{{'[`SelectedData`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_SelectedData)'| markdownify }}</td><td>
Gets the selected data between selected ranges.</td></tr>
<tr>
<td>
{{'[`ShowGridLines`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_ShowGridLines)'| markdownify }}</td><td>
Shows the gridlines inside the content.</td></tr>
<tr>
<td>
{{'[`Minimum`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_Minimum)'| markdownify }}</td><td>
Sets the minimum or starting range of the navigator.</td></tr>
<tr>
<td>
{{'[`Maximum`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_Maximum)'| markdownify }}</td><td>
Sets the maximum or ending range of the navigator.</td></tr>
<tr>
<td>
{{'[`ViewRangeStart`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfRangeNavigator_ViewRangeStart)'| markdownify }}</td><td>
Gets the start value of the selected range.</td></tr>
<tr>
<td>
{{'[`ViewRangeEnd`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfRangeNavigator_ViewRangeEnd)'| markdownify }}</td><td>
Gets the end value of the selected range.</td></tr>
<tr>
<td>
{{'[`EnableDeferredUpdate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_EnableDeferredUpdate)'| markdownify }}</td><td>
Enables deferred scrolling and panning.</td></tr>
<tr>
<td>
{{'[`DeferredUpdateDelay`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_DeferredUpdateDelay)'| markdownify }}</td><td>
Gets or sets the delay value when the EnableDeferredUpdate is enabled.</td></tr>
</table>


## Events

<table>
<tr>
<th>
Event</th><th>
Parameters</th><th>
Description</th></tr>
<tr>
<td>
{{'[`ValueChanged`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfRangeNavigator.html)'| markdownify }}</td><td>
ValueChanged (Object sender, EventArgs e)</td><td>
This event is triggered when the position of the scrollbar is changed</td></tr>
<tr>
<td>
`LowerBarLabelsCreated`<br/><br/></td><td>
LowerBarLabelsCreated(Object sender, LowerBarLabelsCreatedEventArgs e)<br/><br/></td><td>
This event is triggered when the lower bar labels gets created.<br/><br/></td></tr>
<tr>
<td>
`UpperBarLabelsCreated`<br/><br/></td><td>
UpperBarLabelsCreated(Object sender, UpperBarLabelsCreatedEventArgs e)<br/><br/></td><td>
This event is triggered when the upper bar labels gets created.<br/><br/></td></tr>
</table>

{% tabs %}

{% highlight xaml %}

<chart:SfChart x:Name="financialChart">            

  <chart:SfChart.PrimaryAxis>

         <chart:CategoryAxis Name="axis1" ZoomPosition="{Binding ElementName=RangeNavigator, Path=ZoomPosition, Mode=TwoWay}" 
         
                             ZoomFactor="{Binding ElementName=RangeNavigator, Path=ZoomFactor, Mode=TwoWay}"

                             Header="Date" LabelFormat="MMM/dd" 

                             LabelTemplate="{StaticResource labelTemplate}" />                

  </chart:SfChart.PrimaryAxis>            

  <chart:SfChart.SecondaryAxis>                

                  <chart:NumericalAxis  />  

</chart:SfChart.SecondaryAxis>            

<chart:CandleSeries Name="series" ItemsSource="{Binding StockPriceDetails}" XBindingPath="_Date"  High="High" Open="Open" Close="Close" Low="Low"  Label="Candleseries">            

</chart:CandleSeries>        

</chart:SfChart>        

<chart:SfDateTimeRangeNavigator x:Name="RangeNavigator" ItemsSource="{Binding StockPriceDetails}" XBindingPath="_Date" >                

	<chart:SfDateTimeRangeNavigator.Content>                   

		<chart:SfLineSparkline ItemsSource="{Binding StockPriceDetails}"   YBindingPath="High" > 

        </chart:SfLineSparkline>                

	</chart:SfDateTimeRangeNavigator.Content>            

</chart:SfDateTimeRangeNavigator>

{% endhighlight  %}

{% highlight c# %}

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    VerticalAlignment = VerticalAlignment.Top

};

SfLineSparkline sparkline = new SfLineSparkline()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    YBindingPath = "High"

};

rangeNavigator.Content = sparkline;

Grid.SetColumn(rangeNavigator, 1);

SfChart chart = new SfChart();

chart.PrimaryAxis = new CategoryAxis()
{

    PlotOffset = 25,

    Header = "Date",

    LabelFormat = "MMM/dd",

    ZoomPosition = rangeNavigator.ZoomPosition,

    ZoomFactor = rangeNavigator.ZoomFactor

};

chart.SecondaryAxis = new NumericalAxis();

CandleSeries candleSeries=new CandleSeries ()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    High ="High", Low = "Low",

    Open ="Open", Close ="Close",

    XBindingPath ="Date",

    Label ="CandleSeries"

};

chart.Series.Add(candleSeries);

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates selecting one quarter of data.

![Zooming support in WPF SfDateTimeRangeNavigator](Interactivity_images/Interactivity_img1.png)

The following screenshot illustrates the control after zooming into weeks of data from 6 months of data.

![Zooming support in WPF SfDateTimeRangeNavigator](Interactivity_images/Interactivity_img2.png)


## Thumb style customization

SfDateTimeRangeNavigator [LeftThumbStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_LeftThumbStyle) and [RightThumbStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_RightThumbStyle) can be customized by using the following properties:

### SymbolTemplate

[SymbolTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ThumbStyle.html#Syncfusion_UI_Xaml_Charts_ThumbStyle_SymbolTemplate) can be used for gets or sets the data template for the symbol.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfDateTimeRangeNavigator x:Name="navigator">

    <syncfusion:SfRangeNavigator.Resources>

        <DataTemplate x:Key="symbolTemplate">

            <Grid>

                <Ellipse Height="40" Width="40"  Fill="Green" Stroke="Black"
                                 
                                 VerticalAlignment="Center" StrokeThickness="2"/>

                <Ellipse Height="7" Width="7" Fill="White" 

                         VerticalAlignment="Center"/>
                        
            </Grid>

        </DataTemplate>

    </syncfusion:SfRangeNavigator.Resources>

    <syncfusion:SfDateTimeRangeNavigator.RightThumbStyle>

        <syncfusion:ThumbStyle SymbolTemplate="{StaticResource symbolTemplate}"/>

    </syncfusion:SfDateTimeRangeNavigator.RightThumbStyle>

</syncfusion:SfDateTimeRangeNavigator>

{% endhighlight %}

{% highlight c# %}

ThumbStyle thumbStyle = new ThumbStyle()
{

    SymbolTemplate = grid.Resources["symbolTemplate"] as DataTemplate

};

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    RightThumbStyle = thumbStyle

};

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates the control after customizing the right thumb.

![Thumb customization support in WPF SfDateTimeRangeNavigator](Interactivity_images/Interactivity_img3.png)

### LineStyle

[`LineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ThumbStyle.html#Syncfusion_UI_Xaml_Charts_ThumbStyle_LineStyle) can be used for gets or sets the style for the thumb line.

{% tabs %}

{% highlight xaml %}

<Grid x:Name="grid">

<Grid.Resources>

    <Style TargetType="Line" x:Key="lineStyle1">

        <Setter Property="Stroke" Value="Red"></Setter>

        <Setter Property="StrokeThickness" Value="3"></Setter>

        <Setter Property="StrokeDashArray" Value="2,1"></Setter>

    </Style>

    <Style TargetType="Line" x:Key="lineStyle2">

        <Setter Property="Stroke" Value="Red"></Setter>

        <Setter Property="StrokeThickness" Value="3"></Setter>

        <Setter Property="StrokeDashArray" Value="2,1"></Setter>

    </Style>

</Grid.Resources>

<syncfusion:SfDateTimeRangeNavigator>

    <syncfusion:SfDateTimeRangeNavigator.LeftThumbStyle>

        <syncfusion:ThumbStyle LineStyle="{StaticResource lineStyle1}"/>

     </syncfusion:SfDateTimeRangeNavigator.LeftThumbStyle>

    <syncfusion:SfDateTimeRangeNavigator.RightThumbStyle>

        <syncfusion:ThumbStyle LineStyle="{StaticResource lineStyle2}"/>

    </syncfusion:SfDateTimeRangeNavigator.RightThumbStyle>

</syncfusion:SfDateTimeRangeNavigator>

</Grid>

{% endhighlight %}

{% highlight c# %}

ThumbStyle thumbLineStyle1 = new ThumbStyle()
{

    LineStyle = grid.Resources["lineStyle1"] as DataTemplate

};

ThumbStyle thumbLineStyle2 = new ThumbStyle()
{

    LineStyle = grid.Resources["lineStyle2"] as DataTemplate

};

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    LineStyle = thumbLineStyle1,

    LineStyle = thumbLineStyle2

};

{% endhighlight %}

{% endtabs %}

![LineThumbStyle](Interactivity_images/LineStyle.jpeg)


## Higher and lower bars customization

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
{{'[`HigherBarGridLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_HigherBarGridLineStyle)'| markdownify }}</td><td>
Defines the style for gridlines of upper labels bar.</td></tr>
<tr>
<td>
{{'[`LowerBarGridLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_LowerBarGridLineStyle)'| markdownify }}</td><td>
Defines the style for gridlines of lower labels bar.</td></tr>
<tr>
<td>
{{'[`HigherBarTickLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_HigherBarTickLineStyle)'| markdownify }}</td><td>
Defines the style for ticklines of upper labels bar.</td></tr>
<tr>
<td>
{{'[`LowerBarTickLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_LowerBarTickLineStyle)'| markdownify }}</td><td>
Defines the style for ticklines of lower labels bar.</td></tr>
</table>
