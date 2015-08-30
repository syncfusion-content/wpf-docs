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


~~~ xml




<syncfusion:TabNavigationControl TransitionEffect="Slide"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>
~~~
{:.prettyprint}





* Fade – During navigation, the previous item fades out and the new item appears with variation in opacity.


~~~ xml




 <syncfusion:TabNavigationControl TransitionEffect="Fade"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>
~~~
{:.prettyprint}




* Zoom – The new item appears with a zooming effect.


~~~xml




  <syncfusion:TabNavigationControl TransitionEffect="Zoom"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>
~~~
{:.prettyprint}




* Blur – The new item appears with blur effect.


~~~ xml




 <syncfusion:TabNavigationControl TransitionEffect="Blur"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>
~~~
{:.prettyprint}




* Push – The new item descends from the top 


~~~ xml




 <syncfusion:TabNavigationControl TransitionEffect="Push"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>

~~~
{:.prettyprint}



* PushIn – The new item ascends from the bottom


~~~ xml




 <syncfusion:TabNavigationControl TransitionEffect="PushIn"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>
~~~
{:.prettyprint}




* Wipe – The old item gets washed out and the new item appears.


~~~ xml




 <syncfusion:TabNavigationControl TransitionEffect="Wipe"  

                                         ItemsSource="{Binding MyCollection}">



        </syncfusion:TabNavigationControl>

~~~
{:.prettyprint}



