---
layout: post
title: Icon in WPF Radial Menu control | Syncfusion
description: Learn here all about Icon support in Syncfusion WPF Radial Menu (SfRadialMenu) control, its elements and more.
platform: wpf
control: SfRadialMenu 
documentation: ug
---

# Icon in WPF Radial Menu (SfRadialMenu)

The Icon property of the RadialMenu is used to customize the icon displayed in the center of RadialMenu circle.   

{%highlight xaml%}



<navigation:SfRadialMenu IsOpen="True" >

<navigation:SfRadialMenu.Icon>

                <Grid Background="White">

                    <Image Source="ms-appx:///Assets/text.png" Width="20"  

 	 	 	                Stretch="Uniform"/>

                </Grid>

            </navigation:SfRadialMenu.Icon>



 </navigation:SfRadialMenu>



{%endhighlight%}



![Concepts_img4](Concepts_images/Concepts_img4.png)


