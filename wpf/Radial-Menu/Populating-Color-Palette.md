---
layout: post
title: Color Palette in WPF Radial Menu | Syncfusion®
description: Create interactive color palettes using radial color items to display and select colors within the WPF Radial Menu.
platform: wpf
control: SfRadialMenu 
documentation: ug
---

# Color Palette in WPF Radial Menu (SfRadialMenu)

A color palette can be formed in the WPF Radial Menu with the radial color items. 

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



![Concepts_img5](Concepts_images/Concepts_img5.png)

