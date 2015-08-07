---
layout: post
title: DateTime-Patterns
description: datetime patterns
platform: wpf
control: DateTimeEdit
documentation: ug
---

# DateTime Patterns

You can customize the display format of the date in the DateTimeEdit control by using the Pattern and CustomPattern properties.

## Pattern

The date patterns supported by the DateTimeEdit control can be classified into the following eleven patterns: 

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

The pattern is set by using the Pattern property. The following code snippet illustrates how to set the pattern as FullDateTime:



{% highlight html %}
XAML

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200"                          DateTime="07/15/2010" Pattern="ShortDate"></syncfusion:DateTimeEdit>
{% endhighlight  %}
{% highlight c# %}
C#


Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new                    Syncfusion.Windows.Shared.DateTimeEdit();dateTimeEdit.Width = 200;dateTimeEdit.Height = 25;dateTimeEdit.DateTime = new DateTime(2010, 07, 05);//Setting predefined patterndateTimeEdit.Pattern = DateTimePattern.ShortDate;
{% endhighlight  %}


![](DateTime-Patterns_images/DateTime-Patterns_img1.png)



## Custom Pattern

You can also set the custom pattern for displaying the date in the DateTimeEdit control by using the CustomPattern property.


{% highlight html %}

XAML

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200"                          DateTime="07/15/2010" Pattern="CustomPattern"                          CustomPattern="MM/dd/yy hh:mm:ss"></syncfusion:DateTimeEdit>
{% endhighlight %}
{% highlight c# %}
C#

Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new Syncfusion.Windows.Shared.DateTimeEdit();dateTimeEdit.Width = 200;dateTimeEdit.Height = 25;dateTimeEdit.DateTime = new DateTime(2010, 07, 05);dateTimeEdit.Pattern = DateTimePattern.CustomPattern;//Setting Custom PatterndateTimeEdit.CustomPattern = "MM/dd/yy hh:mm:ss";this.LayoutRoot.Children.Add(dateTimeEdit);
{% endhighlight %}


![](DateTime-Patterns_images/DateTime-Patterns_img2.png)



> Note: CustomPattern support can be enabled by setting the Pattern property to the DateTimePattern.CustomPattern.


