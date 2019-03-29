---
layout: post
title: Null Value support| DoubleTextBox  | Wpf | Syncfusion
description: null value support
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Null Value support

DoubleTextBox accepts null values. To enable the null option you have to set the [UseNullOption](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~UseNullOption.html) property to true. You can also set the NullValue property for the DoubleTextBox. When you set the null value to the [Value](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property, by default the value of the NullValue (Default value is null)property will be assigned to the Value property. 

{% tabs %}
{% highlight xaml %} 
<syncfusion:DoubleTextBox x:Name="doubleTextBox" Height="25" Width="150"              
UseNullOption="True" NullValue="1"/> 
{% endhighlight %} 

{% highlight C# %} 
Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new   
Syncfusion.Windows.Shared.DoubleTextBox();
doubleTextBox.Width = 150;
doubleTextBox.Height = 25;
doubleTextBox.UseNullOption = true;
doubleTextBox.NullValue = 1; 
{% endhighlight %} 
{% endtabs %}


In this sample, the NullValue (NullValue = 1) is set to the Value property of the DoubleTextBox because the default value of the [Value](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property is null.



![Null value support](Null-Value-support_images/Null-Value-support_img1.png)




{% tabs %}
{% highlight xaml %} 
<syncfusion:DoubleTextBox x:Name="doubleTextBox" 
Height="25" Width="150"                             
UseNullOption="True" NullValue="{x:Null}"/>
 {% endhighlight %} 

{% highlight C# %}
 Syncfusion.Windows.Shared.DoubleTextBox doubleTextBox = new            
 Syncfusion.Windows.Shared.DoubleTextBox();
 doubleTextBox.Width = 150;
 doubleTextBox.Height = 25;
 doubleTextBox.UseNullOption = true;
 doubleTextBox.NullValue = null; 
 {% endhighlight %} 
{% endtabs %}


In this sample, the NullValue (NullValue = null) is set to the [Value](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property of the DoubleTextBox. (Default value of the Value property is null).



![Null value support](Null-Value-support_images/Null-Value-support_img2.png)



{% seealso %}

Maximum and Minimum Value

Watermark support

{% endseealso %}