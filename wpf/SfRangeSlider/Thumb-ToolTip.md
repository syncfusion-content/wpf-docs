---
layout: post
title: Thumb-ToolTip
description: thumb tooltip  
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Thumb ToolTip  

The Thumb tooltip displays the current value where the Thumb stands. 



![](Thumb-ToolTip_images/Thumb-ToolTip_img1.jpeg)



## Thumb ToolTip Precision  

ThumbToolTipPrecision property is used to define the precision of the value displayed in the tooltip.  


{%highlight xml%}

[XAML]

<editors:SfRangeSlider Width="200" VerticalAlignment="Center" Minimum="0" Maximum="100" Value="50" ThumbToolTipPrecision="2"/>

{%endhighlight%}

![](Thumb-ToolTip_images/Thumb-ToolTip_img2.jpeg)



## Thumb ToolTip Position 

The position of the Thumb tooltip in relation to the Thumb can be controlled by the ThumbToolTipPlacement property. It has the following options.  

1. BottomRight 
2. TopLeft 
3. None 

### BottmRight  

Tooltip is placed either below the Thumb in horizontal orientation or right of the Thumb in vertical orientation. 

{%highlight xml%}

[XAML]

<editors:SfRangeSlider Width="200" Minimum="0" Maximum="100" Value="50" ThumbToolTipPlacement="BottonRight" />


{%endhighlight%}

![](Thumb-ToolTip_images/Thumb-ToolTip_img3.jpeg)



> _Note: This option displays the tooltip to right in vertical orientation._  

### TopLeft 

Tooltip is placed either above the Thumb in horizontal orientation or left of the Thumb in vertical orientation. 


{%highlight xml%}

[XAML]

<editors:SfRangeSlider Width="200" Minimum="0" Maximum="100" Value="50" ThumbToolTipPlacement="TopLeft" />

{%endhighlight%}

![](Thumb-ToolTip_images/Thumb-ToolTip_img4.jpeg)



> _Note: This option displays the tooltip to left in vertical orientation._  

### None 

No Tooltip appears. 



![](Thumb-ToolTip_images/Thumb-ToolTip_img5.jpeg)



