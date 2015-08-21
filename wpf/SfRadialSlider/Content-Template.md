---
layout: post
title: Content-Template
description: content template  
platform: wpf
control: Radial Slider 
documentation: ug
---

# Content Template

The ContentTemplate property can be used to customize the content of the Radial Slider. 


{% highlight html %}

  <syncfusion:SfRadialSlider

            Content="{Binding RelativeSource={RelativeSource Self}, Path=Value}"

            x:Name="rSlider1">

            <syncfusion:SfRadialSlider.ContentTemplate>

                <DataTemplate>

                  <TextBlock Text="{Binding}" FontSize="24" Foreground="LightSkyBlue"/>

                </DataTemplate>

            </syncfusion:SfRadialSlider.ContentTemplate>

  </syncfusion:SfRadialSlider>

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/5.png](Concepts_images/Concepts_img4.png)








