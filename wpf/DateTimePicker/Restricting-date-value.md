---
layout: post
title: WPF DateTimeEdit Minimum and Maximum value | Syncfusion
description: This section describes how to restrict users to choose a date within maximum and minimum values in the DateTimeEdit control.
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Restricting date value

This section explains how to change the [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) value of DateTimeEdit control. And also to select a date and time in a particular range by specifying [minimum](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTime.html) and [maximum](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTime.html) dates in DateTimeEdit control.

## Changing date value 

The DateTimeEdit allows the end-user to change the value using the [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) property. 

### Binding date value

Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source -> target or target <- source)or bidirectional (source <-> target). By assigning a value to the **DateTime** property by binding, you can change the DateTimeEdit value.

The following code snippets illustrate the value binding from one DateTimeEdit to another.

{% tabs %}

{% highlight XAML %}

<StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">
    <syncfusion:DateTimeEdit x:Name="dateTimeEdit1" Height="25" Width="200" DateTime="{Binding Path=MyValue,Mode=TwoWay, UpdateSourceTrigger=PropertyChanged}"/>
    <syncfusion:DateTimeEdit x:Name="dateTimeEdit2" Height="25" Width="200" DateTime="{Binding ElementName=dateTimeEdit1, Path=DateTime,Mode=TwoWay}" Margin="10"/>
</StackPanel>

{% endhighlight %}

{% highlight C# %}

class ViewModel : NotificationObject
{
    private DateTime myValue = new DateTime(2010, 7, 15);
    public DateTime MyValue
    {
        get
        {
            return myValue;
        }
        set
        {
            myValue = value;
            RaisePropertyChanged("MyValue");
        }
    }
}

{% endhighlight %}

{% endtabs %}

![WPF DateTimeEdit binding support](Maximum-and-Minimum-Value_images/wpf-datetimeedit-binding.png)

### Value change notification

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

## Setting the null value

The `DateTimeEdit` control accepts null values. The [NullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~NullValue.html) support in the DateTimeEdit control can be enabled by setting the [IsEmptyDateEnabled](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~IsEmptyDateEnabled.html) property to `true` and [ShowMaskOnNullValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~ShowMaskOnNullValue.html) property to `false`. If the value is null and the editing text box is empty then the `Watermark` will be displayed as the text in the DateTimeEdi control.

{% tabs %}

{% highlight xaml %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" 
                         ShowMaskOnNullValue="False" NullValue="{x:Null}"
                         IsEmptyDateEnabled="True" />

{% endhighlight %}

{% endtabs %}

![WPF DateTimeEdit display null value](Watermark-Support_images/wpf-datetimeedit-null-value.png)

## Setting the watermark text

The DateTimeEdit control provides support to display a hint information using watermark text when the selected date is null. In addition, it also provides support to define null DateTime value. You can customize the watermark text using the [NoneDateText](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~NoneDateText.html) property of DateTimeEdit.

{% tabs %}

{% highlight xaml %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" 
                         ShowMaskOnNullValue="False" NullValue="{x:Null}"
                         IsEmptyDateEnabled="True" NoneDateText="Choose a date"/>

{% endhighlight %}

{% endtabs %}

![WPF DateTimeEdit watermark support](Watermark-Support_images/wpf-datetimeedit-watermark.png)

## Restricting date value

Prevents users from selecting a date and time in a particular range by specifying [minimum](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTime.html) and [maximum](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTime.html) dates in DateTimeEdit control. The Calendar also displays only the dates between the MinDateTime and MaxDateTime.

### Minimum date value

The [MinDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTime.html) helps you to restrict the DateTime value which is lesser than the specific DateTime value. If the [DateTime value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) of DateTimeEdit is less than **MinDateTime**, then the DateTime property will be reset to MinDateTime. The **MinDateTime** should be lesser than the [MaxDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTime.html) of the DateTimeEdit. When the MinDateTime is set, if the new **MinDateTime** value is greater than the **MaxDateTime**, then the MaxDateTime will be reset to the MinDateTime.

### Maximum date value

The [MaxDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTime.html) helps you to restrict the DateTime value that is set greater than the specific DateTime value. If the [DateTime value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) of DateTimeEdit is greater than **MaxDateTime**, then the DateTime property will be reset to MaxDateTime. The **MaxDateTime** should be greater than [MinDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTime.html) of the DateTimeEdit. When the MaxDateTime is set, if the **MinDateTime** property is greater than the new **MaxDateTime**, then the MinDateTime will be reset to the MaxDateTime.

{% tabs %}

{% highlight xaml %}

<!--Setting date range -->
<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" 
                         DateTime="07/05/2010" MinDateTime="07/01/2010" 
                         MaxDateTime="07/28/2010"/>

{% endhighlight  %}

{% highlight c# %}

dateTimeEdit.MinDateTime = new DateTime(2010, 01, 01);
dateTimeEdit.MaxDateTime = new DateTime(2010, 07, 28);

{% endhighlight  %}

{% endtabs %}

![Setting minimum and maximum value in WPF DateTimeEdit](Maximum-and-Minimum-Value_images/wpf-datetimeedit-minimum-and-maximum.png)

### Minimum Maximum value change notification

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

## Block particular dates 

You can restrict the user to select the date within some range by blocking the particular date in the `DateTimeEdit`. If you try to set the blackout dates as the selected datetime through editing or when pressing down arrow, it will reset the previous valid date from `StartDate` of blackout dates in `DateTimeEdit`. If you try to set the blackout dates as the selected datetime  by pressing down arrow, it will reset the next valid date from `EndDate` of blackout dates in `DateTimeEdit`.

N> If you try to set the `DateTime` value which contained in blackout dates collection or  try to add the selected `DateTime` value in blackout dates collection, its throws the `Specified argument was out of the range of valid values`.

{% tabs %}
{% highlight xaml %}

<syncfusion:DateTimeEdit Loaded="DateTimeEdit_Loaded" 
                         Name="dateTimeEdit"/>

{% endhighlight  %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

//Setting the blockout days
private void DateTimeEdit_Loaded(object sender, RoutedEventArgs e) {
    //Setting start and end range for blocking dates
    DateTime StartDate = new DateTime(DateTime.Now.Year, DateTime.Now.Month, 1);
    DateTime EndDate = new DateTime(DateTime.Now.Year, DateTime.Now.Month, DateTime.Now.Day - 2);
    Syncfusion.Windows.Controls.CalendarDateRange blackOutDays = new Syncfusion.Windows.Controls.CalendarDateRange() 
    {
        Start = StartDate, 
        End = EndDate
    };
    Syncfusion.Windows.Controls.Calendar calendar = dateTimeEdit.DateTimeCalender as Syncfusion.Windows.Controls.Calendar;
    calendar.BlackoutDates.Add(blackOutDays);
}

{% endhighlight  %}
{% endtabs %}

![Block particular dates in WPF DateTimeEdit](Maximum-and-Minimum-Value_images/BlackOutDays.gif)

N> View [Sample](https://github.com/SyncfusionExamples/wpf-date-time-edit-examples/tree/master/Samples/BlackOutdates) in GitHub

## ReadOnly 

The DateTimeEdit cannot allow the user input, edits when **IsReadOnly** property is sets to true. However, value can be changed programmatically in readonly mode.

{% tabs %}

{% highlight xaml %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit1" Height="25" Width="200" 
                         DateTime="7/15/2010" IsReadOnly="True"/>

{% endhighlight  %}

{% highlight c# %}

dateTimeEdit.IsReadOnly = true;

{% endhighlight  %}

{% endtabs %}

![WPF DateTimeEdit read only mode](Maximum-and-Minimum-Value_images/wpf-datetimeedit-read-only-mode.png)