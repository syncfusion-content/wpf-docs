---
layout: post
title: Concepts | SfRadialSlider  | wpf | Syncfusion
description: concepts  
platform: wpf
control: SfRadialSlider
documentation: ug
---
# Appearance and Styling 

## Inner Rim 

Inner Rim term denotes the circle in the center of Radial Slider.  Following properties can be used to customize the Inner Rim. 

### Inner Rim Radius Factor

[InnerRimRadiusFactor](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~InnerRimRadiusFactor.html) property decides the radius of Inner Rim from the total radius available to render the Radial Slider. 

### Inner Rim Stroke

[InnerRimStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~InnerRimStroke.html) property can be used to set the stroke color of the Inner Rim. 

### Inner Rim Stroke Thickness

[InnerRimStrokeThickness](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~InnerRimStrokeThickness.html) property can be used to set the thickness of the Inner Rim.

### Inner Rim Fill

[InnerRimFill](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~InnerRimFill.html) property can be used the set the fill color of the Inner Rim. 

{% highlight xaml %}

  <syncfusion:SfRadialSlider

InnerRimFill="LightGray"

            InnerRimRadiusFactor="0.25"

            InnerRimStroke="LightSkyBlue"

            InnerRimStrokeThickness="4" />

{% endhighlight  %}

![Radial slider inner rim fill](Concepts_images/Concepts_img6.png) 



## Outer Rim 

Outer Rim term denotes circular track (outer circle) of Radial Slider.  Following properties can be used to customize the Inner Rim

### Outer Rim Radius Factor

[OuterRimRadiusFactor](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~OuterRimRadiusFactor.html) property decides the radius of Outer Rim from the total radius available to render the Radial Slider. 

### Outer Rim Stroke 

[OuterRimStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~OuterRimStroke.html) property can be used to set the stroke color of the Outer Rim. 

### Outer Rim Stroke Thickness 

[OuterRimStrokeThickness](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~OuterRimStrokeThickness.html) property can be used to set the thickness of the Outer Rim. 

### Background

Background property can be used to fill the Outer Rim.

{% highlight xaml %}

<syncfusion:SfRadialSlider

            Background="LightGray"

            OuterRimRadiusFactor="0.8"

            OuterRimStroke="LightSkyBlue"

            OuterRimStrokeThickness="4" />

{% endhighlight %}

![Radial slider outer rim customization](Concepts_images/Concepts_img7.png) 



## Ticks

Ticks displayed along the circular path can be customized using the following properties. 

### Tick Template

Ticks can be customized using the [TickTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~TickTemplate.html) property. 


{% highlight xaml %}

<syncfusion:SfRadialSlider>

            <syncfusion:SfRadialSlider.TickTemplate>

                <DataTemplate>

                    <Border Background="Red"></Border>

                </DataTemplate>

            </syncfusion:SfRadialSlider.TickTemplate>

 </syncfusion:SfRadialSlider>

{% endhighlight  %}



![Radial slider tick template](Concepts_images/Concepts_img8.png) 



### Tick Radius Factor

[TickRadiusFactor](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~TickRadiusFactor.html) property decides the radius of the ticks from the total radius available to render the Radial Slider. 
{% highlight xaml %}

<syncfusion:SfRadialSlider  TickRadiusFactor="0.75"  />


{% endhighlight  %}


![Radial slider tick factor](Concepts_images/Concepts_img9.png)



### Tick Visibility

Visibility of ticks can be controlled by [TickVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~TickVisibility.html) property. 


{% highlight xaml %}

<syncfusion:SfRadialSlider TickVisibility="Collapsed" />


{% endhighlight  %}


![Ticks collapsed](Concepts_images/Concepts_img10.png)



## Labels

Labels displayed along the circular path in the Radial slider can be customized by the following properties. 

### Label Template

The [LabelTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~LabelTemplate.html) property can be used to customize the label object. 

{% highlight xaml %}

<syncfusion:SfRadialSlider>

<syncfusion:SfRadialSlider.LabelTemplate>

           <DataTemplate>

               <TextBlock Text="{Binding}" Foreground="DodgerBlue"></TextBlock>

           </DataTemplate>

       </syncfusion:SfRadialSlider.LabelTemplate>

</syncfusion:SfRadialSlider>

{% endhighlight  %}

![Label template](Concepts_images/Concepts_img11.png)





### Label Radius Factor

[LabelRadiusFactor](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~LabelRadiusFactor.html) property decides the radius of the labels from the total radius available to render the Radial Slider. 


{% highlight xaml %}

<syncfusion:SfRadialSlider LabelRadiusFactor="0.7" />


{% endhighlight  %}


![Label radius factor](Concepts_images/Concepts_img12.png) 





### Label Visibility

Visibility of ticks can be controlled by [LabelVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~LabelVisibility.html) property. 

{% highlight xaml %}

<syncfusion:SfRadialSlider  LabelVisibility="Collapsed" />


{% endhighlight %}


![Label collapsed](Concepts_images/Concepts_img13.png) 



## Pointer

The Pointer that is used for the select the value by dragging in circular track can be customized with the following properties. 

### Pointer Radius Factor

The [PointerRadiusFactor](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~PointerRadiusFactor.html) property decides the radius of the Pointer from the total radius available to render the Radial Slider. 

{% highlight xaml %}

<syncfusion:SfRadialSlider PointerRadiusFactor="0.5" />



{% endhighlight %}

![Pointer radius factor](Concepts_images/Concepts_img14.png) 



#### Pointer Style

Style of the Pointer can be customized using the [PointerStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~PointerStyle.html) property. 


{% highlight xaml %}

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



![Pointer style](Concepts_images/Concepts_img15.png) 



### Preview Pointer Style

The Preview Pointer that appears when hovering over the Radial Slider can be customized using the [PreviewPointerStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfRadialMenu.Wpf~Syncfusion.Windows.Controls.Navigation.SfRadialSlider~PreviewPointerStyle.html) property. 

{% highlight XAML %}

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


![Preview pointer style](Concepts_images/Concepts_img16.png) 