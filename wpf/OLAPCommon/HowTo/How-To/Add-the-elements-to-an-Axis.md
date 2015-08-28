---
layout: post
title: Add-the-elements-to-an-Axis
description: add the elements to an axis
platform: wpf
control: OLAP Common
documentation: ug
---

# Add the elements to an Axis

After creating the element, add the element to the specific axis. The OlapReport contains the axis as CategoricalElements, SeriesElement and SliceElements. By adding the created elements to any of these elements group, you can specify the axis position of the elements.

The following codes will describe the adding of the elements to categorical, series element:

{% highlight c# %}



///Adding Column Members
olapReport.CategoricalElements.Add(dimensionElementColumn);
///Adding Measure Element
olapReport.CategoricalElements.Add(measureElementColumn);

///Adding Row Members
olapReport.SeriesElements.Add(dimensionElementRow);

{% endhighlight  %}



{% highlight vbnet %}



'''Adding Column Members

olapReport.CategoricalElements.Add(dimensionElementColumn)

'''Adding Measure Element

olapReport.CategoricalElements.Add(measureElementColumn)



'''Adding Row Members

olapReport.SeriesElements.Add(dimensionElementRow)



{% endhighlight  %}

