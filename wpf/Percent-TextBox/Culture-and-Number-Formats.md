---
layout: post
title: Culture and Number Formats| PercentTextBox  | Wpf | Syncfusion
description: culture and number formats
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Culture and Number Formats

## Culture

PercentTextBox provides globalization support through the Culture property. 

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="150"                       
   Culture="en-US" PercentValue="1234567"/>
   {% endhighlight %}


{% highlight C# %}
PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 150;percentTextBox.Height = 25;
percentTextBox.PercentValue = 1234567;
percentTextBox.Culture = new CultureInfo("en-US");
{% endhighlight %}
{% endtabs %}


![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img1.png)

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="150"    
                      Culture="bs-Latn" PercentValue="1234567"/>
					  {% endhighlight %}
			

{% highlight C# %}
PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 150;percentTextBox.Height = 25;
percentTextBox.PercentValue = 1234567;
percentTextBox.Culture = new CultureInfo("bs-Latn");
{% endhighlight %}
{% endtabs %}


![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img2.png)


As you have seen in these samples whenever you change the Culture property the PercentValue is formatted based on the Culture.

## Number format

You can customize the Number Format either by using the Number Format property or the PercentGroupSeparator, PercentGroupSizes, PercentDecimalDigits, PercentDecimalSeparator, PercentNegativePattern, PercentPositivePattern, and PercentageSymbol properties.

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="150"    
         PercentValue="1234567">    <syncfusion:PercentTextBox.NumberFormat>   
		 <numberformat:NumberFormatInfo PercentGroupSeparator="/"    
		 PercentDecimalDigits="4" PercentDecimalSeparator="*"      
		 PercentSymbol="%"/>    
		 </syncfusion:PercentTextBox.NumberFormat>
{% endhighlight %}
{% highlight C# %}
PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 150;percentTextBox.Height = 25;p
percentTextBox.PercentValue = 1234567;percentTextBox.NumberFormat = new NumberFormatInfo(){    PercentGroupSeparator = "/",    PercentDecimalDigits = 4,    PercentDecimalSeparator = "*",    PercentSymbol = "%"};
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="150"   
 PercentValue="1234567"          
 PercentageSymbol="%" PercentDecimalDigits="4"   
 PercentDecimalSeparator="*" PercentGroupSeparator="/"/>
						 {% endhighlight %}

{% highlight C# %}
PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 150;
percentTextBox.Height = 25;
percentTextBox.PercentValue = 1234567;percentTextBox.PercentageSymbol = "%";
percentTextBox.PercentDecimalDigits = 4;percentTextBox.PercentDecimalSeparator = "/";
percentTextBox.PercentGroupSeparator = "*";
{% endhighlight %}
{% endtabs %}


![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img3.png)


## PercentPositivePattern

Gets or sets the format pattern for the positive percent values. In the table displayed below “%” denotes the Percent symbol and n denotes the number.



<table>
<tr>
<th>
Value</th><th>
Associated Pattern</th></tr>
<tr>
<td>
0</td><td>
n %</td></tr>
<tr>
<td>
1</td><td>
n%</td></tr>
<tr>
<td>
2</td><td>
%n</td></tr>
<tr>
<td>
3</td><td>
% n</td></tr>
</table>

{% tabs %}
{% highlight xaml %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="150" 
            PercentValue="1234" PercentPositivePattern="3"/>

{% endhighlight %}
{% endtabs %}





![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img4.png)


## PercentNegativePattern

Gets or sets the format pattern for the negative percent values. In the table displayed below “%” denotes the Percent symbol and n denotes the number.



<table>
<tr>
<th>
Value</th><th>
Associated Pattern</th></tr>
<tr>
<td>
0</td><td>
-n %</td></tr>
<tr>
<td>
1</td><td>
-n%</td></tr>
<tr>
<td>
2</td><td>
-%n</td></tr>
<tr>
<td>
3</td><td>
%-n</td></tr>
<tr>
<td>
4</td><td>
%n-</td></tr>
<tr>
<td>
5</td><td>
n-%</td></tr>
<tr>
<td>
6</td><td>
n%-</td></tr>
<tr>
<td>
7</td><td>
-% n</td></tr>
<tr>
<td>
8</td><td>
n %-</td></tr>
<tr>
<td>
9</td><td>
% n-</td></tr>
<tr>
<td>
10</td><td>
% -n</td></tr>
<tr>
<td>
11</td><td>
n- %</td></tr>
</table>

{% tabs %}
{% highlight xaml %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="150" 
            PercentValue="1234" PercentNegativePattern="7"/>

{% endhighlight %}
{% endtabs %}





![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img5.png)


