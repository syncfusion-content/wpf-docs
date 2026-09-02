---
layout: post
title: Icon Customization in WPF Radial Menu | Syncfusion®
description: Customize the icon displayed in the center of the WPF Radial Menu to provide a distinctive navigation experience.
platform: wpf
control: SfRadialMenu 
documentation: ug
---

# Icon Customization in WPF Radial Menu (SfRadialMenu)

The Icon property of the WPF Radial Menu is used to customize the icon displayed in the center of WPF Radial Menu circle.   

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


