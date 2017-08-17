---
layout: post
title: Performance and Limitations
description: Describes how to improve the performance of Essential Calculate and its limitations
platform: wpf
control: Calculate
documentation: ug
---

# Performance and Limitations

This section explains about the performance and limitations of Essential Calculate.

## To improve the performance

By default, [CalcEngine](https://help.syncfusion.com/cr/cref_files/windowsforms/calculate/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine.html) calculates the formulas quickly. But to improve the performance in Essential Calculate, user need to set the following
properties of `CalcEngine`.

**AllowShortCircuitIFs**

If the application contains more nested if formulas for calculation, then setting [AllowShortCircuitIFs](https://help.syncfusion.com/cr/cref_files/windowsforms/calculate/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~AllowShortCircuitIFs.html) property to `true` computes the formulas
quickly.

**CalculatingSuspended**

If there are more number of dependent cells in the formulas for calculation, then user can set [CalculatingSuspended](https://help.syncfusion.com/cr/cref_files/windowsforms/calculate/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~CalculatingSuspended.html) property to `true`, 
to suspend calculations while a series of changes are made to dependent cells either by the user or programmatically.

**UseFormulaValues**

To avoid the repeated calculations for a formula cell which contains more dependency cells, set [UseFormulaValues](https://help.syncfusion.com/cr/cref_files/windowsforms/calculate/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~UseFormulaValues.html) property to `true` to
return the formula value stored in [FormulaInfoTable](https://help.syncfusion.com/cr/cref_files/windowsforms/calculate/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~FormulaInfoTable.html).

**Parse Formula and Compute Formula**

[ParseFormula](https://help.syncfusion.com/windowsforms/calculate/parse-and-compute#parse-formula) method in `CalcEngine` parses the formula in the cell and user can 
reset the value of variables or dependent cell values of formula cell at runtime and get the updated result by computing the parsed formula using 
[ComputeFormula](https://help.syncfusion.com/windowsforms/calculate/parse-and-compute#computeformula) method which avoids the repeated parsing of formula.

**For Example:**

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

//Set values to the variables
calcData.SetValueRowCol(100, 1, 1); 
calcData.SetValueRowCol(200, 1, 2);
calcData.SetValueRowCol(140, 2, 2);
calcData.SetValueRowCol(120, 3, 2);
calcData.SetValueRowCol(100, 4, 2);  

//Parsing the formula,
var parsedFormula = engine.ParseFormula("=SUM(A1:E4)"); 

//Computing the value of parsed formula,
string result = engine.ComputeFormula(parsedFormula);

//Computes the nested IF formulas quickly,
engine.AllowShortCircuitIFs = true;

//To avoid the repeated calculations,
engine.UseFormulaValues = true;

// Turn off calculations,
engine.CalculatingSuspended = true;

// Makes multiple updates to cells involved in calculation
for (int i = 0; i < 5000; i++)
{
    for (int j = 0; j < 5000; j++)
    {
        calcData.SetValueRowCol(random.Next(5) + 1,i,j);
    }
}

// Turn on calculations,
engine.CalculatingSuspended = false;

//Again computing the value of parsed formula,
result = engine.ComputeFormula(parsedFormula);

{% endhighlight %}
{% endtabs %}

## To avoid stack overflow exception

To avoid the stack overflow exception while computing the formulas iteratively exceeding the maximum capacity, user need to set the following properties of `CalcEngine`,

[**ThrowCircularException**](https://help.syncfusion.com/cr/cref_files/windowsforms/calculate/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~ThrowCircularException.html) 

Setting this property to `true` will throw an exception when the circular exception is encountered and also
avoids the recursive looping.

[**IterationMaxCount**](https://help.syncfusion.com/cr/cref_files/windowsforms/calculate/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~IterationMaxCount.html)

`CalcEngine` provides an option to set iterative calculations and maximum iteration count to calculate the formula having circular references.
The default value is 0 indicating that iterative calculation support is turned off. `ThrowCircularException` property will be automatically set
to `true` when you set a non-zero value to `IterationMaxCount`.

[**MaximumRecursiveCalls**](https://help.syncfusion.com/cr/cref_files/windowsforms/calculate/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~MaximumRecursiveCalls.html)

`CalcEngine` have `MaximumRecursiveCalls` property for which value is 100 by default. So, if the recursive call during calculations exceeds more than 100, 
stack overflow exception occurs which can be avoided by setting this property to required limit at the sample level.

[**MaxStackDepth**](https://help.syncfusion.com/cr/cref_files/windowsforms/calculate/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~MaxStackDepth.html)

`CalcEngine` have `MaxStackDepth` property for which value is 50 by default. So, if the stack size is exceeding more than 50, stack overflow exception 
occurs which can be avoided by setting this property to required limit at the sample level. 

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

CalcEngine.MaxStackDepth = 10000;   
engine.MaximumRecursiveCalls = 10000;
engine.IterationMaxCount = 10000;  

{% endhighlight %}
{% endtabs %} 

If the _stack overflow exception_ occurs even after setting these properties, user need to calculate the value in the thread by
specifying the maximum stack size (Default stack size is 1 Mb. Throws exception if exceeds).    

{% tabs %}
{% highlight c# %}

private string calValue1;
CalcEngine engine;  
private void Main()  
{   
    //Class derived from ICalcData,
    CalcData calcData = new CalcData();

    engine = new CalcEngine(calcData);
    calValue1 = String.Empty;   
    var maxSize = 10000000; 

    var thread = new Thread(GetCalculatedValue, maxSize);   
    thread.Start();   
    thread.Join();   

    MessageBox.Show("val:" + calValue1);   
}   
   
private void GetCalculatedValue()   
{        
    engine.UseFormulaValues = true;   
    engine.MaximumRecursiveCalls = 10000;   
    CalcEngine.MaxStackDepth = 10000; 

    //Computing the value of formula cell "D1",
    calValue1 = engine.ParseAndComputeFormula("D1");   
}   

{% endhighlight %}
{% endtabs %} 

## Limitations

* Essential Calculate is not a UI component, but it can be can be added to the user’s own business objects.

* Essential Calculate does not support to localize the registered formulas in the Calculate API to any specific language other 
  than English(en-US), which is by default. But we have support to compute the formulas in different region settings.

* The parameters passed in any of the function library of Essential Calculate is of type string.

