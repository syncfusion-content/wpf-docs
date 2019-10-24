---
layout: post
title: Content-Template | SfRadialSlider  | wpf | Syncfusion
description: content template  
platform: wpf
control: SfRadialSlider 
documentation: ug
---

# Content Template

The [ContentTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~ContentTemplate.html) property can be used to customize the content of the Radial Slider. 


{% highlight XAML %}

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

![Content template](Concepts_images/Concepts_img4.png)








