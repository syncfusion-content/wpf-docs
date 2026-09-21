---
layout: post
title: Spin Button Alignment in WPF SfDomainUpdown | Syncfusion®
description: Configure the alignment of the spin buttons in the Syncfusion WPF SfDomainUpDown control to match your application layout.
platform: wpf
control: DomainUpDown
documentation: ug
---

# Spin Button Alignment in WPF Domain UpDown

The spin button's position in the `WPF Domain UpDown` control can be changed using the `SpinButtonsAlignment` property (defined in the `Syncfusion.Windows.Controls` namespace). The default value is `Right`. The property accepts three values:

1. `Right`: Spin buttons are aligned on the right side of the control.
2. `Left`: Spin buttons are aligned on the left side of the control.
3. `Both`: The decrement button is aligned on the left, and the increment button is aligned on the right.

N> All examples below assume an `editors:` xmlns is declared and a `DataContext` exposing an `Employees` property is set.

## Right

The spin buttons are aligned on the right side of the control.

{% tabs %}
{%highlight xaml%}

<editors:SfDomainUpDown x:Name="domainUpDown"
                       HorizontalAlignment="Center"
                       VerticalAlignment="Center"
                       Width="200"
                       SpinButtonsAlignment="Right"
                       ItemsSource="{Binding Employees}" />

{%endhighlight%}
{% endtabs %}

![Spin button aligned right](Spin-Button-Alignment_images/Spin-Button-Alignment_img1.png)

![Spin-Button-Alignment_img2](Spin-Button-Alignment_images/Spin-Button-Alignment_img2.png)

## Left

The spin buttons are aligned on the left side of the control.

{% tabs %}
{%highlight xaml%}

<editors:SfDomainUpDown x:Name="domainUpDown"
                       HorizontalAlignment="Center"
                       VerticalAlignment="Center"
                       Width="200"
                       SpinButtonsAlignment="Left"
                       ItemsSource="{Binding Employees}" />

{%endhighlight%}
{% endtabs %}

![Spin button aligned left](Spin-Button-Alignment_images/Spin-Button-Alignment_img3.png)

## Both

The spin button's decrement button is aligned on the left side of the control, and the increment button is aligned on the right side of the control.

{% tabs %}
{%highlight xaml%}

<editors:SfDomainUpDown x:Name="domainUpDown"
                       HorizontalAlignment="Center"
                       VerticalAlignment="Center"
                       Width="200"
                       SpinButtonsAlignment="Both"
                       ItemsSource="{Binding Employees}" />

{%endhighlight%}
{% endtabs %}

![Spin button aligned both](Spin-Button-Alignment_images/Spin-Button-Alignment_img5.png)
