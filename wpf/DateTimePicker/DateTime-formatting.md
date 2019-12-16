---
layout: post
title: WPF DateTimeEdit DateTime Format | Syncfusion
description: This section describes how to display the date time information in the DateTimeEdit control using predefined patterns and custom pattern.
platform: wpf
control: DateTimeEdit
documentation: ug
---

# DateTime formatting

The DateTime [Pattern](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~Pattern.html) helps you to specify the date-time display pattern for the `DateTimeEdit` control. The display format of the date in the `DateTimeEdit` control can be customized by the [Pattern](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~Pattern.html) and [CustomPattern](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~CustomPattern.html) properties.

## Predefined display patterns

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

The different display formats of the DateTime can be set by the [Pattern](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~Pattern.html) property. Also, the DateTimeEdit notifies that the pattern is changed through the [PatternChanged](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~PatternChanged_EV.html) event. You can use the **OldValue** and **NewValue** properties to get the old and new pattern in the **PatternChanged** event. The following code snippet illustrates how to set the format as FullDateTime:

{% tabs %}

{% highlight XAML %}

<Grid x:Name="grid">
   <!--Setting FullDateTime Pattern-->
   <syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="235" 
                            DateTime="7/15/2019" Pattern="FullDateTime"
                            PatternChanged="DateTimeEdit_PatternChanged" />
</Grid>

{% endhighlight  %}

{% highlight C# %}

Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new  Syncfusion.Windows.Shared.DateTimeEdit();

public MainWindow()
{
    InitializeComponent();
    dateTimeEdit.Width = 235;
    dateTimeEdit.Height = 25;
    dateTimeEdit.DateTime = new DateTime(2019, 7, 15);
   
    //Setting predefined FullDateTime pattern
    dateTimeEdit.Pattern = DateTimePattern.FullDateTime;

    // Invoked pattern changed event
    dateTimeEdit.PatternChanged += DateTimeEdit_PatternChanged;

    this.grid.Children.Add(dateTimeEdit);
}

private void DateTimeEdit_PatternChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
   Console.WriteLine("PatternChanged event is fired"); 
}

{% endhighlight  %}

{% endtabs %} 

![Setting full date time pattern in WPF DateTimeEdit](DateTime-Format_images/wpf-datetimeedit-fulldatetime-pattern.png)

## Custom display pattern

You can also set the custom pattern for displaying the date in the DateTimeEdit control by using the [CustomPattern](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~CustomPattern.html) property. Also, the DateTimeEdit notifies that the custom pattern is changed through the [CustomPatternChanged](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~CustomPatternChanged_EV.html) event. You can use the **OldValue** and **NewValue** properties to get the old and new custom pattern in the **CustomPatternChanged** event.

{% tabs %}

{% highlight XAML %}

<Grid x:Name="grid">
    <syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" 
                             DateTime="7/15/2019" CustomPatternChanged="DateTimeEdit_CustomPatternChanged" 
                             Pattern="CustomPattern" CustomPattern="MM**dd**yy" />
</Grid>

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new Syncfusion.Windows.Shared.DateTimeEdit();

public MainWindow()
{
    InitializeComponent();
    dateTimeEdit.Width = 200;
    dateTimeEdit.Height = 25;
    dateTimeEdit.DateTime = new DateTime(2019, 7, 15);
    dateTimeEdit.Pattern = DateTimePattern.CustomPattern;

    //Setting Custom Pattern
    dateTimeEdit.CustomPattern = "MM**dd**yy";

    // Invoked CustomPatternChanged event of DateTimeEdit
    dateTimeEdit.CustomPatternChanged += DateTimeEdit_CustomPatternChanged;

    this.grid.Children.Add(dateTimeEdit);
}

private void DateTimeEdit_CustomPatternChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    Console.WriteLine("CustomPatternChanged event is fired"); 
}

{% endhighlight %}

{% endtabs %} 

![Setting custom pattern in WPF DateTimeEdit](DateTime-Format_images/wpf-datetimeedit-custom-pattern.png)

N>[CustomPattern](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~CustomPattern.html) support can be enabled by setting the [Pattern](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~Pattern.html) property to the DateTimePattern.CustomPattern.

## Change culture 

The DateTimeEdit control provides globalization support that allows you to design and develop a world-ready application that supports localized interfaces and regional data for users in multiple cultures. By default, the DateTimeEdit supports system’s current culture. You can change the culture of DateTimeEdit by using the [CultureInfo](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~CultureInfo.html) property. 

{% tabs %}

{% highlight XAML %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" 
                         DateTime="7/15/2019" Pattern="LongDate" 
                         CultureInfo="en-US" />

{% endhighlight  %}

{% highlight C# %}

Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new Syncfusion.Windows.Shared.DateTimeEdit();
dateTimeEdit.Width = 200;
dateTimeEdit.Height = 25;
dateTimeEdit.DateTime = new DateTime(2019, 7, 15);
dateTimeEdit.Pattern = DateTimePattern.LongDate;
dateTimeEdit.CultureInfo = new CultureInfo("en-US");

{% endhighlight  %}

{% endtabs %} 


![Setting culture in WPF DateTimeEdit](DateTime-Format_images/wpf-datetimeedit-culture.png)

{% tabs %}

{% highlight XAML %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" 
                         DateTime="7/15/2019" Pattern="LongDate" 
                         CultureInfo="fr-FR" />

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new  Syncfusion.Windows.Shared.DateTimeEdit();
dateTimeEdit.Width = 200;
dateTimeEdit.Height = 25;
dateTimeEdit.DateTime = new DateTime(2019, 7, 15);
dateTimeEdit.Pattern = DateTimePattern.LongDate;
dateTimeEdit.CultureInfo = new CultureInfo("fr-FR");

{% endhighlight  %}

{% endtabs %} 

![Setting french culture in WPF DateTimeEdit](DateTime-Format_images/wpf-datetimeedit-french-culture.png)

N> Download demo application from [GitHub](https://github.com/SyncfusionExamples/wpf-date-time-edit-examples/tree/master/Samples/DateTimeFormatting)