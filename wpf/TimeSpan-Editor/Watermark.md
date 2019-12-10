---
layout: post
title: Watermark in WPF TimeSpanEdit | Syncfusion
description:  Learn here about Watermark support with Syncfusion WPF TimeSpanEdit control and more details about the control features.
platform: wpf
control: TimeSpanEdit
documentation: ug
---

# Watermark for null value

## Assign null value

AllowNull property can be used to set the TimeSpanEdit value to Null. When this property is enabled along with the Value property whose value is Null, then the TimeSpanEdit control will not display any value.

{% tabs %}
{% highlight xaml %}

<syncfusion:TimeSpanEdit Value="10.2:25:52" Width="150" Height="50" AllowNull="True"/>

{% endhighlight %}
{% endtabs %}

![Applied null value text in WPF TimeSpanEdit](Watermark_images\AllowNull-in-timespanedit-control_img1.png)

## Show Watermark on null value

When the `AllowNull` property is enabled. We can use Watermark to show the text in the TimeSpanEdit control by using `NullString` when the value is null.

{% tabs %}
{% highlight xaml %}

<syncfusion:TimeSpanEdit Value="10.2:25:52" Width="150" Height="50" AllowNull="True" Nullstring="Syncfusion.."/>

{% endhighlight %}
{% endtabs %}

![Watermark in TimeSpanEdit](Watermark_images\NullString-in-TimeSpanEdit-control_img2.png)







