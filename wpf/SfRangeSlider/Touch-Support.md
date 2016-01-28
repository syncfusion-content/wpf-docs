---
layout: post
title: Touch Support | SfRangeSlider | wpf | Syncfusion
description: touch support
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Touch Support

With the MoveToPoint property, you can move the thumb of the SfRangeSlider by tapping or clicking on the track of the SfRangeSlider. This property provides the following options:

* MoveToTapPosition
* IncrementBySmallChange
* IncrementByLargeChange
* None



### MoveToTapPosition

To move the thumb of the SfRangeSlider to the tapped position, you have to set the MoveToPoint property to MoveToTapPosition, and then tap or click on the track of the SfRangeSlider. This moves the thumb to the tapped position.

The following code example and screenshot illustrates the above.

{%highlight xaml%}




<editors:SfRangeSlider Height="200" Width="400” HorizontalAlignment="Center" Minimum="0" Maximum="100" Value="50" SmallChange="5" LargeChange="10" MoveToPoint="MoveToTapPosition"/>

{%endhighlight%}

![](Touch-Support_images/Touch-Support_img1.png)



### IncrementBySmallChange

To move the thumb of the SfRangeSlider based on the SmallChange value, you have to set the MoveToPoint property to IncrementBySmallChange, and then tap or click on the track of the SfRangeSlider. This increments the SfRangeSlider value by the SmallChange value.

The following code example and screenshot illustrates the above.

{%highlight xaml%}




<editors:SfRangeSlider Height="200" Width="400” HorizontalAlignment="Center" Minimum="0" Maximum="100" Value="50" SmallChange="5" LargeChange="10" MoveToPoint="IncrementBySmallChange"/>

{%endhighlight%}

![](Touch-Support_images/Touch-Support_img2.png)



### IncrementByLargeChange

To move the thumb of the SfRangeSlider based on the LargeChange value, you have to set the MoveToPoint property to IncrementByLargeChange, and then tap on the track of the SfRangeSlider. This increments the SfRangeSlider value by the LargeChange value.

The following code example and screenshot illustrates the above.

{%highlight xaml%}





<editors:SfRangeSlider Height="200" HorizontalAlignment="Center" Minimum="0" Maximum="100" Value="50" SmallChange="5" LargeChange="10" Width="400” MoveToPoint="IncrementByLargeChange"/>

{%endhighlight%}

![](Touch-Support_images/Touch-Support_img3.png)



### None

To fix the thumb movement of the SfRangeSlider, you have to set the MoveToPoint property to _None_. This does not allow thumb movement of the SfRangeSlider.

The following code example and screenshot illustrates the above.

{%highlight xaml%}




<editors:SfRangeSlider Height="200" Width="400” HorizontalAlignment="Center" Minimum="0" Maximum="100" Value="50" SmallChange="5" LargeChange="10" MoveToPoint="None"/>

{%endhighlight%}

![](Touch-Support_images/Touch-Support_img4.png)







