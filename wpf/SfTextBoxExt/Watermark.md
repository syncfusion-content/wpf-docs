---
layout: post
title: Watermark
description: watermark
platform: wpf
control: TextBoxExt
documentation: ug
---

# Watermark

The control will prompt the user with some information, when it is not in focus and contains an empty string.

## Using the Watermark

Watermark property allows the users to specify some information, when the text is empty. For illustration let us create a simple textbox, where the user is asked to enter names separated by a comma,


{% highlight xml %}



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            Watermark="Enter names separated by comma (Ex : John, Kate)"/>
{% endhighlight %}


![C:/Users/ApoorvahR/Desktop/2.png](Watermark_images/Watermark_img1.png)

> Note: The Watermark property is of the object type so any framework elements can be hosted as Watermark content. Below example shows how to host an image and text as Watermark content.


{% highlight xml %}



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400">

            <editors:SfTextBoxExt.Watermark>

                <StackPanel Orientation="Horizontal">

                    <Image Source="Windows 8.png" Stretch="None" Margin="2"/>

                    <TextBlock Text="Search Windows" Opacity="0.5" Margin="5 2"/>

                </StackPanel>

            </editors:SfTextBoxExt.Watermark>

</editors:SfTextBoxExt>
{% endhighlight %}


![C:/Users/ApoorvahR/Desktop/3.png](Watermark_images/Watermark_img2.png)







## Using the Watermark template

Any business object can be bound to the Watermark property and that object can be decorated by applying the WatermarkTemplate property.


{% highlight xml %}



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            Watermark="{Binding Person}">

            <editors:SfTextBoxExt.WatermarkTemplate>

                <DataTemplate>

                    <TextBlock Text="{Binding PromptText}" Opacity="0.5"/>

                </DataTemplate>

            </editors:SfTextBoxExt.WatermarkTemplate>

</editors:SfTextBoxExt>

{% endhighlight %}

