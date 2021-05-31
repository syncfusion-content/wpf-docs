---
layout: post
title: Spin Button Alignment in WPF Domain Updown control | Syncfusion
description: Learn here all about Spin Button Alignment support in Syncfusion WPF Domain Updown (SfDomainUpDown) control and more.
platform: wpf
control: DomainUpDown
documentation: ug
---

# Spin Button Alignment in WPF Domain Updown (SfDomainUpDown)

The spin button’s position in the DomainUpDown control can be changed using SpinButtonsAlignment. It contains three modes for positioning spin buttons:

1. Right
2. Left
3. Both

## Right

Spin buttons will be aligned on the right side of the control.

{% tabs %}
{%highlight xaml%}

<editors:SfDomainUpDown x:Name="domainUpDown"
                       HorizontalAlignment="Center"
                       VerticalAlignment="Center"
                       Width="200" 
                      SpinButtonsAlignment="Right"
                      ItemsSource="{Binding Employees}">
 </editors:SfDomainUpDown>

{%endhighlight%}
{% endtabs %}

![Spin-Button-Alignment_img1](Spin-Button-Alignment_images/Spin-Button-Alignment_img1.png)

![Spin-Button-Alignment_img2](Spin-Button-Alignment_images/Spin-Button-Alignment_img2.png)

## Left

Spin buttons will be aligned on the left side of the control.

{% tabs %}
{%highlight xaml%}

<editors:SfDomainUpDown x:Name="domainUpDown"
                       HorizontalAlignment="Center"
                       VerticalAlignment="Center"
                       Width="200" 
                      SpinButtonsAlignment="Left"
                      ItemsSource="{Binding Employees}">        </editors:SfDomainUpDown>

{%endhighlight%}
{% endtabs %}

![Spin-Button-Alignment_img3](Spin-Button-Alignment_images/Spin-Button-Alignment_img3.png)

![Spin-Button-Alignment_img4](Spin-Button-Alignment_images/Spin-Button-Alignment_img4.png)

## Both

The spin button’s decrement button will be aligned on the left side of the control and the increment button is aligned on the right side of the control.

{% tabs %}
{%highlight xaml%}

<editors:SfDomainUpDown x:Name="domainUpDown"
                       HorizontalAlignment="Center"
                       VerticalAlignment="Center"
                       Width="200" 
                      SpinButtonsAlignment="Both"
                      ItemsSource="{Binding Employees}">        
</editors:SfDomainUpDown>          

{%endhighlight%}
{% endtabs %}

![Spin-Button-Alignment_img5](Spin-Button-Alignment_images/Spin-Button-Alignment_img5.png)
