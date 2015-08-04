---
layout: post
title: AutoReverse
description: autoreverse
platform: wpf
control: DomainUpDown
documentation: ug
---

# AutoReverse

Incrementing the value starts from the maximum value once it has reached the minimum value and starts from the minimum value once it has reached the maximum value.


{%highlight xaml%}

[XAML]



<editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

                               AutoReverse="True"

                               ItemsSource="{Binding Employees}">

</editors:SfDomainUpDown >


{%endhighlight%}


