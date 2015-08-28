---
layout: post
title: Calculated-Member
description: calculated member
platform: wpf
control: OLAP Common 
documentation: ug
---

# Calculated Member

Calculated Members are the customized measures or dimension members created with the cube. The values are calculated at run-time. It is a user defined Element. The two types of calculated members are as follows:

1. Calculated Measure – Calculated member created from a measure element
2. Calculated Dimension – Calculated member created from a dimension



## Calculated Member to be defined in OlapReport requires the following definitions:

* Name – Name of the calculated member
* Expression – Expression to form the calculated member
* Measure/Dimension Element – You should add a measure or dimension element from which the calculated member should be created.

## The following steps will explain how to create and add a calculated member in an OlapReport

1. Create the dimension measure or dimension element from which the calculated member has to be created.
2. Create the calculated member by giving the name and expression.
3. Add the element created in Step 1 to the calculated member.
4. Once the calculated member is defined, add that member to the calculated member collection in an OlapReport.
5. Add the newly created calculated members in the categorical or series axis of an OlapReport.



## The following code snippet will describe the creation and addition of a calculated member in OlapReport:



## Calculated Measure



{% highlight c# %}

MeasureElement measureElement = new MeasureElement();

measureElement.Name = "Order Quantity";

CalculatedMember calculatedMeasure = new CalculatedMember();

calculatedMeasure.Name = "Oder on Discount"; 

calculatedMeasure1.Expression = "[Measures].[Order Quantity] + ([Measures].[Order Quantity] * 0.10)";

calculatedMeasure1.AddElement(measureElement);

olapReport.CalculatedMembers.Add(calculatedMeasure);

{% endhighlight  %}

{% highlight vbnet %}

Private measureElement As MeasureElement = New MeasureElement()

measureElement.Name = " Order Quantity "

Dim calculatedMeasure As CalculatedMember = New CalculatedMember()

calculatedMeasure.Name = " Order on Discount "

calculatedMeasure1.Expression = "[Measures].[Order Quantity] + ([Measures].[Order Quantity] *0.10)"

calculatedMeasure1.AddElement(measureElement)

olapReport.CalculatedMembers.Add(calculatedMeasure)

{% endhighlight  %}

## Calculated Dimension

{% highlight c# %}

DimensionElement internalDimension = new DimensionElement();

internalDimension.Name = "Product";

internalDimension.AddLevel("Product Categories", "Category");

// Calculated Dimension

CalculatedMember calculateDimension = new CalculatedMember();

calculateDimension.Name = "Bikes & Components";

calculateDimension.Expression = "([Product].[Product Categories].

[Category].[Bikes] + [Product].[Product Categories].[Category].

[Components] )";

calculateDimension.AddElement(internalDimension);

olapReport.CalculatedMembers.Add(calculateDimension)

{% endhighlight  %}

{% highlight vbnet %}

Dim internalDimension As DimensionElement = New DimensionElement()

internalDimension.Name = "Product"

internalDimension.AddLevel("Product Categories", "Category")

' Calculated Dimension

Dim calculateDimension As CalculatedMember = New CalculatedMember()

calculateDimension.Expression = "Bikes & Components"

calculateDimension.Expression = "([Product].[Product Categories].

[Category].[Bikes] + [Product].[Product Categories].[Category].

[Components] )"

calculateDimension.AddElement(internalDimension)

olapReport.CalculatedMembers.Add(calculateDimension)

{% endhighlight  %}

