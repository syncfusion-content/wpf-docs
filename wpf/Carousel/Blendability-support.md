---
layout: post
title: Blendability-support
description: blendability support
platform: wpf
control: Carousel
documentation: ug
---

# Blendability support

The template of the Carousel control can be easily editable in Expression Blend, to give a nice look and feel.

Using Blendability Support in an Application

Following are the steps to edit the template in Expression Blend.

1. Open the Carousel control in blend. 
2. Go to Object ->Edit Style -> Edit a Copy to edit the template of Carousel control as follows.



{ ![](Blendability-support_images/Blendability-support_img1.png) | markdownify }
{:.image }




A window opens as shown below where you can create a new style for the Carousel control and can define exactly where you would like to store it.



{ ![](Blendability-support_images/Blendability-support_img2.png) | markdownify }
{:.image }




What’s produced through this set of steps is quite a bit of XAML which is placed within your application. This XAML represents the default style for the Carousel control. In the same way, you can edit the template of CarouselItem.



{ ![](Blendability-support_images/Blendability-support_img3.png) | markdownify }
{:.image }




Now you can edit each part in the template and can create custom look and feel for the control. In the following example, template for CarouselItem is edited to give a reflection effect.

[XAML]



        &lt;Style TargetType="syncfusion:CarouselItem"&gt;
            &lt;Setter Property="Template"&gt;
                &lt;Setter.Value&gt;
                    &lt;ControlTemplate TargetType="syncfusion:CarouselItem"&gt;
                        &lt;Grid&gt;
                            &lt;Grid.RowDefinitions&gt;
                                &lt;RowDefinition/&gt;
                                &lt;RowDefinition/&gt;
                            &lt;/Grid.RowDefinitions&gt;
                            &lt;Border x:Name="border" BorderBrush="#FF333333" RenderTransformOrigin="0.5,0.5" CornerRadius="4" Padding="4"&gt;

                                &lt;ContentPresenter Content="{TemplateBinding Content}" 							ContentTemplate="{TemplateBinding ContentTemplate}" /&gt;
                            &lt;/Border&gt;

                            &lt;Border BorderThickness="2" Grid.Row="1" Height="100" VerticalAlignment="Top" HorizontalAlignment="Stretch" CornerRadius="5"&gt;
                                &lt;Border.BorderBrush&gt;
                                    &lt;LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0"&gt;
                                        &lt;GradientStop Color="#FFDADADA" Offset="0"/&gt;
                                        &lt;GradientStop Color="Transparent" Offset="0.712"/&gt;
                                    &lt;/LinearGradientBrush&gt;
                                &lt;/Border.BorderBrush&gt;
                                &lt;Border.Background&gt;
                                    &lt;LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0"&gt;
                                        &lt;GradientStop Color="#FFDADADA"/&gt;
                                        &lt;GradientStop Color="Transparent" Offset="0.705"/&gt;
                                    &lt;/LinearGradientBrush&gt;
                                &lt;/Border.Background&gt;

                            &lt;/Border&gt;
                        &lt;/Grid&gt;
                    &lt;/ControlTemplate&gt;
                &lt;/Setter.Value&gt;
            &lt;/Setter&gt;
        &lt;/Style&gt;





{ ![](Blendability-support_images/Blendability-support_img4.png) | markdownify }
{:.image }


