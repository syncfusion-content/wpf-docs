---
layout: post
title: Apply the Filter through filter element| OLAPCommon | Wpf | Syncfusion
description: apply the filter through filter element
platform: wpf
control: OLAPCommon
 documentation: ug
---

# Apply the Filter through filter element

The filter element will get information such as filter condition and filter value from the user, from the filter expression and then get the elements on which the filter has to apply.

The following codes describe the creation of the filter element and its application: 

{% tabs %}
{% highlight c# %}



DimensionElement dimensionElementColumn = new DimensionElement();
//Specifying the Name for the Dimension Element
dimensionElementColumn.Name = "Customer";

MeasureElements measureElementColumn = new MeasureElements();
measureElementColumn.Elements.Add(new MeasureElement { Name = "Internet Sales Amount" });

FilterElement filterElement = new FilterElement(AxisPosition.Categorical);
filterElement.Elements.Add(measureElementColumn);
filterElement.Elements.Add(dimensionElementColumn);
filterElement.FilterCase = FilterCase.GreaterThan;
filterElement.FilterValue.Add(new MeasureElement { Name = "Internet Sales Amount", Visible = true });
filterElement.FilterValue.Add(new FilterValue { Filter_Value = 2700000.00 });
filterElement.IsFilterCondition = true;
/// Adding Column Members
olapReport.CategoricalElements.Add(dimensionElementColumn);
olapReport.CategoricalElements.IsFilterOrSortOn = true;
///Adding Measure Element
olapReport.FilterElements.Add(filterElement);


{% endhighlight  %}


{% highlight vbnet %}



Dim dimensionElementColumn As DimensionElement = New DimensionElement()

'Specifying the Name for the Dimension Element

dimensionElementColumn.Name = "Customer"



Dim measureElementColumn As MeasureElements = New MeasureElements()

measureElementColumn.Elements.Add(New MeasureElement With {.Name = "Internet Sales Amount"})



Dim filterElement As FilterElement = New FilterElement(AxisPosition.Categorical)

filterElement.Elements.Add(measureElementColumn)

filterElement.Elements.Add(dimensionElementColumn)

filterElement.FilterCase = FilterCase.GreaterThan



filterElement.FilterValue.Add(New MeasureElement With {.Name = "Internet Sales Amount", .Visible = True})



filterElement.FilterValue.Add(New FilterValue With {.Filter_Value = 2700000.0})

filterElement.IsFilterCondition = True

''' Adding Column Members

olapReport.CategoricalElements.Add(dimensionElementColumn)

olapReport.CategoricalElements.IsFilterOrSortOn = True

'''Adding Measure Element

olapReport.FilterElements.Add(filterElement)


{% endhighlight %}
{% endtabs %}

