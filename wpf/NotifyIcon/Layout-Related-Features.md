---
layout: post
title: Layout-Related-Features
description: layout related features
platform: wpf
control: NotifyIcon
documentation: ug
---

# Layout Related Features

This section illustrates the following Layout-related feature of NotifyIcon control.

## Setting VisualStyle for NotifyIcon

NotifyIcon supports different visual styles to enhance its look and feel. The visual style for the NotifyIcon is set by using the VisualStyle property.

_Property table_

<table>
<tr>
<td>
Property</td><td>
Description</td></tr>
<tr>
<td>
VisualStyle</td><td>
Sets the visual style for the NotifyIcon control. The options provided are as follows.BlendOffice2003Office2007BlueOffice2007BlackOffice2007SilverShinyBlueShinyRedSyncOrangeVS2010MetroTransparent</td></tr>
</table>


The below code can be used to set various visual style.

[C#]



//For Office2007Blue

SkinStorage.VisualStyle(notifyIcon, "Office2007Blue");



//For Blend

SkinStorage.VisualStyle(notifyIcon, Blend");



//For Office2007Silver

SkinStorage.VisualStyle(notifyIcon, "Office2007Silver");



{{ '![](Layout-Related-Features_images/Layout-Related-Features_img1.jpeg)' | markdownify }}
{:.image }


_NotifyIcon with "Office2007Blue" Visual Style_

{{ '![](Layout-Related-Features_images/Layout-Related-Features_img2.jpeg)' | markdownify }}
{:.image }


_NotifyIcon with "Blend" Visual Style_

{{ '![](Layout-Related-Features_images/Layout-Related-Features_img3.jpeg)' | markdownify }}
{:.image }


_NotifyIcon with "Office2007Silver" Visual Style_

{{ '![](Layout-Related-Features_images/Layout-Related-Features_img4.png)' | markdownify }}
{:.image }


_NotifyIcon with "Metro" Visual Style_

{{ '![C:/Users/ramalakshmim/Desktop/ugss/notifyicon.png](Layout-Related-Features_images/Layout-Related-Features_img5.png)' | markdownify }}
{:.image }


_NotifyIcon with "Transparent" Visual Style_

## Customizing the Header of the NotifyIcon

You can set the background and foreground for the BalloonTipHeader by using the HeaderBackground and HeaderForeground properties, respectively. Use the code below to set these properties.

<table>
<tr>
<td>
[XAML]<syncfusion:NotifyIcon Name="notifyIcon" BalloonTipText="Custom Notify Icon is Available"  BalloonTipTitle="Default NotifyIcon"  HeaderBackground="Blue" HeaderForeground="Red" ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/></td></tr>
<tr>
<td>
[C#]notifyIcon.HeaderForeground = Brushes.Red;notifyIcon.HeaderBackground = Brushes.Blue;</td></tr>
</table>


{{ '![](Layout-Related-Features_images/Layout-Related-Features_img6.jpeg)' | markdownify }}
{:.image }


_HeaderForeground = "Red"; HeaderBackground = "Blue"_

