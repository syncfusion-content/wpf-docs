---
layout: post
title: Binding Support | IntegerTextBox | wpf | Syncfusion
description: binding support
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Binding Support

Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source to target) or bidirectional (source to target and target to source). You can bind the data to the integer textbox through the [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.IntegerTextBox~Value.html) property.

The following example shows a simple binding between the value of the IntegerTextBox and another IntegerTextBox value that reflects the typed value:

{% tabs %}
{% highlight xaml %}

<StackPanel>
<syncfusion:IntegerTextBox x:Name="integerTextBox1" Width="150" Margin="10"/>
<syncfusion:IntegerTextBox x:Name="integerTextBox2" Width="150" Margin="10" Value="{Binding ElementName=integerTextBox1,Path=Value,Mode=TwoWay}"/>
</StackPanel>

{% endhighlight %}
{% endtabs %}

![Binding support](Binding-Support_images/Binding-Support_img1.png)

The Data Context property provides its value to child elements. So you can set the Data Context on a superior layout container and its value is provided to all child elements. This is very useful if you want to build a form that is bound to multiple properties of the same data object. If you don't explicitly define a source of binding, it takes the data context by default.

{% tabs %}
{% highlight xaml %}

<StackPanel DataContext="{StaticResource myCustomer}">
<TextBox Text="{Binding FirstName}"/>
<TextBox Text ="{Binding LastName}"/>
<syncfusion:IntegerTextBox Value="{Binding Phone}"/>
<syncfusion:IntegerTextBox Value="{Binding Income}"/>
</StackPanel>

{% endhighlight %}
{% endtabs %}

If you want to bind types other than integer types, then you need to use the Value Converter. The following example shows a simple binding between the value of the IntegerTextBox and the Textbox text that reflects the typed value:

{% tabs %}
{% highlight xaml %}

<StackPanel>
<StackPanel.Resources>
<c:StringToIntConverter x:Key="stringToIntConverter"/>
</StackPanel.Resources>
<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="150" Margin="10"/>
<TextBox x:Name="textBox" Width="150" Margin="10" Text="{Binding 
ElementName=integerTextBox,Path=Value,Mode=TwoWay,
Converter={StaticResource stringToIntConverter}}"/>    
</StackPanel>

{% endhighlight %}
{% endtabs %}

![Binding support](Binding-Support_images/Binding-Support_img2.png)
