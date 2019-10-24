---
layout: post
title: Events | DateTimeEdit | wpf | Syncfusion
description: events
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Events

DateTimeEdit control exposes the following events:

## DateTimeChanged

This [DateTimeChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTimeChanged_EV.html) event occurs when the [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~DateTime.html) property of the DateTimeEdit control is changed.

{% tabs %}
{% highlight XAML %}

<syncfusion:DateTimeEdit Width="150" DateTimeChanged="DateTimeEdit_DateTimeChanged"/>

{% endhighlight  %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void DateTimeEdit_DateTimeChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)        {        }

{% endhighlight  %}
{% endtabs %}

## MinDateTimeChanged

This [MinDateTimeChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTimeChanged_EV.html) event occurs when the [MinDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MinDateTime.html) property of the DateTimeEdit control is changed.

{% tabs %}

{% highlight XAML %}

<syncfusion:DateTimeEdit Width="150" MinDateTimeChanged="DateTimeEdit_MinDateTimeChanged"/>

{% endhighlight  %}

{% endtabs %}

You can handle the event as follows:

{% tabs %}

{% highlight C# %}

private void DateTimeEdit_MinDateTimeChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)        {        }

{% endhighlight %}

{% endtabs %}

## MaxDateTimeChanged

This [MaxDateTimeChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTimeChanged_EV.html) event occurs when the [MaxDateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~MaxDateTime.html) property of the DateTimeEdit control is changed.

{% tabs %}
{% highlight XAML %}

<syncfusion:DateTimeEdit Width="150" MaxDateTimeChanged="DateTimeEdit_MaxDateTimeChanged"/>

{% endhighlight  %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void DateTimeEdit_MaxDateTimeChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)        
{        
}

{% endhighlight  %}
{% endtabs %}

## PatternChanged

This event occurs when the [Pattern](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~Pattern.html) property of the DateTimeEdit control is changed.

{% tabs %}
{% highlight XAML %}

<syncfusion:DateTimeEdit Width="150" PatternChanged="DateTimeEdit_PatternChanged"/>

{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}

{% highlight C# %}

private void DateTimeEdit_PatternChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)        
{  
}

{% endhighlight  %}

{% endtabs %}

## CalendarPopupOpened

This [CalendarPopupOpened](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeEdit~CalendarPopupOpened_EV.html) event occurs when the Calendar popup is open.

{% tabs %}
{% highlight XAML %}

<syncfusion:DateTimeEdit Height="25" Width="150" EnableClassicStyle="True" CalendarPopupOpened="DateTimeEdit_CalendarPopupOpened"/>

{% endhighlight  %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void DateTimeEdit_CalendarPopupOpened(object sender, RoutedEventArgs e)        
{        
}

{% endhighlight %}
{% endtabs %}
