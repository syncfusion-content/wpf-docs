---
layout: post
title: Color Mapping in WPF HeatMap control | Syncfusion
description: Learn here all about Color Mapping support in Syncfusion WPF HeatMap (SfHeatMap) control, its elements and more.
platform: wpf
control: SfHeatMap
documentation: ug
---

# Color Mapping in WPF HeatMap (SfHeatMap)
Color mapping is used to indicate values as colors instead of numerical values. For example, if a HeatMap represents a data from 0 to 100. `ColorMapping` is used to specify a color for lower value and higher value. For any value between two values, a medium color will be automatically be chosen. 

In color mapping, when white color is set to value 0 and red color is set for value 30, as shown below.
{% highlight xaml %}
<syncfusion:ColorMappingCollection x:Key="colorMapping">
	<syncfusion:ColorMapping Value="0" Color="White"/>
	<syncfusion:ColorMapping Value="30" Color="Red"/>
</syncfusion:ColorMappingCollection>
{% endhighlight %}

Resultant HeatMap will be as shown below.

![ColorMapping](Images/ColorMapping.png)
