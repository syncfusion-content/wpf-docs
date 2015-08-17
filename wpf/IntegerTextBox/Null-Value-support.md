---
layout: post
title: Null-Value-support
description: null value support
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Null Value support

IntegerTextBox accepts null values. To enable the null option you have to set the UseNullOption property to true. You can also set the NullValue property for the integer textbox. When you set the null value to the Value property, by default the value of the NullValue (Default value is null) property will be assigned to the Value property. 

<table>
<tr>
<td>
{% highlight xml %} <syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150"                             UseNullOption="True" NullValue="1"/>{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight C# %} Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();integerTextBox.Width = 150;integerTextBox.Height = 25;integerTextBox.UseNullOption = true;integerTextBox.NullValue = 1;{% endhighlight %}</td></tr>
</table>


In this sample, the NullValue (NullValue = 1) is set to the Value property of the IntegerTextBox because the default value of the Value property is null.

![](Null-Value-support_images/Null-Value-support_img1.png)



<table>
<tr>
<td>
{% highlight xml %} <syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150"                             UseNullOption="True" NullValue="{x:Null}"/>{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight C# %} Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();integerTextBox.Width = 150;integerTextBox.Height = 25;integerTextBox.UseNullOption = true;integerTextBox.NullValue = null;{% endhighlight %}</td></tr>
</table>


In this sample, the NullValue (NullValue = null) is set to the Value property of the IntegerTextBox because the default value of the Value property is null.

![](Null-Value-support_images/Null-Value-support_img2.png)



See Also

Minimum and Maximum Value

Binding Support

