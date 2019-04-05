---
layout: post
title: Working with CalcEngine | Calculate | Syncfusion Essential WPF
description: This section provides a basic idea of properties and methods maintained in CalcEngine for Syncfusion Essential WPF.
platform: wpf
control: Calculate
documentation: ug
---

# Working with CalcEngine 

[CalcEngine](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine.html) encapsulates the code required to parse and compute the formulas. It manages several library functions, hash tables for Essential Calculate.  
All the data's in `CalcEngine` is assumed to be part of a rectangular array reference through cell coordinates.

## Computation using CalcEngine

The [CalcEngine](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine.html) interface allows the `CalcEngine` class to communicate with arbitrary data sources that implement this interface.
If any user defined class which implements the `ICalcData` interface needs to be integrated with `CalcEngine`, then that class’s object can be passed as parameter 
to the `CalcEngine` constructor.

The [ParseAndComputeFormula](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~ParseAndComputeFormula.html) method of `CalcEngine` parses and computes the string formula passed in and updates the computed value.

### Using ICalcData

The `ICalcData` object can be integrated into `CalcEngine` by passing it through constructor. Now, you can compute the expressions or equations using `ParseAndComputeFormula`.

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

//Computing Expressions,

string formula = "(5+25) *2";
string result = engine.ParseAndComputeFormula(formula);

//Computing In-Built formulas,

string formula = “SUM (4,5,6)”;
string result = engine.ParseAndComputeFormula(formula);

{% endhighlight %}
{% endtabs %}

### Using CalcQuickBase

[CalcQuickBase](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcQuickBase.html) is predefined derived class from `ICalcData` interface. So, user can pass the `CalcQuickBase's` object as parameter to the constructor of `CalcEngine` for 
computations.

{% tabs %}
{% highlight c# %}

CalcQuickBase calcQuick = new CalcQuickBase();

//Computing Expressions,

string formula = "(5+25) *2";
string result = calcQuick.Engine.ParseAndComputeFormula(formula);

//Computing In-Built formulas,

string formula = “SUM (4,5,6)”;
string result = calcQuick.Engine.ParseAndComputeFormula(formula);

{% endhighlight %}
{% endtabs %}

## Data Objects maintained in CalcEngine

To track information used during calculations, `CalcEngine` manages several hash tables. In `CalcEngine`, the data's are referred in cell coordinates and these references are maintained as keys in the hash tables.

Below find the list of hash tables in `CalcEngine` and a description of their keys and values.

<table>
<tr>
<th>
Hash Table</th><th>
Key</th><th>
Value</th><th>
Description</th></tr>
<tr>
<td>
{{ '[FormulaInfoTable](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~FormulaInfoTable.html) ' | markdownify }}</td><td>
Cell reference</td><td>
FormulaInfo object</td><td>
Tracks formula/value information for this cell.</td></tr>
<tr>
<td>
{{ '[DependentCells](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~DependentCells.html) ' | markdownify }}</td><td>
Cell reference</td><td>
Hashtable object</td><td>
Tracks cells that depend on this cell.</td></tr>
<tr>
<td>
{{ '[DependentFormulaCells](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~DependentFormulaCells.html) ' | markdownify }}</td><td>
Formula cell reference</td><td>
Hashtable object</td><td>
Tracks cells in which the formula cell depends upon.</td></tr>
<tr>
<td>
{{ '[NamedRanges](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~NamedRanges.html) ' | markdownify }}</td><td>
Name string</td><td>
Value string</td><td>
Associates the named range with its value.</td></tr>
<tr>
<td>
{{ '[LibraryFunctions](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~LibraryFunctions.html) ' | markdownify }}</td><td>
Function name</td><td>
LibraryFunction delegate</td><td>
Associates the function name with its method.</td></tr>
</table>

## Properties in CalcEngine

### ExcelLikeComputations

To return the result of formula computations of Essential Calculate like Microsoft Excel computational result, this bool property [ExcelLikeComputations](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~ExcelLikeComputations.html) is set to true.

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

engine.ExcelLikeComputations = true;

//Computing the DATE formula similar to excel,
string formula = “DATE(2004,5,6)”;

string result = engine.ParseAndComputeFormula(formula);

{% endhighlight %}
{% endtabs %}

### AllowShortCircuitIFs

To specifically avoid the computing of non-used alternative in IF function calculations, set [AllowShortCircuitIFs](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~AllowShortCircuitIFs.html) to true.
The default value is false for code legacy consistency. But when it is set as true, only the necessary alternative of an IF function is computed which 
leads to increase in performance.

### AlwaysComputeDuringRefresh

If `PullUpdatedValue` method is exclusively used to retrieve the computed values, then setting [AlwaysComputeDuringRefresh](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~AlwaysComputeDuringRefresh.html) property to false
may be more efficient as it will only recompute the value once during the calculations.

### CalculatingSuspended

[CalculatingSuspended](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~CalculatingSuspended.html) property is set to true, to suspend calculations while a series of changes are made to dependent cells either by the user or programmatically. 
When the changes are complete, set this property to false, and then call [RecalculateRange](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~RecalculateRange.html) to recalculate the affected ranges.

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

// Turn off calculations
engine.CalculatingSuspended = true;

// Makes multiple updates to cells involved in calculation
for (int i = 0; i < 5; i++)
{
    for (int j = 0; j < 5; j++)
    {
        calcData.SetValueRowCol(random.Next(5) + 1,i,j);
    }
}

// Turn on calculations
engine.CalculatingSuspended = false;

// invoke RecalculateRange, so any formulas in the data can be computed. 
engine.RecalculateRange(RangeInfo.Cells(4, 4, 2, 1), calcData);   

{% endhighlight %}
{% endtabs %}

### UseFormulaValues

This property is set to true, when a cell contains more dependency cells to return the formula value stored in `FormulaInfoTable` to avoid 
repeated calculations.

### CheckDanglingStack

While computing certain formulas, Essential Calculate ignores the dangling value in the calculation stack and returns the computed value.
If you want this situation flagged as a invalid formula, then set [CheckDanglingStack](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~CheckDanglingStack.html) property to true. The default value is false for backward compatibility purpose.

### ForceRefreshCall

If a value changes, then the [Refresh](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~Refresh.html) method is called recursively every time whenever the [ValueChanged](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.ICalcData~ValueChanged_EV.html) event of `ICalcData` is fired. Setting this [ForceRefreshCall](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~ForceRefreshCall.html) property to false will call the `Refresh` method for only the cells whose calculated value is actually modified.

### FormulaCharacter

In general, in order for Essential Calculate to recognize a string as containing a formula; then the string is required to start with the [FormulaCharacter](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~FormulaCharacter.html). 
A static property that gets or sets the character to identify the formula. The default value is "=".

### GetValueFromArgPreserveLeadingZeros

If you want to preserve the leading zeros in [GetValueFromArg](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~GetValueFromArg.html) method, then set [GetValueFromArgPreserveLeadingZeros](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~GetValueFromArgPreserveLeadingZeros.html) to true.

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

//Assign a value with leading zeros to "A1" cell,
calcData.SetValueRowCol(04510, 1, 1);

CalcEngine engine = new CalcEngine(calcData);

//Setting this property to true, for preserving leading zeros,
engine.GetValueFromArgPreserveLeadingZeros = true;

//Returns the result with leading zeros,
string result = engine.GetValueFromArg("A1")

{% endhighlight %}
{% endtabs %}

### IterationMaxCount

Gets or sets the maximum number of iterative calls that can be made on a cell to avoid circular exception. The default value is 0 indicating that iterative 
calculation support is turned off. [ThrowCircularException](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~ThrowCircularException.html) property will be automatically set to true when you set a non-zero value to [IterationMaxCount](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~IterationMaxCount.html).

### IterationMaxTolerance

Gets or sets the success tolerance used by the `CalcEngine's` iterative calculation support. The iterations in calculation continues until either the iteration count 
exceeds IterationMaxCount, or two successive iteration return values have a relative difference less than [IterationMaxTolerance](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~IterationMaxTolerance.html). The default value is 0.001.

### LockDependencies

A bool property that gets or sets whether a changed value should trigger dependent changes.

### MaximumRecursiveCalls

Specifies the maximum number of recursive calls that can be used to compute a cell value.This property comes into play when you have a calculated formula cell that depends on
another calculated formula that depends on another calculated formula and so on. If the depends on another formula exceeds [MaximumRecursiveCalls](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~MaximumRecursiveCalls.html), you will see a too complex message displayed in the cell. The default value is 100, but you can set it higher or lower depending upon your expected needs. The purpose of the limit is to avoid a circular 
reference locking up your application.

### MaxStackDepth

Gets or sets the maximum calculation stack depth. The default value is 50. This is the number of recursive calls that can be made during calculations.

### ParseArgumentSeparator

A static property that gets or sets the character to be recognized by the parsing code as the delimiter for arguments in a named formula's argument list. The default value is ','.

{% tabs %}
{% highlight c# %}

//Assign the argument separator,
CalcEngine.ParseArgumentSeparator = ';';

{% endhighlight %}
{% endtabs %}

### ParseDecimalSeparator

A static property that gets or sets the character to be recognized by the parsing engine as decimal separator for numbers. The default value is '.'.

{% tabs %}
{% highlight c# %}

//Assign the decimal separator,
CalcEngine.ParseDecimalSeparator = ',';

{% endhighlight %}
{% endtabs %}

### ParseDateTimeSeparator

A static property that gets/sets the character to be recognized by the parsing engine as decimal separator for date. The default value is '/'.

{% tabs %}
{% highlight c# %}

//Assign the date time separator,
CalcEngine.ParseDateTimeSeparator = '-';

{% endhighlight %}
{% endtabs %}

### RethrowLibraryComputationExceptions

Gets or sets whether the `CalcEngine` rethrow any exception raised during the computation of a library function. The default value is false.

### SupportLogicalOperators

 If you want to use any logical operators such as AND, OR, XOR,... in a formula, you can set [SupportLogicalOperators](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~SupportLogicalOperators.html) property of `CalcEngine` as true .

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

engine.SupportLogicalOperators = true;

string result = engine.ParseAndComputeFormula(“=IF("C"="S "OR" C"="C",1,2)”);

{% endhighlight %}
{% endtabs %}

### SupportsSheetRanges

Gets or sets whether the sheet range notation is supported. The default value is true. For backward compatibility with earlier versions that did
not support the sheet range notation, you can set [SupportsSheetRanges](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~SupportsSheetRanges.html) property to false.

{% tabs %}
{% highlight c# %}

//Initialization of first ICalcData object in CalcEngine,
calcData = new CalcData();
CalcEngine engine = new CalcEngine(calcData);

//Initialization of second ICalcData object in CalcEngine,
calcData1 = new calcData1();
engine = new CalcEngine(calcData1);

//Create a unique family id,
int i = CalcEngine.CreateSheetFamilyID();

//Register the first ICalcData object as "Sheet1",
engine.RegisterGridAsSheet("Sheet1", calcData, i);

//Register the second ICalcData object as "Sheet2",
engine.RegisterGridAsSheet("Sheet2", calcData1, i);

engine.SupportsSheetRanges = true;

string result = engine.ParseAndComputeFormula(“=SUM(sheet1!B1:B4,sheet2!B1:B4)”);

{% endhighlight %}
{% endtabs %}

### ThrowCircularException

Gets or sets whether the `CalcEngine` should throw an exception when a circular calculation is encountered. If [ThrowCircularException](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~ThrowCircularException.html) property is true, then `CalcEngine` will throw an exception when it detects a circular calculation, else no exception is thrown and the calculation will loop recursively until [MaximumRecursiveCalls](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~MaximumRecursiveCalls.html) is exceeded.

### UseDependencies

Gets or sets whether the `CalcEngine` should track dependencies or not. If you invoke [PullUpdatedValue](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~PullUpdatedValue.html) to access the computations, then setting [UseDependencies](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~UseDependencies.html) property to false will make things more 
efficient as any requested computed value will be fully computed every time it is retrieved. In this situation, the `CalcEngine` does not need to track dependencies.

### UseNoAmpersandQuotes

Gets or sets whether the computational result of strings should be returned with double quotes or not. 

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

engine.UseNoAmpersandQuotes = true;

string result = engine.ParseAndComputeFormula("=CONCAT(\"abc\",\"sample\")");

{% endhighlight %}
{% endtabs %}

### UseDatesInCalculations

Gets or sets whether dates can be used as operands in calculations. The default value is false. Setting [UseDatesInCalculations](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~UseDatesInCalculations.html) property to true, 
you can compute DateTime related calculations in your application.

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

engine.UseDatesInCalculations = true;

calcData.SetValueRowCol("02/10/2017 11:15 am", 1, 1);
calcData.SetValueRowCol("02/12/2017 9:45 am", 2, 1);

//Computing the difference in hours between two date time values,
string result = engine.ParseAndComputeFormula("=(A2-A1)*24");

{% endhighlight %}
{% endtabs %}

### TreatStringsAsZero

Setting the property [TreatStringsAsZero](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~TreatStringsAsZero.html) as true means that if a nonempty string is encountered during an arithmetic 
operation or computation, it will be treated as zero.

## Methods in CalcEngine

### GetValueFromArg

This method takes the argument and checks whether it is a parsed formula, a raw number, or a cell reference. It returns the string
by computing the value based on the argument passed in.

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

string result = engine.GetValueFromArg("=SUM(4,5,6)");

{% endhighlight %}
{% endtabs %}
 
### GetValueFromParentObject

This method takes the argument and check whether it is a formula or a cell reference and returns either the computed value or the cell value.

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

//Assign values,
calcData.SetValueRowCol(2, 1, 2);
calcData.SetValueRowCol(3, 2, 2);
calcData.SetValueRowCol(4, 3, 2);
calcData.SetValueRowCol("=SUM(B1,B2,B3)", 1, 4);

CalcEngine engine = new CalcEngine(calcData);

//Passing the cell reference,
string result = engine.GetValueFromParentObject("D1")

//Passing the row/column index,
string result = engine.GetValueFromParentObject(1, 4);

{% endhighlight %}
{% endtabs %}

N> [GetValueFromParentObject](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~GetValueFromParentObject.html) does not accepts the argument as raw number or parsed formula, it only accepts the cell references whereas [GetValueFromArg](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~GetValueFromArg.html) accepts parsed formula, a raw number, or a cell reference

### ParseAndComputeFormula

A method that parses and computes the string formula passed in. For more reference, see [here](https://help.syncfusion.com/wpf/calculate/parse-and-compute#parseandcomputeformula).

### ParseFormula

A method that parses the string formula passed in. For more reference, see [here](https://help.syncfusion.com/wpf/calculate/parse-and-compute#parse-formula).

### ComputeFormula

A method that computes a parsed formula. For more reference, see [here](https://help.syncfusion.com/wpf/calculate/parse-and-compute#computeformula).

### RegisterGridAsSheet

 A method that registers an `ICalcData` object so it can be referenced in a formula from another `ICalcData` object. For more reference, see [here](https://help.syncfusion.com/wpf/calculate/getting-started#cross-sheet-reference).

### UpdateCalcID

Every formula has a calculation ID level associated with it. Every time a formula is retrieved, its calculation ID level is compared with the `CalcEngine`
ID level. If they do not agree, the formula is recomputed. Invoking [UpdateCalcID](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~UpdateCalcID.html) will force any formula to be recomputed the next time it is retrieved.

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

//Assign values initially,
calcData.SetValueRowCol(2, 1, 2);
calcData.SetValueRowCol(3, 2, 2);
calcData.SetValueRowCol(4, 3, 2);
calcData.SetValueRowCol("=SUM(B1,B2,B3)", 1, 4);

CalcEngine engine = new CalcEngine(calcData);

//compute the formula,
string val = engine.ParseAndComputeFormula("D1");

//Changing the value of B2 cell,
calcData.SetValueRowCol(20, 2, 2);

//Invoking UpdateCalcID method to retrieve latest change,
engine.UpdateCalcID();

//Computing the formula with latest changes,
string val1 = engine.ParseAndComputeFormula("D1");

{% endhighlight %}
{% endtabs %}

### PullUpdatedValue

This method retrieves the value in the requested cell reference by computing with latest changes of cells that affect the value of the requested cell.

{% tabs %}
{% highlight c# %}

//Initialization of first ICalcData object in CalcEngine,
calcData = new CalcData();
CalcEngine engine = new CalcEngine(calcData);

//Initialization of second ICalcData object in CalcEngine,
ICalcData calcData1 = new CalcData1();
engine = new CalcEngine(calcData1);

//Register the first ICalcData object as "Sheet1",
engine.RegisterGridAsSheet("Sheet1", calcData, 1);

//Register the second ICalcData object as "Sheet2",
engine.RegisterGridAsSheet("Sheet2", calcData1, 1);

//Assign a formula in the calcData1's A1 cell,
calcData1.SetValueRowCol("=SUM(Sheet1!A1, Sheet1!B2, Sheet1!C2, Sheet1!D2)",1,1);

Random r = new Random();

engine.CalculatingSuspended = true;

//Set random values,
calcData.SetValueRowCol(r.Next(74) + 15, 1, 1);
calcData.SetValueRowCol(r.Next(2), 2, 2);
calcData.SetValueRowCol(r.Next(50),3, 2);
calcData.SetValueRowCol(r.Next(15),4, 2);
calcData.SetValueRowCol(r.Next(11),5, 2);
calcData.SetValueRowCol(33 + r.Next(1972),6, 2);
calcData.SetValueRowCol(r.Next(2),7, 2);
calcData.SetValueRowCol(r.Next(20),8, 5);

//Calculations are suspended so need to pull the computed value to make sure it has been calculated with the latest changes,
engine.UpdateCalcID();
engine.PullUpdatedValue(engine.GetSheetID(calcData1), 1, 1);

//Get the Calculated value from calcData1 object,
string val = calcData1.GetValueRowCol(1,1).ToString();

engine.CalculatingSuspended = false;

{% endhighlight %}
{% endtabs %}

### RecalculateRange

Recalculates any formula cells in the specified range of `CalcEngine`.

{% tabs %}
{% highlight c# %}

// Creates some data object that implements ICalcData.
this.data = new ArrayCalcData(a);

// Creates a CalcEngine object using this ICalcData object.
CalcEngine engine = new CalcEngine(this.data);

//Turn off calculations.
engine.CalculatingSuspended = true;      

// Makes multiple updates to this.data.

// Turn on calculations.
engine.CalculatingSuspended = false;

// Calls RecalculateRange so any formulas in the data can be computed.            
engine.RecalculateRange(RangeInfo.Cells(1, 1, nRows + 1, nCols + 1), data);

{% endhighlight %}
{% endtabs %}

### UpdateDependenciesAndCell

This method triggers a calculation for any cells depending upon the given cell.

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

//Assign values initially,
calcData.SetValueRowCol(2, 1, 2);
calcData.SetValueRowCol(3, 2, 2);
calcData.SetValueRowCol(4, 3, 2);
calcData.SetValueRowCol("=SUM(B1,B2,B3)", 1, 4);

CalcEngine engine = new CalcEngine(calcData);

//Add the formula in formula info hashtable,
engine.FormulaInfoTable.Add("D1", new FormulaInfo{FormulaText = "=SUM(B1,B2,B3)"});

//compute the formula,
string val = engine.ParseAndComputeFormula("D1");

//Changing the value of B2 cell,
calcData.SetValueRowCol(20, 2, 2);

//Invoke UpdateDependenciesAndCell method for the formula cell,
engine.UpdateDependenciesAndCell("D1");

//Computing the formula with latest changes,
string val1 = engine.ParseAndComputeFormula("D1");

{% endhighlight %}
{% endtabs %}
