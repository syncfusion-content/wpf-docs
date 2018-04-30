---
layout: post
title: Watermark Support | DateTimeEdit | wpf | Syncfusion
description: watermark support
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Watermark Support

Watermark is the dummy content displayed in the DateTimeEdit control when the DateTime property is set to null. You can set the content of the Watermark by using the NoneDateText property.

{% tabs %}
{% highlight xaml %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="230" Margin="10"                             NullValue="{x:Null}" IsEmptyDateEnabled="True"                             NoneDateText="No date is selected"/>

{% endhighlight  %}
{% endtabs %}

![](Watermark-Support_images/Watermark-Support_img1.png)


{% seealso %}

NullValue support

{% endseealso %}