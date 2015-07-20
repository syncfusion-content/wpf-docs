---
layout: post
title: Interactive-Features
description: interactive features
platform: wpf
control: NotifyIcon
documentation: ug
---

# Interactive Features

This section illustrates the following interactive features of NotifyIcon control. 

## BalloonTip

This section illustrates the following parts of a BallonTip.

### Header of BalloonTip

Using the BalloonTipHeaderVisibility property, user can collapse or show the header of the NotifyIcon control.

The following code snippet is used to set this property.

<table>
<tr>
<td>
[XAML]<!--BalloonTipHeaderVisibility="Visible" --><syncfusion:NotifyIcon Name="notifyIcon" BalloonTipText="Custom Notify Icon is Available"  BalloonTipTitle="Default NotifyIcon" BalloonTipHeaderVisibility="Visible" ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/><!--BalloonTipHeaderVisibility="Collapsed" --><syncfusion:NotifyIcon Name="notifyIcon" BalloonTipText="Custom Notify Icon is Available"  BalloonTipTitle="Default NotifyIcon" BalloonTipHeaderVisibility="Collapsed" ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/></td></tr>
<tr>
<td>
[C#]//BalloonTipHeaderVisibility="Visible"notifyIcon.BalloonTipHeaderVisibility = Visibility.Visible;//BalloonTipHeaderVisibility="Collapsed"notifyIcon.BalloonTipHeaderVisibility = Visibility.Collapsed;</td></tr>
</table>


{{ '![](Interactive-Features_images/Interactive-Features_img1.jpeg)' | markdownify }}
{:.image }


{{ '![](Interactive-Features_images/Interactive-Features_img2.jpeg)' | markdownify }}
{:.image }


### Text and Title of BalloonTip

BalloonTipText property is used to set the text that should be displayed in the Notify icon. BalloonTipTitle is used to set the title for NotifyIcon. The following code snippet is used to set these properties.

<table>
<tr>
<td>
[XAML]<syncfusion:NotifyIcon Name="notifyIcon" BalloonTipText="Virus Scan has been completed" BalloonTipTitle="AntiVirus Software" ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/></td></tr>
<tr>
<td>
[C#]notifyIcon.BalloonTipText = "Virus Scan has been completed";notifyIcon.BalloonTipTitle = "AntiVirus Software"; </td></tr>
</table>


{{ '![](Interactive-Features_images/Interactive-Features_img3.jpeg)' | markdownify }}
{:.image }


_BalloonTipTitle = "AntiVirus Software"_

### Icon of BalloonTip

You can display the following five different icons in the NotifyIcon control. 

* Custom
* Info
* Error
* None
* Warning

The following code snippet is used to set this property.

<table>
<tr>
<td>
[XAML]<!-- BalloonTipIcon="Warning" --><syncfusion:NotifyIcon Name="notifyIcon" BalloonTipText="Custom Notify Icon is Available"  BalloonTipTitle="Default NotifyIcon" BalloonTipIcon="Warning" ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/></td></tr>
<tr>
<td>
[C#]//BalloonTipIcon="Warning"notifyIcon.BalloonTipIcon = BalloonTipIcon.Warning;</td></tr>
</table>


{{ '![](Interactive-Features_images/Interactive-Features_img4.jpeg)' | markdownify }}
{:.image }


## Animation

This topic illustrates the animation type and animation time for NotifyIcon control.

Animation Type

You can set different animation effects for the NotifyIcon by using the BalloonTipAnimationEffect property. They are listed below.

* Custom
* Fade
* Slide
* Scale

Animation Time

NotifyIcon display time is set by using the property called ShowBalloonTipTime. The time during which the NotifyIcon is hidden is set by using the property called HideBalloonTipTime.

The following code snippet is used to set these properties.

<table>
<tr>
<td>
[XAML]<!-- For Fade --><syncfusion:NotifyIcon Name="notifyIcon" BalloonTipText="Custom Notify Icon is Available"  BalloonTipTitle="Default NotifyIcon" BalloonTipAnimationEffect="Fade"  ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/><!-- For Scale --><syncfusion:NotifyIcon Name="notifyIcon" BalloonTipText="Custom Notify Icon is Available"  BalloonTipTitle="Default NotifyIcon" BalloonTipAnimationEffect="Scale"  ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/></td></tr>
<tr>
<td>
[C#]NotifyIcon notifyIcon = new NotifyIcon();notifyIcon.BalloonTipText = "Custom Notify Icon is Available";notifyIcon.BalloonTipTitle = "Default NotifyIcon";//For FadenotifyIcon.BalloonTipAnimationEffect = BalloonTipAnimationEffects.Fade;//For ScalenotifyIcon.BalloonTipAnimationEffect = BalloonTipAnimationEffects.Scale;// Duration for Showing NotifyIconnotifyIcon.ShowBalloonTipTime = 1000;// // Duration for Hiding NotifyIconnotifyIcon.HideBalloonTipTime = 1000;</td></tr>
</table>
## Setting the position of the Notify Icon

The position where the NotifyIcon is to be displayed is specified using the property called BalloonTipLocation. To set this property, refer the below code.

<table>
<tr>
<td>
[XAML]<syncfusion:NotifyIcon Name="notifyIcon" BalloonTipLocation="500,500" BalloonTipText="Custom Notify Icon is Available"BalloonTipTitle="Default NotifyIcon" ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/></td></tr>
<tr>
<td>
[C#]defaults.BalloonTipLocation = new Point(500, 500);</td></tr>
</table>
## Setting the Shape of the Notify Icon

NotifyIcon can take the following three different shapes.

* Balloon
* Rectangle
* RoundedRectangle

The shape for the NotifyIcon is set by using the BalloonTipShape property. The following code snippet is used to change the Shape of the NotifyIcon control.

<table>
<tr>
<td>
[XAML]<!-- Rectangle Shape --><syncfusion:NotifyIcon Name="notifyIcon" BalloonTipText="Custom Notify Icon is Available"  BalloonTipTitle="Default NotifyIcon" BalloonTipShape="Rectangle" ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/><!-- RoundedRectangle Shape --><syncfusion:NotifyIcon Name="notifyIcon" BalloonTipText="Custom Notify Icon is Available"  BalloonTipTitle="Default NotifyIcon" BalloonTipShape="RoundedRectangle" ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/><!-- Balloon Shape --><syncfusion:NotifyIcon Name="notifyIcon" BalloonTipText="Custom Notify Icon is Available"  BalloonTipTitle="Default NotifyIcon" BalloonTipShape="Balloon" ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/></td></tr>
<tr>
<td>
[C#]// Rectangle ShapenotifyIcon.BalloonTipShape = BalloonTipShapes.Rectangle;//RoundedRectangle ShapenotifyIcon.BalloonTipShape = BalloonTipShapes.RoundedRectangle;//Balloon ShapenotifyIcon.BalloonTipShape = BalloonTipShapes.RoundedRectangle;</td></tr>
</table>


{{ '![](Interactive-Features_images/Interactive-Features_img5.jpeg)' | markdownify }}
{:.image }


{{ '![](Interactive-Features_images/Interactive-Features_img6.jpeg)' | markdownify }}
{:.image }


