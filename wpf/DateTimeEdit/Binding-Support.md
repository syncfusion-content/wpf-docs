---
layout: post
title: Binding-Support
description: binding support
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Binding Support

Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source to target) or bidirectional (source to target and target to source). You can bind the data to the DateTimeEdit control through the DateTime property.

The following example shows a simple binding between the DateTime property of the DateTimeEditcontrol and another DateTimeEdit control:



{% highlight html %}
XAML

<syncfusion:DateTimeEdit x:Name="dateTimeEdit1" Height="25" Width="220" Margin="10"/><syncfusion:DateTimeEdit x:Name="dateTimeEdit2" Height="25" Width="220"                          DateTime="{Binding ElementName=dateTimeEdit1,                                             Path=DateTime,Mode=TwoWay}"                         Margin="10"/>

{% endhighlight  %}

![](Binding-Support_images/Binding-Support_img1.png)



See Also

Setting Date

NullValue Support

Maximum and Minimum Value

