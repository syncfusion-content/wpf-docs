---
layout: post
title: Sort-Element
description: sort element
platform: wpf
control: OLAP Common
documentation: ug
---

# Sort Element

The result set can be sorted by using the SortElement. We can create Sort elements and add it to the OlapReport. There are four types of sorting orders. They are:

* ASC – Sort the elements in ascending order.
* BASC – Sort the elements in ascending order by breaking the Hierarchy.
* DESC – Sort the elements in Descending order.
* BDESC – Sort the elements in Descending order by breaking the Hierarchy.

The following report will illustrate the creation of Sort element:

{% highlight c# %}

SortElement sortElement = new SortElement(AxisPosition.Categorical, SortOrder.BDESC, true);

sortElement.Element.UniqueName = "[Measures].[Internet Sales Amount]";

{% endhighlight  %}

{% highlight vbnet %}

Dim sortElement As SortElement = New SortElement(AxisPosition.Categorical, SortOrder.BDESC, True)

sortElement.Element.UniqueName = "[Measures].[Internet Sales Amount]"

{% endhighlight  %}

