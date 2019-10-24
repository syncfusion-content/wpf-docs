---
layout: post
title: Binding Support| PercentTextBox  | Wpf | Syncfusion
description: binding support
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Binding Support

Data binding is the process of establishing a connection between the application UI and business logic. PercentTextBox supports unidirectional (source -> target or target <- source) or bidirectional (source <-> target). You can bind the data to the PercentTextBox through the Value property.

The following example shows a simple binding between the PercentValue of the PercentTextBox and another PercentTextBox PercentValue that reflects the typed value:

{% tabs %}
{% highlight xaml %}

<StackPanel>
<syncfusion:PercentTextBox x:Name="percentTextBox1" Width="150" Margin="10"/>
<syncfusion:PercentTextBox x:Name="percentTextBox2" Width="150" Margin="10"  
                        PercentValue="{Binding ElementName=percentTextBox1, 
                        Path=PercentValue,Mode=TwoWay}"/>
</StackPanel>

{% endhighlight %}
{% endtabs %}

![](Binding-Support_images/Binding-Support_img1.png)

The Data Context property provides its value to child elements. So you can set the Data Context on a superior layout container and its value is provided to all child elements. This is very useful if you want to build a form that is bound to multiple properties of the same data object. If you don't explicitly define a source of binding, it takes the data context by default.

{% tabs %}
{% highlight xaml %}

<StackPanel DataContext="{StaticResource myCustomer}">
<TextBox Text="{Binding FirstName}"/>
<TextBox Text ="{Binding LastName}"/>
<syncfusion:PercentTextBox PercentValue="{Binding Phone}"/>
<syncfusion:PercentTextBox PercentValue="{Binding Income}"/>
</StackPanel>

{% endhighlight %}
{% endtabs %}

If you want to bind values other than double values, then you need to use the Value Converter. The following example shows a simple binding between the PercentValue of the PercentTextBox and the Textbox text that reflects the typed value:

{% tabs %}
{% highlight xaml %}

<StackPanel>
<StackPanel.Resources>
<c:StringToDoubleConverter x:Key="stringToDoubleConverter"/>
</StackPanel.Resources>
<syncfusion:PercentTextBox x:Name="percentTextBox" Width="150" Margin="10"/>
<TextBox x:Name="textBox" Width="150" Margin="10" Text="{Binding 
        ElementName= percentTextBox,Path=PercentValue,Mode=TwoWay,
        Converter={StaticResource stringToDoubleConverter}}"/>
</StackPanel>

{% endhighlight %}
{% endtabs %}

![](Binding-Support_images/Binding-Support_img2.png)
