---
layout: post
title: Culture-and-Number-Formats
description: culture and number formats
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Culture and Number Formats

## Culture

DoubleTextBox provides globalization support through the Culture property. 

{% highlight xml %}
 <syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="150"  Culture="en-US" Value="1234567"/>
 {% endhighlight %} 
{% highlight C# %} 
Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new Syncfusion.Windows.Shared.DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 1234567;
doubleTextBox.Culture = new CultureInfo("en-US");
{% endhighlight %}


![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img1.png)


{% highlight xml %}
 <syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="150" Culture="bs-Latn" Value="1234567"/>
 {% endhighlight %}

{% highlight C# %}
 Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new Syncfusion.Windows.Shared.DoubleTextBox();
 doubleTextBox.Width = 150;doubleTextBox.Height = 25;
 doubleTextBox.Value = 1234567;
 doubleTextBox.Culture = new CultureInfo("bs-Latn");
 {% endhighlight %}


![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img2.png)





In the first sample culture is set to “en-US” (US Culture) in the second sample culture is set to “bs-Latn” (Latin Culture). The US culture uses “,” as the NumberGroupSeparator and the Latin culture uses “.” as the NumberGroupSeparator. When you change the Culture property the Value is formatted based on the Culture.

## Number Format

You can customize the Number Format either by using the NumberFormat property or the NumberGroupSeparator, NumberGroupSizes, NumberDecimalDigits, and NumberDecimalSeparator properties.


{% highlight xml %}
 <syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="200"  Value="123456789012345"> 
 <syncfusion:DoubleTextBox.NumberFormat>   
 <numberformat:NumberFormatInfo NumberGroupSeparator="/" NumberDecimalDigits="4"  NumberDecimalSeparator="*"/>
 </syncfusion:DoubleTextBox.NumberFormat></syncfusion:DoubleTextBox> 
 {% endhighlight %} 

{% highlight C# %} 
Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new  Syncfusion.Windows.Shared.DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.Value = 1234567;
doubleTextBox.NumberFormat = new NumberFormatInfo(){ NumberGroupSeparator = "/", NumberDecimalDigits = 4, NumberDecimalSeparator = "*" };
 {% endhighlight %} 


![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img3.png)


{% highlight xml %}
<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="200"  Value="123456789012345" NumberGroupSeparator="/"  NumberDecimalDigits="4" NumberDecimalSeparator="*"/>
 {% endhighlight %}

{% highlight C# %} 
Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new Syncfusion.Windows.Shared.DoubleTextBox();
doubleTextBox.Width = 150;doubleTextBox.Height = 25;
doubleTextBox.Value = 1234567;
doubleTextBox.NumberGroupSeparator = "/";
doubleTextBox.NumberDecimalSeparator = "*";
doubleTextBox.NumberDecimalDigits = 4;
{% endhighlight %} 


![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img4.png)



