---
layout: post
title: Small-Change
description: small change  
platform: wpf
control: Radial Slider 
documentation: ug
---

# Small Change 

The SmallChange property (Inherited from [RangeBase](http://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.primitives.rangebase.aspx)) can be used to control the smallest possible range of value to be selected in Radial Slider.  For example, if SmallChange is set to 5, then it is only possible to select values that are multiples of 5. 


{% highlight html %}

<syncfusion:SfRadialSlider

            Minimum="0" Maximum="100"  

            SmallChange="5" />


{% endhighlight %}


