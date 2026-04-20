---
layout: post
title: Header in WPF Busy Indicator Control | Syncfusion®
description: Learn all about Header support in the Syncfusion® WPF Busy Indicator (SfBusyIndicator) control and more.
platform: WPF
control: Busy Indicator
documentation: ug
---

# Header in WPF Busy Indicator (SfBusyIndicator)

## Header

The Header is displayed below the animation. The `Header` property can be used to get or set the content that indicates information related to the loading process.

{% tabs %}

{% highlight xaml %}

<!-- To set the header for SfBusyIndicator -->

<Grid  Background="CornflowerBlue">
<Notification:SfBusyIndicator Header="Loading..." Foreground="White" />
</Grid>

{% endhighlight %}

{% highlight C# %}

// To set the Header for SfBusyIndicator
SfBusyIndicator SfBusyIndicator = new SfBusyIndicator();
SfBusyIndicator.Header = "Loading..";
grid1.Children.Add(SfBusyIndicator);

{% endhighlight %}

{% highlight VB %}

'To set the Header for SfBusyIndicator
Dim SfBusyIndicator As New SfBusyIndicator()
SfBusyIndicator.Header = "Loading.."
grid1.Children.Add(SfBusyIndicator)

{% endhighlight %}

{% endtabs %}


![Header](Header_images/Header_img1.png)

Busy Indicator with a header
{:.caption}


## Header Template

The `HeaderTemplate` property is used to get or set the template that defines the appearance of the header section of the `SfBusyIndicator` control.

{% tabs %}

{% highlight xaml %}

<!-- To set the HeaderTemplate for SfBusyIndicator -->

<Notification:SfBusyIndicator Grid.Row="0" Foreground="White" Background="CornflowerBlue" >
<Notification:SfBusyIndicator.HeaderTemplate>
<DataTemplate >
<TextBlock Text="Loading..." TextAlignment="Center" FontSize="15" Width="100" Foreground="Yellow" />
</DataTemplate>
</Notification:SfBusyIndicator.HeaderTemplate>
</Notification:SfBusyIndicator>

{% endhighlight %}

{% endtabs %}

![Header_Template](Header_images/Header_img2.png)

Busy Indicator with a header template
{:.caption}

> **Note:** View the [sample](https://github.com/SyncfusionExamples/wpf-BusyIndicator-examples/tree/master/Samples/Header) on GitHub.
