---
layout: post
title: Culture-and-Number-Formats
description: culture and number formats
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Culture and Number Formats

## Culture

IntegerTextBox provides globalization support through the Culture property. 

{% highlight xml %} <syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150" Culture="en-US" Value="1234567"/>
{% endhighlight %}

{% highlight C# %} 
Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();
integerTextBox.Width = 150;integerTextBox.Height = 25;
integerTextBox.Value = 1234567;
integerTextBox.Culture = new System.Globalization.CultureInfo("en-US");
{% endhighlight %}


![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img1.png)


{% highlight xml %} 
<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150" Culture="bs-Latn" Value="1234567"/>
{% endhighlight %}
{% highlight C# %} 
Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();
integerTextBox.Width = 150;integerTextBox.Height = 25;integerTextBox.Value = 1234567;
integerTextBox.Culture = new System.Globalization.CultureInfo("bs-Latn");
{% endhighlight %}


![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img2.png)



In the first sample culture is set to “en-US” (US Culture) and in the second sample culture is set to “bs-Latn” (Latin Culture). The US culture uses “,” as the NumberGroupSeparator and the Latin culture uses “.” as the NumberGroupSeparator. When you change the Culture property the Value is formatted based on the Culture.

## Number Format

You can customize the Number Format either by using the NumberFormat property or the NumberGroupSeparator and the NumberGroupSizes property.

{% highlight xml %}
<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150" Culture="en-US" Value="123456789012345">
     <syncfusion:IntegerTextBox.NumberFormat>      
	 <numberformat:NumberFormatInfo NumberGroupSeparator="/"/> 
	 </syncfusion:IntegerTextBox.NumberFormat>
</syncfusion:IntegerTextBox>
{% endhighlight %}
{% highlight C# %} 
Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();
integerTextBox.Width = 150;integerTextBox.Height = 25;integerTextBox.Value = 1234567;
integerTextBox.Culture = new System.Globalization.CultureInfo("en-US");
integerTextBox.NumberFormat = new System.Globalization.NumberFormatInfo() {NumberGroupSeparator = "/" };
{% endhighlight %}


![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img3.png)


{% highlight xml %} 
<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150" Culture="en-US" Value="123456789012345" NumberGroupSeparator="/"/>
{% endhighlight %}
{% highlight C# %}
 Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();
 integerTextBox.Width = 150;integerTextBox.Height = 25;
 integerTextBox.Value = 1234567;integerTextBox.Culture = new System.Globalization.CultureInfo("en-US");
 integerTextBox.NumberGroupSeparator = "/";
 {% endhighlight %}


![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img4.png)



You can also change the NumberGroupSizes by using the NumberGroupSizes property.

Here is a sample for setting the NumberGroupSizes by using the NumberFormat property.

{% highlight C# %}



Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();

integerTextBox.Width = 150;

integerTextBox.Height = 25;

integerTextBox.Value = 123456789012345;

integerTextBox.NumberFormat = new System.Globalization.NumberFormatInfo() { 

                              NumberGroupSeparator = "/", 

                              NumberGroupSizes = new int[] { 2, 3, 4 } };


{% endhighlight %}

![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img5.png)



Here is a sample for setting the NumberGroupSizes by using the NumberGroupSizes property of the integer textbox:

{% highlight C# %}



Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();

integerTextBox.Width = 150;

integerTextBox.Height = 25;

integerTextBox.Value = 123456789012345;

integerTextBox.NumberGroupSeparator = "/";

integerTextBox.NumberGroupSizes = new Int32Collection() { 2, 3, 0 };

{% endhighlight %}

![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img6.png)



