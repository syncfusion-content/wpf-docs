---
layout: post
title: Null Value support | DateTimeEdit | WPF | Syncfusion
description: DateTimeEdit control provides null value support to accept null values by using IsEmptyDateEnabled property.
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Null Value Support

DateTimeEdit control accepts null values. [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~NullValue.html) support in the DateTimeEdit control can be enabled by setting the [IsEmptyDateEnabled](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~IsEmptyDateEnabled.html) property to true. You can also specify the Value when you set the null to the [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) property by using the [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~NullValue.html) property.  You can set the WatermarkText when the null Value is set to the DateTime property.

{% tabs %}
{% highlight xaml %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" IsEmptyDateEnabled="True" NullValue="{x:Null}">

{% endhighlight %}
{% endtabs %}

![Null value support](Null-Value-support_images/Null-Value-support_img1.png)

Here is an example to change the DateTime property by using the [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~NullValue.html) property when you set null to the [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) property.

In the example displayed below when you set null to the [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) property, then automatically the value of the [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~NullValue.html) property is set to the [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200"   IsEmptyDateEnabled="True" NullValue="07/05/2010">

{% endhighlight  %}
{% endtabs %}

![Null value support](Null-Value-support_images/Null-Value-support_img2.png)

{% seealso %}

[Maximum and Minimum Value](/wpf/datetimeedit/maximum-and-minimum-value)

{% endseealso %}