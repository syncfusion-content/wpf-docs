---
layout: post
title: Header | Busy Indicator | wpf | Syncfusion
description: header
platform: wpf
control: Busy Indicator
documentation: ug
---

# Header

## Header

The Header is displayed below the animation. The Header property can be used to get or set the content which indicates the information related to loading. 

{% tabs %}

{% highlight xaml %}

<!--To set the header for SfBusyIndicator-->

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


![](Header_images/Header_img1.png)

Busy Indicator with header
{:.caption}


## Header Template

Header template can be used to get or set the template that defines how the header section of the SfBusyIndicator control is displayed.

{% tabs %}

{% highlight xaml %}

<!--To set the HeaderTemplate for SfBusyIndicator-->

<Notification:SfBusyIndicator Grid.Row="0" Foreground="White" Background="CornflowerBlue" >
<Notification:SfBusyIndicator.HeaderTemplate>
<DataTemplate >
<TextBlock Text="Loading..." TextAlignment="Center" FontSize="15" Width="100" Foreground="Yellow" />
</DataTemplate>
</Notification:SfBusyIndicator.HeaderTemplate>
</Notification:SfBusyIndicator>

{% endhighlight %}

{% endtabs %}

![](Header_images/Header_img2.png)

Busy Indicator with header template
{:.caption}


N> View [sample](https://github.com/SyncfusionExamples/wpf-BusyIndicator-examples/tree/master/Samples/Header) in GitHub
