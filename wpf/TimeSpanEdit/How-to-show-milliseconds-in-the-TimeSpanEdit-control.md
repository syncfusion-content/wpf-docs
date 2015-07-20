---
layout: post
title: How-to-show-milliseconds-in-the-TimeSpanEdit-control
description:  how to show milliseconds in the timespanedit control?
platform: wpf
control: TimeSpanEdit
documentation: ug
---

###  How to show milliseconds in the TimeSpanEdit control?

The character z in the format string is used to display milliseconds in the TimeSpanEdit control. 

{{ '![](How-to-show-milliseconds-in-the-TimeSpanEdit-control_images/How-to-show-milliseconds-in-the-TimeSpanEdit-control_img1.png)' | markdownify }}
{:.image }




[XAML]

<syncfusion:TimeSpanEdit Value="10.2:25:52" Format=" d 'days' h 'hours' m 'minutes' :s 'sec' z 'msec' "/>





[C#]

timeSpanEdit1.Format = @" d 'days' h 'hours' m 'minutes' :s 'sec' z 'msec'";







