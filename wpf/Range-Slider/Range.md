---
layout: post
title: Range | SfRangeSlider | wpf | Syncfusion
description: range 
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Range 

The SfRangeSlider control supports to select range of value using two Thumbs.  

## ShowRange  

When ShowRange property is set to true, two Thumbs are placed in the track. One thumb is used to update the start of the range selection and another thumb is used to update the end of the range selection.  

{%highlight xaml%}


<editors:SfRangeSlider Width="200" VerticalAlignment="Center" Minimum="0" Maximum="100" ShowRange="True" RangeStart="40" RangeEnd="70"/>

{%endhighlight%}

![](Range_images/Range_img1.jpeg)



## RangeStart  

Gets or sets the start value of the range start.  

{%highlight xaml%}


<editors:SfRangeSlider Width="200" VerticalAlignment="Center" Minimum="0" Maximum="10" ShowRange="True" RangeStart="10" RangeEnd="70"/>

{%endhighlight%}

![](Range_images/Range_img2.jpeg)



## RangeEnd 

Gets or sets the end value of the range end.  

{%highlight xaml%}


<editors:SfRangeSlider Width="200" VerticalAlignment="Center" Minimum="0" Maximum="100" ShowRange="True" RangeStart="30" RangeEnd="90"  />

{%endhighlight%}

![](Range_images/Range_img3.jpeg)



