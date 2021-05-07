---
layout: post
title: AutoReverse in WPF Domain Updown control | Syncfusion
description: Learn here all about AutoReverse support in Syncfusion WPF Domain Updown (SfDomainUpDown) control and more.
platform: wpf
control: DomainUpDown
documentation: ug
---

# AutoReverse in WPF Domain Updown (SfDomainUpDown)

Incrementing the value starts from the maximum value once it has reached the minimum value and starts from the minimum value once it has reached the maximum value.

{% tabs %}
{%highlight xaml%}

<editors:SfDomainUpDown x:Name="domainUpDown"
                       HorizontalAlignment="Center"
                       VerticalAlignment="Center"
                       Width="200" 
                       AutoReverse="True"
                       ItemsSource="{Binding Employees}">
</editors:SfDomainUpDown >

{%endhighlight%}
{% endtabs %}
