---
layout: post
title: Culture and Number Formatting | UpDown | WPF | Syncfusion
description: Culture and Number Formatting
platform: wpf
control: UpDown
documentation: ug
---
# Culture and Number Formatting

The `UpDown` control provides globalization support by enabling to change the culture of the control by using the `Culture` property.

The Number formatting controls how a number is displayed in the `UpDown` control by specifying the culture-specific group separator, decimal separator, and the number of decimal digits to be used. It can also format the value of the `UpDown` control by using the `NumberFormatInfo` property.

## Culture

`Culture` can be set to `en-US` for the `UpDown` control as shown in the following code example. The U.S. culture uses “.” as the `NumberDecimalSeparator`.

{%tabs%}

{% highlight XAML %}
<syncfusion:UpDown Name="upDown" Culture="en-US" Width="100" Height="23" />



{% endhighlight %}

{% highlight C# %}
UpDown updown = new UpDown();

updown.Width = 100;

updown.Height = 23;

System.Globalization.CultureInfo cultureInfo = new System.Globalization.CultureInfo("en-US");

updown.Culture = cultureInfo;

Grid1.Children.Add(updown);



{% endhighlight %}

{% endtabs %} 

![](CultureandNumberFormatting-images/CultureandNumberFormatting-img1.jpeg)


`Culture` can also be set to `bs-Latn` for the `UpDown` control as shown in the following code example. The Latin culture uses “,” as the `NumberDecimalSeparator`.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Culture="bs-Latn" Width="100" Height="23" />



{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();

updown.Width = 100;

updown.Height = 23;

System.Globalization.CultureInfo cultureInfo = new System.Globalization.CultureInfo("bs-Latn");

updown.Culture = cultureInfo;

Grid1.Children.Add(updown);



{% endhighlight %}

{% endtabs %} 

![](CultureandNumberFormatting-images/CultureandNumberFormatting-img2.jpeg)


<table>
<tr>
<td>
**Property**<br/><br/></td><td>
**Description**<br/><br/></td><td>
**Type**<br/><br/></td><td>
**Data** **Type**<br/><br/></td></tr>
<tr>
<td>
Culture<br/><br/></td><td>
Gets or sets the CultureInfo.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
CultureInfo<br/><br/></td></tr>
</table>

## NumberFormatInfo

The `NumberFormatInfo` can be set for the `UpDown` control as shown in the following code example.

{% tabs %}

{% highlight XAML %}
<syncfusion:UpDown Name="upDown" Value="5555555">

<syncfusion:UpDown.NumberFormatInfo>

<globalization:NumberFormatInfo NumberGroupSeparator="/" NumberDecimalDigits="4" NumberDecimalSeparator="*"/>

</ syncfusion:UpDown.NumberFormatInfo>  

</ syncfusion:UpDown>



{% endhighlight %}

{% endtabs %} 

![](CultureandNumberFormatting-images/CultureandNumberFormatting-img3.jpeg)


## GroupSeperatorEnabled

`GroupSeperatorEnabled` feature helps to add the separator for the groups in the value of the `UpDown` control. By default its value is `false`.

The following code example explains to set the `GroupSeperatorEnabled` for the `UpDown` control:

{% tabs %}

{% highlight XAML %}
<syncfusion:UpDown Name="upDown" Width="100" Height="23" Value="1000000" GroupSeperatorEnabled="True" />





{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();

updown.Width = 100;

updown.Height = 23;

updown.Value = 1000000;

updown.GroupSeperatorEnabled = true;

Grid1.Children.Add(updown);  



{% endhighlight %}


{% endtabs %}
 
## Tables for NumberFormat Properties and Events of UpDown

<table>
<tr>
<td>
**Property**<br/><br/></td><td>
**Description**<br/><br/></td><td>
**Type**<br/><br/></td><td>
**Data** **Type**<br/><br/></td></tr>
<tr>
<td>
NumberFormatInfo<br/><br/></td><td>
Gets or sets the format of the number.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
NumberFormatInfo<br/><br/></td></tr>
</table>
<table>
<tr>
<td>
**Events**<br/><br/></td><td>
**Description**<br/><br/></td><td>
**Arguments**<br/><br/></td><td>
**Type******<br/><br/></td></tr>
<tr>
<td>
NumberFormatInfoChanged<br/><br/></td><td>
Occurs when the format of the number changes.<br/><br/></td><td>
DependencyObject and DependencyPropertyChangedEventArgs.<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td></tr>
</table>
