---
layout: post
title: Null Value support| PercentTextBox  | Wpf | Syncfusion
description: null value support
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Null Value Support

PercentTextBox accepts null values. To enable the null option you have to set the UseNullOption property to true. You can also set the NullValue property for the PercentTextBox. When you set the null value to the PercentValue property, by default the value of the NullValue (Default value is null) property will be assigned to the PercentValue property. 

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="150" 
                           UseNullOption="True" NullValue="1"/>
						   {% endhighlight %}
				

{% highlight c# %} 
PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 150;
percentTextBox.Height = 25;
percentTextBox.UseNullOption = true;
percentTextBox.NullValue = 1;
{% endhighlight %}
{% endtabs %}


In this sample, the NullValue (NullValue = 1) is set to the Value property of the PercentTextBox because the default value of the PercentValue property is zero.

![](Null-Value-support_images/Null-Value-support_img1.png)


{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="150"  
                          UseNullOption="True" NullValue="{x:Null}"/>
						  {% endhighlight %}
				

{% highlight c# %}
PercentTextBox percentTextBox = new PercentTextBox();
percentTextBox.Width = 150;
percentTextBox.Height = 25;
percentTextBox.UseNullOption = true;
percentTextBox.NullValue = null;
{% endhighlight %}
{% endtabs %}


In this sample, the NullValue (NullValue = null) is set to the Value property of the PercentTextBox. (Default value of the PercentValue property is zero).

![](Null-Value-support_images/Null-Value-support_img2.png)


