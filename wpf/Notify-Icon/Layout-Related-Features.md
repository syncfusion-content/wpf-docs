---
layout: post
title: Layout Related Features| NotifyIcon | Wpf | Syncfusion
description: layout related features
platform: wpf
control: NotifyIcon
documentation: ug
---

# Layout Related Features

This section illustrates the following Layout-related feature of NotifyIcon control.

## Setting VisualStyle for NotifyIcon

NotifyIcon supports different visual styles to enhance its look and feel. The visual style for the NotifyIcon is set by using the VisualStyle property.

### Property table

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
VisualStyle</td><td>
Sets the visual style for the NotifyIcon control. The options provided are as follows.BlendOffice2003Office2007BlueOffice2007BlackOffice2007SilverShinyBlueShinyRedSyncOrangeVS2010MetroTransparent</td></tr>
</table>


The below code can be used to set various visual style.

{% highlight c# %}




//For Office2007Blue

SkinStorage.VisualStyle(notifyIcon, "Office2007Blue");



//For Blend

SkinStorage.VisualStyle(notifyIcon, Blend");



//For Office2007Silver

SkinStorage.VisualStyle(notifyIcon, "Office2007Silver");

{% endhighlight %}

![](Layout-Related-Features_images/Layout-Related-Features_img1.jpeg)



NotifyIcon with "Office2007Blue" Visual Style
{:.caption}

![](Layout-Related-Features_images/Layout-Related-Features_img2.jpeg)



NotifyIcon with "Blend" Visual Style
{:.caption}

![](Layout-Related-Features_images/Layout-Related-Features_img3.jpeg)



NotifyIcon with "Office2007Silver" Visual Style
{:.caption}

![](Layout-Related-Features_images/Layout-Related-Features_img4.png)



NotifyIcon with "Metro" Visual Style
{:.caption}

![](Layout-Related-Features_images/Layout-Related-Features_img5.png)



NotifyIcon with "Transparent" Visual Style
{:.caption}

## Customizing the Header of the NotifyIcon

You can set the background and foreground for the BalloonTipHeader by using the HeaderBackground and HeaderForeground properties, respectively. Use the code below to set these properties.

{% tabs %}
{% highlight xaml %}

<syncfusion:NotifyIcon Name="notifyIcon" BalloonTipText="Custom Notify 
Icon is Available"  BalloonTipTitle="Default NotifyIcon"  HeaderBackground="Blue" HeaderForeground="Red" 
ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/>
{% endhighlight %}

{% highlight c# %}

notifyIcon.HeaderForeground = Brushes.Red;notifyIcon.HeaderBackground = Brushes.Blue;
{% endhighlight %}
{% endtabs %}


![](Layout-Related-Features_images/Layout-Related-Features_img6.jpeg)



HeaderForeground = "Red"; HeaderBackground = "Blue"
{:.caption}

