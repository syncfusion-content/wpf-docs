---
layout: post
title: Restriction-or-Validation-in-WPF-TimeSpanEdit
description:  To validation the Min and Max value in TimeSpanEdit.
platform: wpf
control: TimeSpanEdit
documentation: ug
---

#  Validation in WPF TimeSpanEdit

## Restrict within min and max value

The `Value` of the `TimeSpanEdit` can be restricted within the maximum and minimum limits. Once the percent value has reached the maximum or minimum value , the value does not exceed the limit. We can change the maximum and minimum limits by using the MinValue property and MaxValue property.

Another way,

By using the keyboard, you can not enter the value above or below the predefined maximized or minimized value.

* **MaxValue** - The [MaxValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TimeSpanEdit~MaxValue.html) property is the maximum value that can be set for the `TimeSpanEdit` control.

* **MinValue** - The [MinValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TimeSpanEdit~MinValue.html) property is the minimum value that can be set for the `TimeSpanEdit` control.

{% tabs %}
{% highlight xaml %}

<syncfusion:TimeSpanEdit Value="10.2:25:52" Width="150" Height="30" MinValue="2.0:0:0" MaxValue="31.0:0:0"/>

{% endhighlight %}

{% highlight C# %}

timespan.MinValue= new TimeSpan(2,0,0,0);
timespan.MaxValue = new TimeSpan(31, 0, 0, 0);

{% endhighlight %}
{% endtabs %}

### Min value
![Validate the minimum in WPF TimeSpanedit](Restriction-or-validation_images/wpf-TimeSpanEdit-minValue.png)
### Max value

![Validate the maximum in WPF TimeSpanedit](Restriction-or-validation_images/wpf-TimeSpanEdit-maxValue.png)


## Read only value

The `TimeSpanEdit` cannot allow the user input, edits when [IsReadOnly](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.isreadonly?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_Primitives_TextBoxBase_IsReadOnly) property is sets to `true`. The user can still select text and display the cursor on the `TimeSpanEdit` by setting the [IsReadOnlyCaretVisible](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.primitives.textboxbase.isreadonlycaretvisible?view=netframework-4.8) property to `true`. However, value can be changed programmatically in readonly mode.

{% tabs %}
{% highlight XAML %}

<syncfusion:TimeSpanEdit x:Name="timespanedit" IsReadOnly="True" Value="1.2:3:4" IsReadOnlyCaretVisible="True"/>

{% endhighlight %}
{% highlight C# %}

TimeSpanEdit timespanedit = new TimeSpanEdit();
timespanedit.Value = new TimeSpan(3, 5, 4, 3);
timespanedit.IsReadOnly = true;
timespanedit.IsReadOnlyCaretVisible = true;

{% endhighlight %}
{% endtabs %}

![TimeSpanEdit in read-only mode](Restriction-or-validation_images/Restriction-or-Validation_ReadOnly.png)

