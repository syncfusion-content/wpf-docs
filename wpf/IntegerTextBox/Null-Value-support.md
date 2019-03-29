---
layout: post
title: Null Value support | IntegerTextBox | wpf | Syncfusion
description: null value support
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Null Value Support

IntegerTextBox accepts null values. To enable the null option you have to set the [UseNullOption](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~UseNullOption.html) property to true. You can also set the NullValue property for the integer textbox. When you set the null value to the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~Value.html) property, by default the value of the NullValue (Default value is null) property will be assigned to the Value property. 

{%tabs%}
{% highlight xaml %} <syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150"                             UseNullOption="True" NullValue="1"/>{% endhighlight %}

{% highlight C# %} Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();integerTextBox.Width = 150;integerTextBox.Height = 25;integerTextBox.UseNullOption = true;integerTextBox.NullValue = 1;{% endhighlight %}

{%endtabs%}

In this sample, the NullValue (NullValue = 1) is set to the Value property of the IntegerTextBox because the default value of the Value property is null.

![Null value support](Null-Value-support_images/Null-Value-support_img1.png)



{%tabs%}
{% highlight xaml %} <syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150"                             UseNullOption="True" NullValue="{x:Null}"/>{% endhighlight %}

{% highlight C# %} Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();integerTextBox.Width = 150;integerTextBox.Height = 25;integerTextBox.UseNullOption = true;integerTextBox.NullValue = null;{% endhighlight %}
{%endtabs%}


In this sample, the NullValue (NullValue = null) is set to the Value property of the IntegerTextBox because the default value of the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~Value.html) property is null.

![Null value support](Null-Value-support_images/Null-Value-support_img2.png)



{%seealso%}

Minimum and Maximum Value

Binding Support
{%endseealso%}
