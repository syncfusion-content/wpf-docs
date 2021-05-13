---
layout: post
title: Legend in WPF HeatMap control | Syncfusion
description: Learn here all about Legend support in Syncfusion WPF HeatMap (SfHeatMap) control, its elements and more.
platform: wpf
control: SfHeatMap
documentation: ug
---

# Legend in WPF HeatMap (SfHeatMap)
Legend is a control used to summarize the range of colors in HeatMap. This gives visual guideline for mapping between value and color.

## Create Legend
Legend can be created with color mapping as shown below,

{% highlight xaml %}

<syncfusion:ColorMappingCollection x:Key="colorMapping">
    <syncfusion:ColorMapping Value="0" Color="#fe0002" Label="Poor"/>
    <syncfusion:ColorMapping Value="3" Color="#ffff01" Label="Average"/>
    <syncfusion:ColorMapping Value="6" Color="#13ab11" Label="Good"/>
    <syncfusion:ColorMapping Value="10" Color="#005ba2 " Label="Excellent"/>
</syncfusion:ColorMappingCollection>

<syncfusion:SfHeatMapLegend ColorMappingCollection="{StaticResource colorMapping}"/>

{% endhighlight %}

Resultant legend will be like following image,

![Legend](Images/Legend.png)

## Legend Mode
There are two modes for Legend

* Gradient
* List


### Gradient:
{% highlight xaml %}
<syncfusion:SfHeatMapLegend 
	LegendMode="Gradient" 
	ColorMappingCollection="{StaticResource colorMapping}"/>
{% endhighlight %}

![Legend_Gradient](Images/Legend_Gradient.png)

### List:
{% highlight xaml %}
<syncfusion:SfHeatMapLegend
	LegendMode="List" 
	ColorMappingCollection="{StaticResource colorMapping}"/>
{% endhighlight %}

![Legend_List](Images/Legend_List.png)

## Orientation
There are 2 types of Orientation, applicable for Gradient and List Mode
* Horizontal
* Vertical

### Horizontal:
{% highlight xaml %}
<syncfusion:SfHeatMapLegend 
	LegendMode="List" 
	Orientation="Horizontal" 
	ColorMappingCollection="{StaticResource colorMapping}"/>
{% endhighlight %}

![Legend_Horizontal](Images/Legend_Horizontal.png)

### Vertical:
{% highlight xaml %}
<syncfusion:SfHeatMapLegend 
	LegendMode="List" 
	Orientation="Vertical" 
	ColorMappingCollection="{StaticResource colorMapping}"/>
{% endhighlight %}

![Legend_Vertical](Images/Legend_Vertical.png)
