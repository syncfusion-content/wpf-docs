---
layout: post
title: Transition-effects
description: transition effects
platform: wpf
control: TabNavigationControl
documentation: ug
---

# Transition effects

Transition Effect property is used to set the effect for the Tab navigation control. The Transition effect is an enum that contains five values namely:

* Slide – The item/page navigates with slide effect.



XAML



<syncfusion:TabNavigationControl TransitionEffect="Slide"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>





* Fade – During navigation, the previous item fades out and the new item appears with variation in opacity.



XAML



 <syncfusion:TabNavigationControl TransitionEffect="Fade"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>





* Zoom – The new item appears with a zooming effect.



XAML



  <syncfusion:TabNavigationControl TransitionEffect="Zoom"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>





* Blur – The new item appears with blur effect.



XAML



 <syncfusion:TabNavigationControl TransitionEffect="Blur"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>





* Push – The new item descends from the top 



XAML



 <syncfusion:TabNavigationControl TransitionEffect="Push"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>





* PushIn – The new item ascends from the bottom



XAML



 <syncfusion:TabNavigationControl TransitionEffect="PushIn"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>





* Wipe – The old item gets washed out and the new item appears.



XAML



 <syncfusion:TabNavigationControl TransitionEffect="Wipe"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>





