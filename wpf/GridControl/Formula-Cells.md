---
layout: post
title: Formula Cells in WPF GridControl | Syncfusion
description: Learn about Formula Cells support in Syncfusion Essential Studio WPF GridControl, its elements and more details.
platform: wpf
control: GridControl
 documentation: ug
---

# Formula Cells in WPF GridControl

Setting the CellType of a cell to a FormulaCell will allow you to enter algebraic expressions using formulas and cell references. Cell references are entries such as A11 for column A row 11 or BA3 for column BA row 3. A formula is a defined calculation from the Formula Library which, is included with Essential Grid. This Formula Library is extensible and allows you to add additional formulas.

This section comprises the following topics:

## Defining a FormulaCell

You can use FormulaCells for every cell in a grid or for just a few cells. Even if you assign a CellType FormulaCell to every cell in a grid, the default behavior is to treat such cells as text box cells unless you start the cell entry with an equal sign. If the cell value starts with an equal sign then, the cell is considered as a formula cell and its contents are treated as such. 

To make all cells present in a grid as potential formula cells, you will have to set the CellType of the standard BaseStyle to a FormulaCell using the following code. 

{% tabs %}
{% highlight c# %}
// Set up a Formula Cell.
this.gridControl1.BaseStylesMap["Standard"].StyleInfo.CellType = "FormulaCell";
{% endhighlight %}
{% highlight vbnet %}
'  Set up a Formula Cell.
Me.GridControl1.BaseStylesMap("Standard"). StyleInfo.CellType = "FormulaCell"
{% endhighlight %}
{% endtabs %}

## Using the Formula Library

Essential Grid's Formula Library contains the mathematical functions that are available in the .NET FrameWork's System.Math class. In addition, there are Sum and Avg members. For a complete list of these library functions, please see the Class Reference for GridFormulaEngine. You can also add additional functions to this library using your own code. 

![Sample formula library usage](Formulacells_images/formulacells.jpeg)

In the above image, cell A2 has a formula that uses four different library functions: Sqrt, Pow, Cos, and Sin.

### Supported Arithmetic Operators and Calculation Precedence

The current formula support will allow you to enter well-formed parenthetical algebraic expressions using operators and operands. The nine supported operators are shown in the precedence table given below, with operators on the same level being calculated as encountered when the expression is scanned from left to right. 

<table>
<tr>
<th>
Operations</th><th>
Symbols</th><th>
Calculation Precedence</th></tr>
<tr>
<td>
Multiplication, Division </td><td>
 /  *  </td><td>
1st</td></tr>
<tr>
<td>
Addition, Subtraction </td><td>
+  -  </td><td>
2nd</td></tr>
<tr>
<td>
Less Than, Greater Than, Equal, Less Than Or Equal, Greater Than Or Equal, Not Equal </td><td>
 <  > = <= >= <>  </td><td>
3rd</td></tr>
</table>


The supported operands include those listed in the table given below. An operand by itself is also a well-formed algebraic expression that can serve as an entire formula in a cell.

<table>
<tr>
<th>
Operand</th><th>
Examples</th></tr>
<tr>
<td>
number</td><td>
532.1, -10.2, or 18.</td></tr>
<tr>
<td>
cell reference </td><td>
A12, BB1010, or Q18.</td></tr>
<tr>
<td>
library formula with valid arguments </td><td>
Abs(E14), Cos(-3.14), or Sum(A1:A14).</td></tr>
<tr>
<td>
any well formed algebraic expression </td><td>
E1+E2, Cos(2)<A4, or Abs(A1-A5).</td></tr>
</table>


Within a formula cell, a case is ignored. So, a1 is the same as A1, and Cos(3) is the same as COS(3).

## Adding Formulas to the Formula Library

Here are the steps that are required to add a function to the Function Library.

1. First, define a method that has this signature.

{% tabs %}
{% highlight c# %}
// Define a method whose name is the FormulaName.
public string MyLibraryFormulaName(string args)
{% endhighlight %}
{% highlight vbnet %}
'Define a method whose name is the FormulaName.
Public Function MyLibraryFormulaName(ByVal args As String) As String
{% endhighlight %}
{% endtabs %}

Here MyLibraryFormulaName must be a name that has not been already used in the Function Library and must include only letters and digits. If you want to replace an existing formula with a formula of the same name, first remove the existing formula before adding the new formula. Use the GridFormulaEngine.RemoveFunction method to remove a formula. 

Then, write an implementation for your method. Here we use code to implement a function that will sum only positive numbers that are passed in as either a range like A1:A5 and/or a list such as A1, A4, A10. The code uses the FormulaEngine helper method to extract these values from the cells. The GetCellsFromArgs method will return an array of cells from a range such as A1:A5, and GetValueFromArgs method will take cells such as A3 and return a value such as 123.3. 

{% tabs %}
{% highlight c# %}
// Implement Your Method.

public string ComputeSumPosNums(string args)
{
    GridFormulaCellModel model = this.gridControl1.CellModels["FormulaCell"] as GridFormulaCellModel;
    if(model != null)
    {
        GridFormulaEngine engine = model.Engine;
        double sum = 0d;
        double d;
        string s1;

        // Loop through any arguments and sum up the positive values.
        foreach(string r in args.Split(new char[]{','}))
        {
            // Cell range
            if(r.IndexOf(':') > -1) 
            {
                foreach(string s in engine.GetCellsFromArgs(r))
                {
                    // s is a cell line a21 or c3, and so on.
                    try
                    {
                        s1 = engine.GetValueFromArg(s);
                    }
                    catch(Exception ex)
                    {
                        return ex.Message;
                    }
                    if(s1 != "")
                    {
                        // Add only if positive.
                        if(double.TryParse(s1, NumberStyles.Number, null, out d)
                                    && d > 0)
                        {
                            sum += d; 
                        }
                    }
                }
            }
            else
            {
                try
                {
                    s1 = engine.GetValueFromArg(r);
                }
                catch(Exception ex)
                {
                    return ex.Message;
                }
                if(s1 != "")
                {
                    if(double.TryParse(s1, NumberStyles.Number, null, out d) && d > 0)
                    {
                        sum += d; 
                    }
                }
            }
        }        
        return sum.ToString();
    }
    return "";
}
{% endhighlight %}
{% highlight vbnet %}
' Implement Your Method.

Public Function ComputeSumPosNums(args As String) As String
Dim model As GridFormulaCellModel = Me.gridControl1.CellModels("FormulaCell")
    If Not (model Is Nothing) Then
        Dim engine As GridFormulaEngine = model.Engine
        Dim sum As Double = 0.0
        Dim d As Double
        Dim s1 As String

        ' Loop through any arguments and sum up the positive values.
        Dim r As String
        For Each r In args.Split(New Char() {","c})
            ' Cell range
            If r.IndexOf(":"c) > -1 Then  
                Dim s As String
                For Each s In engine.GetCellsFromArgs(r)
                    ' s is a cell line a21 or c3, and so on.
                    Try
                        s1 = engine.GetValueFromArg(s)
                    Catch ex As Exception
                        Return ex.Message
                    End Try
                    If s1 <> "" Then
                        ' Add only if positive.
                        If Double.TryParse(s1, NumberStyles.Number, Nothing, d) And d > 0 Then
                            sum += d
                        End If
                    End If
                Next s
            Else
                Try
                    s1 = engine.GetValueFromArg(r)
                Catch ex As Exception
                    Return ex.Message
                End Try
                If s1 <> "" Then
                    If Double.TryParse(s1, NumberStyles.Number, Nothing, d) And d > 0 Then
                        sum += d
                    End If
                End If
            End If
        Next r
        Return sum.ToString()
    End If
    Return ""
End Function 
{% endhighlight %}
{% endtabs %}

The last step is to actually add your formula to the library. You should do this after the grid has been created, say in a Form.Load event handler.

{% tabs %}
{% highlight c# %}
GridFormulaCellModel cellModel = this.gridControl1.CellModels["FormulaCell"] as GridFormulaCellModel;

// Add a formula named SumPosNums to the Library.
cellModel.Engine.AddFunction("SumPosNums", new GridFormulaEngine.LibraryFunction(ComputeSumPosNums));
{% endhighlight %}
{% highlight vbnet %}
Dim cellModel As GridFormulaCellModel = Me.gridControl1.CellModels("FormulaCell")

' Add a formula named SumPosNums to the Library.
cellModel.Engine.AddFunction("SumPosNums", New GridFormulaEngine.LibraryFunction(AddressOf ComputeSumPosNums))
{% endhighlight %}
{% endtabs %}

## Function Reference Section

The Syncfusion Grid control supports 370 formulas under various categories including math, statistical, logical, engineering, information, date, time, text, web, financial, lookup, and database functions.

### Math & Trigonometry functions



<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Syntax</th></tr>
<tr>
<td>
ABS</td><td>
Returns the number without its sign.</td><td>
ABS(number)</td></tr>
<tr>
<td>
ACOS</td><td>
Returns the arccosine, or inverse cosine, of a number. The returned angle is given in radians in the range 0 (zero) to pi.</td><td>
ACOS(number)number must be in the range of -1 to 1.</td></tr>
<tr>
<td>
ACOSH</td><td>
Returns the inverse hyperbolic cosine of a number.The inverse hyperbolic cosine is the value whose hyperbolic cosine is number.</td><td>
ACOSH(number)number must be a real number. </td></tr>
<tr>
<td>
ACOT</td><td>
Returns the principal value of the arc cotangent, or inverse cotangent, of a number.</td><td>
ACOT(number)number must be a real number.</td></tr>
<tr>
<td>
ACOTH</td><td>
Returns the inverse hyperbolic cotangent of a number.</td><td>
ACOTH(number)number must be greater than 1.</td></tr>
<tr>
<td>
ARABIC</td><td>
Converts a Roman numeral to an Arabic numeral.</td><td>
ARABIC( text )</td></tr>
<tr>
<td>
ASIN</td><td>
Returns the arcsine, or inverse sine, of a number.The returned angle is given in radians in the range -pi/2 to pi/2.</td><td>
ASIN(number)number must be in the range of -1 to 1.</td></tr>
<tr>
<td>
ASINH</td><td>
Returns the inverse hyperbolic sine of a number.</td><td>
ASINH(number)number must be a real number.</td></tr>
<tr>
<td>
ATAN</td><td>
Returns the arctangent, or inverse tangent, of a number.The returned angle is given in radians in the range -pi/2 to pi/2.</td><td>
ATAN(number)</td></tr>
<tr>
<td>
ATAN2</td><td>
Returns the arctangent, or inverse tangent, of the specified x- and y-coordinates.</td><td>
ATAN2(x_num, y_num)</td></tr>
<tr>
<td>
ATANH</td><td>
Returns the inverse hyperbolic tangent of a number.</td><td>
ATANH(number)number must be in the range of -1 and 1.</td></tr>
<tr>
<td>
BASE</td><td>
Converts a number into a text representation with the given radix.</td><td>
BASE(Number, Radix, [Min_length])Number must be an integer greater than or equal to 0 and less than 2^53.Radix must be an integer greater than or equal to 2 and less than or equal to 36.Min_Length must be an integer greater than or equal to 0. (Optional)</td></tr>
<tr>
<td>
CEILING</td><td>
Returns number rounded up to the nearest multiple of significance.</td><td>
CEILING(number, significance)</td></tr>
<tr>
<td>
CEILING.MATH</td><td>
Rounds a number up to the nearest integer or to the nearest multiple of significance.</td><td>
CEILING(number, [significance],  [mode])number must be less than 9.99E+307 and greater than -2.229E-308.Significance: The multiple to which the number is to be rounded. (Optional)Mode: For negative numbers, controls whether number is rounded toward or away from zero. (Optional)</td></tr>
<tr>
<td>
COMBIN</td><td>
Returns the number of combinations for a given number of items.</td><td>
COMBIN(number, number_chosen)</td></tr>
<tr>
<td>
COMBINA</td><td>
Returns the number of combinations (with repetitions) for a given number of items.</td><td>
COMBINA(number, number_chosen)</td></tr>
<tr>
<td>
COS</td><td>
Returns the cosine of the given angle.</td><td>
COS(number)</td></tr>
<tr>
<td>
COSH</td><td>
Returns the hyperbolic cosine of a number.</td><td>
COSH(number)</td></tr>
<tr>
<td>
COT</td><td>
Returns the cotangent of an angle specified in radians.</td><td>
COT(number)</td></tr>
<tr>
<td>
COTH</td><td>
Returns the hyperbolic cotangent of a hyperbolic angle.</td><td>
COTH(number)</td></tr>
<tr>
<td>
CSC</td><td>
Returns the cosecant of an angle specified in radians.</td><td>
CSC(number)</td></tr>
<tr>
<td>
CSCH</td><td>
Returns the hyperbolic cosecant of an angle specified in radians.</td><td>
CSCH(number)</td></tr>
<tr>
<td>
DECIMAL</td><td>
Converts a text representation of a number in a given base into a decimal number.</td><td>
DECIMAL(text, radix)Radix must be an integer.</td></tr>
<tr>
<td>
DEGREES</td><td>
Converts radians into degrees.</td><td>
DEGREES(angle)</td></tr>
<tr>
<td>
EVEN</td><td>
Returns number rounded up to the nearest even integer.</td><td>
EVEN(number)</td></tr>
<tr>
<td>
EXP</td><td>
Returns e raised to the power of number. The constant e equals 2.71828182845904, the base of the natural logarithm.</td><td>
EXP(number)</td></tr>
<tr>
<td>
FACT</td><td>
Returns the factorial of a number.</td><td>
FACT(number)</td></tr>
<tr>
<td>
FACTDOUBLE</td><td>
Returns the double factorial of a number.</td><td>
FACTDOUBLE(number)</td></tr>
<tr>
<td>
FLOOR</td><td>
Rounds number down, toward zero, to the nearest multiple of significance.</td><td>
FLOOR(number, significance)</td></tr>
<tr>
<td>
GCD</td><td>
Returns the greatest common divisor of two or more integers.</td><td>
GCD(number1, [number2], ...)</td></tr>
<tr>
<td>
INT</td><td>
Rounds a number down to the nearest integer.</td><td>
INT(number)</td></tr>
<tr>
<td>
LCM</td><td>
Returns the least common multiple of integers.</td><td>
LCM(number1, [number2], ...)</td></tr>
<tr>
<td>
LN</td><td>
Returns the natural logarithm of a number.</td><td>
LN(number)</td></tr>
<tr>
<td>
LOG</td><td>
Returns the logarithm of a number to the base you specify.</td><td>
LOG(number, [base])Number must be a positive real number.Base: Optional, if base is omitted it is assumed to be 10.</td></tr>
<tr>
<td>
LOG10</td><td>
Returns the base 10 logarithm of a number.</td><td>
LOG10(number)</td></tr>
<tr>
<td>
MDETERM</td><td>
Returns the matrix determinant of an array.</td><td>
MDETERM(array)Array is a numeric array with an equal number of rows and columns.</td></tr>
<tr>
<td>
MINVERSE</td><td>
Returns the inverse matrix for the matrix stored in an array.</td><td>
MINVERSE(array)Array is a numeric array with an equal number of rows and columns.</td></tr>
<tr>
<td>
MMULT</td><td>
Returns the matrix product of two arrays.</td><td>
MMULT(array1, array2)</td></tr>
<tr>
<td>
MOD</td><td>
Returns the remainder after number is divided by divisor. The result has the same sign as divisor.</td><td>
MOD(number, divisor)</td></tr>
<tr>
<td>
MROUND</td><td>
Returns a number rounded to the desired multiple.</td><td>
MROUND(number, multiple)</td></tr>
<tr>
<td>
MULTINOMIAL</td><td>
Returns the ratio of the factorial of a sum of values to the product of factorials.</td><td>
MULTINOMIAL(number1, [number2], ...)</td></tr>
<tr>
<td>
MUNIT</td><td>
Returns the unit matrix for the specified dimension.</td><td>
MUNIT(dimension)Dimension must be an integer greater than 0.</td></tr>
<tr>
<td>
ODD</td><td>
Returns number rounded up to the nearest odd integer.</td><td>
ODD(number)</td></tr>
<tr>
<td>
PI</td><td>
Returns the number 3.14159265358979</td><td>
PI()</td></tr>
<tr>
<td>
POW</td><td>
Returns the result of a number raised to a power.</td><td>
POW(number, power)</td></tr>
<tr>
<td>
POWER</td><td>
Returns the result of a number raised to a power.</td><td>
POWER(number, power)</td></tr>
<tr>
<td>
PRODUCT</td><td>
Multiplies all of the numbers given as arguments and returns the product.</td><td>
PRODUCT(number1, [number2], ...)</td></tr>
<tr>
<td>
QUOTIENT</td><td>
Returns the integer portion of a division.</td><td>
QUOTIENT(numerator, denominator)</td></tr>
<tr>
<td>
RADIANS</td><td>
Converts degrees to radians.</td><td>
RADIANS(angle)</td></tr>
<tr>
<td>
ROMAN</td><td>
Converts an Arabic numeral to a Roman numeral as text.</td><td>
ROMAN(number, [form])Number is an Arabic numeral you want converted.Form: Optional. A number specifying the type of Roman numeral you want</td></tr>
<tr>
<td>
ROUND</td><td>
Rounds a number to a specified number of digits.</td><td>
ROUND(number, num_digits)</td></tr>
<tr>
<td>
ROUNDDOWN</td><td>
Rounds a number down, toward zero.</td><td>
ROUNDDOWN(number, num_digits)</td></tr>
<tr>
<td>
ROUNDUP</td><td>
Rounds a number up, away from zero.</td><td>
ROUNDUP(number, num_digits)</td></tr>
<tr>
<td>
SEC</td><td>
Returns the secant of an angle.</td><td>
SEC(number)</td></tr>
<tr>
<td>
SECH</td><td>
Returns the hyperbolic secant of an angle.</td><td>
SECH(number)</td></tr>
<tr>
<td>
SIGN</td><td>
Determines the sign of a number. Returns 1 if the number is positive, zero (0) if the number is 0, and -1 if the number is negative.</td><td>
SIGN(number)Number must be a real number.</td></tr>
<tr>
<td>
SIN</td><td>
Returns the sine of the given angle.</td><td>
SIN(number)</td></tr>
<tr>
<td>
SINH</td><td>
Returns the hyperbolic sine of a number.</td><td>
SINH(number)Number must be a real number.</td></tr>
<tr>
<td>
SQRT</td><td>
Returns a positive square root.</td><td>
SQRT(number)</td></tr>
<tr>
<td>
SQRTPI</td><td>
Returns the square root of (number * pi).</td><td>
SQRTPI(number)</td></tr>
<tr>
<td>
SUBTOTAL</td><td>
Returns a subtotal in a list or database.</td><td>
SUBTOTAL(function_num,ref1,[ref2],...)function_num specifies which function to use in calculating subtotals.<table><br><tr><br><th colspan = "3"><br>Function_num</th><th>
Function</th></tr>
<tr>
<td colspan = "2">
1</td><td>
101</td><td>
AVERAGE</td></tr>
<tr>
<td colspan = "2">
2</td><td>
102</td><td>
COUNT</td></tr>
<tr>
<td colspan = "2">
3</td><td>
103</td><td>
COUNTA</td></tr>
<tr>
<td colspan = "2">
4</td><td>
104</td><td>
MAX</td></tr>
<tr>
<td colspan = "2">
5</td><td>
105</td><td>
MIN</td></tr>
<tr>
<td>
6</td><td colspan = "2">
106</td><td>
PRODUCT</td></tr>
<tr>
<td>
7</td><td colspan = "2">
107</td><td>
STDEV</td></tr>
<tr>
<td>
8</td><td colspan = "2">
108</td><td>
STDEVP</td></tr>
<tr>
<td>
9</td><td colspan = "2">
109</td><td>
SUM</td></tr>
<tr>
<td>
10</td><td colspan = "2">
110</td><td>
VAR</td></tr>
<tr>
<td>
11</td><td colspan = "2">
111</td><td>
VARP</td></tr>
</table>

The function_num 1-11 includes hidden cell values, and the 101-111 ignores the hidden values.

Ref1: NamedRange or References

Ref2: Optional , named range or cell references.

</td></tr>
<tr>
<td>
SUM</td><td>
Adds all the numbers that have been specified as arguments.</td><td>
SUM(number1,[number2],...)</td></tr>
<tr>
<td>
SUMIFS</td><td>
Adds the cells in a range that meet multiple criteria.</td><td>
SUMIFS(sum_range,criteria_range1, criteria1, [criteria_range2, criteria2], ...)Sum_range: One or more cells to sum, including numbers or names, ranges, or cell references that contain numbers. Blank and text values are ignored.Criteria_range1: The first range in which to evaluate the associated criteria.Criteria1: The criteria in the form of a number, expression etc.Criteria_range2 , Criteria2: Optional.</td></tr>
<tr>
<td>
SUMPRODUCT</td><td>
Multiplies corresponding components in the given arrays, and returns the sum of those products.</td><td>
SUMPRODUCT(array1, [array2], [array3], ...)Array1: The first array argument whose components you want to multiply and then add.Array2, array3,...     Optional.</td></tr>
<tr>
<td>
SUMSQ</td><td>
Returns the sum of the squares of the arguments.</td><td>
SUMSQ(number1, [number2], ...)</td></tr>
<tr>
<td>
SUMX2MY2</td><td>
Returns the sum of the difference of squares of corresponding values in two arrays.</td><td>
SUMX2MY2(array_x, array_y)</td></tr>
<tr>
<td>
SUMX2PY2</td><td>
Returns the sum of the sum of squares of corresponding values in two arrays.</td><td>
SUMX2PY2(array_x, array_y)</td></tr>
<tr>
<td>
SUMXMY2</td><td>
Returns the sum of squares of differences of corresponding values in two arrays.</td><td>
SUMXMY2(array_x, array_y)</td></tr>
<tr>
<td>
TAN</td><td>
Returns the tangent of the given angle.</td><td>
TAN(number)</td></tr>
<tr>
<td>
TANH</td><td>
Returns the hyperbolic tangent of a number.</td><td>
TANH(number)</td></tr>
<tr>
<td>
TRUNC</td><td>
Truncates a number to an integer by removing the fractional part of the number.</td><td>
TRUNC(number, [num_digits])</td></tr>
<tr>
<td>
TRUNCATE</td><td>
Truncates a number to an integer by removing the fractional part of the number.</td><td>
TRUNCATE(number, [num_digits])</td></tr>
</table>

### Statistical functions

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Syntax</th></tr>
<tr>
<td>
AVEDEV</td><td>
Returns the average of the absolute deviations of data points from their mean.</td><td>
AVEDEV(number1, [number2], ...)</td></tr>
<tr>
<td>
AVERAGE</td><td>
Returns the average (arithmetic mean) of the arguments.</td><td>
AVERAGE(number1, [number2], ...)</td></tr>
<tr>
<td>
AVERAGEA</td><td>
Calculates the average (arithmetic mean) of the values in the list of arguments.</td><td>
AVERAGEA(value1, [value2], ...)</td></tr>
<tr>
<td>
AVE</td><td>
Equivalent to Average. Added for compatibility with older versions.</td><td>
AVE(number1, [number2], ...)</td></tr>
<tr>
<td>
BINOM.DIST</td><td>
Returns the individual term binomial distribution probability.</td><td>
BINOM.DIST(number_s,trials,probability_s,cumulative)Number_s: The number of successes in trials.Trials:  The number of independent trials.Probability_s: The probability of success on each trial.Cumulative: A logical value (TRUE/FALSE)</td></tr>
<tr>
<td>
BINOM.INV</td><td>
Returns the smallest value for which the cumulative binomial distribution is greater than or equal to a criterion value.</td><td>
BINOM.INV(trials,probability_s,alpha)Trials: The number of Bernoulli trials.Probability_s:  The probability of a success on each trial.Alpha: The criterion value.</td></tr>
<tr>
<td>
BINOMDIST</td><td>
Equivalent to BINOM.DIST, added for compatibility with older versions.</td><td>
BINOMDIST(number_s,trials,probability_s,cumulative)</td></tr>
<tr>
<td>
CHIDIST</td><td>
Equivalent to CHISQ.DIST, added for compatibility with older versions.</td><td>
CHIDIST(x,deg_freedom)</td></tr>
<tr>
<td>
CHIINV</td><td>
Equivalent to CHISQ.INV, added for compatibility with older versions.</td><td>
CHIINV(probability,deg_freedom)</td></tr>
<tr>
<td>
CHISQ.DIST.RT</td><td>
Returns the right-tail probability of the chi-squared distribution.</td><td>
CHISQ.DIST.RT(x,deg_freedom)X : The value at which you want to evaluate the distribution.Deg_freedom : The number of degrees of freedom.</td></tr>
<tr>
<td>
CHISQ.INV</td><td>
Returns the inverse of the left-tail probability of the chi-squared distribution.</td><td>
CHISQ.INV(probability,deg_freedom)Probability: A probability associated with the chi-squared distribution.Deg_freedom: The number of degrees of freedom.</td></tr>
<tr>
<td>
CHISQ.INV.RT</td><td>
Returns the inverse of the right-tail probability of the chi-squared distribution.</td><td>
CHISQ.INV.RT(probability,deg_freedom)Probability: A probability associated with the chi-squared distribution.Deg_freedom: The number of degrees of freedom.</td></tr>
<tr>
<td>
CHISQ.TEST</td><td>
Returns the value from the chi-squared (χ2)</td><td>
CHISQ.TEST(actual_range,expected_range)Actual_range: The range of data that contains observations to test against expected values.Expected_range: The range of data that contains the ratio of the product of row totals and column totals to the grand total.</td></tr>
<tr>
<td>
CHITEST</td><td>
Equivalent to CHISQ.TEST, added for compatibility with older versions.</td><td>
CHITEST(actual_range,expected_range)</td></tr>
<tr>
<td>
CONFIDENCE</td><td>
Returns the confidence interval for a population mean, using a normal distribution.</td><td>
CONFIDENCE(alpha,standard_dev,size)Alpha: The significance level used to compute the confidence level. Standard_dev: The population standard deviation for the data range, it is assumed to be known.Size: The sample size.</td></tr>
<tr>
<td>
CONFIDENCE.NORM</td><td>
Returns the confidence interval for a population mean, using a normal distribution.</td><td>
CONFIDENCE.NORM(alpha,standard_dev,size)Alpha: The significance level used to compute the confidence level. Standard_dev: The population standard deviation for the data range, it is assumed to be known.Size: The sample size.</td></tr>
<tr>
<td>
CONFIDENCE.T</td><td>
Returns the confidence interval for a population mean, using a student's t distribution.</td><td>
CONFIDENCE.T(alpha,standard_dev,size)</td></tr>
<tr>
<td>
CORREL</td><td>
Returns the correlation coefficient of the Array1 and Array2 cell ranges.</td><td>
CORREL(array1, array2)Array1:  A cell range of values.Array2: A second cell range of values.</td></tr>
<tr>
<td>
COUNT</td><td>
Counts the number of cells that contain numbers.</td><td>
COUNT(value1, [value2], ...)Value1, value2: Cell Reference or Range</td></tr>
<tr>
<td>
COUNTA</td><td>
Counts the number of cells that are not empty in a range.</td><td>
COUNTA(value1, [value2], ...)value1: The first argument representing the values that you want to count.value2: Additional arguments representing the values that you want to count. (Optional)</td></tr>
<tr>
<td>
COUNTBLANK</td><td>
Counts the empty cells in a specified range of cells.</td><td>
COUNTBLANK(range)</td></tr>
<tr>
<td>
COUNTIF</td><td>
Counts the number of cells within a range that meet a single criterion that you specify.</td><td>
COUNTIF(range, criteria)range: One or more cells to count.criteria: A number, expression, cell reference, or text string.</td></tr>
<tr>
<td>
COVAR</td><td>
Returns covariance, the average of the products of deviations for each data point pair in two data sets.</td><td>
COVAR(array1,array2)Array1: The first cell range of integers.Array2: The second cell range of integers. </td></tr>
<tr>
<td>
COVARIANCE.P</td><td>
Returns population covariance, the average of the products of deviations for each data point pair in two data sets.</td><td>
COVARIANCE.P(array1,array2)Array1: The first cell range of integers.Array2: The second cell range of integers.</td></tr>
<tr>
<td>
COVARIANCE.S</td><td>
Returns the sample covariance, the average of the products of deviations for each data point pair in two data sets.</td><td>
COVARIANCE.S(array1,array2)Array1: The first cell range of integers.Array2: The second cell range of integers.</td></tr>
<tr>
<td>
CRITBINOM</td><td>
Equivalent to BINOM.INV, added for compatibility with older versions.</td><td>
CRITBINOM(trials,probability_s,alpha)</td></tr>
<tr>
<td>
DEVSQ</td><td>
Returns the sum of squares of deviations of data points from their sample mean.</td><td>
DEVSQ(number1, [number2], ...)</td></tr>
<tr>
<td>
EXPON.DIST</td><td>
Returns the exponential distribution.</td><td>
EXPON.DIST(x,lambda,cumulative)X: The value of the function.Lambda: The parameter value.Cumulative: A logical value. If cumulative is TRUE, EXPON.DIST returns the cumulative distribution function; if FALSE, it returns the probability density function.</td></tr>
<tr>
<td>
EXPONDIST</td><td>
Equivalent to EXPON.DIST, added for Compatibility with older versions.</td><td>
EXPONDIST(x,lambda,cumulative)</td></tr>
<tr>
<td>
F.DIST</td><td>
Returns the F probability distribution.</td><td>
F.DIST(x,deg_freedom1,deg_freedom2,cumulative)X: The value at which to evaluate the function.Deg_freedom1: The numerator degrees of freedom.Deg_freedom2: The denominator degrees of freedom.Cumulative: A logical value. If cumulative is TRUE, F.DIST returns the cumulative distribution function; if FALSE, it returns the probability density function.</td></tr>
<tr>
<td>
F.DIST.RT</td><td>
Returns the (right-tailed) F probability distribution for two data sets.</td><td>
F.DIST.RT(x,deg_freedom1,deg_freedom2)X :The value at which to evaluate the function.Deg_freedom1: The numerator degrees of freedom.Deg_freedom2: The denominator degrees of freedom.</td></tr>
<tr>
<td>
F.INV.RT</td><td>
Returns the inverse of the (right-tailed) F probability distribution.</td><td>
F.INV.RT(probability,deg_freedom1,deg_freedom2)Probability: A probability associated with the F cumulative distribution.Deg_freedom1: The numerator degrees of freedom.Deg_freedom2: The denominator degrees of freedom.</td></tr>
<tr>
<td>
FDIST</td><td>
Equivalent to F.DIST, added for compatibility with older versions.</td><td>
FDIST(x,deg_freedom1,deg_freedom2)</td></tr>
<tr>
<td>
FINV</td><td>
Equivalent to F.INV, added for compatibility with older versions.</td><td>
FINV(probability,deg_freedom1,deg_freedom2)</td></tr>
<tr>
<td>
FISHER</td><td>
Returns the Fisher transformation at x.</td><td>
FISHER(x)X: A numeric value for which you want the transformation.</td></tr>
<tr>
<td>
FISHERINV</td><td>
Returns the inverse of the Fisher transformation.</td><td>
FISHERINV(y)Y: The value for which you want to perform the inverse of the transformation.</td></tr>
<tr>
<td>
FORECAST</td><td>
Calculates, or predicts, a future value using existing values.</td><td>
FORECAST(x, known_y's, known_x's)X: The data point for which you want to predict a value.Known_y's: The dependent array or range of data.Known_x's: The independent array or range of data.</td></tr>
<tr>
<td>
GAMMA.DIST</td><td>
Returns the gamma distribution.</td><td>
GAMMA.DIST(x,alpha,beta,cumulative)X: The value at which you want to evaluate the distribution.Alpha: A parameter to the distribution.Beta: A parameter to the distribution. Cumulative: If cumulative is TRUE, GAMMA.DIST returns the cumulative distribution function; if FALSE, it returns the probability density function.</td></tr>
<tr>
<td>
GAMMA.INV</td><td>
Returns the inverse of the gamma cumulative distribution.</td><td>
GAMMA.INV(probability,alpha,beta)Probability: The probability associated with the gamma distribution.Alpha: A parameter to the distribution.Beta: A parameter to the distribution. If beta = 1, GAMMA.INV returns the standard gamma distribution.</td></tr>
<tr>
<td>
GAMMADIST</td><td>
Equivalent to GAMMA.DIST, added for compatibility with older versions.</td><td>
GAMMADIST(x,alpha,beta,cumulative)</td></tr>
<tr>
<td>
GAMMAINV</td><td>
Equivalent to GAMMA.INV, added for compatibility with older versions.</td><td>
GAMMAINV(probability,alpha,beta)</td></tr>
<tr>
<td>
GAMMALN</td><td>
Returns the natural logarithm of the gamma function, Γ(x).</td><td>
GAMMALN(x)X: The value for which you want to calculate GAMMALN.</td></tr>
<tr>
<td>
GAMMALN.PRECISE</td><td>
Returns the natural logarithm of the gamma function, Γ(x).</td><td>
GAMMALN.PRECISE(x)X: The value for which you want to calculate GAMMALN.PRECISE.</td></tr>
<tr>
<td>
GEOMEAN</td><td>
Returns the geometric mean of an array or range of positive data.</td><td>
GEOMEAN(number1, [number2], ...)</td></tr>
<tr>
<td>
HARMEAN</td><td>
Returns the harmonic mean of a data set.</td><td>
HARMEAN(number1, [number2], ...)</td></tr>
<tr>
<td>
HYPGEOM.DIST</td><td>
Returns the hypergeometric distribution.</td><td>
HYPGEOM.DIST(sample_s,number_sample,population_s,number_pop, ,cumulative)Sample_s: The number of successes in the sample.Number_sample: The size of the sample.Population_s: The number of successes in the population.Number_pop: The population size.Cumulative: If cumulative is TRUE, then HYPGEOM.DIST returns the cumulative distribution function; if FALSE, it returns the probability mass function.</td></tr>
<tr>
<td>
HYPGEOMDIST</td><td>
Equivalent to HYPGEOM.DIST, added for compatibility with older versions.</td><td>
HYPGEOMDIST(sample_s,number_sample,population_s,number_pop)</td></tr>
<tr>
<td>
INTERCEPT</td><td>
Calculates the point at which a line will intersect the y-axis by using existing x-values and y-values.</td><td>
INTERCEPT(known_y's, known_x's)Known_y's: The dependent set of observations or data.Known_x's: The independent set of observations or data.</td></tr>
<tr>
<td>
KURT</td><td>
Returns the kurtosis of a data set.</td><td>
KURT(number1, [number2], ...)</td></tr>
<tr>
<td>
LARGE</td><td>
Returns the k-th largest value in a data set.</td><td>
LARGE(array, k)Array: The array or range of data .K: The position in the array or cell range of data to return</td></tr>
<tr>
<td>
LOGINV</td><td>
Equivalent to LOGNORM.INV, added for compatibility with older versions.</td><td>
LOGINV(probability, mean, standard_dev)</td></tr>
<tr>
<td>
LOGNORM.DIST</td><td>
Returns the log-normal distribution of x.</td><td>
LOGNORM.DIST(x,mean,standard_dev,cumulative)X: The value at which to evaluate the function.Mean: The mean of ln(x).Standard_dev: The standard deviation of ln(x).Cumulative: If cumulative is TRUE, LOGNORM.DIST returns the cumulative distribution function; if FALSE, it returns the probability density function.</td></tr>
<tr>
<td>
LOGNORM.INV</td><td>
Returns the inverse of the log-normal cumulative distribution function of x.</td><td>
LOGNORM.INV(probability, mean, standard_dev)Probability: A probability associated with the log-normal distribution.Mean: The mean of ln(x).Standard_dev: The standard deviation of ln(x).</td></tr>
<tr>
<td>
LOGNORMDIST</td><td>
Equivalent to LOGNORM.DIST, added for Compatibility with older versions.</td><td>
LOGNORMDIST(x,mean,standard_dev)</td></tr>
<tr>
<td>
MAX</td><td>
Returns the largest value in a set of values.</td><td>
MAX(number1, [number2], ...)</td></tr>
<tr>
<td>
MAXA</td><td>
Returns the largest value in the list of arguments.</td><td>
MAXA(value1,[value2],...)</td></tr>
<tr>
<td>
MEDIAN</td><td>
Returns the median of the given numbers.</td><td>
MEDIAN(number1, [number2], ...)</td></tr>
<tr>
<td>
MIN</td><td>
Returns the smallest value in a set of values.</td><td>
MIN(number1, [number2], ...)</td></tr>
<tr>
<td>
MINA</td><td>
Returns the smallest value in the list of arguments.</td><td>
MINA(value1, [value2], ...)</td></tr>
<tr>
<td>
MODE</td><td>
Returns the most frequently occurring, or repetitive, value in an array or range of data.</td><td>
MODE(number1,[number2],...)</td></tr>
<tr>
<td>
NEGBINOM.DIST</td><td>
Returns the negative binomial distribution.</td><td>
NEGBINOM.DIST(number_f,number_s,probability_s,cumulative)Number_f: The number of failures.Number_s: The threshold number of successes.Probability_s: The probability of a success.Cumulative: If cumulative is TRUE, NEGBINOM.DIST returns the cumulative distribution function; if FALSE, it returns the probability density function.</td></tr>
<tr>
<td>
NEGBINOMDIST</td><td>
Equivalent to NEGBINOM.DIST, added for compatibility with old versions.</td><td>
NEGBINOMDIST(number_f,number_s,probability_s)</td></tr>
<tr>
<td>
NORM.DIST</td><td>
Returns the normal distribution for the specified mean and standard deviation.</td><td>
NORM.DIST(x,mean,standard_dev,cumulative)X: The value for which you want the distribution.Mean: The arithmetic mean of the distribution.Standard_dev: The standard deviation of the distribution.Cumulative: If cumulative is TRUE, NORM.DIST returns the cumulative distribution function; if FALSE, it returns the probability mass function.</td></tr>
<tr>
<td>
NORM.INV</td><td>
Returns the inverse of the normal cumulative distribution for the specified mean and standard deviation.</td><td>
NORM.INV(probability,mean,standard_dev)Probability: A probability corresponding to the normal distribution.Mean: The arithmetic mean of the distribution.Standard_dev: The standard deviation of the distribution.</td></tr>
<tr>
<td>
NORM.S.DIST</td><td>
Returns the standard normal distribution.</td><td>
NORM.S.DIST(z,cumulative)Z: The value for which you want the distribution.Cumulative: If cumulative is TRUE, NORMS.DIST returns the cumulative distribution function; if FALSE, it returns the probability mass function.</td></tr>
<tr>
<td>
NORM.S.INV</td><td>
Returns the inverse of the standard normal cumulative distribution.</td><td>
NORM.S.INV(probability)Probability: A probability corresponding to the normal distribution.</td></tr>
<tr>
<td>
NORMDIST</td><td>
Equivalent to NORM.DIST, added for compatibility with old versions.</td><td>
NORMDIST(x,mean,standard_dev,cumulative)</td></tr>
<tr>
<td>
NORMINV</td><td>
Equivalent to NORM.INV, added for compatibility with old versions.</td><td>
NORMINV(probability,mean,standard_dev)</td></tr>
<tr>
<td>
NORMSDIST</td><td>
Equivalent to NORM.S.DIST, added for compatibility with old versions.</td><td>
NORMSDIST(z,cumulative)</td></tr>
<tr>
<td>
NORMSINV</td><td>
Equivalent to NORM.S.INV, added for compatibility with old versions.</td><td>
NORMSINV(z,cumulative)</td></tr>
<tr>
<td>
PEARSON</td><td>
Returns the Pearson product moment correlation coefficient.</td><td>
PEARSON(array1, array2)Array1: A set of independent values.Array2: A set of dependent values.</td></tr>
<tr>
<td>
PERCENTILE</td><td>
Returns the k-th percentile of values in a range.</td><td>
PERCENTILE(array,k)Array: The array or range of data that defines relative standing.K: The percentile value in the range of 0 to 1, inclusively.</td></tr>
<tr>
<td>
PERCENTILE.EXC</td><td>
Returns the k-th percentile of values in a range, where k is in the range of 0 to 1, exclusively.</td><td>
PERCENTILE.EXC(array,k)Array: The array or range of data that defines relative standing.K: The percentile value in the range of 0 to 1, exclusively.</td></tr>
<tr>
<td>
PERCENTILE.INC</td><td>
Returns the k-th percentile of values in a range, where k is in the range of 0 to 1, inclusively.</td><td>
PERCENTILE.INC(array,k)Array: The array or range of data that defines relative standing.K: The percentile value in the range 0 to 1, exclusively.</td></tr>
<tr>
<td>
PERCENTRANK</td><td>
Returns the rank of a value in a data set as a percentage of the data set.</td><td>
PERCENTRANK(array,x,[significance])Array: The array or range of data with numeric values that defines relative standing.X: The value for which you want to know the rank.Significance: A value that identifies the number of significant digits for the returned percentage value.</td></tr>
<tr>
<td>
PERCENTRANK.EXC</td><td>
Returns the rank of a value in a data set as a percentage (0 to 1, exclusively) of the data set.</td><td>
PERCENTRANK.EXC(array,x,[significance])Array: The array or range of data with numeric values that defines relative standing.X: The value for which you want to know the rank.Significance: A value that identifies the number of significant digits for the returned percentage value.</td></tr>
<tr>
<td>
PERCENTRANK.INC</td><td>
Returns the rank of a value in a data set as a percentage (0 to1, inclusively) of the data set.</td><td>
PERCENTRANK.INC(array,x,[significance])Array: The array or range of data with numeric values that defines relative standing.X: The value for which you want to know the rank.Significance: A value that identifies the number of significant digits for the returned percentage value.</td></tr>
<tr>
<td>
PERMUT</td><td>
Returns the number of permutations for a given number of objects that can be selected from number objects.</td><td>
PERMUT(number, number_chosen)Number: An integer that describes the number of objects.Number_chosen: An integer that describes the number of objects in each permutation.</td></tr>
<tr>
<td>
PERMUTATIONA</td><td>
Returns the number of permutations for a given number of objects (with repetitions) that can be selected from the total objects.</td><td>
PERMUTATIONA(number, number-chosen)Number: An integer that describes the number of objects.Number_chosen: An integer that describes the number of objects in each permutation.</td></tr>
<tr>
<td>
POISSON</td><td>
This function has been replaced with the POISSON.DIST function. This function is available for compatibility with older versions.</td><td>
POISSON(x,mean,cumulative)</td></tr>
<tr>
<td>
POISSON.DIST</td><td>
Returns the Poisson distribution.</td><td>
POISSON.DIST(x,mean,cumulative)X: The number of events.Mean: The expected numeric value.Cumulative: If cumulative is TRUE, POISSON.DIST returns the cumulative Poisson distribution. If FALSE, it returns the Poisson probability mass function.</td></tr>
<tr>
<td>
PROB</td><td>
Returns the probability that values in a range are between two limits.</td><td>
PROB(x_range, prob_range, [lower_limit], [upper_limit])X_range: The range of numeric values of x with which there are associated probabilities.Prob_range: A set of probabilities associated with values in x_range.Lower_limit: The lower limit on the value for which you want a probability.Upper_limit: The optional upper limit on the value for which you want a probability.</td></tr>
<tr>
<td>
QUARTILE</td><td>
This function has been replaced with QUARTILE.EXC and QUARTILE.INC.However, this function is available for compatibility with older versions.</td><td>
QUARTILE(array,quart)</td></tr>
<tr>
<td>
QUARTILE.EXC</td><td>
Returns the quartile of the data set, based on percentile values from 0 to1, exclusively.</td><td>
QUARTILE.EXC(array, quart)Array: The array or cell range of numeric values for which you want the quartile value.Quart: Indicates which value to return.</td></tr>
<tr>
<td>
QUARTILE.INC</td><td>
Returns the quartile of a data set, based on percentile values from 0 to 1, inclusively.</td><td>
QUARTILE.INC(array,quart)Array: The array or cell range of numeric values for which you want the quartile value.Quart: Indicates which value to return.</td></tr>
<tr>
<td>
RANK.AVG</td><td>
Returns the rank of a number in a list of numbers.</td><td>
RANK.AVG(number,ref,[order])Number: The number whose rank you want to find.Ref: An array of, or a reference to, a list of numbers. Non numeric values in Ref are ignored.Order: A number specifying how to rank number.</td></tr>
<tr>
<td>
RANK.EQ</td><td>
Returns the rank of a number in a list of numbers.</td><td>
RANK.EQ(number,ref,[order])Number: The number whose rank you want to find.Ref: An array of, or a reference to, a list of numbers. Non numeric values in Ref are ignored.Order: A number specifying how to rank number.</td></tr>
<tr>
<td>
RANK</td><td>
This function has been replaced with the RANK.AVG and RANK.EQ functions.This is available for compatibility with older versions.</td><td>
RANK(number,ref,[order])</td></tr>
<tr>
<td>
RSQ</td><td>
Returns the square of the Pearson product moment correlation coefficient through data points in known_y's and known_x's.</td><td>
RSQ(known_y's,known_x's)Known_y's: An array or range of data points.Known_x's: An array or range of data points.</td></tr>
<tr>
<td>
SKEW</td><td>
Returns the skewness of a distribution.</td><td>
SKEW(number1, [number2], ...)</td></tr>
<tr>
<td>
SKEW.P</td><td>
Returns the skewness of a distribution based on a population.</td><td>
SKEW.P(number 1, [number 2],…)</td></tr>
<tr>
<td>
SLOPE</td><td>
Returns the slope of the linear regression line through data points in known_y's and known_x's.</td><td>
SLOPE(known_y's, known_x's)Known_y's: An array or cell range of numeric dependent data points.Known_x's: The set of independent data points.</td></tr>
<tr>
<td>
SMALL</td><td>
Returns the k-th smallest value in a data set.</td><td>
SMALL(array, k)Array: An array or range of numerical data for which you want to determine the k-th smallest value.K: The position (from the smallest) in the array or range of data to return.</td></tr>
<tr>
<td>
STANDARDIZE</td><td>
Returns a normalized value from a distribution characterized by mean and standard_dev.</td><td>
STANDARDIZE(x, mean, standard_dev)X: The value you want to normalize.Mean: The arithmetic mean of the distribution.Standard_dev: The standard deviation of the distribution.</td></tr>
<tr>
<td>
STDEV</td><td>
This function has been replaced with the STDEV.S function.This function is available for compatibility with  older versions.</td><td>
STDEV(number1,[number2],...)</td></tr>
<tr>
<td>
STDEV.P</td><td>
Calculates standard deviation based on the entire population given as arguments.</td><td>
STDEV.P(number1,[number2],...)</td></tr>
<tr>
<td>
STDEV.S</td><td>
Estimates standard deviation based on a sample (ignores logical values and text in the sample).</td><td>
STDEV.S(number1,[number2],...)</td></tr>
<tr>
<td>
STDEVA</td><td>
Estimates standard deviation based on a sample.</td><td>
STDEVA(value1, [value2], ...)</td></tr>
<tr>
<td>
STDEVP</td><td>
This function has been replaced with the STDEV.P function. It is available for compatibility with older versions.</td><td>
STDEVP(number1,[number2],...)</td></tr>
<tr>
<td>
STDEVPA</td><td>
Calculates standard deviation based on the entire population given as arguments, including text and logical values.</td><td>
STDEVPA(value1, [value2], ...)</td></tr>
<tr>
<td>
STEYX</td><td>
Returns the standard error of the predicted y-value for each x in the regression.</td><td>
STEYX(known_y's, known_x's)Known_y's: An array or range of dependent data points.Known_x's: An array or range of independent data points.</td></tr>
<tr>
<td>
T.INV</td><td>
Returns the left-tail inverse of the Student's t-distribution.</td><td>
T.INV(probability,deg_freedom)Probability: The probability associated with the Student's t-distribution.Deg_freedom: The number of degrees of freedom with which to characterize the distribution.</td></tr>
<tr>
<td>
TRIMMEAN</td><td>
Returns the mean of the interior of a data set.</td><td>
TRIMMEAN(array, percent)Array: The array or range of values to trim and average.Percent: The fractional number of data points to exclude from the calculation.</td></tr>
<tr>
<td>
VAR</td><td>
This function has been replaced with the VAR.S function.This is available for compatibility with older versions.</td><td>
VAR(number1,[number2],...)</td></tr>
<tr>
<td>
VARA</td><td>
Estimates variance based on a sample.</td><td>
VARA(value1, [value2], ...)</td></tr>
<tr>
<td>
VARP</td><td>
This function has been replaced with the VAR.P function.This is available for compatibility with older versions.</td><td>
VARP(number1,[number2],...)</td></tr>
<tr>
<td>
VARPA</td><td>
Calculates the variance based on the entire population.</td><td>
VARPA(value1, [value2], ...)</td></tr>
<tr>
<td>
WEIBULL</td><td>
This function has been replaced with the WEIBULL.DIST function.This is available for compatibility with older versions.</td><td>
WEIBULL(x,alpha,beta,cumulative)</td></tr>
<tr>
<td>
WEIBULL.DIST</td><td>
Returns the Weibull distribution.</td><td>
WEIBULL.DIST(x,alpha,beta,cumulative)X: The value at which to evaluate the function.Alpha: A parameter for the distribution.Beta: A parameter for the distribution.Cumulative: Determines the form of the function.</td></tr>
<tr>
<td>
Z.TEST</td><td>
Returns the one-tailed P-value of a z-test.</td><td>
Z.TEST(array,x,[sigma])Array: The array or range of data against which to test x.x: The value to test.Sigma: The population (known) standard deviation.</td></tr>
<tr>
<td>
ZTEST</td><td>
This function has been replaced with the Z.TEST function.This is available for compatibility with older versions.</td><td>
ZTEST(array,x,[sigma])</td></tr>
</table>

### Logical functions

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Syntax</th></tr>
<tr>
<td>
AND</td><td>
Returns TRUE if all of its arguments evaluate to TRUE.Returns FALSE if one or more arguments evaluate to FALSE.</td><td>
AND(logical1, [logical2], ...)logical1: The first condition that you want to test that can evaluate to either TRUE or FALSE.logical2: Additional conditions that you want to test that can evaluate to either TRUE or FALSE, up to a maximum of 255 conditions. (Optional)</td></tr>
<tr>
<td>
IF</td><td>
The IF function returns one value if a specified condition evaluates to TRUE, and another value if that condition evaluates to FALSE.</td><td>
IF(logical_test,[value_if_true], [value_if_false])Logical_test: Any value or expression that can be evaluated to TRUE or FALSE.Value_if_true: The value that you want to be returned if the logical_test argument evaluates to TRUE. (Optional)Value_if_false : The value that you want to be returned if the logical_test argument evaluates to FALSE. (Optional)</td></tr>
<tr>
<td>
IFERROR</td><td>
Returns a value you specify if a formula evaluates to an error; otherwise, returns the result of the formula.</td><td>
IFERROR(value, value_if_error)Value: The argument that is checked for an error.Value_if_error: The value to return if the formula evaluates to an error.</td></tr>
<tr>
<td>
NOT</td><td>
Reverses the value of its argument. Use NOT when you want to make sure a value is not equal to one particular value.</td><td>
NOT(logical)Logical: A value or expression that can be evaluated to TRUE or FALSE.</td></tr>
<tr>
<td>
OR</td><td>
Returns TRUE if any argument is TRUE; returns FALSE if all arguments are FALSE.</td><td>
OR(logical1, [logical2], ...)Logical1, logical2: 1 to 255 conditions you want to test that can be either TRUE or FALSE.</td></tr>
<tr>
<td>
FALSE</td><td>
Returns the logical value FALSE.</td><td>
FALSE()</td></tr>
<tr>
<td>
TRUE</td><td>
Returns the logical value TRUE.</td><td>
TRUE()</td></tr>
</table>

### Engineering functions

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Syntax</th></tr>
<tr>
<td>
BESSELI</td><td>
Returns the modified Bessel function.</td><td>
BESSELI(X, N)X: The value at which to evaluate the function.N: The order of the Bessel function. If n is not an integer, it is truncated.</td></tr>
<tr>
<td>
BESSELJ</td><td>
Returns the Bessel function.</td><td>
BESSELJ(X, N)X: The value at which to evaluate the function.N: The order of the Bessel function. If n is not an integer, it is truncated.</td></tr>
<tr>
<td>
BESSELK</td><td>
Returns the modified Bessel function, which is equivalent to the Bessel functions evaluated for purely imaginary arguments.</td><td>
BESSELK(X, N)X: The value at which to evaluate the function.N: The order of the function. If n is not an integer, it is truncated.</td></tr>
<tr>
<td>
BESSELY</td><td>
Returns the Bessel function, which is also called the Weber function or the Neumann function.</td><td>
BESSELY(X, N)X: The value at which to evaluate the function.N: The order of the function. If n is not an integer, it is truncated.</td></tr>
<tr>
<td>
BIN2DEC</td><td>
Converts a binary number to decimal.</td><td>
BIN2DEC(number)Number: The binary number you want to convert.</td></tr>
<tr>
<td>
BIN2HEX</td><td>
Converts a binary number to hexadecimal.</td><td>
BIN2HEX(number, [places])Number: The binary number you want to convert.Places: The number of characters to use.</td></tr>
<tr>
<td>
BIN2OCT</td><td>
Converts a binary number to octal.</td><td>
BIN2OCT(number, [places])Number: The binary number you want to convert.Places: The number of characters to use.</td></tr>
<tr>
<td>
BITAND</td><td>
Returns a bitwise 'AND' of two numbers.</td><td>
BITAND( number1, number2)Number1,Number2: Must be in decimal form and greater than or equal to 0.</td></tr>
<tr>
<td>
BITLSHIFT</td><td>
Returns a number shifted left by the specified number of bits.</td><td>
BITLSHIFT(number, shift_amount)Number: Number must be an integer greater than or equal to 0.Shift_amount: Shift_amount must be an integer.</td></tr>
<tr>
<td>
BITOR</td><td>
Returns a bitwise 'OR' of two numbers.</td><td>
BITOR(number1, number2)Number1, Number2: Must be in decimal form and greater than or equal to 0.</td></tr>
<tr>
<td>
BITRSHIFT</td><td>
Returns a number shifted right by the specified number of bits.</td><td>
BITRSHIFT(number, shift_amount)Number: Number must be an integer greater than or equal to 0.Shift_amount: Shift_amount must be an integer.</td></tr>
<tr>
<td>
BITXOR</td><td>
Returns a bitwise 'XOR' of two numbers.</td><td>
BITXOR(number1, number2)Number1,Number2: Must be in decimal form and greater than or equal to 0.</td></tr>
<tr>
<td>
COMPLEX</td><td>
Converts real and imaginary coefficients into a complex number of the form x + yi or x + yj.</td><td>
COMPLEX(real_num, i_num, [suffix])Real_num: The real coefficient of the complex number.I_num: The imaginary coefficient of the complex number.Suffix: The suffix for the imaginary component of the complex number. If omitted, suffix is assumed to be "i".</td></tr>
<tr>
<td>
CONVERT</td><td>
Converts a number from one measurement system to another.</td><td>
CONVERT(number,from_unit,to_unit)Number: the value in from_units to convert.From_unit: the units for number.To_unit: the units for the result.</td></tr>
<tr>
<td>
DEC2BIN</td><td>
Converts a decimal number to binary.</td><td>
DEC2BIN(number, [places])Number: The decimal integer you want to convert.Places: The number of characters to use.</td></tr>
<tr>
<td>
DEC2HEX</td><td>
Converts a decimal number to hexadecimal.</td><td>
DEC2HEX(number, [places])Number: The decimal integer you want to convert.Places: The number of characters to use.</td></tr>
<tr>
<td>
DEC2OCT</td><td>
Converts a decimal number to octal.</td><td>
DEC2OCT(number, [places])Number: The decimal integer you want to convert.Places: The number of characters to use.</td></tr>
<tr>
<td>
ERF</td><td>
Returns the error function integrated between lower_limit and upper_limit.</td><td>
ERF(lower_limit,[upper_limit])Lower_limit: The lower bound for integrating ERF.Upper_limit: The upper bound for integrating ERF. (Optional)</td></tr>
<tr>
<td>
ERF.PRECISE</td><td>
Returns the error function.</td><td>
ERF.PRECISE(x)X: The lower bound for integrating ERF.PRECISE.</td></tr>
<tr>
<td>
ERFC.PRECISE</td><td>
Returns the complementary ERF function integrated between x and infinity.</td><td>
ERFC.PRECISE(x)X: The lower bound for integrating ERFC.PRECISE.</td></tr>
<tr>
<td>
GESTEP</td><td>
Returns 1 if number ≥ step; returns 0 (zero) otherwise.</td><td>
GESTEP(number, [step])Number: The value to test against step.Step: The threshold value. If you omit a value for step, GESTEP uses zero. (Optional)</td></tr>
<tr>
<td>
HEX2BIN</td><td>
Converts a hexadecimal number to binary.</td><td>
HEX2BIN(number, [places])Number: The hexadecimal number you want to convert.Places: The number of characters to use.</td></tr>
<tr>
<td>
HEX2DEC</td><td>
Converts a hexadecimal number to decimal.</td><td>
HEX2DEC(number)Number: The hexadecimal number you want to convert.</td></tr>
<tr>
<td>
HEX2OCT</td><td>
Converts a hexadecimal number to octal.</td><td>
HEX2OCT(number, [places])Number: The hexadecimal number you want to convert.Places: The number of characters to use.</td></tr>
<tr>
<td>
IMABS</td><td>
Returns the absolute value of a complex number in x + yi or x + yj text format.</td><td>
IMABS(inumber)Inumber: A complex number for which you want the absolute value.</td></tr>
<tr>
<td>
IMAGINARY</td><td>
Returns the imaginary coefficient of a complex number in x + yi or x + yj text format.</td><td>
IMAGINARY(inumber)Inumber: A complex number for which you want the imaginary coefficient.</td></tr>
<tr>
<td>
IMARGUMENT</td><td>
Returns the argument Theta.</td><td>
IMARGUMENT(inumber)Inumber: A complex number for which you want the argument Theta.</td></tr>
<tr>
<td>
IMCONJUGATE</td><td>
Returns the complex conjugate of a complex number in x + yi or x + yj text format.</td><td>
IMCONJUGATE(inumber)Inumber: A complex number for which you want the conjugate.</td></tr>
<tr>
<td>
IMCOS</td><td>
Returns the cosine of a complex number in x + yi or x + yj text format.</td><td>
IMCOS(inumber)Inumber: A complex number for which you want the cosine.</td></tr>
<tr>
<td>
IMCOSH</td><td>
Returns the hyperbolic cosine of a complex number in x+yi or x+yj text format.</td><td>
IMCOSH(inumber)Inumber: A complex number for which you want the hyperbolic cosine.</td></tr>
<tr>
<td>
IMCOT</td><td>
Returns the cotangent of a complex number in x+yi or x+yj text format.</td><td>
IMCOT(inumber)Inumber: A complex number for which you want the cotangent.</td></tr>
<tr>
<td>
IMCSC</td><td>
Returns the cosecant of a complex number in x+yi or x+yj text format.</td><td>
IMCSC(inumber)Inumber: A complex number for which you want the cosecant.</td></tr>
<tr>
<td>
IMCSCH</td><td>
Returns the hyperbolic cosecant of a complex number in x+yi or x+yj text format.</td><td>
IMCSCH(inumber)Inumber: A complex number for which you want the hyperbolic cosecant.</td></tr>
<tr>
<td>
IMDIV</td><td>
Returns the quotient of two complex numbers in x + yi or x + yj text format.</td><td>
IMDIV(inumber1, inumber2)Inumber1: The complex numerator or dividend.Inumber2: The complex denominator or divisor.</td></tr>
<tr>
<td>
IMEXP</td><td>
Returns the exponential of a complex number in x + yi or x + yj text format.</td><td>
IMEXP(inumber)Inumber: A complex number for which you want the exponential.</td></tr>
<tr>
<td>
IMLN</td><td>
Returns the natural logarithm of a complex number in x + yi or x + yj text format.</td><td>
IMLN(inumber)Inumber: A complex number for which you want the natural logarithm.</td></tr>
<tr>
<td>
IMLOG10</td><td>
Returns the common logarithm (base 10) of a complex number in x + yi or x + yj text format.</td><td>
IMLOG10(inumber)Inumber: A complex number for which you want the common logarithm.</td></tr>
<tr>
<td>
IMLOG2</td><td>
Returns the base-2 logarithm of a complex number in x + yi or x + yj text format.</td><td>
IMLOG2(inumber)Inumber: A complex number for which you want the base-2 logarithm.</td></tr>
<tr>
<td>
IMPOWER</td><td>
Returns a complex number in x + yi or x + yj text format raised to a power.</td><td>
IMPOWER(inumber, number)Inumber: A complex number you want to raise to a power.Number: The power to which you want to raise the complex number.</td></tr>
<tr>
<td>
IMPRODUCT</td><td>
Returns the product of 1 to 255 complex numbers in x + yi or x + yj text format.</td><td>
IMPRODUCT(inumber1, [inumber2], ...)</td></tr>
<tr>
<td>
IMREAL</td><td>
Returns the real coefficient of a complex number in x + yi or x + yj text format.</td><td>
IMREAL(inumber)Inumber: A complex number for which you want the real coefficient.</td></tr>
<tr>
<td>
IMSEC</td><td>
Returns the secant of a complex number in x+yi or x+yj text format.</td><td>
IMSEC(inumber)Inumber: A complex number for which you want the secant.</td></tr>
<tr>
<td>
IMSECH</td><td>
Returns the hyperbolic secant of a complex number in x+yi or x+yj text format.</td><td>
IMSECH(inumber)Inumber: A complex number for which you want the hyperbolic secant.</td></tr>
<tr>
<td>
IMSIN</td><td>
Returns the sine of a complex number in x + yi or x + yj text format.</td><td>
IMSIN(inumber)Inumber: A complex number for which you want the sine.</td></tr>
<tr>
<td>
IMSINH</td><td>
Returns the hyperbolic sine of a complex number in x+yi or x+yj text format.</td><td>
IMSINH(inumber)Inumber: A complex number for which you want the hyperbolic sine.</td></tr>
<tr>
<td>
IMSQRT</td><td>
Returns the square root of a complex number in x + yi or x + yj text format.</td><td>
IMSQRT(inumber)Inumber: A complex number for which you want the square root.</td></tr>
<tr>
<td>
IMSUB</td><td>
Returns the difference of two complex numbers in x + yi or x + yj text format.</td><td>
IMSUB(inumber1, inumber2)Inumber1: The complex number from which to subtract inumber2.Inumber2: The complex number to subtract from inumber1.</td></tr>
<tr>
<td>
IMSUM</td><td>
Returns the sum of two or more complex numbers in x + yi or x + yj text format.</td><td>
IMSUM(inumber1, [inumber2], ...)</td></tr>
<tr>
<td>
IMTAN</td><td>
Returns the tangent of a complex number in x+yi or x+yj text format.</td><td>
IMTAN(inumber)Inumber: A complex number for which you want the tangent.</td></tr>
<tr>
<td>
OCT2BIN</td><td>
Converts an octal number to binary.</td><td>
OCT2BIN(number, [places])Number: The octal number you want to convert.Places: The number of characters to use.</td></tr>
<tr>
<td>
OCT2DEC</td><td>
Converts an octal number to decimal.</td><td>
OCT2DEC(number)Number: The octal number you want to convert.</td></tr>
<tr>
<td>
OCT2HEX</td><td>
Converts an octal number to hexadecimal.</td><td>
OCT2HEX(number, [places])Number: The octal number you want to convert.Places: The number of characters to use.</td></tr>
</table>


### Information functions


<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Syntax</th></tr>
<tr>
<td>
CELL</td><td>
Returns information about the formatting, location, or contents of a cell.</td><td>
CELL(info_type, [reference])Info_type: A text value that specifies what type of cell information you want to return.<table><br><tr><br><td><br>Info_type</td><td>
Returns</td></tr>
<tr>
<td>
'col'</td><td>
Column Number of ref.</td></tr>
<tr>
<td>
'color'</td><td>
1 for negative values, otherwise 0.</td></tr>
<tr>
<td>
'contents'</td><td>
Value of the upper left cell in ref.</td></tr>
<tr>
<td>
'filename'</td><td>
Full path of the file that contains ref.</td></tr>
<tr>
<td>
'format'</td><td>
Text value of the number format specified in the referenced cell.</td></tr>
<tr>
<td>
'parenthesis'</td><td>
1 if the cell is formatted with parentheses for positive or all values; otherwise returns 0.</td></tr>
<tr>
<td>
'prefix'</td><td>
Label prefix of the cell.</td></tr>
<tr>
<td>
'protect'</td><td>
0 if the cell is not locked, otherwise 1.</td></tr>
<tr>
<td>
'row'</td><td>
Row number of the cell in reference.</td></tr>
<tr>
<td>
'type'</td><td>
B if the cell is empty.L if the cell contains a label.V if the cell contains a value.</td></tr>
<tr>
<td>
'width'</td><td>
Column width of the ref cell.</td></tr>
</table>




</td></tr>
<tr>
<td>
ERROR.TYPE</td><td>
Returns a number corresponding to one of the error values in Microsoft Excel, or returns the #N/A error if no error exists.</td><td>
ERROR.TYPE(error_val)<table><br><tr><br><td><br>error_val</td><td>
Returns</td></tr>
<tr>
<td>
#NULL!</td><td>
1</td></tr>
<tr>
<td>
#DIV/0!</td><td>
2</td></tr>
<tr>
<td>
#VALUE!</td><td>
3</td></tr>
<tr>
<td>
#REF!</td><td>
4</td></tr>
<tr>
<td>
#NAME?</td><td>
5</td></tr>
<tr>
<td>
#NUM!</td><td>
6</td></tr>
<tr>
<td>
#N/A</td><td>
7</td></tr>
<tr>
<td>
#GETTING_DATA</td><td>
8</td></tr>
<tr>
<td>
Anything else</td><td>
#N/A</td></tr>
</table>




</td></tr>
<tr>
<td>
INFO</td><td>
Returns information about the current operating environment.</td><td>
INFO(type_text)<table><br><tr><br><td><br>Type_text</td><td>
Returns</td></tr>
<tr>
<td>
'directory'</td><td>
Path of the current directory or folder.</td></tr>
<tr>
<td>
'num file'</td><td>
Number of active worksheets in the open workbooks.</td></tr>
<tr>
<td>
'origin'</td><td>
Returns the absolute cell reference of the top and leftmost cell visible in the window.</td></tr>
<tr>
<td>
'OS version'</td><td>
Current operating system version, as text.</td></tr>
<tr>
<td>
'recalc'</td><td>
Current recalculation mode; returns 'Automatic' or 'Manual'.</td></tr>
<tr>
<td>
'release'</td><td>
Version of Microsoft Excel, as text.</td></tr>
<tr>
<td>
'system'</td><td>
Name of the operating environment:<br>Macintosh = "mac"<br>Windows = "pcdos"</td></tr>
</table>




</td></tr>
<tr>
<td>
ISBLANK</td><td>
Returns TRUE if the cell is blank, otherwise returns FALSE.</td><td>
ISBLANK(value)</td></tr>
<tr>
<td>
ISERR</td><td>
Returns TRUE if value refers to any error value except #N/A.</td><td>
ISERR(value)</td></tr>
<tr>
<td>
ISERROR</td><td>
Returns TRUE if value refers to any error value (#N/A, #VALUE!, #REF!, #DIV/0!, #NUM!, #NAME?, or #NULL!).</td><td>
ISERROR(value)</td></tr>
<tr>
<td>
ISEVEN</td><td>
Returns TRUE if number is even, or FALSE if number is odd.</td><td>
ISEVEN(number)</td></tr>
<tr>
<td>
ISFORMULA</td><td>
Returns TRUE if referenced to a cell that contains a formula, otherwise FALSE.</td><td>
ISFORMULA(reference)</td></tr>
<tr>
<td>
ISLOGICAL</td><td>
Returns TRUE if value refers to a logical value.</td><td>
ISLOGICAL(value)</td></tr>
<tr>
<td>
ISNA</td><td>
Returns TRUE if value refers to the #N/A (value not available) error value.</td><td>
ISNA(value)</td></tr>
<tr>
<td>
ISNONTEXT</td><td>
Returns TRUE if value refers to any item that is not text.</td><td>
ISNONTEXT(value)</td></tr>
<tr>
<td>
ISNUMBER</td><td>
Returns TRUE if value refers to a number.</td><td>
ISNUMBER(value)</td></tr>
<tr>
<td>
ISODD</td><td>
Returns TRUE if number is odd, or FALSE if number is even.</td><td>
ISODD(number)</td></tr>
<tr>
<td>
ISTEXT</td><td>
Returns TRUE if value refers to text.</td><td>
ISTEXT(value)</td></tr>
<tr>
<td>
N</td><td>
Returns a value converted to a number.</td><td>
N(value)</td></tr>
<tr>
<td>
NA</td><td>
Returns the error value #N/A. #N/A is the error value that means "no value is available.</td><td>
NA( )</td></tr>
<tr>
<td>
TYPE</td><td>
Returns the type of value.</td><td>
TYPE(value)<table><br><tr><br><td><br>value</td><td>
returns</td></tr>
<tr>
<td>
Number</td><td>
1</td></tr>
<tr>
<td>
Text</td><td>
2</td></tr>
<tr>
<td>
Logical value</td><td>
4</td></tr>
<tr>
<td>
Error value</td><td>
16</td></tr>
<tr>
<td>
Array (array: Used to build single formulas that produce multiple results or that operate on a group of arguments that are arranged in rows and columns. An array range shares a common formula; an array constant is a group of constants used as an argument.)</td><td>
64</td></tr>
</table>

</td></tr>
</table>

### Date & Time functions

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Syntax</th></tr>
<tr>
<td>
DATE</td><td>
Returns the sequential serial number that represents a particular date.</td><td>
DATE(year,month,day)Year: The value of the year argument can include one to four digits.Month: A positive or negative integer representing the month of the year from 1 to 12 (January to December).Day: A positive or negative integer representing the day of the month from 1 to 31.</td></tr>
<tr>
<td>
DATEVALUE</td><td>
Converts a date that is stored as text into a serial number that Excel recognizes as a date.</td><td>
DATEVALUE(date_text)Date_text: Text that represents a date in an Excel date format.</td></tr>
<tr>
<td>
DAY</td><td>
Returns the day of a date, represented by a serial number.</td><td>
DAY(serial_number)Serial_number: The date of the day you are trying to find.</td></tr>
<tr>
<td>
DAYS</td><td>
Returns the number of days between two dates.</td><td>
DAYS(end_date, start_date)Start_date and End_date are the two dates between which you want to know the number of days.</td></tr>
<tr>
<td>
DAYS360</td><td>
The DAYS360 function returns the number of days between two dates based on a 360-day year (twelve 30-day months).</td><td>
DAYS360(start_date,end_date,[method])Start_date, end_date: The two dates between which you want to know the number of days.Method: A logical value that specifies whether to use the U.S. or European method in the calculation.</td></tr>
<tr>
<td>
EDATE</td><td>
Returns the serial number that represents the date that is the indicated number of months before or after a specified date.</td><td>
EDATE(start_date, months)Start_date: A date that represents the start date.Months: The number of months before or after start_date.</td></tr>
<tr>
<td>
EOMONTH</td><td>
Returns the serial number for the last day of the month that is the indicated number of months before or after start_date.</td><td>
EOMONTH(start_date, months)Start_date: A date that represents the starting date.Months: The number of months before or after start_date.</td></tr>
<tr>
<td>
HOUR</td><td>
Returns the hour of a time value.</td><td>
HOUR(serial_number)Serial_number: The time that contains the hour you want to find.</td></tr>
<tr>
<td>
ISOWEEKNUM</td><td>
Returns number of the ISO week number of the year for a given date.</td><td>
ISOWEEKNUM(date)Date: Date is the date-time code used by Excel for date and time calculation.</td></tr>
<tr>
<td>
MINUTE</td><td>
Returns the minutes of a time value. The minute is given as an integer, ranging from 0 to 59.</td><td>
MINUTE(serial_number)Serial_number: The time that contains the minute you want to find.</td></tr>
<tr>
<td>
MONTH</td><td>
Returns the month of a date represented by a serial number.</td><td>
MONTH(serial_number)Serial_number: The date of the month you are trying to find.</td></tr>
<tr>
<td>
NETWORKDAYS.INTL</td><td>
Returns the number of whole workdays between two dates using parameters to indicate which and how many days are weekend days.</td><td>
NETWORKDAYS.INTL (start_date, end_date, [weekend], [holidays])Start_date and end_date: The dates for which the difference is to be computed.Weekend is a weekend number or string that specifies when weekends occur.</td></tr>
<tr>
<td>
NOW</td><td>
Returns the serial number of the current date and time.</td><td>
NOW()</td></tr>
<tr>
<td>
SECOND</td><td>
Returns the seconds of a time value.</td><td>
SECOND(serial_number)Serial_number: The time that contains the seconds you want to find.</td></tr>
<tr>
<td>
TIME</td><td>
Returns the decimal number for a particular time.</td><td>
TIME(hour, minute, second)Hour: A number from 0 (zero) to 32767 representing the hour.Minute: A number from 0 to 32767 representing the minute.Second: A number from 0 to 32767 representing the second.</td></tr>
<tr>
<td>
TIMEVALUE</td><td>
Returns the decimal number of the time represented by a text string.</td><td>
TIMEVALUE(time_text)Time_text: A text string that represents a time in any of the time formats.</td></tr>
<tr>
<td>
TODAY</td><td>
Returns the serial number of the current date.</td><td>
TODAY()</td></tr>
<tr>
<td>
WEEKDAY</td><td>
Returns the day of the week corresponding to a date.</td><td>
WEEKDAY(serial_number,[return_type])Serial_number: A sequential number that represents the date you are trying to find.Return_type: A number that determines the type of return value. (Optional)</td></tr>
<tr>
<td>
WEEKNUM</td><td>
Returns the week number of a specific date.</td><td>
WEEKNUM(serial_number,[return_type])Serial_number: A date within the week.Return_type: A number that determines on which day the week begins. The default is 1. (Optional)</td></tr>
<tr>
<td>
WORKDAY</td><td>
Returns a number that represents a date that is the indicated number of working days before or after a date.</td><td>
WORKDAY(start_date, days, [holidays])Start_date: A date that represents the start date.Days: The number of non-weekend and non-holiday days before or after start_date.Holidays: An optional list of one or more dates to exclude from the working calendar, such as state and federal holidays and floating holidays.</td></tr>
<tr>
<td>
WORKDAY.INTL</td><td>
Returns the serial number of the date before or after a specified number of workdays with custom weekend parameters.</td><td>
WORKDAY.INTL(start_date, days, [weekend], [holidays])Start_date: The start date, truncated to integer.Days: The number of workdays before or after the start_date.Weekend: Indicates the days of the week that are weekend days and are not considered working days. (Optional)</td></tr>
<tr>
<td>
YEAR</td><td>
Returns the year corresponding to a date.</td><td>
YEAR(serial_number)Serial_number: The date of the year you want to find.</td></tr>
<tr>
<td>
YEARFRAC</td><td>
Calculates the fraction of the year represented by the number of whole days between two dates.</td><td>
YEARFRAC(start_date, end_date, [basis])Start_date: A date that represents the start date.End_date: A date that represents the end date.Basis: The type of day count basis to use. (Optional)<table><br><tr><br><td><br>Basis</td><td>
Day count basis</td></tr>
<tr>
<td>
0 or omitted</td><td>
US (NASD) 30/360</td></tr>
<tr>
<td>
1</td><td>
Actual/actual</td></tr>
<tr>
<td>
2</td><td>
Actual/360</td></tr>
<tr>
<td>
3</td><td>
Actual/365</td></tr>
<tr>
<td>
4</td><td>
European 30/360</td></tr>
</table>

</td></tr>
</table>

### Financial functions

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Syntax</th></tr>
<tr>
<td>
CUMIPMT</td><td>
Returns the cumulative interest paid on a loan between start_period and end_period.</td><td>
CUMIPMT(rate, nper, pv, start_period, end_period, type)Rate: The interest rate.Nper:  The total number of payment periods.Pv: The present value.Start_period: The first period in the calculation. End_period: The last period in the calculation.Type: The timing of the payment.<table><br><tr><br><td><br>Type</td><td>
Timing</td></tr>
<tr>
<td>
0 (zero)</td><td>
Payment at the end of the period.</td></tr>
<tr>
<td>
1</td><td>
Payment at the beginning of the period.</td></tr>
</table>


</td></tr>
<tr>
<td>
CUMPRINC</td><td>
Returns the cumulative principal paid on a loan between start_period and end_period.</td><td>
CUMPRINC(rate, nper, pv, start_period, end_period, type)Rate: The interest rate.Nper:  The total number of payment periods.Pv: The present value.Start_period: The first period in the calculation. End_period: The last period in the calculation.Type: The timing of the payment.<table><br><tr><br><td><br>Type</td><td>
Timing</td></tr>
<tr>
<td>
0 (zero)</td><td>
Payment at the end of the period.</td></tr>
<tr>
<td>
1</td><td>
Payment at the beginning of the period.</td></tr>
</table>




</td></tr>
<tr>
<td>
DB</td><td>
Returns the depreciation of an asset for a specified period using the fixed-declining balance method.</td><td>
DB(cost, salvage, life, period, [month])Cost: The initial cost of the asset.Salvage: The value at the end of the depreciation Life: The number of periods over which the asset is being depreciated.Period: The period for which you want to calculate the depreciation. Period must use the same units as life.Month: The number of months in the first year. If month is omitted, it is assumed to be 12. (Optional)</td></tr>
<tr>
<td>
DDB</td><td>
Returns the depreciation of an asset for a specified period using the double-declining balance method or some other method you specify.</td><td>
DDB(cost, salvage, life, period, [factor])Cost: The initial cost of the asset.Salvage: The value at the end of the depreciation This value can be 0.Life: The number of periods over which the asset is being depreciated.Period: The period for which you want to calculate the depreciation. Period must use the same units as life.Factor: The rate at which the balance declines. (Optional)</td></tr>
<tr>
<td>
DISC</td><td>
Returns the discount rate for a security.</td><td>
DISC(settlement, maturity, pr, redemption, [basis])Settlement: The security's settlement date. Maturity: The security's maturity date. The maturity date is the date when the security expires.Pr: The security's price per $100 face value.Redemption: The security's redemption value per $100 face value.Basis: The type of day count basis to use. (Optional)</td></tr>
<tr>
<td>
DOLLARDE</td><td>
Converts a dollar price expressed as an integer part and a fraction part, such as 1.02, into a dollar price expressed as a decimal number.</td><td>
DOLLARDE(fractional_dollar, fraction)Fractional_dollar: A number expressed as an integer part and a fraction part, separated by a decimal symbol.Fraction: The integer to use in the denominator of the fraction.</td></tr>
<tr>
<td>
DOLLARFR</td><td>
Use DOLLARFR to convert decimal numbers to fractional dollar numbers, such as securities prices.</td><td>
DOLLARFR(decimal_dollar, fraction)Decimal_dollar: A decimal number.Fraction: The integer to use in the denominator of a fraction.</td></tr>
<tr>
<td>
DURATION</td><td>
Returns the Macaulay duration for an assumed par value of $100.</td><td>
DURATION(settlement, maturity, coupon, yield, frequency, [basis])Settlement: The security settlement date is the date after the issue date when the security is traded to the buyer.Maturity: The maturity date is the date when the security expires.Coupon: The security's annual coupon rate.Yield: The security's annual yield.Frequency: The number of coupon payments per year. For annual payments, frequency = 1; for semiannual, frequency = 2; for quarterly, frequency = 4.Basis: The type of day count basis to use. (Optional)<table><br><tr><br><td><br>Basis</td><td>
Day count basis</td></tr>
<tr>
<td>
0 or omitted</td><td>
US (NASD) 30/360</td></tr>
<tr>
<td>
1</td><td>
Actual/actual</td></tr>
<tr>
<td>
2</td><td>
Actual/360</td></tr>
<tr>
<td>
3</td><td>
Actual/365</td></tr>
<tr>
<td>
4</td><td>
European 30/360</td></tr>
</table>




</td></tr>
<tr>
<td>
FV</td><td>
Returns the future value of an investment based on periodic, constant payments and a constant interest rate.</td><td>
FV(rate,nper,pmt,[pv],[type])Rate: The interest rate per period.Nper: The total number of payment periods in an annuity.Pmt: The payment made each period.Pv: The present value, or the lump-sum amount that a series of future payments is worth right now. If pv is omitted, it is assumed to be 0. (Optional)Type: The number 0 or 1, which indicates when payments are due. If type is omitted, it is assumed to be 0. (Optional)</td></tr>
<tr>
<td>
FVSHEDULE</td><td>
Returns the future value of an initial principal after applying a series of compound interest rates.</td><td>
FVSCHEDULE(principal, schedule)Principal: The present value.Schedule: An array of interest rates to apply.</td></tr>
<tr>
<td>
INTRATE</td><td>
Returns the interest rate for a fully invested security.</td><td>
INTRATE(settlement, maturity, investment, redemption, [basis])Settlement: The security settlement date is the date after the issue date when the security is traded to the buyer.Maturity: The maturity date is the date when the security expires.Investment: The amount invested in the security.Redemption: The amount to be received at maturity.Basis: The type of day count basis to use.<table><br><tr><br><td><br>Basis</td><td>
Day count basis</td></tr>
<tr>
<td>
0 or omitted</td><td>
US (NASD) 30/360</td></tr>
<tr>
<td>
1</td><td>
Actual/actual</td></tr>
<tr>
<td>
2</td><td>
Actual/360</td></tr>
<tr>
<td>
3</td><td>
Actual/365</td></tr>
<tr>
<td>
4</td><td>
European 30/360</td></tr>
</table>


</td></tr>
<tr>
<td>
IPMT</td><td>
Returns the interest payment for a given period for an investment based on periodic, constant payments and a constant interest rate.</td><td>
IPMT(rate, per, nper, pv, [fv], [type])Rate: The interest rate per period.Per: The period for which you want to find the interest and must be in the range 1 to nper.Nper: The total number of payment periods in an annuity.Pv: The present value, or the lump-sum amount that a series of future payments is worth right now.Fv: The future value or a cash balance you want to attain after the last payment is made. If fv is omitted, it is assumed to be 0 (the future value of a loan, for example, is 0).Type: The number 0 or 1.<table><br><tr><br><td><br>Type</td><td>
Payment Due</td></tr>
<tr>
<td>
0</td><td>
At the end of the period.</td></tr>
<tr>
<td>
1</td><td>
At the beginning of the period.</td></tr>
</table>




</td></tr>
<tr>
<td>
IRR</td><td>
Returns the internal rate of return for a series of cash flows represented by the numbers in values.</td><td>
IRR(values, [guess])Values: An array or a reference to cellsGuess: A number that you guess is close to the result of IRR. (Optional)</td></tr>
<tr>
<td>
ISPMT</td><td>
Calculates the interest paid during a specific period of an investment. This function is provided for compatibility with Lotus 1-2-3.</td><td>
ISPMT(rate, per, nper, pv)Rate: The interest rate for the investment.Per: The period for which you want to find the interest, and must be between 1 and nper.Nper: The total number of payment periods for the investment.Pv: The present value of the investment. For a loan, pv is the loan amount.</td></tr>
<tr>
<td>
MIRR</td><td>
Returns the modified internal rate of return for a series of periodic cash flows.</td><td>
MIRR(values, finance_rate, reinvest_rate)Values: An array or a reference to cells that contain numbers.Finance_rate: The interest rate you pay on the money used in the cash flows.Reinvest_rate: The interest rate you receive on the cash flows as you reinvest them.</td></tr>
<tr>
<td>
NPER</td><td>
Returns the number of periods for an investment based on periodic, constant payments and a constant interest rate.</td><td>
NPER(rate,pmt,pv,[fv],[type])Rate : The interest rate per period.Pmt : The payment made each period; Pv : The present value, or the lump-sum amount that a series of future payments is worth right now.Fv : The future value, or a cash balance you want to attain after the last payment is made. (Optional)Type : The number 0 or 1 and indicates when payments are due. (Optional)</td></tr>
<tr>
<td>
NPV</td><td>
Calculates the net present value of an investment by using a discount rate and a series of future payments and income.</td><td>
NPV(rate,value1,[value2],...)Rate: The rate of discount over the length of one period.</td></tr>
<tr>
<td>
PMT</td><td>
Calculates the payment for a loan based on constant payments and a constant interest rate.</td><td>
PMT(rate, nper, pv, [fv], [type])Rate: The interest rate for the loan.Nper: The total number of payments for the loan.Pv: The present value, or the total amount that a series of future payments is worth now.Fv: The future value, or a cash balance you want to attain after the last payment is made. Type: The number 0 (zero) or 1, it indicates when payments are due. (Optional)</td></tr>
<tr>
<td>
PPMT</td><td>
Returns the payment on the principal for a given period for an investment based on periodic, constant payments and a constant interest rate.</td><td>
PPMT(rate, per, nper, pv, [fv], [type])Rate: The interest rate per period.Per: Specifies the period and must be in the range 1 to nper.Nper: The total number of payment periods in an annuity.Pv: The present value — the total amount that a series of future payments is worth now.Fv: The future value, or a cash balance you want to attain after the last payment is made. If fv is omitted, it is assumed to be 0 (zero), that is, the future value of a loan is 0.Type: The number 0 or 1, it indicates when payments are due. (Optional)</td></tr>
<tr>
<td>
PV</td><td>
Returns the present value of an investment. The present value is the total amount that a series of future payments is worth now.</td><td>
PV(rate, nper, pmt, [fv], [type])Rate: The interest rate per period. Nper: The total number of payment periods in an annuity. Pmt: The payment made each period and cannot change over the life of the annuity. Fv: The future value, or a cash balance you want to attain after the last payment is made.Type: The number 0 or 1, it indicates when payments are due. (Optional)</td></tr>
<tr>
<td>
RATE</td><td>
Returns the interest rate per period of an annuity.</td><td>
RATE(nper, pmt, pv, [fv], [type], [guess])Nper: The total number of payment periods in an annuity.Pmt: The payment made each period and cannot change over the life of the annuity. Pv: The present value — the total amount that a series of future payments is worth now.Fv: The future value, or a cash balance you want to attain after the last payment is made. Type: The number 0 or 1 and indicates when payments are due. (Optional)<table><br><tr><br><td><br>Type </td><td>
Payment Due</td></tr>
<tr>
<td>
0 or omitted</td><td>
At the end of the period.</td></tr>
<tr>
<td>
1</td><td>
At the beginning of the period.</td></tr>
</table>
Guess: Your guess for what the rate will be. (Optional)

</td></tr>
<tr>
<td>
RRI</td><td>
Returns an equivalent interest rate for the growth of an investment.</td><td>
RRI(nper, pv, fv)Nper: Nper is the number of periods for the investment.Pv: Pv is the present value of the investment.Fv: Fv is the future value of the investment.</td></tr>
<tr>
<td>
SLN</td><td>
Returns the straight-line depreciation of an asset for one period.</td><td>
SLN(cost, salvage, life)Cost: The initial cost of the asset.Salvage: The value at the end of the depreciation.Life: The number of periods over which the asset is depreciated.</td></tr>
<tr>
<td>
SYD</td><td>
Returns the sum-of-years' digits depreciation of an asset for a specified period.</td><td>
SYD(cost, salvage, life, per)Cost: The initial cost of the asset.Salvage: The value at the end of the depreciation.Life: The number of periods over which the asset has depreciated.Per: The period, it must use the same units as life.</td></tr>
<tr>
<td>
VDB</td><td>
Returns the depreciation of an asset for any specified period, including partial periods.</td><td>
VDB(cost, salvage, life, start_period, end_period, [factor], [no_switch])Cost: The initial cost of the asset.Salvage: The value at the end of the depreciation This value can be 0.Life: The number of periods over which the asset is depreciated.Start_period: The starting period for which you want to calculate the depreciation.End_period: The ending period for which you want to calculate the depreciation. Factor: The rate at which the balance declines. (Optional) No_switch: A logical value specifying whether to switch to straight-line depreciation when depreciation is greater than the declining balance calculation. (Optional)</td></tr>
<tr>
<td>
XIRR</td><td>
Returns the internal rate of return for a schedule of cash flows that is not necessarily periodic.</td><td>
XIRR(values, dates, [guess])Values: A series of cash flows that corresponds to a schedule of payments in dates. Dates: A schedule of payment dates that corresponds to the cash flow paymentsGuess: A number that you guess is close to the result of XIRR. (Optional)</td></tr>
</table>

### Lookup & Reference functions

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Syntax</th></tr>
<tr>
<td>
AREA</td><td>
Returns the number of areas in a reference. An area is a range of contiguous cells or a single cell.</td><td>
AREAS(reference)Reference: A reference to a cell or range of cells, it can refer to multiple areas.</td></tr>
<tr>
<td>
COLUMN</td><td>
Returns the column number of the given cell reference.</td><td>
COLUMN([reference])Reference: The cell or range of cells for which you want to return the column number. (Optional)</td></tr>
<tr>
<td>
COLUMNS</td><td>
Returns the number of columns in an array or reference.</td><td>
COLUMNS(array)Array: An array or array formula, or a reference to a range of cells for which you want the number of columns.</td></tr>
<tr>
<td>
FORMULATEXT</td><td>
Returns a formula as a string.</td><td>
FORMULATEXT(reference)Reference: A reference to a cell or range of cells.</td></tr>
<tr>
<td>
HLOOKUP</td><td>
Searches for a value in the top row of a table or an array of values, and then returns a value in the same column from a row you specify in the table or array.</td><td>
HLOOKUP(lookup_value,table_array, row_index_num, [range_lookup])Lookup_value: The value to be found in the first row of the table. Table_array: A table of information in which data is looked up. Row_index_num: The row number in table_array from which the matching value will be returned. Range_lookup: A logical value that specifies whether you want HLOOKUP to find an exact match or an approximate match. </td></tr>
<tr>
<td>
HYPERLINK</td><td>
Creates a shortcut or jump that opens a document stored on a network server, an intranet, or the Internet.</td><td>
HYPERLINK(link_location, [friendly_name])Link_location: The path and file name to the document to be opened.Friendly_name: The jump text or numeric value that is displayed in the cell.</td></tr>
<tr>
<td>
INDIRECT</td><td>
Returns the reference specified by a text string. References are immediately evaluated to display their contents.</td><td>
INDIRECT(ref_text, [a1])Ref_text: A reference to a cell that contains an A1-style reference, an R1C1-style reference, a name defined as a reference, or a reference to a cell as a text string.A1: A logical value that specifies what type of reference is contained in the cell ref_text.</td></tr>
<tr>
<td>
MATCH</td><td>
The MATCH function searches for a specified item in a range of cells, and then returns the relative position of that item in the range.</td><td>
MATCH(lookup_value, lookup_array, [match_type])lookup_value: The value that you want to match in lookup_array. The lookup_value argument can be a value or a cell reference to a number, text, or logical value.lookup_array: The range of cells being searched.match_type: The number -1, 0, or 1.<table><br><tr><br><td><br>Match_type</td><td>
Behavior</td></tr>
<tr>
<td>
1 or omitted</td><td>
MATCH finds the largest value that is less than or equal to {{ '_lookup_value_'| markdownify}} </td></tr>
<tr>
<td>
0</td><td>
MATCH finds the first value that is exactly equal to {{ '_lookup_value_'| markdownify}} </td></tr>
<tr>
<td>
-1</td><td>
MATCH finds the smallest value that is greater than or equal to{{' _lookup_value_'| markdownify}} </td></tr>
</table>


</td></tr>
<tr>
<td>
OFFSET</td><td>
Returns a reference to a range that is a specified number of rows and columns from a cell or range of cells.</td><td>
OFFSET(reference, rows, cols, [height], [width])Reference: The reference from which you want to base the offset. Rows: The number of rows, up or down, that you want the upper-left cell to refer to. Cols: The number of columns, to the left or right, that you want the upper-left cell of the result to refer to. Height: The height, in number of rows, that you want the returned reference to be. Height must be a positive number. (Optional)Width: The width, in number of columns, that you want the returned reference to be. Width must be a positive number. (Optional)</td></tr>
<tr>
<td>
ROW</td><td>
Returns the row number of a reference.</td><td>
ROW([reference])Reference: The cell or range of cells for which you want the row number.</td></tr>
<tr>
<td>
ROWS</td><td>
Returns the number of rows in a reference or array.</td><td>
ROWS(array)Array: An array, an array formula, or a reference to a range of cells for which you want the number of rows.</td></tr>
<tr>
<td>
SHEET</td><td>
Returns the sheet number of the reference sheet.</td><td>
SHEET(value)Value: Value is the name of a sheet or a reference for which you want the sheet number.</td></tr>
<tr>
<td>
SHEETS</td><td>
Returns the number of sheets in a reference.</td><td>
SHEETS(reference)Reference: Reference is a reference for which you want to know the number of sheets it contains. (Optional)</td></tr>
<tr>
<td>
TRANSPOSE</td><td>
The TRANSPOSE function returns a vertical range of cells as a horizontal range, or vice versa.</td><td>
TRANSPOSE(array)array: An array or range of cells on a worksheet that you want to transpose.</td></tr>
<tr>
<td>
VLOOKUP</td><td>
You can use the VLOOKUP function to search the first column of a range of cells, and then return a value from any cell on the same row of the range.</td><td>
VLOOKUP(lookup_value, table_array, col_index_num, [range_lookup])lookup_value: The value to search in the first column of the table or range. table_array: The range of cells that contains the data. col_index_num: The column number in the table_array argument from which the matching value must be returned. range_lookup: A logical value that specifies whether you want VLOOKUP to find an exact match or an approximate match. (Optional)</td></tr>
</table>

### Text functions

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Syntax</th></tr>
<tr>
<td>
CODE</td><td>
Returns a numeric code for the first character in a text string.</td><td>
CODE(text)Text: The text for which you want the code of the first character.</td></tr>
<tr>
<td>
CONCATENATE</td><td>
The CONCATENATE function joins up to 255 text strings into one text string.</td><td>
CONCATENATE(text1, [text2], ...)Text1: The first text item to be concatenated.Text2: Additional text items, up to a maximum of 255 items.</td></tr>
<tr>
<td>
DOLLAR</td><td>
The function described in this Help topic converts a number to text format and applies a currency symbol.</td><td>
DOLLAR(number, [decimals])Number: A number, a reference to a cell containing a number, or a formula that evaluates to a number.Decimals: The number of digits to the right of the decimal point. (Optional)</td></tr>
<tr>
<td>
FINDB</td><td>
FINDB counts each double-byte character as 2 when editing of a language that supports DBCS is enabled and has been set as the default language.</td><td>
FINDB(find_text, within_text, [start_num])Find_text: The text you want to find.Within_text: The text containing the text you want to find.Start_num: Specifies the character at which to start the search. (Optional)</td></tr>
<tr>
<td>
FIXED</td><td>
Rounds a number to the specified number of decimals, formats the number in decimal format using a period and commas, and returns the result as text.</td><td>
FIXED(number, [decimals], [no_commas])Number: The number you want to round and convert to text.Decimals: The number of digits to the right of the decimal point.No_commas: A logical value that, if TRUE, prevents FIXED from including commas in the returned text. (Optional)</td></tr>
<tr>
<td>
JIS</td><td>
Converts half-width (single-byte) letters within a character string to full-width (double-byte) characters.</td><td>
JIS(Text)Text: The text or a reference to a cell that contains the text you want to change.</td></tr>
<tr>
<td>
LEFT</td><td>
LEFT returns the first character or characters in a text string, based on the number of characters you specify.</td><td>
LEFT(text, [num_chars])</td></tr>
<tr>
<td>
LEFTB</td><td>
LEFTB returns the first character or characters in a text string, based on the number of bytes you specify.</td><td>
LEFTB(text, [num_bytes])Text: The text string that contains the characters you want to extract.Num_chars: Specifies the number of characters you want LEFT to extract. (Optional)Num_bytes: Specifies the number of characters you want LEFTB to extract, based on bytes. (Optional)</td></tr>
<tr>
<td>
LEN</td><td>
LEN returns the number of characters in a text string.</td><td>
LEN(text)Text: The text whose length you want to find. Spaces count as characters.</td></tr>
<tr>
<td>
LENB</td><td>
LENB returns the number of bytes used to represent the characters in a text string.</td><td>
LENB(text)Text: The text whose length you want to find. Spaces count as characters.</td></tr>
<tr>
<td>
LOWER</td><td>
Converts all uppercase letters in a text string to lowercase.</td><td>
LOWER(text)Text: The text you want to convert to lowercase.</td></tr>
<tr>
<td>
MID</td><td>
MID returns a specific number of characters from a text string, starting at the position you specify, based on the number of characters you specify.</td><td>
MID(text, start_num, num_chars)Text: The text string containing the characters you want to extract.Start_num: The position of the first character you want to extract in text. The first character in text has start_num 1, and so on.Num_chars: Specifies the number of characters you want MID to return from text.Num_bytes: Specifies the number of characters you want MIDB to return from text, in bytes.</td></tr>
<tr>
<td>
MIDB</td><td>
MIDB returns a specific number of characters from a text string, starting at the position you specify, based on the number of bytes you specify.</td><td>
MIDB(text, start_num, num_chars)Text: The text string containing the characters you want to extract.Start_num: The position of the first character you want to extract in text. The first character in text has start_num 1, and so on.Num_chars: Specifies the number of characters you want MID to return from text.Num_bytes: Specifies the number of characters you want MIDB to return from text, in bytes.</td></tr>
<tr>
<td>
NUMBERVALUE</td><td>
Converts text to a number, in a locale-independent way.</td><td>
NUMBERVALUE(Text,[Decimal_separator], [Group_separator ])Text: The text to convert to a number.Decimal_separator: The character used to separate the integer and fractional part of the result.Group_separator : The character used to separate groupings of numbers, such as thousands from hundreds and millions from thousands.</td></tr>
<tr>
<td>
PROPER</td><td>
Capitalizes the first letter in a text string and any other letters in that string that follow non-letter characters.</td><td>
PROPER(text)Text: Text enclosed in quotation marks, a formula that returns text, or a reference to a cell containing the text you want to partially capitalize.</td></tr>
<tr>
<td>
REPLACE</td><td>
Replaces part of a text string, based on the number of characters you specify, with a different text string.</td><td>
REPLACE(old_text, start_num, num_chars, new_text)Old_text: Text in which you want to replace some characters.Start_num: The position of the character in old_text that you want to replace with new_text.Num_chars: The number of characters in old_text for REPLACE to replace with new_text.Num_bytes: The number of bytes in old_text for REPLACEB to replace with new_text.New_text: The text that will replace characters in old_text.</td></tr>
<tr>
<td>
REPT</td><td>
Repeats text a given number of times.</td><td>
REPT(text, number_times)Text: The text you want to repeat.Number_times: A positive number specifying the number of times to repeat text.</td></tr>
<tr>
<td>
RIGHT</td><td>
RIGHT returns the last character or characters in a text string, based on the specified number of characters.</td><td>
RIGHT(text,[num_chars])Text: The text string containing the characters you want to extract.Num_chars: Specifies the number of characters you want RIGHT to extract. (Optional)</td></tr>
<tr>
<td>
RIGHTB</td><td>
RIGHTB returns the last character or characters in a text string, based on the number of bytes specified.</td><td>
RIGHTB(text,[num_bytes])Text: The text string containing the characters you want to extract.Num_bytes: Specifies the number of characters you want RIGHTB to extract, based on bytes. (Optional)</td></tr>
<tr>
<td>
SEARCHB</td><td>
Locates one text string within a second text string, and returns the number of the starting position of the first text string from the first character of the second text string.</td><td>
SEARCHB(find_text,within_text,[start_num])find_text: The text that you want to find.within_text: The text in which you want to search for the value of the find_text argument.start_num: The character number in the within_text argument at which you want to start searching.</td></tr>
<tr>
<td>
SUBSTITUTE</td><td>
Substitutes new_text for old_text in a text string.</td><td>
SUBSTITUTE(text, old_text, new_text, [instance_num])Text: The text or the reference to a cell containing text for which you want to substitute characters.Old_text: The text you want to replace.New_text: The text you want to replace old_text with.Instance_num: Specifies which occurrence of old_text you want to replace with new_text. (Optional)</td></tr>
<tr>
<td>
T</td><td>
Returns the text referred to by value.</td><td>
T(value)Value: The value you want to test.</td></tr>
<tr>
<td>
TEXT</td><td>
The TEXT function converts a numeric value to text and lets you specify the display formatting by using special format strings.</td><td>
TEXT(value, format_text)value: A numeric value, a formula that evaluates to a numeric value, or a reference to a cell containing a numeric value.format_text: A numeric format as a text string enclosed in quotation marks.</td></tr>
<tr>
<td>
TRIM</td><td>
Removes all spaces from text except for single spaces between words.</td><td>
TRIM(text)Text: The text from which you want spaces removed.</td></tr>
<tr>
<td>
UNICHAR</td><td>
Returns the Unicode character that is referenced by the given numeric value.</td><td>
UNICHAR(number)Number is the Unicode number that represents the character.</td></tr>
<tr>
<td>
UNICODE</td><td>
Returns the number (code point) corresponding to the first character of the text.</td><td>
UNICODE(text)Text: Text is the character for which you want the Unicode value.</td></tr>
<tr>
<td>
UPPER</td><td>
Converts text to uppercase.</td><td>
UPPER(text)Text: The text you want converted to uppercase.</td></tr>
<tr>
<td>
VALUE</td><td>
Converts a text string that represents a number to a number.</td><td>
VALUE(text)Text: The text enclosed in quotation marks or a reference to a cell containing the text you want to convert.</td></tr>
</table>

### Database functions

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Syntax</th></tr>
<tr>
<td>
DAVERAGE</td><td>
Averages the values in a field of records in a list or database that match conditions you specify.</td><td>
DAVERAGE(database, field, criteria)Database: The range of cells that makes up the list or database. Field: Indicates which column is used in the function. Enter the column label enclosed between double quotation marks.Criteria: The range of cells that contains the conditions you specify.</td></tr>
<tr>
<td>
DCOUNT</td><td>
Counts the cells that contain numbers in a field of records in a list or database that match conditions that you specify.</td><td>
DCOUNT(database, field, criteria)Database: The range of cells that makes up the list or database. Field: Indicates which column is used in the function. Enter the column label enclosed between double quotation marks.Criteria: The range of cells that contains the conditions you specify.</td></tr>
<tr>
<td>
DCOUNTA</td><td>
Counts the filled cells in a field of records in a list or database that match conditions that you specify.</td><td>
DCOUNTA(database, field, criteria)Database: The range of cells that makes up the list or database. Field: indicates which column is used in the function. Enter the column label enclosed between double quotation marks.Criteria: The range of cells that contains the conditions you specify.</td></tr>
<tr>
<td>
DGET</td><td>
Extracts a single value from a column of a list or database that matches conditions that you specify.</td><td>
DGET(database, field, criteria)Database: The range of cells that makes up the list or database. Field: indicates which column is used in the function. Enter the column label enclosed between double quotation marks.Criteria: The range of cells that contains the conditions you specify.</td></tr>
<tr>
<td>
DMAX</td><td>
Returns the largest number in a field of records in a list or database that matches conditions you that specify.</td><td>
DMAX(database, field, criteria)Database: The range of cells that makes up the list or database. Field: Indicates which column is used in the function. Enter the column label enclosed between double quotation marks.Criteria: is the range of cells that contains the conditions you specify.</td></tr>
<tr>
<td>
DMIN</td><td>
Returns the smallest number in a field of records in a list or database that matches conditions that you specify.</td><td>
DMIN(database, field, criteria)Database: The range of cells that makes up the list or database. Field: Indicates which column is used in the function. Enter the column label enclosed between double quotation marks.Criteria: The range of cells that contains the conditions you specify.</td></tr>
<tr>
<td>
DSTDEV</td><td>
The standard deviation of a population based on a sample by using the numbers in a field (column) of records in a list.</td><td>
DSTDEV(database, field, criteria)Database: is the range of cells that makes up the list or database. Field: Indicates which column is used in the function. Enter the column label enclosed between double quotation marks.Criteria: is the range of cells that contains the conditions you specify.</td></tr>
<tr>
<td>
DSTDEVP</td><td>
The standard deviation of a population based on the entire population using the numbers in a field of records in a list.</td><td>
DSTDEVP(database, field, criteria)Database: The range of cells that makes up the list or database. Field: Indicates which column is used in the function. Enter the column label enclosed between double quotation marks.Criteria: Is the range of cells that contains the conditions you specify.</td></tr>
<tr>
<td>
DSUM</td><td>
The numbers in a field of records in a list or database that match conditions that you specify.</td><td>
DSUM(database, field, criteria)Database: The range of cells that makes up the list or database. Field: Indicates which column is used in the function. Enter the column label enclosed between double quotation marks.Criteria: The range of cells that contains the conditions you specify.</td></tr>
<tr>
<td>
DVAR</td><td>
The variance of a population based on a sample using the numbers in a field of records in a list.</td><td>
DVAR(database, field, criteria)Database: The range of cells that makes up the list or database. Field: indicates which column is used in the function. Enter the column label enclosed between double quotation marks.Criteria: is the range of cells that contains the conditions you specify.</td></tr>
<tr>
<td>
DVARP</td><td>
The variance of a population based on the entire population by using the numbers in a field of records in a list.</td><td>
DVARP(database, field, criteria)Database: The range of cells that makes up the list or database. Field: Indicates which column is used in the function. Enter the column label enclosed between double quotation marks.Criteria: The range of cells that contains the conditions you specify.</td></tr>
</table>

### Web functions

<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Syntax</th></tr>
<tr>
<td>
ENCODEURL</td><td>
Returns a URL-encoded string.</td><td>
ENCODEURL(text)Text: A string to be URL encoded.</td></tr>
<tr>
<td>
FILTERXML</td><td>
Returns specific data from the XML content by using the specified XPath.</td><td>
FILTERXML(xml, xpath)Xml: A string in valid XML format.Xpath: A string in standard XPath format.</td></tr>
<tr>
<td>
WEBSERVICE</td><td>
Returns data from a web service on the Internet or Intranet.</td><td>
WEBSERVICE(url)Url: The URL of the web service.</td></tr>
</table>
