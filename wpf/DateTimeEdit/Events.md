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

This event occurs when the DateTime property of the DateTimeEdit control is changed.

{% highlight html %}

<syncfusion:DateTimeEdit Width="150" DateTimeChanged="DateTimeEdit_DateTimeChanged"/>

{% endhighlight  %}

You can handle the event as follows:

{% highlight c# %}

private void DateTimeEdit_DateTimeChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)        {        }

{% endhighlight  %}

## MinDateTimeChanged

This event occurs when the MinDateTime property of the DateTimeEdit control is changed.

{% highlight html %}

<syncfusion:DateTimeEdit Width="150" MinDateTimeChanged="DateTimeEdit_MinDateTimeChanged"/>

{% endhighlight  %}

You can handle the event as follows:

{% highlight c# %}

private void DateTimeEdit_MinDateTimeChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)        {        }

{% endhighlight %}

## MaxDateTimeChanged

This event occurs when the MaxDateTime property of the DateTimeEdit control is changed.

{% highlight xaml %}

<syncfusion:DateTimeEdit Width="150" MaxDateTimeChanged="DateTimeEdit_MaxDateTimeChanged"/>

{% endhighlight  %}

You can handle the event as follows:

{% highlight c# %}

private void DateTimeEdit_MaxDateTimeChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)        
{        
}

{% endhighlight  %}

## PatternChanged

This event occurs when the Pattern property of the DateTimeEdit control is changed.

{% highlight xaml %}

<syncfusion:DateTimeEdit Width="150" PatternChanged="DateTimeEdit_PatternChanged"/>

{% endhighlight %}

You can handle the event as follows:

{% highlight c# %}

private void DateTimeEdit_PatternChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)        {        }

{% endhighlight  %}

## CalendarPopupOpened

This event occurs when the Calendar popup is open.

{% highlight xaml %}

<syncfusion:DateTimeEdit Height="25" Width="150" EnableClassicStyle="True" CalendarPopupOpened="DateTimeEdit_CalendarPopupOpened"/>

{% endhighlight  %}

You can handle the event as follows:

{% highlight c# %}

private void DateTimeEdit_CalendarPopupOpened(object sender, RoutedEventArgs e)        
{        
}

{% endhighlight %}