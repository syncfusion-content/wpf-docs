---
layout: post
title: Content
description: content 
platform: wpf
control: Radial Slider 
documentation: ug
---

# Content

The Content property can be used to place any content inside the Inner Rim. 


{% highlight html %}
[XAML]

<syncfusion:SfRadialSlider x:Name="rSlider1">

    <TextBlock Text="{Binding ElementName=rSlider1,Path=Value}" FontSize="24"/>

</syncfusion:SfRadialSlider>


{% endhighlight  %}

![C:/Users/ApoorvahR/Desktop/4.png](Concepts_images/Concepts_img3.png)



