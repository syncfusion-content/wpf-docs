---
layout: post
title: Populating Color Palette | SfRadialMenu | wpf | Syncfusion
description: populating color palette
platform: wpf
control: SfRadialMenu 
documentation: ug
---

# Populating Color Palette

Color Palette can be formed in Radial Menu with the Radial Color Items. 

{%highlight xaml%}





<navigation:SfRadialMenu IsOpen="True" >

    <navigation:SfRadialMenuItem Header="Font Color">



       <navigation:SfRadialMenuItem Header="Font"/>



       <navigation:SfRadialColorItem Color="Red">

           <navigation:SfRadialColorItem Color="DarkRed"/>

           <navigation:SfRadialColorItem Color="IndianRed"/>

           <navigation:SfRadialColorItem Color="OrangeRed"/>

           <navigation:SfRadialColorItem Color="MediumVioletRed"/>

       </navigation:SfRadialColorItem>

       <navigation:SfRadialColorItem Color="Green"/>

       <navigation:SfRadialColorItem Color="Blue"/>



     </navigation:SfRadialMenuItem>

</navigation:SfRadialMenu>

{%endhighlight%}



![](Concepts_images/Concepts_img5.png)

