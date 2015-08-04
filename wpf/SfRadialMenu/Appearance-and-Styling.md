---
layout: post
title: Appearance-and-Styling
description: appearance and styling 
platform: wpf
control: Radial Menu 
documentation: ug
---

## Appearance and Styling 

## Radius 

RadiusX and RadiusY properties in the Radial Menu can be used to define the X and Y axis radius to render the control. 


{%highlight xaml%}

[XAML]

<navigation:SfRadialMenu RadiusX="150" RadiusY="150" />

{%endhighlight%}

## CenterRimRadiusFactor

CenterRimRadiusFactor property can be used to define the radius of the center rim (inner circle). 

{%highlight xaml%}

[XAML]



<navigation:SfRadialMenu   CenterRimRadiusFactor="0.3" IsOpen="True" />

{%endhighlight%}

![][C:/Users/ApoorvahR/Desktop/7.png](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)



## RimBackground

RimBackground property used to fill the outer rim (outer circle).

{%highlight xaml%}

[XAML]

{%endhighlight%}

<navigation:SfRadialMenu IsOpen="True" RimBackground="Green" />



![][C:/Users/ApoorvahR/Desktop/8.png](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)



_RadialMenu outer ring flled with color_



## RimActiveBrush

RimActiveBrush property used to fill the expander rim and this expander rim only visible when the items have sub items.   

{%highlight xaml%}

[XAML]



<navigation:SfRadialMenu RimActiveBrush="Red" RimBackground="Green" IsOpen="True" />


{%endhighlight%}



![][C:/Users/ApoorvahR/Desktop/9.png](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)



## RimHoverBrush

The RimHoverBrush property can be used to fill the expander rim while the pointer is hovering over it. 

{%highlight xaml%}

[XAML]



<navigation:SfRadialMenu RimActiveBrush="Red" RimBackground="Green"   RimHoverBrush="Blue" IsOpen="True" />

{%endhighlight%}



![][C:/Users/ApoorvahR/Desktop/10.png](Appearance-and-Styling_images/Appearance-and-Styling_img4.png)



## RimRadiusFactor

RimRadiusFactor property of Radial Menu can be used to set the radius of the items panel. Lowest values to this factor increases the thickness of the outer rim. Highest values to this factor decreases the thickness of the outer rim. 

{%highlight xaml%}

[XAML]



<navigation:SfRadialMenu RimActiveBrush="Red" RimRadiusFactor="0.7" RimBackground="Green"   RimHoverBrush="Blue" IsOpen="True" />

{%endhighlight%}

![][C:/Users/ApoorvahR/Desktop/11.png](Appearance-and-Styling_images/Appearance-and-Styling_img5.png)



## Navigation Button Style

The navigation button displayed in the center of radial menu can be styled using NaviationButtonStyle property. 

{%highlight xaml%}

[XAML]



<syncfusion:SfRadialMenu NavigationButtonStyle="{StaticResource NavigationButtonStyle}"

IsOpen="True" />

{%endhighlight%}

## MenuMouseOverBackgroundColor

Each SfRadialMenuItem can be set with a different background color on mouse over by using the MenuMouseOverBackgroundColor property. Before that, the ShowMouseOverStyle property should be set to true.

{%highlight xaml%}

[XAML]



<navigation:SfRadialMenu IsOpen="True">
  <navigation:SfRadialMenuItem Header="Bold" MenuMouseOverBackgroundColor="Pink" ShowMouseOverStyle="true">
    <navigation:SfRadialMenuItem/>
  </navigation:SfRadialMenuItem>
  <navigation:SfRadialMenuItem Header="Copy" MenuMouseOverBackgroundColor="PaleTurquoise" ShowMouseOverStyle="true">
    <navigation:SfRadialMenuItem/>
  </navigation:SfRadialMenuItem>
  <navigation:SfRadialMenuItem Header="Undo" MenuMouseOverBackgroundColor="Pink" ShowMouseOverStyle="true">
    <navigation:SfRadialMenuItem/>
  </navigation:SfRadialMenuItem>
  <navigation:SfRadialMenuItem Header="Font Size" MenuMouseOverBackgroundColor="PaleTurquoise" ShowMouseOverStyle="true">
    <navigation:SfRadialMenuItem/>
  </navigation:SfRadialMenuItem>
 <navigation:SfRadialMenuItem Header="Color" MenuMouseOverBackgroundColor="Lavender" ShowMouseOverStyle="true">
    <navigation:SfRadialMenuItem/>
  </navigation:SfRadialMenuItem>
</navigation:SfRadialMenu> 

{%endhighlight%}

![](Appearance-and-Styling_images/Appearance-and-Styling_img6.png)



