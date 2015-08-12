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
{{ '**Property**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td></tr>
<tr>
<td>
VisualStyle</td><td>
Sets the visual style for the NotifyIcon control. The options provided are as follows.BlendOffice2003Office2007BlueOffice2007BlackOffice2007SilverShinyBlueShinyRedSyncOrangeVS2010MetroTransparent</td></tr>
</table>


The below code can be used to set various visual style.

{%highlight c#%}



//For Office2007Blue

SkinStorage.VisualStyle(notifyIcon, "Office2007Blue");



//For Blend

SkinStorage.VisualStyle(notifyIcon, Blend");



//For Office2007Silver

SkinStorage.VisualStyle(notifyIcon, "Office2007Silver");

{%endhighlight%}

![](Layout-Related-Features_images/Layout-Related-Features_img1.jpeg)



_NotifyIcon with "Office2007Blue" Visual Style_

![](Layout-Related-Features_images/Layout-Related-Features_img2.jpeg)



_NotifyIcon with "Blend" Visual Style_

![](Layout-Related-Features_images/Layout-Related-Features_img3.jpeg)



_NotifyIcon with "Office2007Silver" Visual Style_

![](Layout-Related-Features_images/Layout-Related-Features_img4.png)



_NotifyIcon with "Metro" Visual Style_

![](Layout-Related-Features_images/Layout-Related-Features_img5.png)



_NotifyIcon with "Transparent" Visual Style_

## Customizing the Header of the NotifyIcon

You can set the background and foreground for the BalloonTipHeader by using the HeaderBackground and HeaderForeground properties, respectively. Use the code below to set these properties.


{%highlight xml%}

<syncfusion:NotifyIcon Name="notifyIcon" BalloonTipText="Custom Notify 
Icon is Available"  BalloonTipTitle="Default NotifyIcon"  HeaderBackground="Blue" HeaderForeground="Red" 
ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/>
{%endhighlight%}

{%highlight c#%}

notifyIcon.HeaderForeground = Brushes.Red;notifyIcon.HeaderBackground = Brushes.Blue;
{%endhighlight%}



![](Layout-Related-Features_images/Layout-Related-Features_img6.jpeg)



_HeaderForeground = "Red"; HeaderBackground = "Blue"_

