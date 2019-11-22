---
layout: post
title: WPF DateTimeEdit Minimum and Maximum value | Syncfusion
description: This section describes how to restrict users to choose a date within maximum and minimum values in the DateTimeEdit control.
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Date range

Prevents user from setting a date and time within a specified range can be achieved by using the [MinDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTime.html) and [MaxDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTime.html) properties of the DateTimeEdit. The Calendar also displays only the dates between the MinDateTime and MaxDateTime.

## Change the value

The date and time of the DateTimeEdit can be changed by the [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) property. The DateTime can be set to null when the [IsEmptyDateEnabled](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~IsEmptyDateEnabled.html) is true. The value can also be edited by selecting the DateTimeField and editing the value. This value will be validated when the control lost its focus or the enter key is pressed.

### Detect the value change

The [DateTimeChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTimeChanged_EV.html) event will be invoked when the change is occurred in the [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) property of the DateTimeEdit. If you need to do any custom actions while value changed, that can be done at the DateTimeChanged event. 

{% tabs %}

{% highlight C# %}

dateTimeEdit.DateTimeChanged += DateTimeEdit_DateTimeChanged;

private void DateTimeEdit_DateTimeChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    Console.WriteLine("DateTimeChanged event is fired");     
}

{% endhighlight %}

{% endtabs %}

N> You can also edit value of DateTimeEdit while scrolling the mouse by setting the [EnableMouseWheelEdit](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~EnableMouseWheelEdit.html) property to true.  

## Minimum DateTime

The [MinDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTime.html) helps you to restrict the DateTime value which is lesser than the specific DateTime value. If the [DateTime value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) of DateTimeEdit is less than [MinDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTime.html), then the DateTime property will be reset to MinDateTime. The [MinDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTime.html) should be lesser than the [MaxDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTime.html) of the DateTimeEdit. When the MinDateTime is set, if the new [MinDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTime.html) value is greater than the [MaxDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTime.html), then the MaxDateTime will be reset to the MinDateTime.

## Maximum DateTime

The [MaxDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTime.html) helps you to restrict the DateTime value that is set greater than the specific DateTime value. If the [DateTime value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) of DateTimeEdit is greater than [MaxDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTime.html), then the DateTime property will be reset to MaxDateTime. The [MaxDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTime.html) should be greater than [MinDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTime.html) of the DateTimeEdit. When the MaxDateTime is set, if the [MinDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTime.html) property is greater than the new [MaxDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTime.html), then the MinDateTime will be reset to the MaxDateTime.

{% tabs %}

{% highlight xaml %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" DateTime="07/05/2010" MinDateTime="01/01/2010" MaxDateTime="07/15/2010"/>

{% endhighlight  %}

{% highlight c# %}

Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new Syncfusion.Windows.Shared.DateTimeEdit();
dateTimeEdit.Width = 200;
dateTimeEdit.Height = 25;
dateTimeEdit.DateTime = new DateTime(2010, 07, 05);
dateTimeEdit.MinDateTime = new DateTime(2010, 01, 01);
dateTimeEdit.MaxDateTime = new DateTime(2010, 07, 15);
dateTimeEdit.Pattern = DateTimePattern.LongDate;
this.LayoutRoot.Children.Add(dateTimeEdit);

{% endhighlight  %}

{% endtabs %}

![Setting minimum and maximum value in WPF DateTimeEdit](Maximum-and-Minimum-Value_images/wpf-datetimeedit-minimum-and-maximum.png)

### Detect the minimum and maximum value change

The DateTimeEdit notifies that the minimum and maximum value is changed through the [MinDateTimeChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTimeChanged_EV.html) and [MaxDateTimeChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTimeChanged_EV.html) event. You can use the **OldValue** and **NewValue** properties to get the old and new minimum / maximum date time value.

{% tabs %}

{% highlight C# %}

dateTimeEdit.MinDateTimeChanged += DateTimeEdit_MinDateTimeChanged;
dateTimeEdit.MaxDateTimeChanged += DateTimeEdit_MaxDateTimeChanged;

private void DateTimeEdit_MaxDateTimeChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    Console.WriteLine("MinDateTimeChanged event is fired"); 
}

private void DateTimeEdit_MinDateTimeChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    Console.WriteLine("MinDateTimeChanged event is fired"); 
}

{% endhighlight %}

{% endtabs %}
