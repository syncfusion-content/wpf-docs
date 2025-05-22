---
layout: post
title: Resizable Scrollbar in WPF Charts control | Syncfusion
description: Learn here all about Resizable Scrollbar support in Syncfusion® WPF Charts (SfChart) control and more.
platform: wpf
control: SfChart
documentation: ug
---

# Resizable Scrollbar in WPF Charts (SfChart)

The resizable scrollbar is a type of scrollbar that can be resized within the track area by adjusting the scrolling thumbs. In SfChart, a resizable scrollbar is used for zooming and panning across different chart segments.

## Adding Scrollbar to the Axis

The [`EnableScrollBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_EnableScrollBar) property allows you to add a scrollbar to a particular axis. The following code snippet illustrates adding a scrollbar to the primary axis:

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

## Deferred Scrolling

SfChart provides support to suspend value updates during thumb movement. This can be achieved using the [`DeferredScrolling`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_DeferredScrolling) property in the chart axis. The following code snippet demonstrates deferred scrolling:

{% tabs %}

{% highlight xaml %}
<syncfusion:SfChart.PrimaryAxis>
    <syncfusion:CategoryAxis EnableScrollBar="True" DeferredScrolling="True"/>
</syncfusion:SfChart.PrimaryAxis>
{% endhighlight %}

{% highlight c# %}
chart.PrimaryAxis = new CategoryAxis()
{
    EnableScrollBar = true,
    DeferredScrolling = true
};
{% endhighlight %}

{% endtabs %}

## Resizing the Scrollbar

SfChart allows you to enable or disable scrollbar resizing using the [`EnableScrollBarResizing`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_EnableScrollBarResizing) property. By default, this property is set to true. The following code example demonstrates how to disable scrollbar resizing:

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
    EnableScrollBarResizing = false
};
{% endhighlight %}

{% endtabs %}

![Resizing the scrollbar in WPF Chart](Interactive-Features_images/Interactive-Features_img42.jpeg)

## Scrollbar for Touch Mode

Scrollbar provides a touch-friendly style by enabling the [`EnableTouchMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_EnableTouchMode) property as shown in the code snippet below:

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

### Thumb Label

In touch mode, you can display thumb labels while resizing or dragging the scrollbar by setting the [`ThumbLabelVisibility`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_ThumbLabelVisibility) property to Visible. The following code example demonstrates how to enable thumb labels:

{% tabs %}

{% highlight xaml %}
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

### Thumb Label Template

The [`ThumbLabelTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_ThumbLabelTemplate) property allows you to customize the appearance of the scrollbar thumb labels:

{% tabs %}

{% highlight xaml %}
<syncfusion:SfChart x:Name="chart">
    <syncfusion:SfChart.Resources>
        <DataTemplate x:Key="labelTemplate">
            <Grid>
                <Border BorderBrush="Black" Background="Pink" BorderThickness="2">
                    <TextBlock Text="{Binding}" FontSize="15"/>
                </Border>
            </Grid>
        </DataTemplate>
    </syncfusion:SfChart.Resources>

    <syncfusion:SfChart.PrimaryAxis>
        <syncfusion:CategoryAxis EnableTouchMode="True" 
                                 EnableScrollBar="True"
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