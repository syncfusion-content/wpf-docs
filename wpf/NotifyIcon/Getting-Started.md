---
layout: post
title: Getting Started| NotifyIcon | Wpf | Syncfusion
description: getting started
platform: wpf
control: NotifyIcon
documentation: ug
---

# Getting Started

This section guides you on getting started with NotifyIcon control. 

![](Getting-Started_images/Getting-Started_img1.jpeg)



## Why to use our NotifyIcon control

Here are some highlights of our Notify Icon control.

* Different Animation support
* Different shape support

## Creating NotifyIcon Control


NotifyIcon is created either by using XAML code or with C# code, as follows.

{% tabs %}
{% highlight xaml %}



<syncfusion:NotifyIcon Name="notifyIcon" BalloonTipText="Custom Notify 
Icon is Available" BalloonTipTitle="Default NotifyIcon" 
ShowBalloonTipTime="1000" HideBalloonTipTime="1000"/>

{% endhighlight %}

{% highlight c# %}
NotifyIcon notifyIcon = new NotifyIcon();
notifyIcon.BalloonTipText = "Custom Notify Icon is Available";
notifyIcon.BalloonTipTitle = "Default NotifyIcon";
notifyIcon.ShowBalloonTipTime = 1000;
notifyIcon.HideBalloonTipTime = 1000;

{% endhighlight %}
{% endtabs %}


![](Getting-Started_images/Getting-Started_img2.jpeg)


