---
layout: post
title: NamedSet-Element
description: namedset element
platform: wpf
control: OLAP Common
documentation: ug
---

# NamedSet Element

A named set is a collection of tuples and members, which can be defined and saved as a part of the cube definition. Named set records reside inside the sets folder, which is under a dimension element. These elements can be dragged to Categories/Series/Slicer axis of Axes Element Builder. To help make working with a lengthy, complex, or commonly used expression easier, Multidimensional Expressions (MDX) lets you to define a named set.

The following code will describe the creation of a Named set Element:

{% highlight c# %}

NamedSetElement dimensionElementRow = new NamedSetElement();

// Specifying the dimension name

dimensionElementRow.Name = "Negative Margin Products";


{% endhighlight  %}




{% highlight vbnet %}

Dim dimensionElementRow As NamedSetElement = New NamedSetElement()

' Specifying the dimension name

dimensionElementRow.Name = "Negative Margin Products"

{% endhighlight  %}

