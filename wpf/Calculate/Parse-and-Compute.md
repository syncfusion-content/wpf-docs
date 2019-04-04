---
layout: post
title: Parse and Compute | Calculate | Essential wpf/Syncfusion
description: This section lists out the parsing and computing methods to compute a custom function in Calculate for wpf/Syncfusion
platform: wpf
control: Calculate
documentation: ug
---

# Parse and Compute

 This section describes about the parse and compute functions in Essential Calculate.

## Parsing

Essential Calculate have built in formula parser to parse the formula into well-formed version to compute internally.

### Parse Formula

The built-in formula parser will parse the formula into Reverse Polish Notation expression using [ParseFormula](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~ParseFormula.html) method of `CalcEngine` for computing it.
The parser uses some tokens to identify the operators, operands. It recognizes and replaces the `NameRanges` with their corresponding value. The parser also recognizes library functions and tokenizes them as well.

`ParseFormula` method accepts a string formula and checks whether it is a valid formula that `CalcEngine` can understand.
After that, it returns a string that represents a parsed version of the formula that can be more readily computed.

For example,

Formula:  2+3*1

Parsed Formula in RPN format: "n2n3n1ma"

In this 'n' denotes as values and 'm' denotes as multiplication and 'a' as addition.

Using ICalcData,

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

string formula = “2+3*1”;

string parsedFormula = engine.ParseFormula(formula);

{% endhighlight %}
{% endtabs %}

Using CalcQuickBase,

{% tabs %}
{% highlight c# %}

CalcQuickBase calcQuick = new CalcQuickBase();

string formula = “2+3*1”;

string parsedFormula = calcQuick.Engine.ParseFormula(formula);

{% endhighlight %}
{% endtabs %}

### Parsing Order

The parsed formula is a Reverse Polish Notation expression using tokens to compactly represent the entered formula. 

All the operands will be indexed into a stack and we need to pop out for calculation. It can be functions, references, operators or constants.
The parsing will be done from left to right and the order for parsing of operators is as follows,

1. E+ E- (handles exponential notation like 1.2e-1 or 1.2e+1 to 1.2e1)
2. ^ 
3. / *
4. +(plus), -(minus)
5. < > = <= >= <>
6. & 

## Computation

Essential Calculate provides support to calculate the formulas using various computation methods.

### ComputeFormula

[ComputeFormula](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~ComputeFormula.html) method of `CalcEngine` computes the parsed formula from `ParseFormula` method and returns the computed value.
It uses a stack oriented calculation technique to convert the parsed formula into the value that it represents.

Using ICalcData,

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

string formula = “2+3*1”;

string parsedFormula = engine.ParseFormula(formula);

string result = engine.ComputeFormula(parsedFormula);

{% endhighlight %}
{% endtabs %}

Using CalcQuickBase,

{% tabs %}
{% highlight c# %}

CalcQuickBase calcQuick = new CalcQuickBase();

string formula = “2+3*1”;

string parsedFormula = calcQuick.Engine.ParseFormula(formula);

string result = calcQuick.Engine.ComputeFormula(parsedFormula);

{% endhighlight %}
{% endtabs %}

### ParseAndCompute

The [ParseAndCompute](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcQuickBase~ParseAndCompute.html) method of `CalcQuickBase` parses and computes the given formula string and returns the computed value.

{% tabs %}
{% highlight c# %}

CalcQuickBase calcQuick = new CalcQuickBase();   

//Computing Expressions,

string formula = "(5+25) *2";
string result = calcQuick.ParseAndCompute(formula);

//Computing In-Built formulas,

string formula = "SUM (5,5)";
string result = calcQuick.ParseAndCompute(formula);

{% endhighlight %}
{% endtabs %}

### ParseAndComputeFormula

The [ParseAndComputeFormula](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~ParseAndComputeFormula.html) method of `CalcEngine` parses and computes the given formula string passed in and returns the computed value.

Using ICalcData,

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

Using CalcQuickBase,

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

## Error Messages

The error messages that are displayed by Essential Calculate can be found in the string arrays such as [ErrorStrings](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~ErrorStrings.html) and [FormulaErrorStrings](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~FormulaErrorStrings.html) of `CalcEngine`.
After a `CalcEngine` object has been created, the text of error messages in this array lists can be changed by altering the array values.

* `ErrorStrings` of `CalcEngine` gets or sets the list of error strings which are recognized by Excel such as "#N/A", "#VALUE!", "#REF!", "#DIV/0!", "#NUM!", "#NAME?", "#NULL!".

* `FormulaErrorStrings` of `CalcEngine` holds the list of error strings which are used within the Essential Calculate internally. Users can make changes to this internal error strings
default settings by assigning the new strings to the corresponding position. `ReloadErrorStrings` should be invoked to reset or modify the internal error strings.

Below shows the list of `FormulaErrorStrings` which are used internally,

"binary operators cannot start an expression",	
"cannot parse",									
"bad library",									
"invalid char in front of",						
"number contains 2 decimal points",				
"expression cannot end with an operator",		
"invalid characters following an operator",		
"invalid character in number",					
"mismatched parentheses",						
"unknown formula name",							
"requires a single argument",					
"requires 3 arguments",							
"invalid Math argument",					
"requires 2 arguments",						
"#NAME?",
"too complex",									
"circular reference: ",							
"missing formula",								
"improper formula",							
"invalid expression",							
"cell empty",									
"bad formula",									
"empty expression",								
"",                                             
"mismatched string quotes",                             
"wrong number of arguments",                   
"invalid arguments",								
"iterations do not converge",                       
"Control named '{0}' is already registered",          
"Calculation overflow",								
"Missing sheet"

## Formatting the Computed Results

By default, the values will be returned as an object after computation. This value can be converted as a string by using `ToString` method to format the results.

To format the result of the calculations, the result can be parsed by using any of the formatting methods. 

**For example,**

int.Parse     ->    For converting to integer
double.Parse  ->    For converting to double
decimal.Parse ->    For converting to decimal  

Using ICalcData,

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

string formula = “SUM (4,5,6)”;

//Formatted as decimal value,
string result = decimal. Parse(engine.ParseAndComputeFormula(formula)).ToString("0.00");

//Formatted as double value,
string result1 = double.Parse(engine.ParseAndComputeFormula(formula)).ToString("0.00%");

{% endhighlight %}
{% endtabs %}

Using CalcQuickBase,

{% tabs %}
{% highlight c# %}

CalcQuickBase calcQuick = new CalcQuickBase();

string formula = “SUM (4,5,6)”;

//Formatted as decimal value,
string result = decimal.Parse(calcQuick.ParseAndCompute(formula)).ToString("0.00");

//Formatted as double value,
string result1 = double.Parse(engine.ParseAndCompute(formula)).ToString("0.00%");

{% endhighlight %}
{% endtabs %}
