---
layout: post
title: DateTime formatting in WPF DateTimePicker control | Syncfusion
description: Learn here all about DateTime formatting support in Syncfusion WPF DateTimePicker (DateTimeEdit) control and more.
platform: wpf
control: DateTimeEdit
documentation: ug
---

# DateTime formatting in WPF DateTimePicker (DateTimeEdit)

you can specify the selected datetime display format in the [DateTimeEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DateTimeEdit.html) by using the predefined patterns and custom patterns.

## Predefined display patterns

You can display the selected date time in the predefined patterns
by setting the pattern value to the [Pattern](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DateTimeBase.html#Syncfusion_Windows_Shared_DateTimeBase_Pattern) property. The default value of `Pattern` property is `ShortDate`.

The `DateTimeEdit` control supports the following patterns:
* LongDate 
* LongTime 
* ShortDate 
* ShortTime 
* FullDateTime 
* MonthDay 
* CustomPattern 
* ShortableDateTime 
* UniversalShortableDateTime 
* RFC1123 
* YearMonth 

![Setting date time pattern in WPF DateTimeEdit](Getting-Started_images/wpf-datetimeedit-pattern.png)

{% tabs %}
{% highlight XAML %}

<syncfusion:DateTimeEdit Pattern="FullDateTime" 
                         Name="dateTimeEdit" />


{% endhighlight  %}
{% highlight C# %}

DateTimeEdit dateTimeEdit = new DateTimeEdit();
dateTimeEdit.Pattern = DateTimePattern.FullDateTime;

{% endhighlight %}
{% endtabs %}

![Setting full date time pattern in WPF DateTimeEdit](DateTime-Format_images/wpf-datetimeedit-fulldatetime-pattern.png)

N> View [Sample](https://github.com/SyncfusionExamples/wpf-datetimepicker-examples/tree/master/Samples/DateTimeFormatting) in GitHub

### Pattern Changed notification

The `DateTimeEdit` notifies that the pattern is changed through the [PatternChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DateTimeBase.html) event. You can get the old and new pattern by using the `OldValue` and `NewValue` properties in the `PatternChanged` event.

{% tabs %}
{% highlight C# %}

DateTimeEdit dateTimeEdit = new DateTimeEdit();
dateTimeEdit.PatternChanged += DateTimeEdit_PatternChanged;

private void DateTimeEdit_PatternChanged(DependencyObject d, DependencyPropertyChangedEventArgs e) {
    //Get old and new pattern values
    var oldPattern = e.OldValue;
    var newPattern = e.NewValue;
}

{% endhighlight %}
{% endtabs %}

## Change datetime format

you can change the date time format by using the [DateTimeFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DateTimeBase.html#Syncfusion_Windows_Shared_DateTimeBase_DateTimeFormat)  property. The default value of `` property is ``.

{% tabs %}
{% highlight XAML %}

<syncfusion:DateTimeEdit Name="dateTimeEdit">
    <syncfusion:DateTimeEdit.DateTimeFormat>
        <global:DateTimeFormatInfo ShortDatePattern="MM/dd/yy hh:mm:ss"/>
    </syncfusion:DateTimeEdit.DateTimeFormat>
</syncfusion:DateTimeEdit>

{% endhighlight  %}
{% highlight C# %}

DateTimeEdit dateTimeEdit = new DateTimeEdit();
dateTimeEdit.DateTimeFormat = new DateTimeFormatInfo()
{ 
    ShortDatePattern = "MM/dd/yy hh:mm:ss" 
};

{% endhighlight %}
{% endtabs %}

![Setting datetime format for WPF DateTimeEdit](DateTime-Format_images/wpf-datetimeedit-DateTimeFormat.png)

N> View [Sample](https://github.com/SyncfusionExamples/wpf-datetimepicker-examples/tree/master/Samples/DateTimeFormatting) in GitHub

## Custom display pattern

You can also set the custom pattern for displaying the datetime in the `DateTimeEdit` control by using the [CustomPattern](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DateTimeBase.html#Syncfusion_Windows_Shared_DateTimeBase_CustomPattern) property. You can enable the custom display pattern by setting the `Pattern` property value as `CustomPattern`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DateTimeEdit CustomPattern="MM**dd**yy" 
                         Pattern="CustomPattern" 
                         Name="dateTimeEdit" />


{% endhighlight  %}
{% highlight C# %}

DateTimeEdit dateTimeEdit = new DateTimeEdit();
dateTimeEdit.CustomPattern = "MM**dd**yy";
dateTimeEdit.Pattern = DateTimePattern.CustomPattern;

{% endhighlight %}
{% endtabs %}

![Setting custom pattern in WPF DateTimeEdit](DateTime-Format_images/wpf-datetimeedit-custom-pattern.png)

N> View [Sample](https://github.com/SyncfusionExamples/wpf-datetimepicker-examples/tree/master/Samples/DateTimeFormatting) in GitHub

### Custom pattern Changed notification

The `DateTimeEdit` notifies that the custom pattern is changed through the [CustomPatternChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DateTimeBase.html) event. You can get the old and new custom pattern by using the `OldValue` and `NewValue` properties in the `CustomPatternChanged` event.

{% tabs %}
{% highlight C# %}

DateTimeEdit dateTimeEdit = new DateTimeEdit();
dateTimeEdit.CustomPatternChanged += dateTimeEdit_CustomPatternChanged;

private void dateTimeEdit_CustomPatternChanged(DependencyObject d, DependencyPropertyChangedEventArgs e) {
    //Get old and new custom pattern values
    var oldCustomPattern = e.OldValue;
    var newCustomPattern = e.NewValue;
}

{% endhighlight %}
{% endtabs %}

N> View [Sample](https://github.com/SyncfusionExamples/wpf-datetimepicker-examples/tree/master/Samples/DateTimeFormatting) in GitHub

## Change culture 

By default, the `DateTimeEdit` supports system’s current culture. You can change the culture of `DateTimeEdit` by using the [CultureInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.DateTimeBase.html#Syncfusion_Windows_Shared_DateTimeBase_CultureInfo) property. Based on the value of `CultureInfo` property, `DateTimeEdit` control elements localized.

![Setting various culture in WPF DateTimeEdit](DateTime-Format_images/wpf-datetimeedit-culture1.png)

{% tabs %}
{% highlight XAML %}

<syncfusion:DateTimeEdit CultureInfo="en-US" 
                         Pattern="FullDateTime"
                         Name="dateTimeEdit" />


{% endhighlight  %}
{% highlight C# %}

DateTimeEdit dateTimeEdit = new DateTimeEdit();
dateTimeEdit.CultureInfo = new CultureInfo("fr-FR");
dateTimeEdit.Pattern = DateTimePattern.FullDateTime;

{% endhighlight %}
{% endtabs %}

![Setting US culture in WPF DateTimeEdit](DateTime-Format_images/wpf-datetimeedit-culture.png)

N> View [Sample](https://github.com/SyncfusionExamples/wpf-datetimepicker-examples/tree/master/Samples/DateTimeFormatting) in GitHub
