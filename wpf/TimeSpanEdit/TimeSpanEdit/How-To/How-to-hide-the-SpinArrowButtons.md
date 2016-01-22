---
layout: post
title:  How to hide the SpinArrowButtons
description:   How to hide the SpinArrowButtons?
platform: wpf
control: TimeSpanEdit
documentation: ug
---


# How to hide the SpinArrowButtons?

The SpinArrowButtons can be hidden by setting the ShowArrowButtons property as False.

![](How-to-show-milliseconds-in-the-TimeSpanEdit-control_images/How-to-show-milliseconds-in-the-TimeSpanEdit-control_img2.png)
 
TimeSpanEdit without SpinArrowButtons

 

{%highlight xaml%}

<syncfusion:TimeSpanEdit Value="10.2:25:52" Format=" d 'days' h 'hours'"  Height="40" Margin="42,136,315,136" ShowArrowButtons="False"  />

{%endhighlight%}