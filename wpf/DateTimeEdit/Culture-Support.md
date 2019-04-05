---
layout: post
title: Culture Support | DateTimeEdit | wpf | Syncfusion
description: culture support
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Culture Support

DateTimeEdit control provides globalization support through the [CultureInfo](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DateTimeBase~CultureInfo.html) property. 

{% tabs %}

{% highlight XAML %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" DateTime="07/15/2010" Pattern="LongDate" CultureInfo="en-US"/>

{% endhighlight  %}

{% highlight C# %}

Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new Syncfusion.Windows.Shared.DateTimeEdit();
dateTimeEdit.Width = 200;
dateTimeEdit.Height = 25;
dateTimeEdit.DateTime = new DateTime(2010, 07, 05);
dateTimeEdit.Pattern = DateTimePattern.LongDate;
dateTimeEdit.CultureInfo = new CultureInfo("en-US");

{% endhighlight  %}

{% endtabs %} 


![Culture support](Culture-Support_images/Culture-Support_img1.png)

{% tabs %}

{% highlight XAML %}

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" DateTime="07/15/2010" Pattern="LongDate" CultureInfo="fr-FR"/>

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.DateTimeEdit dateTimeEdit = new  Syncfusion.Windows.Shared.DateTimeEdit();
dateTimeEdit.Width = 200;
dateTimeEdit.Height = 25;
dateTimeEdit.DateTime = new DateTime(2010, 07, 05);
dateTimeEdit.Pattern = DateTimePattern.LongDate;
dateTimeEdit.CultureInfo = new CultureInfo("fr-FR");

{% endhighlight  %}

{% endtabs %} 

![Culture support](Culture-Support_images/Culture-Support_img2.png)

As you have seen in these samples whenever you change the Culture property the Date is displayed based on the Culture.