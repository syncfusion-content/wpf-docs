---
layout: post
title: Zooming and Panning in WPF Charts control | Syncfusion
description: Learn here all about Zooming and Panning support in Syncfusion WPF Charts (SfChart) control and more.
platform: wpf
control: SfChart
documentation: ug
---

# Zooming and Panning in WPF Charts (SfChart)

SfChart allows you to zoom the chart area with the help of the zoom feature. This behavior is mostly used to view the data point in the specific area, when there are a number of data points inside the chart.

Zooming and panning provides you to take a close-up look of the data point plotted in the series

## Enable Zooming and Panning

You can create an instance ChartZoomPanBehavior and add it to the Behaviors collection.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior >                                             

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior();

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}


## Zooming the ChartArea

**Zooming** **by** **setting** **ZoomFactor** **and** **ZoomPosition**

[`ZoomFactor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_ZoomFactor) defines the percentage of visible range from the total range of axis values. [`ZoomPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_ZoomPosition) defines the ranges of values that need to be displayed as a result of [`ZoomFactor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_ZoomFactor). 

The following code example demonstrates the zooming the chart axis by setting zoom position and zoom factor.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis 

ShowGridLines="False"

ZoomFactor="0.3" ZoomPosition="0.1" />

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    ShowGridLines = false,

    ZoomFactor = 0.1,

    ZoomPosition = 0.3

};

{% endhighlight %}

{% endtabs %}

![Zooming support in WPF Chart](Interactive-Features_images/Interactive-Features_img24.jpeg)

**Mouse** **Wheel** **Zooming**

Zooming can be performed by mouse wheel action by setting [`EnableMouseWheelZooming`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnableMouseWheelZooming) property to true.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableMouseWheelZooming="True" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableMouseWheelZooming = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

**Pinch** **Zooming**

If you want to zoom using fingers by touch, then you have to set [`EnablePinchZooming`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnablePinchZooming) property to true as shown in the below code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnablePinchZooming="True" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnablePinchZooming = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

**Zooming** **Relative** **to** **Cursor**

To enable the zooming relative to cursor position you can set [`ZoomRelativeToCursor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ZoomRelativeToCursor) property to true. This support is applicable only for mouse wheel zooming.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior ZoomRelativeToCursor="True" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    ZoomRelativeToCursor = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

**SelectionZooming**

SelectionZooming helps us to zoom a particular area by selecting the region using  rectangle.To enable the selection ,you have to set [`EnableSelectionZooming`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnableSelectionZooming) property to true.

The following code snippet demonstrated selection zooming.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Selection zooming support in WPF Chart](Interactive-Features_images/Interactive-Features_img25.jpeg)


**Customization** **of** **Selection** **Rectangle**

Selection Rectangle can be customized by setting the following properties 

* [`Fill`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_Fill)-Represents the brush filled in selection rectangle. 
* [`Stroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_Stroke)- Represents the outer line color of selection rectangle.
* [`StrokeThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_StrokeThickness)- Represents the selection rectangle outer line thickness. 

The following code example demonstrates the customization of selection rectangle

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" 

Fill="LightBlue" Stroke="Blue" StrokeThickness="2" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true,

    Fill = new SolidColorBrush(Colors.LightBlue),

    Stroke = new SolidColorBrush(Colors.Blue),

    StrokeThickness = 2

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Customizing selection rectangle support in WPF Chart](Interactive-Features_images/Interactive-Features_img26.jpeg)


**Zooming** **Mode**

The zooming can be done both horizontally and vertically. The zooming direction is defined using [`ZoomMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ZoomMode) property.

Zooming along [`X`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomMode.html) axis

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" ZoomMode="X">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true,

    ZoomMode = ZoomMode.X

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Zoom mode support in WPF Chart](Interactive-Features_images/Interactive-Features_img27.jpeg)


Zooming along Y axis

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" ZoomMode="Y">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true,

    ZoomMode = ZoomMode.Y

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Zoom mode support in WPF Chart](Interactive-Features_images/Interactive-Features_img28.jpeg)

**Maximum** **Zoom** **Level**

You can also limit the zooming by setting [`MaximumZoomLevel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_MaximumZoomLevel) property as shown in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" MaximumZoomLevel="100">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true,

    MaximumZoomLevel = 100

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

## Zooming Toolbar

Zooming Toolbar encompassed with buttons for performing actions like Zoom In/Out, Reset, Pan, etc. You can add the zooming toolbar to the chart area by setting [`EnableZoomingToolBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnableZoomingToolBar) property to True.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableZoomingToolBar="True">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableZoomingToolBar = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

The following image depicts the default view of the zooming toolbar.

![Zooming toolbar in WPF Chart](Interactive-Features_images/Interactive-Features_img29.jpeg)


**Positioning** **the** **zooming** **toolbar**

Zooming Toolbar can be positioned using the [`HorizontalPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_HorizontalPosition) and [`VerticalPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_VerticalPosition) properties.The following code demonstrates the positioning of the toolbar.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableZoomingToolBar="True" HorizontalPosition="Left" VerticalPosition="Bottom">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableZoomingToolBar = true,

    HorizontalPosition = HorizontalAlignment.Left,

    VerticalPosition = VerticalAlignment.Bottom

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Positioning the zooming toolbar in WPF Chart](Interactive-Features_images/Interactive-Features_img30.jpeg)


**Customization** **of** **Zooming** **Toolbar**

Zooming Toolbar can be customized using the following APIs:

* [`ToolBarBackground`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarBackground)- Represents the zooming toolkit background.
* [`ToolBarItems`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarItems)- Collection value that contains zooming toolkit items. 
* [`ToolBarItemMargin`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarItemMargin)-Represents the margin for the toolbar item.
* [`ToolBarItemWidth`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarItemWidth) -Represents the width of the toolbar item
* [`ToolBarItemHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarItemHeight)-Represents the height of the toolbar item

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableZoomingToolBar="True" ToolBarItemHeight="15" 

ToolBarItemWidth="15" ToolBarBackground="Black" 

ToolBarItems="All" ToolBarItemMargin="10">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableZoomingToolBar = true,

    ToolBarBackground = new SolidColorBrush(Colors.Black),

    ToolBarItemHeight = 15,

    ToolBarItemWidth = 15,

    ToolBarItemMargin = new Thickness(10),

    ToolBarItems = ZoomToolBarItems.All

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Customization of zooming toolbar in WPF Chart](Interactive-Features_images/Interactive-Features_img31.jpeg)


**Orientation** **of** **Zooming** **Toolbar**

Zooming toolbar orientation is horizontal by default.You can change the orientation to vertical by setting 

[`ToolBarOrientation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarOrientation) property to Vertical.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableZoomingToolBar="True" 

ToolBarOrientation="Vertical">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableZoomingToolBar = true,

    ToolBarOrientation = Orientation.Vertical

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Orientation of zooming toolbar in WPF Chart](Interactive-Features_images/Interactive-Features_img32.jpeg)


## Panning the ChartArea

Panning feature allows moving the visible area of the chart when it is zoomed in. To enable panning, you have to set [`EnablePanning`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnablePanning) property to true.

{% tabs %}

{% highlight xml %}
<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableMouseWheelZooming="True" EnablePanning="True">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableMouseWheelZooming = true,

    EnablePanning = true
     
};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

The following image demonstrates the cursor panning in the left direction.

![Panning support in WPF Chart](Interactive-Features_images/Interactive-Features_img33.jpeg)


## Resetting the Zooming/Panning

SfChart provides support to reset to the default view when you double tap the chart area by setting [`ResetOnDoubleTap`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ResetOnDoubleTap) property to true.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior  ResetOnDoubleTap="True">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    ResetOnDoubleTap = true
     
};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}


## Events

The following events are available in SfChart for ChartZoomPanBehavior:

### ZoomChanging

The [`ZoomChanging`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) event occurs when users start zooming the chart. This is a cancelable event. This argument contains the following information.

* [`Axis`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomEventArgs_Axis) - Gets an instance of the axis whose range is changed through zooming. This event is triggered for each axis in the chart.
* [`Cancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomChangingEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomChangingEventArgs_Cancel) - Gets or Sets a value that indicates whether the zooming should be canceled.
* [`CurrentFactor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomEventArgs_CurrentFactor) - Gets the current zoom factor of the axis.
* [`CurrentPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomEventArgs_CurrentPosition) - Gets the current zoom position of the axis.
* [`OldRange`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomEventArgs_OldRange) - Gets the old visible range of the axis.
* [`PreviousFactor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomEventArgs_PreviousFactor) - Gets the previous zoom factor of the axis.
* [`PreviousPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomEventArgs_PreviousPosition) - Gets the previous zoom position of the axis.

### ZoomChanged

The [`ZoomChanged`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) event occurs after the zooming has been completed. This argument contains the following information.

* [`Axis`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomEventArgs_Axis) - Gets an instance of the axis whose range is changed through zooming. This event is triggered for each axis in the chart.
* [`CurrentFactor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomEventArgs_CurrentFactor) - Gets the current zoom factor of the axis.
* [`CurrentPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomEventArgs_CurrentPosition) - Gets the current zoom position of the axis.
* [`OldRange`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomEventArgs_OldRange) - Gets the old visible range of the axis.
* [`NewRange`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomChangedEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomChangedEventArgs_NewRange) - Gets the new visible range of the axis.
* [`PreviousFactor`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomEventArgs_PreviousFactor) - Gets the previous zoom factor of the axis.
* [`PreviousPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ZoomEventArgs_PreviousPosition) - Gets the previous zoom position of the axis.

### SelectionZoomingStart

The [`SelectionZoomingStart`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) event occurs when users start selection zooming. This argument contains the following information.

* [`ZoomRect`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SelectionZoomingEventArgs.html#Syncfusion_UI_Xaml_Charts_SelectionZoomingEventArgs_ZoomRect) - Gets the initial bounds of the selected region.

### SelectionZoomingEnd

The [`SelectionZoomingEnd`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) event occurs after selection zooming ends. This argument contains the following information.

* [`ZoomRect`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SelectionZoomingEventArgs.html#Syncfusion_UI_Xaml_Charts_SelectionZoomingEventArgs_ZoomRect) - Gets the final bounds of the selected region.

### SelectionZoomingDelta

The [`SelectionZoomingDelta`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) event occurs when selecting a region to be zoomed. This is a cancelable event. This argument contains the following information.

* [`ZoomRect`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SelectionZoomingEventArgs.html#Syncfusion_UI_Xaml_Charts_SelectionZoomingEventArgs_ZoomRect) - Gets the final bounds of the selected region.
* [`Cancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SelectionZoomingDeltaEventArgs.html#Syncfusion_UI_Xaml_Charts_SelectionZoomingDeltaEventArgs_Cancel) - Gets or Sets a value that indicates whether the selection zooming should be canceled.

### PanChanging

The [`PanChanging`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) event occurs when users start panning the chart. This is a cancelable event. This argument contains the following information:

* [`Axis`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PanningEventArgs.html#Syncfusion_UI_Xaml_Charts_PanningEventArgs_Axis) - Gets an instance of the axis whose range is changed while panning. This event is triggered for each axis in the chart.
* [`Cancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PanChangingEventArgs.html#Syncfusion_UI_Xaml_Charts_PanChangingEventArgs_Cancel) - Gets or Sets a value that indicates whether the panning should be canceled.
* [`NewZoomPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PanningEventArgs.html#Syncfusion_UI_Xaml_Charts_PanningEventArgs_NewZoomPosition) - Gets a new zoom position of the axis.
* [`OldZoomPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PanChangingEventArgs.html#Syncfusion_UI_Xaml_Charts_PanChangingEventArgs_OldZoomPosition) - Gets the old zoom position of the axis.

### PanChanged

The [`PanChanged`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) event occurs when panning is completed. This argument contains the following information.

* [`Axis`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PanningEventArgs.html#Syncfusion_UI_Xaml_Charts_PanningEventArgs_Axis) - Gets an instance of the axis whose range is changed while panning. This event is triggered for each axis in the chart.
* [`NewZoomPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.PanningEventArgs.html#Syncfusion_UI_Xaml_Charts_PanningEventArgs_NewZoomPosition) - Gets a new zoom position of the axis.
 
### ResetZooming

The [`ResetZooming`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) event occurs when resetting the chart on double tap. This is a cancelable event. This argument contains the following information.

* [`Axis`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ResetZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ResetZoomEventArgs_Axis) - Gets an instance of the axis whose range is changed when panning. This event is triggered for each axis in the chart.
* [`Cancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ResetZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ResetZoomEventArgs_Cancel) - Gets or Sets a value that indicates whether the panning should be canceled.
* [`PreviousZoomRange`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ResetZoomEventArgs.html#Syncfusion_UI_Xaml_Charts_ResetZoomEventArgs_PreviousZoomRange) - Gets the previous visible range of the axis.

## See also

[`How to improve performance while zooming by using scrollbar`](https://www.syncfusion.com/kb/5489/how-to-improve-performance-while-zooming-by-using-scrollbar)

[`How to set default zoom/pan position for charts`](https://www.syncfusion.com/kb/2904/how-to-set-default-zoom-pan-position-for-charts)

[`How to display the visible range of labels while zooming`](https://www.syncfusion.com/kb/2712/how-to-display-the-visible-range-of-labels-while-zooming )

[`How to reset zooming `](https://www.syncfusion.com/kb/2562/how-to-reset-zooming)
