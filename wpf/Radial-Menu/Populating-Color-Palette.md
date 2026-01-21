---
layout: post
title: Populating Color Palette in WPF Radial Menu Control | Syncfusion®
description: Learn about populating color palette support in the Syncfusion® WPF Radial Menu (SfRadialMenu) control.
platform: WPF
control: SfRadialMenu 
documentation: ug
---

# Populating Color Palette in WPF Radial Menu (SfRadialMenu)

A color palette can be created in the Radial Menu using Radial Color Items.

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

![Concepts](Concepts_images/Concepts_img5.png)
