---
layout: post
title: Icon
description: icon
platform: wpf
control: Radial Menu 
documentation: ug
---

# Icon  

The Icon property of the RadialMenu is used to customize the icon displayed in the center of RadialMenu circle.   

{%highlight xml%}

[XAML]



<navigation:SfRadialMenu IsOpen="True" >

<navigation:SfRadialMenu.Icon>

                <Grid Background="White">

                    <Image Source="ms-appx:///Assets/text.png" Width="20"  

 	 	 	                Stretch="Uniform"/>

                </Grid>

            </navigation:SfRadialMenu.Icon>



 </navigation:SfRadialMenu>



{%endhighlight%}



![](Concepts_images/Concepts_img4.png)


