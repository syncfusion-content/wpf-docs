---
layout: post
title: Named Ranges | Calculate | Syncfusion Essential WPF
description: This section explains that how the named ranges are works with CalcEngine in Essential Calculate for Syncfusion Essential WPF.
platform: wpf
control: Calculate
documentation: ug
---

# Named Ranges Support in Essential Calculate

Defining a name for cell, range of cells, formulas, constants or tables is called Named Ranges. By using names, users can easily identify the purpose of cell references 
also make the formulas much easier to understand and maintain.

For example, the name can be defined for the cell range of "A1:D1" as "SUMRANGE".

## Syntax to define a name

* The name can be started with a letter or underscore(_). Also, it must not be a single letter.
* The name must not be equal to cell references. For example: A1
* No space must be included and the name cannot be empty string.
* A name can contain up to 255 characters.
* The names will be case-insensitive. Thus it does not distinguish between uppercase and lowercase characters.

## Add Named Ranges

A name can be added for a cell or range of cells using [AddNamedRange](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~AddNamedRange.html) method of [CalcEngine](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine.html).

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

//Adding the name to the named range collection,
engine.AddNamedRange("GROUPCELLS", "A1:C4");

//Using the name for computing formulas,
string formula = "SUM(GROUPCELLS)";

string result = engine.ParseAndComputeFormula(formula);

{% endhighlight %}
{% endtabs %}

## Remove Named Ranges

A name can be removed from a cell or range of cells using [RemoveNamedRange](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~RemoveNamedRange.html) method of [CalcEngine](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine.html).

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

//Removing the range from NamedRange's collection,
engine.RemoveNamedRange("GROUPCELLS");

{% endhighlight %}
{% endtabs %}

## Manage Named Ranges

The names are maintained in a collection called [NamedRanges](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~NamedRanges.html). Also, the ranges of particular name can be changed or replaced using this collection.

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

//Total name ranges count,
int count = engine.NamedRanges.Count;

//Changing the range of particular named range,
engine.NamedRanges["GROUPCELLS"] = "A3:A8";

{% endhighlight %}
{% endtabs %}