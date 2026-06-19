---
layout: post
title: Appearance and Styling in WPF Radial Menu Control | Syncfusion®
description: Learn about appearance and styling support in the Syncfusion® WPF Radial Menu (SfRadialMenu) control.
platform: WPF
control: SfRadialMenu 
documentation: ug
---

# Appearance and Styling

## Radius

The `RadiusX` and `RadiusY` properties in the Radial Menu define the X and Y axis radii to render the control.


{%highlight xaml%}



<navigation:SfRadialMenu RadiusX="150" RadiusY="150" />

{%endhighlight%}

## CenterRimRadiusFactor

The `CenterRimRadiusFactor` property defines the radius of the center rim (inner circle).

{%highlight xaml%}

<navigation:SfRadialMenu CenterRimRadiusFactor="0.3" IsOpen="True" />

{% endhighlight %}

![Appearance-and-Styling](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)

## RimBackground

The `RimBackground` property fills the outer rim (outer circle).

{%highlight xaml%}




<navigation:SfRadialMenu IsOpen="True" RimBackground="Green" />

{%endhighlight%}

![Appearance-and-Styling](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)

The outer ring of the Radial Menu filled with color.

## RimActiveBrush

The `RimActiveBrush` property fills the expander rim, which is visible only when the items have sub-items.

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

{% endhighlight %}

![Appearance-and-Styling](Appearance-and-Styling_images/Appearance-and-Styling_img7.png)

## RimHoverBrush

The `RimHoverBrush` property fills the expander rim while the pointer hovers over it.

{%highlight xaml%}

<navigation:SfRadialMenu RimActiveBrush="Red" RimBackground="Green" RimHoverBrush="Blue" IsOpen="True" />

{% endhighlight %}

![Appearance-and-Styling](Appearance-and-Styling_images/Appearance-and-Styling_img4.png)

## IsExpanderVisible

The visibility of the expander arrow in the OuterRim of `SfRadialMenu` can be changed by the `IsExpanderVisible` property of `SfRadialMenuItem`. By default, `IsExpanderVisible` is set to `True`.

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

![Appearance-and-Styling](Appearance-and-Styling_images/Appearance-and-Styling_img8.png)

## RimRadiusFactor

The `RimRadiusFactor` property of the Radial Menu sets the radius of the items panel. Lower values increase the thickness of the outer rim, whereas higher values decrease it.

{%highlight xaml%}

<navigation:SfRadialMenu RimActiveBrush="Red" RimRadiusFactor="0.7" RimBackground="Green" RimHoverBrush="Blue" IsOpen="True" />

{% endhighlight %}

![Appearance-and-Styling](Appearance-and-Styling_images/Appearance-and-Styling_img5.png)

## Navigation Button Style

The navigation button displayed in the center of the radial menu can be styled using the `NavigationButtonStyle` property.

{%highlight xaml%}




<syncfusion:SfRadialMenu NavigationButtonStyle="{StaticResource NavigationButtonStyle}"

IsOpen="True" />

{%endhighlight%}

## MenuBackgroundColor

The `MenuBackgroundColor` property allows each `SfRadialMenuItem` to have a different background color.
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

![Menu Background](menu-item-customization-images/menubackground.png)

## MenuMouseOverBackgroundColor

The `MenuMouseOverBackgroundColor` property sets a different background color on mouse-over for each `SfRadialMenuItem`. Ensure the `ShowMouseOverStyle` property is set to `True`.
{% highlight xaml %}

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

![Appearance-and-Styling](Appearance-and-Styling_images/Appearance-and-Styling_img6.png)
