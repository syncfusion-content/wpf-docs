---
layout: post
title: Apply Formatting for Measure elements
description: To apply the formatting for the measure and value elements in olap grid.
platform: wpf
control: OlapGrid
documentation: ug
---

# Apply Formatting for Measure elements

Olap grid provides the following format type support for the measure element and value element types.

* `Percent` - is used to display the cell value as percentage format.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Percent });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Percent})

{% endhighlight %}

{% endtabs %}

![Displaying measure as percent format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img1.png)

* `Currency` - is used to display the cell value as currency format.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Currency });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Currency})

{% endhighlight %}

{% endtabs %}

![Displaying measure as currency format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img2.png)

* `Number` - is used to display the cell value as numeric format.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Number });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Number})

{% endhighlight %}

{% endtabs %}

![Displaying measure as number format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img3.png)

* `Date` - is used to display the cell value as date format.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Date });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Date})

{% endhighlight %}

{% endtabs %}

![Displaying measure as date format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img4.png)

* `Scientific` - is used to display the cell value as scientific(exponential) format. 

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Scientific });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Scientific})

{% endhighlight %}

{% endtabs %}

![Displaying measure as scientific format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img5.png)

* `Accounting` - is used to display the cell value as accounting format.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Accounting });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Accounting})

{% endhighlight %}

{% endtabs %}

![Displaying measure as accounting format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img6.png)

* `Time` - is used to display the cell value as time format.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Time });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Time})

{% endhighlight %}

{% endtabs %}

![Displaying measure as time format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img7.png)

* `Fraction` - is used to display the cell value as fraction number format.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Fraction });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Fraction})

{% endhighlight %}

{% endtabs %}

![Displaying measure as fraction format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img8.png)

* `HexaDecimal` - is used to display the cell value as hexa decimal format.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.HexaDecimal });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.HexaDecimal})

{% endhighlight %}

{% endtabs %}

![Displaying measure as hexa decimal format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img9.png)

* `Decimal` -  is used to display the cell value as decimal format.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Decimal });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Decimal})

{% endhighlight %}

{% endtabs %}

![Displaying measure as decimal format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img10.png)

* `RoundTrip` -  is used to display the cell value as roundtrip format.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.RoundTrip });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.RoundTrip})

{% endhighlight %}

{% endtabs %}

![Displaying measure as round trip format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img11.png)

* `General` - is used to display the cell value as genaral number format.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.General });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.General})

{% endhighlight %}

{% endtabs %}

![Displaying measure as general format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img12.png)

* `FixedPoint` - is used to display the cell value as fixed point format.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.FixedPoint });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.FixedPoint})

{% endhighlight %}

{% endtabs %}

![Displaying measure as fixed point format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img13.png)

* `Custom` - is used to display the cell values with its own customer order.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.Custom, FormatString = "#0.000" });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.Custom, .FormatString = "#0.000"})

{% endhighlight %}

{% endtabs %}

![Displaying measure as custom format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img14.png)

* `None` - is used to displays the actual value from the cube without any formatting the cell value.

Refer the below code sample:

{% tabs %}

{% highlight c# %}

    MeasureElements measureElementGroup = new MeasureElements();
    measureElementGroup.Elements.Add(new MeasureElement() { ElementName = "Sales Amount", Format = NumberFormat.None });

{% endhighlight %}

{% highlight vb %}

	Dim measureElementGroup As New MeasureElements()
	measureElementGroup.Elements.Add(New MeasureElement() With {.ElementName = "Sales Amount", .Format = NumberFormat.None})

{% endhighlight %}

{% endtabs %}

![Displaying measure as none format](Apply-Formatting-for-Measure-elements_images/Apply-Formatting-for-Measure-elements_img15.png)