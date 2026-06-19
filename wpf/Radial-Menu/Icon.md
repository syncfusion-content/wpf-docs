---
layout: post
title: Icon in WPF Radial Menu Control | Syncfusion®
description: Learn about icon support in the Syncfusion® WPF Radial Menu (SfRadialMenu) control, its elements, and more.
platform: WPF
control: SfRadialMenu 
documentation: ug
---

# Icon in WPF Radial Menu (SfRadialMenu)

The `Icon` property of the Radial Menu is used to customize the icon displayed at the center of the Radial Menu circle.

{%highlight xaml%}



<navigation:SfRadialMenu IsOpen="True" >

<navigation:SfRadialMenu.Icon>

                <Grid Background="White">

                    <Image Source="ms-appx:///Assets/text.png" Width="20"  

 	 	 	                Stretch="Uniform"/>

                </Grid>

            </navigation:SfRadialMenu.Icon>



 </navigation:SfRadialMenu>

{% endhighlight %}

![Concepts](Concepts_images/Concepts_img4.png)
