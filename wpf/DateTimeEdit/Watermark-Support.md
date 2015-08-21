---
layout: post
title: Watermark-Support
description: watermark support
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Watermark Support

Watermark is the dummy content displayed in the DateTimeEdit control when the DateTime property is set to null. You can set the content of the Watermark by using the NoneDateText property.



{% highlight html %}


<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="230" Margin="10"                             NullValue="{x:Null}" IsEmptyDateEnabled="True"                             NoneDateText="No date is selected"/>

{% endhighlight  %}

![](Watermark-Support_images/Watermark-Support_img1.png)



See Also

NullValue support

