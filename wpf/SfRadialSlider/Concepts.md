---
layout: post
title: Concepts
description: concepts  
platform: wpf
control: Radial Slider 
documentation: ug
---

# Concepts  

## Minimum

Gets or sets the minimum possible value. (Inherited from [RangeBase](http://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.primitives.rangebase.aspx)). 


{% highlight xml %}

<syncfusion:SfRadialSlider

            Minimum="0" 

            Maximum="100" />

{% endhighlight  %}

## Maximum

Gets or sets the maximum possible value. (Inherited from [RangeBase](http://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.primitives.rangebase.aspx)).


{% highlight xml %}

<syncfusion:SfRadialSlider

            Minimum="0" 

            Maximum="100"  />

{% endhighlight  %}


## Value

Gets or sets the value of the Radial Slider. (Inherited from [RangeBase](http://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.primitives.rangebase.aspx)). 

{% highlight xml %}


<syncfusion:SfRadialSlider

            Minimum="0"  Maximum="100" Value="40" />



{% endhighlight  %}

The value can be changed by dragging the pointer along the circular track. 

![C:/Users/ApoorvahR/Desktop/3.png](Concepts_images/Concepts_img1.png)



## Ticks 

Ticks are placed along the round track in a uniform manner. The position of tick marks can be customized.

### Tick Frequency

The Tick Frequency property is used to define the number of ticks along the track, based on Minimum and Maximumn values.


{% highlight xml %}

<syncfusion:SfRadialSlider Minimum="0" Maximum="100"  

TickFrequency="5" />


{% endhighlight %}


![C:/Users/ApoorvahR/Desktop/3.png](Concepts_images/Concepts_img2.png) 



## Labels 

Labels are the numerical representation of the ticks starting from Minimum to Maximum. The frequency of the labels also controlled by TickFrequency property. 

## Small Change 

The SmallChange property (Inherited from [RangeBase](http://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.primitives.rangebase.aspx)) can be used to control the smallest possible range of value to be selected in Radial Slider.  For example, if SmallChange is set to 5, then it is only possible to select values that are multiples of 5. 


{% highlight xml %}

<syncfusion:SfRadialSlider

            Minimum="0" Maximum="100"  

            SmallChange="5" />


{% endhighlight %}

## Intermediate Value

The IntermediateValue property can be used to get the values while dragging the pointer along the circular especially when SmallChange is set. Because the SmallChange property does not allow to update the Value property until the value becomes the multiples of SmallChange. 

## Content

The Content property can be used to place any content inside the Inner Rim. 


{% highlight xml %}

<syncfusion:SfRadialSlider x:Name="rSlider1">

    <TextBlock Text="{Binding ElementName=rSlider1,Path=Value}" FontSize="24"/>

</syncfusion:SfRadialSlider>


{% endhighlight  %}

![C:/Users/ApoorvahR/Desktop/4.png](Concepts_images/Concepts_img3.png)



## Content Template

The ContentTemplate property can be used to customize the content of the Radial Slider. 


{% highlight xml %}

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



## Start Angle 

The StartAngle property can be used to set the starting position for generating the ticks in the circular track.  

## End Angle 

The EndAngle property can be used to set the ending position for the ticks in the circular track. 

{% highlight xml %}

<syncfusion:SfRadialSlider  StartAngle="180" EndAngle="360" />

{% endhighlight  %}

![C:/Users/ApoorvahR/Desktop/6.png](Concepts_images/Concepts_img5.png)



## Appearance and Styling 

### Inner Rim 

Inner Rim term denotes the circle in the center of Radial Slider.  Following properties can be used to customize the Inner Rim. 

#### Inner Rim Radius Factor

InnerRimRadiusFactor property decides the radius of Inner Rim from the total radius available to render the Radial Slider. 

#### Inner Rim Stroke

InnerRimStroke property can be used to set the stroke color of the Inner Rim. 

#### Inner Rim Stroke Thickness

InnerRimStrokeThickness property can be used to set the thickness of the Inner Rim.

#### Inner Rim Fill

InnerRimFill property can be used the set the fill color of the Inner Rim. 

{% highlight xml %}

  <syncfusion:SfRadialSlider

InnerRimFill="LightGray"

            InnerRimRadiusFactor="0.25"

            InnerRimStroke="LightSkyBlue"

            InnerRimStrokeThickness="4" />

{% endhighlight  %}

![C:/Users/ApoorvahR/Desktop/7.png](Concepts_images/Concepts_img6.png) 



### Outer Rim 

Outer Rim term denotes circular track (outer circle) of Radial Slider.  Following properties can be used to customize the Inner Rim

#### Outer Rim Radius Factor

OuterRimRadiusFactor property decides the radius of Outer Rim from the total radius available to render the Radial Slider. 

#### Outer Rim Stroke 

OuterRimStroke property can be used to set the stroke color of the Outer Rim. 

#### Outer Rim Stroke Thickness 

OuterRimStrokeThickness property can be used to set the thickness of the Outer Rim. 

#### Background

Background property can be used to fill the Outer Rim.

{% highlight xml %}

<syncfusion:SfRadialSlider

            Background="LightGray"

            OuterRimRadiusFactor="0.8"

            OuterRimStroke="LightSkyBlue"

            OuterRimStrokeThickness="4" />

{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/8.png](Concepts_images/Concepts_img7.png) 



### Ticks

Ticks displayed along the circular path can be customized using the following properties. 

#### Tick Template

Ticks can be customized using the TickTemplate property. 


{% highlight xml %}

<syncfusion:SfRadialSlider>

            <syncfusion:SfRadialSlider.TickTemplate>

                <DataTemplate>

                    <Border Background="Red"></Border>

                </DataTemplate>

            </syncfusion:SfRadialSlider.TickTemplate>

 </syncfusion:SfRadialSlider>

{% endhighlight  %}



![C:/Users/ApoorvahR/Desktop/9.png](Concepts_images/Concepts_img8.png) 



#### Tick Radius Factor

TickRadiusFactor property decides the radius of the ticks from the total radius available to render the Radial Slider. 
{% highlight xml %}

<syncfusion:SfRadialSlider  TickRadiusFactor="0.75"  />


{% endhighlight  %}


![C:/Users/ApoorvahR/Desktop/10.png](Concepts_images/Concepts_img9.png)



#### Tick Visibility

Visibility of ticks can be controlled by TickVisibility property. 


{% highlight xml %}

<syncfusion:SfRadialSlider TickVisibility="Collapsed" />


{% endhighlight  %}


![C:/Users/ApoorvahR/Desktop/11.png](Concepts_images/Concepts_img10.png)



### Labels

Labels displayed along the circular path in the Radial slider can be customized by the following properties. 

#### Label Template

The LabelTemplate property can be used to customize the label object. 

{% highlight xml %}

<syncfusion:SfRadialSlider>

<syncfusion:SfRadialSlider.LabelTemplate>

           <DataTemplate>

               <TextBlock Text="{Binding}" Foreground="DodgerBlue"></TextBlock>

           </DataTemplate>

       </syncfusion:SfRadialSlider.LabelTemplate>

</syncfusion:SfRadialSlider>

{% endhighlight  %}

![C:/Users/ApoorvahR/Desktop/12.png](Concepts_images/Concepts_img11.png)





#### Label Radius Factor

LabelRadiusFactor property decides the radius of the labels from the total radius available to render the Radial Slider. 


{% highlight xml %}

<syncfusion:SfRadialSlider LabelRadiusFactor="0.7" />


{% endhighlight  %}


![C:/Users/ApoorvahR/Desktop/13.png](Concepts_images/Concepts_img12.png) 





#### Label Visibility

Visibility of ticks can be controlled by LabelVisibility property. 

{% highlight xml %}

<syncfusion:SfRadialSlider  LabelVisibility="Collapsed" />


{% endhighlight %}


![C:/Users/ApoorvahR/Desktop/14.png](Concepts_images/Concepts_img13.png) 



### Pointer

The Pointer that is used for the select the value by dragging in circular track can be customized with the following properties. 

#### Pointer Radius Factor

The PointerRadiusFactor property decides the radius of the Pointer from the total radius available to render the Radial Slider. 

{% highlight xml %}

<syncfusion:SfRadialSlider PointerRadiusFactor="0.5" />



{% endhighlight %}

![C:/Users/ApoorvahR/Desktop/15.png](Concepts_images/Concepts_img14.png) 



#### Pointer Style

Style of the Pointer can be customized using the PointerStyle property. 


{% highlight xml %}

<syncfusion:SfRadialSlider>

<syncfusion:SfRadialSlider.PointerStyle>

                <Style TargetType="syncfusion:RadialPointer" >

                    <Setter Property="Height" Value="2"/>

                    <Setter Property="Template">

                        <Setter.Value>

                            <ControlTemplate TargetType="syncfusion:RadialPointer">

                                <Border  Background="Red"/>

                            </ControlTemplate>

                        </Setter.Value>

                    </Setter>

                </Style>

            </syncfusion:SfRadialSlider.PointerStyle>

</syncfusion:SfRadialSlider>

{% endhighlight %}



![C:/Users/ApoorvahR/Desktop/16.png](Concepts_images/Concepts_img15.png) 



#### Preview Pointer Style

The Preview Pointer that appears when hovering over the Radial Slider can be customized using the PreviewPointerStyle property. 

{% highlight xml %}

<syncfusion:SfRadialSlider

            Minimum="0" 

            Maximum="100"  >

            <syncfusion:SfRadialSlider.PreviewPointerStyle>

                <Style TargetType="syncfusion:RadialPreviewPointer" >

                    <Setter Property="Height" Value="2"/>

                    <Setter Property="Template">

                        <Setter.Value>

     <ControlTemplate TargetType="syncfusion:RadialPreviewPointer">

                                <Border Opacity="0.2"  Background="Red"/>

                          </ControlTemplate>

                        </Setter.Value>

                    </Setter>

                </Style>

            </syncfusion:SfRadialSlider.PreviewPointerStyle>

</syncfusion:SfRadialSlider>


{% endhighlight %}


![C:/Users/ApoorvahR/Desktop/17.png](Concepts_images/Concepts_img16.png) 