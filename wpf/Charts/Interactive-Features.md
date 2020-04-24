---
layout: post
title: Syncfusion InteractiveFeatures.
description: How to show the functionality of WPF Chart with available interaction options such as zooming, selecting, and tracking the data points.
platform: wpf
control: SfChart
documentation: ug
---

# Interactive features

SfChart provides interactive features such as tracking data points and resizing the scrollbar.

The following interactive features are supported in SfChart:

* Visual Data Editing
* Resizing Scrollbar
* CrossHair

## Visual data editing

SfChart has a feature that allows you to edit an entire series or a single data point at run time by dragging the single point or the series as a whole.

### Segment dragging

Segment Dragging defines the dragging a particular point or segment based on the series type. The segment dragging can be enabled using the [`EnableSegmentDragging`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~EnableSegmentDragging.html#) property to true.

**Line Series**

{% tabs %}

{% highlight xml %}

<syncfusion:LineSeries Label="2010" EnableSegmentDragging="True"

XBindingPath="Demand"   Interior="#777777"

ItemsSource="{Binding Demands}"                                   

YBindingPath="Year2010">

</syncfusion:LineSeries>

{% endhighlight %}

{% highlight c# %}

LineSeries series = new LineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

chart.Series.Add(series)

{% endhighlight %}

{% endtabs %}

![Segment dragging support in WPF Chart](Interactive-Features_images/Interactive-Features_img19.jpg)


**Column Series**

{% tabs %}

{% highlight xml %}

<syncfusion:ColumnSeries Label="2010" EnableDragTooltip="True" EnableSegmentDragging="True"

XBindingPath="Demand"   Interior="#777777"

ItemsSource="{Binding Demands}"                                   

YBindingPath="Year2010">

</syncfusion:ColumnSeries>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    EnableDragTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

chart.Series.Add(series)

{% endhighlight %}

{% endtabs %}

![Segment dragging support in WPF Chart](Interactive-Features_images/Interactive-Features_img20.jpg)

**Scatter Series**

This series supports dragging in both the x and y co-ordinates. The dragging co-ordinates can be set by using the enum property [`DragDirection`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ScatterSeries~DragDirection.html).

{% tabs %}

{% highlight xml %}

<syncfusion:ScatterSeries ItemsSource="{Binding Data}" XBindingPath="Index" 

                          YBindingPath="Value"  Interior="#777777"

                          EnableSegmentDragging="True" DragDirection="XY" >

 </syncfusion:ScatterSeries>

{% endhighlight %}

{% highlight c# %}

ScatterSeries series = new ScatterSeries()
            
{
                
ItemsSource = new ViewModel().Data,
                
XBindingPath = "Index",
                
YBindingPath = "Value",
                
Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),
                
EnableSegmentDragging = true,

DragDirection = DragType.XY
            
};

chart.Series.Add(series)

{% endhighlight %}

{% endtabs %}

![Segment dragging support in WPF Chart](Interactive-Features_images/Interactive-Features_img55.jpg)

N> By default, the DragDirection of the scatter series is XY.

### Series dragging

SfChart provides support to drag the LineSeries and SplineSeries. This allows the series to move to a new position by dragging. To enable the series dragging, you have to set [`EnableSeriesDragging`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySeriesDraggingBase~EnableSeriesDragging.html#) property to true.

The following code snippet explains the series dragging feature in LineSeries.

{% tabs %}

{% highlight xaml %}

<syncfusion:LineSeries Label="2010" EnableDragTooltip="True" EnableSeriesDragging="True"

XBindingPath="Demand"   Interior="#777777" ItemsSource="{Binding Demands}"

YBindingPath="Year2010"/>

{% endhighlight %}

{% highlight c# %}

LineSeries series = new LineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSeriesDragging = true,

    EnableDragTooltip = true ,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Segment dragging support in WPF Chart](Interactive-Features_images/Interactive-Features_img21.jpeg)


N>In line and Spline Series, if segment and series dragging is enabled, the series dragging is having higher priority over segment dragging.

### ToolTip for dragging

While the series or segment is dragged by default you can view the tooltip showing the new y value. To disable the tooltip while dragging you have to set the [`EnableDragToolTip`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~EnableDragTooltip.html) as false.

{% tabs %}

{% highlight xml %}

<syncfusion:LineSeries Label="2010"  EnableSegmentDragging="True" EnableDragTooltip="False"

XBindingPath="Demand"   Interior="#777777"

Focusable="False"

ItemsSource="{Binding Demands}"                                   

</syncfusion:LineSeries>

{% endhighlight %}

{% highlight c# %}

LineSeries series = new LineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSeriesDragging = true,

    EnableDragTooltip = true ,

    Focusable = false,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

chart.Series.Add(series);


{% endhighlight %}

{% endtabs %}

![Adding tooltip for dragging in WPF Chart](Interactive-Features_images/Interactive-Features_img22.jpeg)


**Drag Tooltip Template**

[`DragTooltipTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~DragTooltipTemplate.html#)  property allows you to customize the default appearance of the tooltip while dragging.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <DataTemplate x:Key="tooltipTemplate">

            <Border CornerRadius="4" BorderBrush="Black"
                            
                    BorderThickness="1" Background="CadetBlue" 
                    
                    Margin="0,0,0,15">

                <TextBlock  FontSize="12" Text="{Binding NewValue}" 
                                    
                            Width="35" Foreground="White" Margin="2">
                
                </TextBlock>

            </Border>

        </DataTemplate>

    </syncfusion:SfChart.Resources>

    <syncfusion:LineSeries Label="2010" EnableSegmentDragging="True" 
                                   
                           Interior="#777777"
                                   
                           Focusable="False" 

                           XBindingPath="Demand" 
                                   
                           ItemsSource="{Binding Demands}"          
                                   
                           YBindingPath="Year2010"
                                   
                           DragTooltipTemplate="{StaticResource tooltipTemplate }">

    </syncfusion:LineSeries>
            
</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    Focusable = false,

    EnableSegmentDragging = true,

    DragTooltipTemplate = chart.Resources["tooltipTemplate"] as DataTemplate,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Customizing tooltip while dragging in WPF Chart](Interactive-Features_images/Interactive-Features_img23.jpg)

**Drag Tooltip Style**

The dragging tooltip can be customized by using the [`DragTooltipStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~DragTooltipStyle.html) property of the series.

The following are the API’s in `ChartDragTooltipStyle`.

[`FontFamily`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle~FontFamily.html) – Gets or sets the font family for dragging tooltip text.

[`FontSize`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle~FontSize.html) – Gets or sets the font size for dragging tooltip text.

[`FontStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle~FontStyle.html) – Gets or sets the font style for dragging tooltip text.

[`Foreground`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle~Foreground.html) – Gets or sets the brush for dragging tooltip text.

[`Background`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle~Background.html) – Gets or sets the background brush for dragging tooltip.

{% tabs %}

{% highlight xml %}

<syncfusion:LineSeries.DragTooltipStyle>
                    
<syncfusion:ChartDragTooltipStyle FontFamily="Calibri" FontSize="14" 
                                                     
                                  FontStyle="Italic" Background="DarkGray" 
                                                      
                                  Foreground="Black" />

</syncfusion:LineSeries.DragTooltipStyle>

{% endhighlight %}

{% highlight c# %}

series.DragTooltipStyle = new ChartDragTooltipStyle()
            
{
                
    FontFamily = new FontFamily("Calibri"),
                
    FontSize = 14,
                
    FontStyle = FontStyles.Italic,
                
    Background = new SolidColorBrush(Colors.DarkGray),
                
    Foreground = new SolidColorBrush(Colors.Black)
            
};

{% endhighlight %}

{% endtabs %}

![Customizing tooltip while dragging in WPF Chart](Interactive-Features_images/Interactive-Features_img56.jpg)

**Rounding** **Off** **the** **Dragged** **Value**

To round off the dragged values, you have to set the [`SnapToPoint`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~SnapToPoint.html#) and [`RoundToDecimal`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~RoundToDecimal.html#) properties. The following code snippet explains rounding the dragged y value to 2 decimal digits.

{% tabs %}

{% highlight xml %}

<syncfusion:SplineSeries   EnableSegmentDragging="True"

SnapToPoint="Round" RoundToDecimal="2" YBindingPath = "Year2010"

UpdateSource="True" XBindingPath="Demand"   Interior="#777777"

ItemsSource="{Binding Demands}"                                   

</syncfusion:SplineSeries>

{% endhighlight %}

{% highlight c# %}

SplineSeries series = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    UpdateSource = true ,

    RoundToDecimal = 2,

    SnapToPoint = SnapToPoint.Round,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

### Updating the Dragged Values to the Source

When dragging the series or segment at run time, to update the underlying data based on the values you have to set the [`UpdateSource`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~UpdateSource.html#) property to true as in the following code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SplineSeries   EnableSegmentDragging="True" UpdateSource="True"

XBindingPath="Demand"   Interior="#777777"

ItemsSource="{Binding Demands}"                                   

YBindingPath="Year2010">

</syncfusion:SplineSeries>

{% endhighlight %}

{% highlight c# %}

SplineSeries series = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    UpdateSource = true ,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

### Drag Cancel using KeyModifiers

While you are dragging you can set the KeyModifiers to cancel the drag by setting [`DragCancelKeyModifier`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~DragCancelKeyModifiers.html#) property as in the below code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SplineSeries  

EnableSegmentDragging="True" 

DragCancelKeyModifiers="Alt"  

UpdateSource="True"

XBindingPath="Demand"                                   

ItemsSource="{Binding Demands}"                                   

YBindingPath="Year2010">

</syncfusion:SplineSeries>

{% endhighlight %}

{% highlight c# %}

SplineSeries series = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    DragCancelKeyModifiers = ModifierKeys.Alt,

    UpdateSource = true ,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}


### Events

Series with visual data editing has support for following events:

* [`DragStart`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~DragStart_EV.html#)- Occurs when segment/series drag started. 
* [`DragDelta`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~DragDelta_EV.html#)- Occurs when segment/series dragging.
* [`DragEnd`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~DragEnd_EV.html#)- Occurs when segment/series drag end. 
* [`PreviewDragEnd`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~PreviewDragEnd_EV.html#)- Occurs before drag end triggered. 
* [`SegmentEnter`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase~SegmentEnter_EV.html#)- Occurs when mouse enters in segment. 



## Resizable Scrollbar

The resizable scrollbar is a type of scrollbar that can be resized within the track area by adjusting the scrolling thumbs. In the SfChart, a resizable scrollbar is used for zooming and panning across different chart segments.

### Adding ScrollBar to the Axis

[`EnableScrollBar`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~EnableScrollBar.html#) property allows you to add the scrollbar for the particular axis. The following code snippet illustrates the scrollbar in the primary axis.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" />

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true

};

{% endhighlight %}

{% endtabs %}

![Adding scrollbar to axis in WPF Chart](Interactive-Features_images/Interactive-Features_img41.jpeg)


**Deferred** **Scrolling**

SfChart provides support to suspend the value updates for every thumb values. This can be done using [`DeferredScrolling`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~DeferredScrolling.html#) property in chart axis.The following code snippet demonstrates the deferred scrolling.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" DeferredScrolling="True"/>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true,

    DeferredScrolling = true,

};

{% endhighlight %}

{% endtabs %}

**Resizing** **the** **scrollbar**

SfChart allows you to resize the scrollbar using [`EnableScrollBarResizing`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~EnableScrollBarResizing.html#) property to true. By default the EnableScrollBarResizing property is true. The following code example and image demonstrates scrollbar without resizing option.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" EnableScrollBarResizing="False"/>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true,

    EnableScrollBarResizing = false,

};

{% endhighlight %}

{% endtabs %}

![Resizing the scrollbar in WPF Chart](Interactive-Features_images/Interactive-Features_img42.jpeg)


### Scrollbar for Touch Mode

Scrollbar provides a touch mode style by enabling [`EnableTouchMode`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~EnableTouchMode.html#) property to true as in the below code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" EnableTouchMode="True"/>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true,

    EnableTouchMode = true

};

{% endhighlight %}

{% endtabs %}

![Scrollbar for touch mode support in WPF Chart](Interactive-Features_images/Interactive-Features_img43.jpeg)


**Thumb** **Label**

In touch mode while resizing or dragging the scrollbar to view thumb labels the [`ThumbLabelVisibility`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxis~ThumbLabelVisibility.html#) is set to true.

The following code example demonstrates the thumb labels in scrollbar.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" ThumbLabelVisibility="Visible" EnableTouchMode="True"/>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true,

    EnableTouchMode = true,

    ThumbLabelVisibility = Visibility.Visible

};

{% endhighlight %}

{% endtabs %}

![Thumb label for scrollbar in WPF Chart](Interactive-Features_images/Interactive-Features_img44.jpeg)


**ThumbLabelTemplate**

[`ThumbLabelTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxis~ThumbLabelTemplate.html#) property provides the custom template for the scroll bar thumb

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <DataTemplate x:Key="labelTemplate">

            <Grid>

                <Border BorderBrush="Black" Background="Pink" 
                                
                        BorderThickness="2">

                    <TextBlock Text="{Binding}" FontSize="15"/>

                </Border>

            </Grid>

        </DataTemplate>

    </syncfusion:SfChart.Resources>

    <syncfusion:SfChart.PrimaryAxis>

        <syncfusion:CategoryAxis EnableTouchMode="True" EnableScrollBar="True"
                                         
                                 ThumbLabelVisibility="Visible"
                                         
                                 ThumbLabelTemplate="{StaticResource labelTemplate}"/>

    </syncfusion:SfChart.PrimaryAxis>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableTouchMode = true,

    EnableScrollBar = true,

    ThumbLabelVisibility = Visibility.Visible,

    ThumbLabelTemplate = chart.Resources["labelTemplate"] as DataTemplate

};

{% endhighlight %}

{% endtabs %}

![Label template support for scrollbar thumb in WPF Chart](Interactive-Features_images/Interactive-Features_img45.jpeg)

## CrossHair

ChartCrossHairBehavior is used to view the values at mouse point or touch contact point. By moving these lines horizontally, you can get the X values and by moving these lines vertically, you can get the Y values.

### Adding CrossHairBehavior to SfChart

You can create an instance [`ChartCrossHairBehavior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior.html#) and add it to the Behaviors collection.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior />

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior();

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

To view the axis labels then set the [`ShowTrackBallInfo`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxis~ShowTrackBallInfo.html#) property to true as in the below code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis  ShowTrackBallInfo="True"/>

</syncfusion:SfChart.PrimaryAxis>

<syncfusion:SfChart.SecondaryAxis>

<syncfusion:NumericalAxis  ShowTrackBallInfo="True"/>

</syncfusion:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior();

chart.Behaviors.Add(behavior);

chart.PrimaryAxis = new CategoryAxis()
{

    ShowTrackBallInfo = true

};

chart.SecondaryAxis = new NumericalAxis()
{

    ShowTrackBallInfo = true

};

{% endhighlight %}

{% endtabs %}

![Cross hair support in WPF Chart](Interactive-Features_images/Interactive-Features_img46.jpeg)


Cross hair is composed of the following parts:

1. Vertical and horizontal line

2. Axis Labels

### Vertical and Horizontal Line

If you add [`ChartCrossHairBehavior`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior.html#) to chart you can see horizontal and vertical lines.The horizontal and vertical lines can be customized using [`HorizontalLineStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior~HorizontalLineStyle.html#) and [`VerticalLineStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior~VerticalLineStyle.html#) properties.

**HorizontalLineStyle**

The following code snippet demonstrates the line style for horizontal line in cross hair.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <Style TargetType="Line" x:Key="lineStyle">

            <Setter Property="Stroke" Value="Green"></Setter>

            <Setter Property="StrokeThickness" Value="1"></Setter>

        </Style>
                
    </syncfusion:SfChart.Resources>

    <syncfusion:SfChart.Behaviors>

        <syncfusion:ChartCrossHairBehavior HorizontalLineStyle="{StaticResource lineStyle}"/>

    </syncfusion:SfChart.Behaviors>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior crosshair = new ChartCrossHairBehavior()
{

    HorizontalLineStyle = chart.Resources["lineStyle"] as Style

};

chart.Behaviors.Add(crosshair);

{% endhighlight %}

{% endtabs %}

![Cross hair line style in WPF Chart](Interactive-Features_images/Interactive-Features_img47.jpeg)


**VerticalLineStyle**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <Style TargetType="Line" x:Key="lineStyle">

            <Setter Property="StrokeDashArray" Value="10,5"/>

            <Setter Property="Stroke" Value="Red"/>

             <Setter Property="StrokeThickness" Value="1"/>

        </Style>
                
    </syncfusion:SfChart.Resources>

     <syncfusion:SfChart.Behaviors>

                <syncfusion:ChartCrossHairBehavior VerticalLineStyle="{StaticResource lineStyle}"/>

    </syncfusion:SfChart.Behaviors>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior crosshair = new ChartCrossHairBehavior()
{

    VerticalLineStyle = chart.Resources["lineStyle"] as Style

};

chart.Behaviors.Add(crosshair);

{% endhighlight %}

{% endtabs %}

![Cross hair line style in WPF Chart](Interactive-Features_images/Interactive-Features_img48.jpeg)


### Horizontal axis label

The vertical line in contact with the x axes shows axis label. The horizontal axis label can be aligned using [`HorizontalAxisLabelAlignment`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior~HorizontalAxisLabelAlignment.html#) property.

Axis Label can be aligned by Near, Far, Center, Auto and None Options.

* [`Auto`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAlignment.html) – Axis label is aligned in Near/Far positions based on the movement of vertical line.

* [`Far`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAlignment.html) - Axis label is positioned far from the position of vertical line in cross hair.

* [`Near`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAlignment.html) - Axis label is near to the position of trackball.

* [`Center`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAlignment.html) - Axis label is aligned to the center of the vertical line. By default the axis label will positioned in center.

The following image demonstrates the horizontal axis label positioned center to the vertical line.

![Axis label alignment support for cross hair in WPF Chart](Interactive-Features_images/Interactive-Features_img49.jpeg)


**Far**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior HorizontalAxisLabelAlignment="Far ">

</syncfusion:ChartCrossHairBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior()
{

    HorizontalAxisLabelAlignment = ChartAlignment.Far

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Axis label alignment support for cross hair in WPF Chart](Interactive-Features_images/Interactive-Features_img50.jpeg)


**Near**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior HorizontalAxisLabelAlignment="Near ">

</syncfusion:ChartCrossHairBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior()
{

    HorizontalAxisLabelAlignment = ChartAlignment.Near

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Axis label alignment support for cross hair in WPF Chart](Interactive-Features_images/Interactive-Features_img51.jpeg)


### Vertical axis label

Vertical axis label is displayed when the horizontal line in contact with x axis.The label can be aligned using [`VerticalAxisLabelAlignment`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior~VerticalAxisLabelAlignment.html#) property.

Axis Label can be aligned by Near, Far, Center, Auto, and None Options.

The following image demonstrates the horizontal axis label positioned center to the vertical line.

![Axis label alignment support for cross hair in WPF Chart](Interactive-Features_images/Interactive-Features_img52.jpeg)


**Near**

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior VerticalAxisLabelAlignment="Near">

</syncfusion:ChartCrossHairBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior()
{

    VerticalAxisLabelAlignment = ChartAlignment.Near

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Axis label alignment support for cross hair in WPF Chart](Interactive-Features_images/Interactive-Features_img53.jpeg)

**Far**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior VerticalAxisLabelAlignment="Far"  >

</syncfusion:ChartCrossHairBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior()
{

    VerticalAxisLabelAlignment = ChartAlignment.Far

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Axis label alignment support for cross hair in WPF Chart](Interactive-Features_images/Interactive-Features_img54.jpeg)

**Customization of Crosshair axis labels**

The default appearance of the crosshair axis labels can be customized by using the [`CrosshairLabelTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxis~CrosshairLabelTemplateProperty.html) property of chart axis. It can be set as shown in the following code example.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>
    
    <chart:CategoryAxis ShowTrackBallInfo="True">
        
        <chart:CategoryAxis.CrosshairLabelTemplate>
                
            <DataTemplate>
                            
                 <Border Background="Orange" 
                                   
                         CornerRadius="4" 
                                    
                          BorderThickness="1" BorderBrush="Black">

                 <TextBlock Margin="2" Text="{Binding ValueX}"/>
                            
                </Border>
                
            </DataTemplate>
             
        </chart:CategoryAxis.CrosshairLabelTemplate>
                
    </chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>
                
       <chart:NumericalAxis ShowTrackBallInfo="True">
                    
            <chart:NumericalAxis.CrosshairLabelTemplate>
                        
                <DataTemplate>
                            
                    <Border Background="Orange" 
                                   
                            CornerRadius="4" 
                            
                             BorderThickness="1" 
                             
                             BorderBrush="Black">

                    <TextBlock  Margin="2" Text="{Binding ValueY}"/>
                   
                    </Border>
                        
                </DataTemplate>
            
            </chart:NumericalAxis.CrosshairLabelTemplate>
       
       </chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

<chart:SfChart.Behaviors>
       
    <chart:ChartCrossHairBehavior />
    
</chart:SfChart.Behaviors>

{% endhighlight %}

{% endtabs %}

![Crosshair axis labels customization in WPF](Interactive-Features_images/crossHairTemplate.png)