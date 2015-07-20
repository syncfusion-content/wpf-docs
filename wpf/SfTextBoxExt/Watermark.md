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

Using the Watermark

Watermark property allows the users to specify some information, when the text is empty. For illustration let us create a simple textbox, where the user is asked to enter names separated by a comma,



[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            Watermark="Enter names separated by comma (Ex : John, Kate)"/>



{ ![C:/Users/ApoorvahR/Desktop/2.png](Watermark_images/Watermark_img1.png) | markdownify }
{:.image }


> _Note: The Watermark property is of the object type so any framework elements can be hosted as Watermark content. Below example shows how to host an image and text as Watermark content._

> 

[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400">

            &lt;editors:SfTextBoxExt.Watermark&gt;

                &lt;StackPanel Orientation="Horizontal"&gt;

                    &lt;Image Source="Windows 8.png" Stretch="None" Margin="2"/&gt;

                    &lt;TextBlock Text="Search Windows" Opacity="0.5" Margin="5 2"/&gt;

                &lt;/StackPanel&gt;

            &lt;/editors:SfTextBoxExt.Watermark&gt;

&lt;/editors:SfTextBoxExt&gt;



{ ![C:/Users/ApoorvahR/Desktop/3.png](Watermark_images/Watermark_img2.png) | markdownify }
{:.image }






Using the Watermark template

Any business object can be bound to the Watermark property and that object can be decorated by applying the WatermarkTemplate property.



[XAML]



<editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="400"

                            Watermark="{Binding Person}">

            &lt;editors:SfTextBoxExt.WatermarkTemplate&gt;

                &lt;DataTemplate&gt;

                    &lt;TextBlock Text="{Binding PromptText}" Opacity="0.5"/&gt;

                &lt;/DataTemplate&gt;

            &lt;/editors:SfTextBoxExt.WatermarkTemplate&gt;

&lt;/editors:SfTextBoxExt&gt;



