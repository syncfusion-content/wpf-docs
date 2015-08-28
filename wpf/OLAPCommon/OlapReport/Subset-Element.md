---
layout: post
title: Subset-Element
description: subset element
platform: wpf
control: OLAP Common
documentation: ug
---

# Subset Element

Subset Elements are used to filter the result set by their count. It will just filter the number records and number of fields in the result set.

The following codes will illustrate the creation of a Subset Element:

{% highlight c# %}

SubsetElement subSetElementColumn = new SubsetElement(5);
subSetElementColumn.Name = "Top 5 Elements";
SubsetElement subSetElementRow = new SubsetElement(3);
subSetElementRow.Name = "Top 3 Elements";

olapReport.CategoricalElements.SubSetElement = subSetElementColumn;

olapReport.SeriesElements.SubSetElement = subSetElementRow;
{% endhighlight  %}


{% highlight vbnet %}

Dim subSetElementColumn As SubsetElement = New SubsetElement(5)

subSetElementColumn.Name = "Top 5 Elements"

Dim subSetElementRow As SubsetElement = New SubsetElement(3)

subSetElementRow.Name = "Top 3 Elements"

olapReport.CategoricalElements.SubSetElement = subSetElementColumn

olapReport.SeriesElements.SubSetElement = subSetElementRow

{% endhighlight  %}

