---
layout: post
title: Appearance and Styling in WPF Radial Menu control | Syncfusion
description: Learn here all about Appearance and Styling support in Syncfusion WPF Radial Menu (SfRadialMenu) control and more.
platform: wpf
control: SfRadialMenu 
documentation: ug
---

## Appearance and Styling 

## Radius 

RadiusX and RadiusY properties in the Radial Menu can be used to define the X and Y axis radius to render the control. 


{%highlight xaml%}



<navigation:SfRadialMenu RadiusX="150" RadiusY="150" />

{%endhighlight%}

## CenterRimRadiusFactor

CenterRimRadiusFactor property can be used to define the radius of the center rim (inner circle). 

{%highlight xaml%}




<navigation:SfRadialMenu   CenterRimRadiusFactor="0.3" IsOpen="True" />

{%endhighlight%}

![Appearance-and-Styling_img1](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)



## RimBackground

RimBackground property used to fill the outer rim (outer circle).

{%highlight xaml%}




<navigation:SfRadialMenu IsOpen="True" RimBackground="Green" />

{%endhighlight%}

![Appearance-and-Styling_img2](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)



RadialMenu outer ring filled with color



## RimActiveBrush

RimActiveBrush property used to fill the expander rim and this expander rim only visible when the items have sub items.   

{%highlight xaml%}




<navigation:SfRadialMenu RimActiveBrush="Red" RimBackground="Green" IsOpen="True" />


{%endhighlight%}



![Appearance-and-Styling_img3](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)


##RimInactiveBrush

`RimInactiveBrush` property used to fill the expander rim item background when the corresponding menu item doesn’t have sub items.

{%highlight xaml%}

      <syncfusion:SfRadialMenu >
            <syncfusion:SfRadialMenuItem Header="Item 1" RimActiveBrush="SlateBlue" RimInactiveBrush="Red"/>
            <syncfusion:SfRadialMenuItem Header="Item 2" RimActiveBrush="Green">
                <syncfusion:SfRadialMenuItem Header="Item 21" />
            </syncfusion:SfRadialMenuItem>
            <syncfusion:SfRadialMenuItem Header="Item 3" RimActiveBrush="Yellow">
                <syncfusion:SfRadialMenuItem Header="Item 31"/>
            </syncfusion:SfRadialMenuItem>
            <syncfusion:SfRadialMenuItem Header="Item 4" RimActiveBrush="Orange">
                <syncfusion:SfRadialMenuItem Header="Item 41"/>
            </syncfusion:SfRadialMenuItem >
            <syncfusion:SfRadialMenuItem   Header="Item 5" IsExpanderVisible="False" RimActiveBrush="Black" RimInactiveBrush="GreenYellow" />
        </syncfusion:SfRadialMenu>


{%endhighlight%}

![Appearance-and-Styling_img7](Appearance-and-Styling_images/Appearance-and-Styling_img7.png)

## RimHoverBrush

The RimHoverBrush property can be used to fill the expander rim while the pointer is hovering over it. 

{%highlight xaml%}




<navigation:SfRadialMenu RimActiveBrush="Red" RimBackground="Green"   RimHoverBrush="Blue" IsOpen="True" />

{%endhighlight%}



![Appearance-and-Styling_img4](Appearance-and-Styling_images/Appearance-and-Styling_img4.png)

## IsExpanderVisible

Expander arrow in the OuterRim of `SfRadialMenu` visibility can be changed by `IsExpanderVisible` property of `SfRadialMenuItem`. By default, `IsExpanderVisible` value is True.

{%highlight xaml%}

      <syncfusion:SfRadialMenu >
        <syncfusion:SfRadialMenuItem Header="Item 1" RimActiveBrush="SlateBlue">      
          <syncfusion:SfRadialMenuItem Header="Item 21"/>
            </syncfusion:SfRadialMenuItem>
            <syncfusion:SfRadialMenuItem Header="Item 2" RimActiveBrush="Green"  >
                <syncfusion:SfRadialMenuItem Header="Item 21" />
            </syncfusion:SfRadialMenuItem>
            <syncfusion:SfRadialMenuItem Header="Item 3" RimActiveBrush="Yellow">
                <syncfusion:SfRadialMenuItem Header="Item 31"/>
            </syncfusion:SfRadialMenuItem>
            <syncfusion:SfRadialMenuItem Header="Item 4" RimActiveBrush="Orange">
                <syncfusion:SfRadialMenuItem Header="Item 41"/>
            </syncfusion:SfRadialMenuItem >
            <syncfusion:SfRadialMenuItem   Header="Item 5" IsExpanderVisible="False" RimActiveBrush="Black" >
                <syncfusion:SfRadialMenuItem Header="Item 41"/>
            </syncfusion:SfRadialMenuItem>
        </syncfusion:SfRadialMenu>

{%endhighlight%}

![Appearance-and-Styling_img8](Appearance-and-Styling_images/Appearance-and-Styling_img8.png)

## RimRadiusFactor

RimRadiusFactor property of Radial Menu can be used to set the radius of the items panel. Lowest values to this factor increases the thickness of the outer rim. Highest values to this factor decreases the thickness of the outer rim. 

{%highlight xaml%}




<navigation:SfRadialMenu RimActiveBrush="Red" RimRadiusFactor="0.7" RimBackground="Green"   RimHoverBrush="Blue" IsOpen="True" />

{%endhighlight%}

![Appearance-and-Styling_img5](Appearance-and-Styling_images/Appearance-and-Styling_img5.png)



## Navigation Button Style

The navigation button displayed in the center of radial menu can be styled using NavigationButtonStyle property. 

{%highlight xaml%}




<syncfusion:SfRadialMenu NavigationButtonStyle="{StaticResource NavigationButtonStyle}"

IsOpen="True" />

{%endhighlight%}

## MenuBackgroundColor

Each `SfRadialMenuItem` can be set a different background color using `MenuBackgroundColor` property.

{% tabs %}

{% highlight XAML %}

<navigation:SfRadialMenu IsOpen="True">

<navigation:SfRadialMenuItem Header="Bold" MenuBackgroundColor="Pink">

<navigation:SfRadialMenuItem/>

</navigation:SfRadialMenuItem>

<navigation:SfRadialMenuItem Header="Copy" MenuBackgroundColor="PaleTurquoise">

<navigation:SfRadialMenuItem/>

</navigation:SfRadialMenuItem>

<navigation:SfRadialMenuItem Header="Undo" MenuBackgroundColor="Pink">

<navigation:SfRadialMenuItem/>

</navigation:SfRadialMenuItem>

<navigation:SfRadialMenuItem Header="Font Size" MenuBackgroundColor="PaleTurquoise">

<navigation:SfRadialMenuItem/>

</navigation:SfRadialMenuItem>

<navigation:SfRadialMenuItem Header="Color" MenuBackgroundColor="Lavender">

<navigation:SfRadialMenuItem/>

</navigation:SfRadialMenuItem>

</navigation:SfRadialMenu>

{% endhighlight %}

{% endtabs %}

![menubackground](menu-item-customization-images/menubackground.png)

## MenuMouseOverBackgroundColor

Each SfRadialMenuItem can be set with a different background color on mouse over by using the MenuMouseOverBackgroundColor property. Before that, the ShowMouseOverStyle property should be set to true.

{%highlight xaml%}




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

![Appearance-and-Styling_img6](Appearance-and-Styling_images/Appearance-and-Styling_img6.png)



