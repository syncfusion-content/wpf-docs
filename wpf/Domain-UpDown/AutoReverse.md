---
layout: post
title: AutoReverse in WPF SfDomainUpdown | Syncfusion®
description: Cycle back to the first item automatically when the last item is reached in the Syncfusion WPF SfDomainUpDown control.
platform: wpf
control: DomainUpDown
documentation: ug
---

# AutoReverse in WPF Domain UpDown

The `AutoReverse` property controls how the value wraps when it reaches the upper or lower bound. When `AutoReverse` is `True`, incrementing past the maximum value continues from the minimum value, and decrementing past the minimum value continues from the maximum value. The default value of `AutoReverse` is `False`.

N> The `editors:` namespace must be declared on the root element:
`xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.WPF"`

A `DataContext` that exposes an `Employees` property must also be set for the binding below to resolve.

{% tabs %}
{%highlight xaml%}

<editors:SfDomainUpDown x:Name="domainUpDown"
                       HorizontalAlignment="Center"
                       VerticalAlignment="Center"
                       Width="200"
                       AutoReverse="True"
                       ItemsSource="{Binding Employees}" />

{%endhighlight%}
{% endtabs %}
