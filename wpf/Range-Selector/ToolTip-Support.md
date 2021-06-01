---
layout: post
title: ToolTip Support in WPF Range Selector control | Syncfusion
description: Learn here all about ToolTip Support in Syncfusion WPF Range Selector (SfDateTimeRangeNavigator) control and more.
platform: wpf
control: SfDateTimeRangeNavigator
 documentation: ug
---

# ToolTip Support in WPF Range Selector (SfDateTimeRangeNavigator)

The date-time range navigator control provides tooltip support to sliders. Sliders are used to select a particular region of data in the control. Tooltips for sliders show the selected start and end date-time values. You can view the exact date values with the milliseconds precision.

## Properties

The following properties are used to customize the tooltip settings:

### Property

<table>
<tr>
<th>
Property Name</th><th>
Description</th></tr>
<tr>
<td>
{{'[`ShowToolTip`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_ShowToolTip)'| markdownify }}</td><td>
Shows or hides the tooltip.</td></tr>
<tr>
<td>
{{'[`ToolTipLabelFormat`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_ToolTipLabelFormat)'| markdownify }}</td><td>
Sets the date-time label format for the tooltip.</td></tr>
<tr>
<td>
{{'[`LeftToolTipTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_LeftToolTipTemplate)'| markdownify }}</td><td>
Sets the data template for the left tooltip.</td></tr>
<tr>
<td>
{{'[`RightToolTipTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_RightToolTipTemplate)'| markdownify }}</td><td>
Sets the data template for the right tooltip.</td></tr>
</table>

{% tabs %}

{% highlight xaml %}

<chart:SfDateTimeRangeNavigator x:Name="RangeNavigator" 

ItemsSource="{Binding StockPriceDetails}" XBindingPath="_Date" 

ShowToolTip="true" ToolTipLabelFormat ="MMM/dd/yyyy">

<chart:SfDateTimeRangeNavigator.LeftToolTipTemplate>

<DataTemplate>

-----------------------

</DataTemplate>

</chart:SfDateTimeRangeNavigator.LeftToolTipTemplate>

<chart:SfDateTimeRangeNavigator.Content>

</chart:SfDateTimeRangeNavigator.Content>

</chart:SfDateTimeRangeNavigator>

{% endhighlight %}

{% highlight c# %}

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    ShowToolTip = true,

    ToolTipLabelFormat = "yyyy/MMM/dd",

    LeftToolTipTemplate = grid.Resources["tooltipTemplate"] as DataTemplate

};

{% endhighlight %}

{% endtabs %}

![ToolTip support in WPF SfDateTimeRangeNavigator](ToolTip-Support_images/ToolTip-Support_img1.png)
