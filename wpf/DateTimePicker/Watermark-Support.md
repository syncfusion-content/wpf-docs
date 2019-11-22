---
layout: post
title: WPF DateTimeEdit Watermark | Syncfusion
description: This section explains how to display hint information in DateTimeEdit control when the selected date is null.
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Watermark

The `DateTimeEdit` control displays hint information using watermark text when the selected date is null. In addition, it provides support to define null DateTime value.

## Null value

The `DateTimeEdit` control accepts null values. The [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~NullValue.html) support in the DateTimeEdit control can be enabled by setting the [IsEmptyDateEnabled](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~IsEmptyDateEnabled.html) property to `true` and [ShowMaskOnNullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~ShowMaskOnNullValue.html) property to `false`. If the value is null and the editing text box is empty then the `Watermark` will be displayed as the text in the DateTimeEdi control.

{% tabs %}

{% highlight xaml %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" ShowMaskOnNullValue="False" IsEmptyDateEnabled="True" NullValue="{x:Null}"/>

{% endhighlight %}

{% endtabs %}

![WPF DateTimeEdit display null value](Watermark-Support_images/wpf-datetimeedit-null-value.png)

## Change watermark

The watermark is a help content that is used to display in the `DateTimeEdit` control when the [IsEmptyDateEnabled](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~IsEmptyDateEnabled.html) property is true when the selected date is null. You can set the content of the Watermark by using the [NoneDateText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~NoneDateText.html) property.

{% tabs %}

{% highlight xaml %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" IsEmptyDateEnabled="True" NullValue="{x:Null}"/>

{% endhighlight %}

{% endtabs %}

![WPF DateTimeEdit watermark support](Watermark-Support_images/wpf-datetimeedit-watermark.png)