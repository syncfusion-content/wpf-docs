---
layout: post
title: How-to-show-milliseconds-in-the-TimeSpanEdit-control
description:  how to show milliseconds in the timespanedit control?
platform: wpf
control: TimeSpanEdit
documentation: ug
---

#  How to Show Milliseconds in the TimeSpanEdit Control

The character z in the format string is used to display milliseconds in the TimeSpanEdit control. 

![](How-to-show-milliseconds-in-the-TimeSpanEdit-control_images/How-to-show-milliseconds-in-the-TimeSpanEdit-control_img1.png)

{% tabs %}
{% highlight xaml %}

<syncfusion:TimeSpanEdit Value="10.2:25:52" Format=" d 'days' h 'hours' m 'minutes' :s 'sec' z 'msec' "/>

{% endhighlight %}

{% highlight C# %}

timeSpanEdit1.Format = @" d 'days' h 'hours' m 'minutes' :s 'sec' z 'msec'";

{% endhighlight %}
{% endtabs %}
