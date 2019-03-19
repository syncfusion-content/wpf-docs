---
layout: post
title: DateTime Format | DateTimeEdit | wpf | Syncfusion
description: datetime format
platform: wpf
control: DateTimeEdit
documentation: ug
---

# DateTime Format

[DateTimeFormat](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~DateTimeFormat.html) property defines the Format to display the date value in the DateTimeEdit control. Using this property you can customize the Standard datetime formats such as the YearMonthPattern, ShortTimePattern, ShortDatePattern, MonthDayPattern, LongTimePattern, LongDatePattern, and FullDateTimePattern. 

{% tabs %}

{% highlight XAML %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" DateTime="07/15/2010" Pattern="ShortDate">    
<syncfusion:DateTimeEdit.DateTimeFormat>        
<global:DateTimeFormatInfo ShortDatePattern="MM/dd/yy hh:mm:ss"/>    
</syncfusion:DateTimeEdit.DateTimeFormat>
</syncfusion:DateTimeEdit>

{% endhighlight  %}

{% highlight C# %}

Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new Syncfusion.Windows.Shared.DateTimeEdit();
dateTimeEdit.Width = 200;
dateTimeEdit.Height = 25;
dateTimeEdit.DateTime = new DateTime(2010, 07, 05);
dateTimeEdit.Pattern = DateTimePattern.ShortDate;
dateTimeEdit.DateTimeFormat = new DateTimeFormatInfo()
{    
	ShortDatePattern = "MM/dd/yy hh:mm:ss"
};

{% endhighlight  %}

{% endtabs %} 

![DateTime format](DateTime-Format_images/DateTime-Format_img1.png)