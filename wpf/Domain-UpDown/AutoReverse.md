---
layout: post
title: AutoReverse in WPF Domain Updown | Syncfusion®
description: Cycle back to the first item automatically when the last item is reached in the Syncfusion WPF Domain Updown (SfDomainUpDown) control.
platform: wpf
control: DomainUpDown
documentation: ug
---

# AutoReverse in WPF Domain Updown

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
