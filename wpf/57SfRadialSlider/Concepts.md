---
layout: post
title: Concepts
description: concepts  
platform: wpf
control: Radial Slider 
documentation: ug
---

## Concepts  

### Minimum

Gets or sets the minimum possible value. (Inherited from [RangeBase](http://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.primitives.rangebase.aspx)). 



[XAML]

<syncfusion:SfRadialSlider

            Minimum="0" 

            Maximum="100" />



### Maximum

Gets or sets the maximum possible value. (Inherited from [RangeBase](http://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.primitives.rangebase.aspx)).



[XAML]

<syncfusion:SfRadialSlider

            Minimum="0" 

            Maximum="100"  />



### Value

Gets or sets the value of the Radial Slider. (Inherited from [RangeBase](http://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.primitives.rangebase.aspx)). 



[XAML]

<syncfusion:SfRadialSlider

            Minimum="0"  Maximum="100" Value="40" />





The value can be changed by dragging the pointer along the circular track. 



{ ![C:/Users/ApoorvahR/Desktop/3.png](Concepts_images/Concepts_img1.png) | markdownify }
{:.image }


### Ticks 

Ticks are placed along the round track in a uniform manner. The position of tick marks can be customized.

Tick Frequency

The Tick Frequency property is used to define the number of ticks along the track, based on Minimum and Maximumn values.



[XAML]

<syncfusion:SfRadialSlider Minimum="0" Maximum="100"  

TickFrequency="5" />





{ ![C:/Users/ApoorvahR/Desktop/3.png](Concepts_images/Concepts_img2.png) | markdownify }
{:.image }


### Labels 

Labels are the numerical representation of the ticks starting from Minimum to Maximum. The frequency of the labels also controlled by TickFrequency property. 

### Small Change 

The SmallChange property (Inherited from [RangeBase](http://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.primitives.rangebase.aspx)) can be used to control the smallest possible range of value to be selected in Radial Slider.  For example, if SmallChange is set to 5, then it is only possible to select values that are multiples of 5. 



[XAML]

<syncfusion:SfRadialSlider

            Minimum="0" Maximum="100"  

            SmallChange="5" />



### Intermediate Value

The IntermediateValue property can be used to get the values while dragging the pointer along the circular especially when SmallChange is set. Because the SmallChange property does not allow to update the Value property until the value becomes the multiples of SmallChange. 

### Content

The Content property can be used to place any content inside the Inner Rim. 



[XAML]

&lt;syncfusion:SfRadialSlider x:Name="rSlider1"&gt;

    &lt;TextBlock Text="{Binding ElementName=rSlider1,Path=Value}" FontSize="24"/&gt;

&lt;/syncfusion:SfRadialSlider&gt;



{ ![C:/Users/ApoorvahR/Desktop/4.png](Concepts_images/Concepts_img3.png) | markdownify }
{:.image }


### Content Template

The ContentTemplate property can be used to customize the content of the Radial Slider. 



[XAML]

  <syncfusion:SfRadialSlider

            Content="{Binding RelativeSource={RelativeSource Self}, Path=Value}"

            x:Name="rSlider1">

            &lt;syncfusion:SfRadialSlider.ContentTemplate&gt;

                &lt;DataTemplate&gt;

                  &lt;TextBlock Text="{Binding}" FontSize="24" Foreground="LightSkyBlue"/&gt;

                &lt;/DataTemplate&gt;

            &lt;/syncfusion:SfRadialSlider.ContentTemplate&gt;

  &lt;/syncfusion:SfRadialSlider&gt;



{ ![C:/Users/ApoorvahR/Desktop/5.png](Concepts_images/Concepts_img4.png) | markdownify }
{:.image }


### Start Angle 

The StartAngle property can be used to set the starting position for generating the ticks in the circular track.  

### End Angle 

The EndAngle property can be used to set the ending position for the ticks in the circular track. 



[XAML]

&lt;syncfusion:SfRadialSlider  StartAngle="180" EndAngle="360" /&gt;



{ ![C:/Users/ApoorvahR/Desktop/6.png](Concepts_images/Concepts_img5.png) | markdownify }
{:.image }


### Appearance and Styling 

#### Inner Rim 

Inner Rim term denotes the circle in the center of Radial Slider.  Following properties can be used to customize the Inner Rim. 

Inner Rim Radius Factor

InnerRimRadiusFactor property decides the radius of Inner Rim from the total radius available to render the Radial Slider. 

Inner Rim Stroke

InnerRimStroke property can be used to set the stroke color of the Inner Rim. 

Inner Rim Stroke Thickness

InnerRimStrokeThickness property can be used to set the thickness of the Inner Rim.

Inner Rim Fill

InnerRimFill property can be used the set the fill color of the Inner Rim. 



[XAML]

  <syncfusion:SfRadialSlider

InnerRimFill="LightGray"

            InnerRimRadiusFactor="0.25"

            InnerRimStroke="LightSkyBlue"

            InnerRimStrokeThickness="4" />



{ ![C:/Users/ApoorvahR/Desktop/7.png](Concepts_images/Concepts_img6.png) | markdownify }
{:.image }


#### Outer Rim 

Outer Rim term denotes circular track (outer circle) of Radial Slider.  Following properties can be used to customize the Inner Rim

Outer Rim Radius Factor

OuterRimRadiusFactor property decides the radius of Outer Rim from the total radius available to render the Radial Slider. 

Outer Rim Stroke 

OuterRimStroke property can be used to set the stroke color of the Outer Rim. 

Outer Rim Stroke Thickness 

OuterRimStrokeThickness property can be used to set the thickness of the Outer Rim. 

Background

Background property can be used to fill the Outer Rim.



[XAML]

<syncfusion:SfRadialSlider

            Background="LightGray"

            OuterRimRadiusFactor="0.8"

            OuterRimStroke="LightSkyBlue"

            OuterRimStrokeThickness="4" />



{ ![C:/Users/ApoorvahR/Desktop/8.png](Concepts_images/Concepts_img7.png) | markdownify }
{:.image }


#### Ticks

Ticks displayed along the circular path can be customized using the following properties. 

Tick Template

Ticks can be customized using the TickTemplate property. 



[XAML]

&lt;syncfusion:SfRadialSlider&gt;

            &lt;syncfusion:SfRadialSlider.TickTemplate&gt;

                &lt;DataTemplate&gt;

                    &lt;Border Background="Red"&gt;&lt;/Border&gt;

                &lt;/DataTemplate&gt;

            &lt;/syncfusion:SfRadialSlider.TickTemplate&gt;

 &lt;/syncfusion:SfRadialSlider&gt;





{ ![C:/Users/ApoorvahR/Desktop/9.png](Concepts_images/Concepts_img8.png) | markdownify }
{:.image }


Tick Radius Factor

TickRadiusFactor property decides the radius of the ticks from the total radius available to render the Radial Slider. 



[XAML]

&lt;syncfusion:SfRadialSlider  TickRadiusFactor="0.75"  /&gt;





{ ![C:/Users/ApoorvahR/Desktop/10.png](Concepts_images/Concepts_img9.png) | markdownify }
{:.image }


Tick Visibility

Visibility of ticks can be controlled by TickVisibility property. 



[XAML]

&lt;syncfusion:SfRadialSlider TickVisibility="Collapsed" /&gt;





{ ![C:/Users/ApoorvahR/Desktop/11.png](Concepts_images/Concepts_img10.png) | markdownify }
{:.image }


#### Labels

Labels displayed along the circular path in the Radial slider can be customized by the following properties. 

Label Template

The LabelTemplate property can be used to customize the label object. 



[XAML]

&lt;syncfusion:SfRadialSlider&gt;

&lt;syncfusion:SfRadialSlider.LabelTemplate&gt;

           &lt;DataTemplate&gt;

               &lt;TextBlock Text="{Binding}" Foreground="DodgerBlue"&gt;&lt;/TextBlock&gt;

           &lt;/DataTemplate&gt;

       &lt;/syncfusion:SfRadialSlider.LabelTemplate&gt;

&lt;/syncfusion:SfRadialSlider&gt;



{ ![C:/Users/ApoorvahR/Desktop/12.png](Concepts_images/Concepts_img11.png) | markdownify }
{:.image }




Label Radius Factor

LabelRadiusFactor property decides the radius of the labels from the total radius available to render the Radial Slider. 



[XAML]

&lt;syncfusion:SfRadialSlider LabelRadiusFactor="0.7" /&gt;





{ ![C:/Users/ApoorvahR/Desktop/13.png](Concepts_images/Concepts_img12.png) | markdownify }
{:.image }




Label Visibility

Visibility of ticks can be controlled by LabelVisibility property. 



[XAML]

&lt;syncfusion:SfRadialSlider  LabelVisibility="Collapsed" /&gt;





{ ![C:/Users/ApoorvahR/Desktop/14.png](Concepts_images/Concepts_img13.png) | markdownify }
{:.image }


#### Pointer

The Pointer that is used for the select the value by dragging in circular track can be customized with the following properties. 

Pointer Radius Factor

The PointerRadiusFactor property decides the radius of the Pointer from the total radius available to render the Radial Slider. 



[XAML]

&lt;syncfusion:SfRadialSlider PointerRadiusFactor="0.5" /&gt;





{ ![C:/Users/ApoorvahR/Desktop/15.png](Concepts_images/Concepts_img14.png) | markdownify }
{:.image }


Pointer Style

Style of the Pointer can be customized using the PointerStyle property. 



[XAML]

&lt;syncfusion:SfRadialSlider&gt;

&lt;syncfusion:SfRadialSlider.PointerStyle&gt;

                &lt;Style TargetType="syncfusion:RadialPointer" &gt;

                    &lt;Setter Property="Height" Value="2"/&gt;

                    &lt;Setter Property="Template"&gt;

                        &lt;Setter.Value&gt;

                            &lt;ControlTemplate TargetType="syncfusion:RadialPointer"&gt;

                                &lt;Border  Background="Red"/&gt;

                            &lt;/ControlTemplate&gt;

                        &lt;/Setter.Value&gt;

                    &lt;/Setter&gt;

                &lt;/Style&gt;

            &lt;/syncfusion:SfRadialSlider.PointerStyle&gt;

&lt;/syncfusion:SfRadialSlider&gt;





{ ![C:/Users/ApoorvahR/Desktop/16.png](Concepts_images/Concepts_img15.png) | markdownify }
{:.image }


Preview Pointer Style

The Preview Pointer that appears when hovering over the Radial Slider can be customized using the PreviewPointerStyle property. 



[XAML]

<syncfusion:SfRadialSlider

            Minimum="0" 

            Maximum="100"  >

            &lt;syncfusion:SfRadialSlider.PreviewPointerStyle&gt;

                &lt;Style TargetType="syncfusion:RadialPreviewPointer" &gt;

                    &lt;Setter Property="Height" Value="2"/&gt;

                    &lt;Setter Property="Template"&gt;

                        &lt;Setter.Value&gt;

     &lt;ControlTemplate TargetType="syncfusion:RadialPreviewPointer"&gt;

                                &lt;Border Opacity="0.2"  Background="Red"/&gt;

                          &lt;/ControlTemplate&gt;

                        &lt;/Setter.Value&gt;

                    &lt;/Setter&gt;

                &lt;/Style&gt;

            &lt;/syncfusion:SfRadialSlider.PreviewPointerStyle&gt;

&lt;/syncfusion:SfRadialSlider&gt;





{ ![C:/Users/ApoorvahR/Desktop/17.png](Concepts_images/Concepts_img16.png) | markdownify }
{:.image }






