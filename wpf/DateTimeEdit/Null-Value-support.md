---
layout: post
title: Null-Value-support
description: null value support
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Null Value support

DateTimeEdit control accepts null values. NullValue support in the DateTimeEdit control can be enabled by setting the IsEmptyDateEnabled property to true. You can also specify the Value when you set the null to the DateTime property by using the NullValue property.  You can set the WatermarkText when the null Value is set to the DateTime property.



{% highlight c# %}
C#

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200"  IsEmptyDateEnabled="True" NullValue="{x:Null}">

{% endhighlight %}

![](Null-Value-support_images/Null-Value-support_img1.png)





Here is an example to change the DateTime property by using the NullValue property when you set null to the DateTime property.

In the example displayed below when you set null to the DateTime property, then automatically the value of the NullValue property is set to the DateTime property.


{% highlight xml %}
XAML

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200"  IsEmptyDateEnabled="True" NullValue="07/05/2010">
{% endhighlight  %}


![](Null-Value-support_images/Null-Value-support_img2.png)


See Also

Setting Date

Maximum and Minimum Value

