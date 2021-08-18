---
layout: post
title: Apply Formatting for Measure and Value Elements | Syncfusion
description: Section helps to know how to apply formatting for the measure and value elements in olap grid. | Syncfusion
platform: wpf
control: OlapGrid
documentation: ug
---

# Apply Formatting for Measure and Value Elements

The values of measure and value element can be formatted by using the `Format` property of corresponding elements. The following are the format types supported by measure and value elements:

* Currency
* Percent
* Number
* Date
* Scientific
* Accounting
* Time
* Fraction
* HexaDecimal
* Decimal
* RoundTrip
* General
* FixedPoint
* Custom
* None

N> To read the [DisplayMeasuresInDesiredOrder](https://help.syncfusion.com/wpf/olap-grid/how-to/display-measures-and-kpis-in-desired-order) section of the documentation for adding the value elements.

## Percent format

This format displays the values of measure and value element in percentage format.

Refer to the following code sample to format the measure element values in percentage format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Percent });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Percent})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in percentage format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.Percent });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Percent})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in percent format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img1.png)

## Currency format

This format displays the values of measure and value element in currency format.

Refer to the following code sample to format the measure element values in currency format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Currency });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Currency})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in currency format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.Currency });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Currency})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in currency format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img2.png)

## Number format

This format displays the values of measure and value element in numeric format.

Refer to the following code sample to format the measure element values in number format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Number });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Number})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in number format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.Number });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Number})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in number format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img3.png)

## Date format

This format displays the values of measure and value element in date format.

Refer to the following code sample to format the measure element values in date format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Date });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Date})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in date format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.Date });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Date})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in date format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img4.png)

## Scientific format

This format displays the values of measure and value element in scientific(exponential) format.

Refer to the following code sample to format the measure element values in scientific format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Scientific });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Scientific})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in scientific format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.Scientific });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Scientific})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in scientific format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img5.png)

## Accounting format

This format displays the values of measure and value element in accounting format.

Refer to the following code sample to format the measure element values in accounting format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Accounting });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Accounting})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in accounting format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.Accounting });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Accounting})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in accounting format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img6.png)

## Time format

This format displays the values of measure and value element in time format.

Refer to the following code sample to format the measure element values in time format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Time });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Time})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in time format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.Time });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Time})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in time format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img7.png)

## Fraction format

This format displays the values of measure and value element in fraction number format.

Refer to the following code sample to format the measure element values in fraction format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Fraction });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Fraction})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in fraction format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.Fraction });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Fraction})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in fraction format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img8.png)

## HexaDecimal format

This format displays the values of measure and value element in hexadecimal format.

Refer to the following code sample to format the measure element values in hexadecimal format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.HexaDecimal });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.HexaDecimal})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in hexadecimal format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.HexaDecimal });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.HexaDecimal})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in hexadecimal format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img9.png)

## Decimal format

This format displays the values of measure and value element in decimal format.

Refer to the following code sample to format the measure element values in decimal format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Decimal });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Decimal})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in decimal format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.Decimal });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Decimal})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in decimal format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img10.png)

## Round trip format

This format displays the values of measure and value element in round trip format.

Refer to the following code sample to format the measure element values in round trip format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.RoundTrip });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.RoundTrip})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in round trip format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.RoundTrip });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.RoundTrip})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in round trip format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img11.png)

## General format

This format displays the values of measure and value element in general number format.

Refer to the following code sample to format the measure element values in general format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.General });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.General})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in general format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.General });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.General})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in general format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img12.png)

## Fixed point format

This format displays the values of measure and value element in fixed point format.

Refer to the following code sample to format the measure element values in fixed point format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.FixedPoint });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.FixedPoint})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in fixed point format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.FixedPoint });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.FixedPoint})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in fixed point format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img13.png)

## Custom format

This format displays the values of measure and value element in custom format. You can define the format of values by using the `FormatString` property.

Refer to the following code sample to format the measure element values in custom format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Custom, FormatString = "#0.000" });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Custom, .FormatString = "#0.000"})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in custom format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Custom, FormatString = "#0.000" });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New MeasureElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Custom, .FormatString = "#0.000"})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in custom format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img14.png)

## None format

This format displays the actual value from the cube without formatting the cell value.

Refer to the following code sample to format the measure element values in none format.

{% tabs %}

{% highlight c# %}

MeasureElements measureElementGroup = new MeasureElements();
measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.None });
olapReport.CategoricalElements.Add(measureElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim measureElementGroup As New MeasureElements()
measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.None})
olapReport.CategoricalElements.Add(measureElementGroup)

{% endhighlight %}

{% endtabs %}

Refer to the following code sample to format the value element values in none format.

{% tabs %}

{% highlight c# %}

ValueElements valueElementGroup = new ValueElements();
valueElementGroup.Elements.Add(new ValueElement() { ElementName = "Sales Amount", Format = NumberFormat.None });
olapReport.CategoricalElements.Add(valueElementGroup);

{% endhighlight %}

{% highlight vb %}

Dim valueElementGroup As New ValueElements()
valueElementGroup.Elements.Add(New ValueElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.None})
olapReport.CategoricalElements.Add(valueElementGroup)

{% endhighlight %}

{% endtabs %}

![Displaying measure values in none format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img15.png)