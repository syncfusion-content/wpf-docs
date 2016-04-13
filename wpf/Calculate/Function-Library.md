---
layout: post
title: Function Library | Calculate | wpf | Syncfusion
description: function library
platform: wpf
control: Calculate
documentation: ug
---

# Function Library

The Function Library contains many functions from statistics, finance and mathematics, along with other general purpose functions. There are more than 400 entries in the library, and it is easy to add your own calculations. 

The functions are discussed in the below topics.

## Add Function

CalcQuickBase relies on a Calculate.Engine object through an ICalcData interface to provide its calculation support. To add functions to the Formula Library available to your CalcQuickBase object, you need to add them to the CalcQuickBase's underlying Engine object. You can access this engine object through the public "read-only" property, CalcQuickBase.Engine. Once you have a reference to the CalcQuickBase's Engine object, you can add library functions by following the steps given below.

Adding a custom function to the Formula Library is a two step process. 

The first step is to write a method that actually does the calculation work for your custom function. The second step is to register this method with the CalcEngine. So, if your CalcEngine object is a member of a form, you can add your additional function methods to the form and then register these methods with the CalcEngine object after the object has been created, in Form_Load for example.

The above steps have been explained in detail in the following topics:

### Step 1-Writing the Method

The method must have the signature specified by the delegate, Syncfusion.Calculate.CalcEngine.LibraryFunction. It accepts a string argument and returns a string value. So here is a minimal implementation. The sample found in \WPF\Calculate.Wpf \Samples\2.0\ DataGridCalculator has code that adds a custom function.
{% highlight c# %}




public string ComputeMymin(string args)

{    

// Computes someString using the values from args.

return someString;

}

{% endhighlight %}
{% highlight vbnet %}





Public Function ComputeMymin(args As String) As String



' Computes someString using the values from args.

Return someString



' ComputeMymin

End Function

{% endhighlight  %}

This is the only requirement on the method. You are free to use any kind of conventions with respect to passing arguments and within your implementation code. So, args may be a single entry like A1 or 153 or, it may be something more complex like A1:C15. It is up to your implementation code to parse args, use the information passed in, to compute the value and then return this value as a string. If you want your arguments to be standard items like cell references, numbers, other formulas, etc., CalcEngine exposes some parsing tools that you can use to minimize the amount of code you may need to write. But, you are not limited to what CalcEngine exposes, you are free to design and implement any argument conventions you want, as long as your method has the required signature.

Here add a method that accepts an argument list and then returns the minimum value in this list. The list may be individual cell references and cell ranges, or numbers. This sample code uses CalcEngine methods to handle the parsing and retrieving of values from the argument list.

N> List separators can vary depending upon culture. While it is reasonable to use a comma as a separator in en-US, this is not the case with fr-FR where the comma is used as a decimal separator. For this reason, CalcEngine.ParseArgumentSeparator is a static member that holds the list separator that is recognized by the parsing of algorithms in the CalcEngine.

In the following code, CalcEngine.ParseArgumentSeparator is used to split the args into a list. Additionally, the code makes use of two utility methods in the CalcEngine object, GetCellsFromArgs and GetValueFromArg. GetCellsFromArgs accepts a range like A3:C6 and returns a string array of the individual cell references in the range. GetValueFromArg accepts a cell reference, formula, or number and return the numerical value that the cell holds.
{% highlight c# %}




// This sample computes the minimum of an arbitrary range.

// Example:    = Mymin(A1:C3)

// Example:    = mymin(a1,c2,a4,b2,100)

public string ComputeMymin(string args)

{ 

       // Assumes that this.engine is the CalcEngine object.



        double min = double.MaxValue;

        double d;

        string s1;



        foreach(string r in args.Split(new char[]{CalcEngine.ParseArgumentSeparator}))

        {

                // Cell range

                if(r.IndexOf(':') > -1) 

                {

                        foreach(string s in engine.GetCellsFromArgs(r))

                        {   

                              // s is a cell line a21 or c3...

                                try

                                {

                                        s1 = engine.GetValueFromArg(s);

                                        if(s1 != ""

                                                && double.TryParse(s1, System.Globalization.NumberStyles.Number, 

                                                        null, out d))

                                        {

                                                min = Math.Min(min, d);

                                        }

                                }

                                catch(Exception ex)

                                {

                                        return ex.Message;

                                }

                        }

                }

                else

                {

                        try

                        {

                                s1 = engine.GetValueFromArg(r);

                                if(s1 != ""

                                        && double.TryParse(s1, System.Globalization.NumberStyles.Number, 

                                                        null, out d))

                                {

                                        min = Math.Min(min, d);

                                }

                        }

                        catch(Exception ex) 

                        {

                                return ex.Message;

                        }

                }

        }        

        if(min != double.MaxValue)

                return min.ToString();

        return "";

}

{% endhighlight %}
{% highlight vbnet %}





' This sample computes the minimum of an arbitrary range.

' Example:    = Mymin(A1:C3)

' Example:    = mymin(a1,c2,a4,b2,100)

Public Function ComputeMymin(ByVal args As String) As String



        ' Assumes that this.engine is the CalcEngine object.

        Dim min As Double = Double.MaxValue

        Dim d As Double

        Dim s1 As String



        Dim r As String

        For Each r In args.Split(New Char() {CalcEngine.ParseArgumentSeparator})



            ' Cell range

            If r.IndexOf(":"c) > -1 Then

                Dim s As String

                For Each s In engine.GetCellsFromArgs(r)



                    ' s is a cell line a21 or c3...

                    Try

                        s1 = engine.GetValueFromArg(s)

                        If s1 <> "" And Double.TryParse(s1, System.Globalization.NumberStyles.Number, Nothing, d) Then

                            min = Math.Min(min, d)

                        End If

                    Catch ex As Exception

                        Return ex.Message

                    End Try

                Next s

            Else

                Try

                    s1 = engine.GetValueFromArg(r)

                    If s1 <> "" And Double.TryParse(s1, System.Globalization.NumberStyles.Number, Nothing, d) Then

                        min = Math.Min(min, d)

                    End If

                Catch ex As Exception

                    Return ex.Message

                End Try

            End If

        Next r

        If min <> Double.MaxValue Then

            Return min.ToString()

        End If

        Return ""



        ' ComputeMymin

End Function

{% endhighlight %}

### Step 2-Registering the Method with the CalcEngine

The second step for adding your own formula is to register your method with the CalcEngine object. This is done with the AddFunction method. This method accepts the string that is used when you reference the function in a spreadsheet formula, and the second argument is a delegate for which you pass your method. The only requirement here is that the function name should start with an alpha character and should only contain alpha-numeric characters. Additionally, the string cannot be the name of any existing library function.

{% highlight c# %}





// Add formula name Mymin to the Library.

this.engine.AddFunction("Mymin", new LibraryFunction(ComputeMymin));
{% endhighlight %}

{% highlight vbnet %}




' Add formula name Mymin to the Library.

Me.engine.AddFunction("Mymin", AddressOf ComputeMymin)

{% endhighlight %}

By convention, within the Essential Calculate library, the C# implementation method for each of the library functions that are shipped with the word "Compute" is named and followed by the name of the library function. The above code confirms to this convention, with the function name being 'Mymin' and the method name being 'ComputeMymin'. Our library functions are public members of the CalcEngine class, so that you can access them directly if it serves your purpose. Additionally, if you own the source code version, you can see implementation details that may be of use to you if you try to implement many custom library methods on your own.

N> Once this is done, you can use your custom method in the same manner as the default library functions.

## Remove and Replace Function

This section discusses the Remove and Replace Function available for the CalcEngine.

### Remove Function

Removing unused functions from the Function Library, reduces the memory usage and speeds up parsing as well. Also, if you are only using a selected few Library functions, you may want to remove the unused ones. This can be done using the methods given below.

* To remove all functions, you can clear the hash table that holds them by using the engine.LibraryFunctions.Clear method.

{% highlight c# %}





// Remove all functions from the Library.

engine.LibraryFunctions.Clear();

{% endhighlight  %}
{% highlight vbnet %}





// Remove all functions from the Library.

engine.LibraryFunctions.Clear()

{% endhighlight %}

After clearing all functions, you can add few functions that are used often. To know how to add functions, see Add Function.

* To remove a single function from the Function Library, use the CalcEngine.RemoveFunction method, passing a "function name" as the string that references this function, from a formula.

{% highlight c# %}





// Remove formula name MyMin from the Library.

engine.RemoveFunction("MyMin");


{% endhighlight  %}
{% highlight vbnet %}




' Remove formula name MyMin from the Library.

engine.RemoveFunction("MyMin")

{% endhighlight %}

### Replace Function

To replace a function with another implementation, you must remove the original name, and add the same name again with a different delegate method.

## Functions 

Here is a list of the Function Library entries included with Essential Calculate which includes more than 150 entries. For detailed information on each function, see Function Reference Section.

### Logical

This section lists the logical functions included with Essential calculate in the below table.



<table>
<tr>
<th>
Function Name</th><th>
Description</th></tr>
<tr>
<td>
And</td><td>
Returns TRUE if all conditions are TRUE. It returns FALSE if any of the conditions are FALSE.</td></tr>
<tr>
<td>
If</td><td>
Returns one value if a specified condition evaluates to TRUE, or another value if it evaluates to FALSE.</td></tr>
<tr>
<td>
IF-THEN-ELSE </td><td>
Statement can only be used in VBA code. Assume there are two conditions that are evaluated. Once a condition is found to be true, the IF-THEN-ELSE statement executes the corresponding code and not evaluate the conditions any further.</td></tr>
<tr>
<td>
True</td><td>
Function returns a logical value of TRUE.</td></tr>
<tr>
<td>
Case(VBA only)</td><td>
It has the functionality of an IF-THEN-ELSE statement.</td></tr>
<tr>
<td>
Nested Ifs(Upto 7)</td><td>
It is possible to nest multiple IF functions within one Excel formula. You can nest up to 7 IF functions to create a complex IF THEN ELSE statement.</td></tr>
<tr>
<td>
Not</td><td>
This function returns the reversed logical value.</td></tr>
<tr>
<td>
False</td><td>
Returns a logical value of FALSE.</td></tr>
<tr>
<td>
NestedIfs (More than )</td><td>
Use this method to nest up to or more than 7 IF conditions.</td></tr>
<tr>
<td>
Or</td><td>
Returns TRUE if any of the conditions are TRUE. Otherwise, it returns FALSE.</td></tr>
</table>

### Text

This section lists the Text functions included with Essential calculate in the below table.



<table>
<tr>
<th>
Function Name</th><th>
Description</th></tr>
<tr>
<td>
Concatenate</td><td>
Joins arguments into a single string.</td></tr>
<tr>
<td>
Left</td><td>
Returns the first character or characters in a text string, based on the number of characters you specify.</td></tr>
<tr>
<td>
Right</td><td>
Returns the last character or characters in a text string, based on the number of characters you specify.</td></tr>
<tr>
<td>
Text</td><td>
Returns a formatted string.</td></tr>
<tr>
<td>
Value</td><td>
Returns a number from a string.</td></tr>
<tr>
<td>
Len</td><td>
Returns the length of a string.</td></tr>
<tr>
<td>
MID</td><td>
Returns a text segment of a character string.</td></tr>
</table>

## Date and Time

This section lists the Date and Time functions included with Essential calculate in the below table.



<table>
<tr>
<th>
Function Name</th><th>
Description</th></tr>
<tr>
<td>
Date</td><td>
Returns the sequential serial number that represents a particular date. </td></tr>
<tr>
<td>
Datevalue</td><td>
Returns the serial number of the date value.</td></tr>
<tr>
<td>
Day</td><td>
Returns the day of the month.</td></tr>
<tr>
<td>
Days360</td><td>
Returns the number of days between two dates using 360-day year.</td></tr>
<tr>
<td>
Hour</td><td>
Returns the hour from 0 to 23.</td></tr>
<tr>
<td>
Minute</td><td>
Returns the minute from 0 to 59.</td></tr>
<tr>
<td>
Month</td><td>
Returns the month from 1 to 12.</td></tr>
<tr>
<td>
Now</td><td>
Returns the current date and time.</td></tr>
<tr>
<td>
Second</td><td>
Returns the second from 0 to 59.</td></tr>
<tr>
<td>
Time</td><td>
Returns serial number time.</td></tr>
<tr>
<td>
Timevalue</td><td>
Returns the serial number time from a string.</td></tr>
<tr>
<td>
Today</td><td>
Returns the current date.</td></tr>
<tr>
<td>
Weekday</td><td>
Returns the weekday from 1 to 7.</td></tr>
<tr>
<td>
Year</td><td>
Returns the year from 1900 to 9999.</td></tr>
</table>

### LookUps and Information

This section lists the LookUp and Information functions included with Essential calculate in the below table.



<table>
<tr>
<th>
Function Name</th><th>
Description</th></tr>
<tr>
<td>
HLookUp</td><td>
Finds a value in one row and returns the corresponding value in another row.</td></tr>
<tr>
<td>
VLookUp</td><td>
Finds a value in one column and returns the corresponding value in another column.</td></tr>
<tr>
<td>
IsError</td><td>
Returns True if cell holds an error.</td></tr>
<tr>
<td>
IsNumber</td><td>
Returns True if cell holds a number.</td></tr>
</table>

## Financial

This section lists the Financial functions included with Essential calculate in the below table.



<table>
<tr>
<th>
Function Name</th><th>
Description</th></tr>
<tr>
<td>
Db</td><td>
Returns the depreciation using fixed declining balance calculation.</td></tr>
<tr>
<td>
Ddb</td><td>
Returns the depreciation using double declining balance calculation.</td></tr>
<tr>
<td>
Fv</td><td>
Returns future value of an investment.</td></tr>
<tr>
<td>
Ipmt</td><td>
Returns interest payment.</td></tr>
<tr>
<td>
Irr</td><td>
Returns internal rate of return.</td></tr>
<tr>
<td>
Ispmt</td><td>
Returns interest payment.</td></tr>
<tr>
<td>
Mirr</td><td>
Returns internal rate of return.</td></tr>
<tr>
<td>
Nper</td><td>
Returns number of payment periods.</td></tr>
<tr>
<td>
Npv</td><td>
Returns net present value.</td></tr>
<tr>
<td>
Pmt</td><td>
Returns loan payment.</td></tr>
<tr>
<td>
Ppmt</td><td>
Returns principal payment.</td></tr>
<tr>
<td>
Pv</td><td>
Returns present value.</td></tr>
<tr>
<td>
Rate</td><td>
Returns interest rate per period.</td></tr>
<tr>
<td>
Sln</td><td>
Returns straight-line depreciation.</td></tr>
<tr>
<td>
Syd</td><td>
Returns sum-of-years depreciation.</td></tr>
<tr>
<td>
Vdb</td><td>
Returns the depreciation using double declining balance calculation.</td></tr>
</table>

## Math and Trig functions

This section lists the Math and Trig functions included with Essential calculate in the below table.



<table>
<tr>
<th>
Function Name</th><th>
Description</th></tr>
<tr>
<td>
Abs</td><td>
Returns the absolute value of a value.</td></tr>
<tr>
<td>
Acos</td><td>
Returns the inverse cosine.</td></tr>
<tr>
<td>
Acosh</td><td>
Returns the inverse hyperbolic cosine.</td></tr>
<tr>
<td>
Asin</td><td>
Returns the inverse sine.</td></tr>
<tr>
<td>
Asinh</td><td>
Returns the inverse hyperbolic sine.</td></tr>
<tr>
<td>
Atan</td><td>
Returns the inverse tangent.</td></tr>
<tr>
<td>
Atan2</td><td>
Returns the inverse tangent.</td></tr>
<tr>
<td>
Atanh</td><td>
Returns the inverse hyperbolic tangent.</td></tr>
<tr>
<td>
Avg</td><td>
Returns the arithmetic mean of the listed arguments.</td></tr>
<tr>
<td>
Ceiling</td><td>
Returns the rounded up value.</td></tr>
<tr>
<td>
Combin</td><td>
Returns the number of combinations.</td></tr>
<tr>
<td>
Cos</td><td>
Returns the cosine.</td></tr>
<tr>
<td>
Cosh</td><td>
Returns the hyperbolic cosine.</td></tr>
<tr>
<td>
Degrees</td><td>
Returns the degrees represented by the given radians.</td></tr>
<tr>
<td>
Even</td><td>
Returns the number rounded up to the nearest event integer.</td></tr>
<tr>
<td>
Exp</td><td>
Returns the value of e raised to the given argument.</td></tr>
<tr>
<td>
Fact</td><td>
Returns the factorial of the given value.</td></tr>
<tr>
<td>
Floor</td><td>
Returns the value rounded down to the nearest value.</td></tr>
<tr>
<td>
Int</td><td>
Returns the value rounded down to nearest integer.</td></tr>
<tr>
<td>
Ln</td><td>
Returns the natural logarithm of the value.</td></tr>
<tr>
<td>
Log</td><td>
Returns the logarithm to a given base.</td></tr>
<tr>
<td>
Log10</td><td>
Returns the logarithm base 10.</td></tr>
<tr>
<td>
Mod</td><td>
Returns the remainder after a division.</td></tr>
<tr>
<td>
Odd</td><td>
Returns the value to the nearest odd integer.</td></tr>
<tr>
<td>
Pi</td><td>
Returns the pi.</td></tr>
<tr>
<td>
Pow</td><td>
Returns the value of one number raised to another number.</td></tr>
<tr>
<td>
Product</td><td>
Returns the product of the listed values.</td></tr>
<tr>
<td>
Radians</td><td>
Returns the radians from given degrees.</td></tr>
<tr>
<td>
Rand</td><td>
Returns a random value.</td></tr>
<tr>
<td>
Round</td><td>
Returns the number to a specified number of digits.</td></tr>
<tr>
<td>
Rounddown</td><td>
Returns the number rounded down.</td></tr>
<tr>
<td>
Roundup</td><td>
Returns the number rounded up.</td></tr>
<tr>
<td>
Sign</td><td>
Returns the sign of the number.</td></tr>
<tr>
<td>
Sine</td><td>
Returns the sine.</td></tr>
<tr>
<td>
Sinh</td><td>
Returns the hyperbolic sine.</td></tr>
<tr>
<td>
Sqrt</td><td>
Returns the square root of a number.</td></tr>
<tr>
<td>
Sum</td><td>
Returns the sum of the listed values.</td></tr>
<tr>
<td>
Sumif</td><td>
Returns the conditional sum of the listed values.</td></tr>
<tr>
<td>
SumProduct</td><td>
Returns the sum of the products.</td></tr>
<tr>
<td>
Sumsq</td><td>
Returns the sum of the squares.</td></tr>
<tr>
<td>
Sumx2my2</td><td>
Returns the differences of the squares.</td></tr>
<tr>
<td>
Sumx2py2</td><td>
Returns the sum of the squares.</td></tr>
<tr>
<td>
Sumxmy2</td><td>
Returns the squares of the differences.</td></tr>
<tr>
<td>
Tan</td><td>
Returns the tangent.</td></tr>
<tr>
<td>
Tanh</td><td>
Returns the hyperbolic tangent.</td></tr>
<tr>
<td>
Trunc</td><td>
Returns the number without a fractional part.</td></tr>
</table>

### Multinomial

The MULTINOMIAL function returns the ratio of the factorial of a sum of values to the product of factorials.

#### Syntax

The syntax of the MULTINOMIAL function is

=MULTINOMIAL(number1, (number2), …)

&#35;NUM!	-	Occurs if any of the supplied arguments are less than 0.

&#35;VALUE! -	Occurs if any of the supplied arguments are non-numeric.

Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=MULTINOMIAL(2, 3, 4)</td><td>
1260</td></tr>
</table>

### ISEVEN

The ISEVEN function returns TRUE if given number is an even number, and returns FALSE if the given number is odd.

#### Syntax:

The syntax of the ISEVEN function is

=ISEVEN (value)

The given value must be a numeric value. If it is non-integer value, the value is rounded down.

N> If the given value is nonnumeric, the ISEVEN function returns the ‘&#35;VALUE!’ error value.



#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=ISEVEN(-1) </td><td>
FALSE</td></tr>
<tr>
<td>
=ISEVEN(2.5) </td><td>
TRUE</td></tr>
<tr>
<td>
=ISEVEN(5) </td><td>
FALSE</td></tr>
</table>

### ISODD

The ISODD function returns TRUE if the given number is an odd number, and returns FALSE if the given number is even.

#### Syntax: 

The syntax of the ISODD function is

=ISODD (value)

The given value must be a numeric value. If it is a non-integer value, the value is rounded down.

N> If the given value is nonnumeric, ISODD function returns the ‘&#35;VALUE!’ error value.



#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=ISODD(-1) </td><td>
TRUE</td></tr>
<tr>
<td>
=ISODD(2.5) </td><td>
FALSE</td></tr>
<tr>
<td>
=ISODD(5) </td><td>
TRUE</td></tr>
</table>

### N

The N function converts the given value into a numeric value.

#### Syntax: 

The syntax of the N function is

=N (value)

A value is required.

Numeric values are converted as numeric values. A date value is converted as a serial number. The Logic operator TRUE returns a value of 1. The other values are returned as 0.

#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=N(7) </td><td>
7</td></tr>
<tr>
<td>
=N(“EVEN”) </td><td>
0</td></tr>
<tr>
<td>
=N(1/1/2008)</td><td>
39448</td></tr>
<tr>
<td>
=N(TRUE)</td><td>
1</td></tr>
</table>

### NA

The NA function returns the #N/A error. This error message is produced when a formula is unable to find a value that it needs. This error message denotes 'value not available.'

#### Syntax: 

The syntax of NA function is

=NA()

The NA function syntax has no arguments.

N> The function doesn’t have any arguments.

#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=NA() </td><td>
#NA</td></tr>
</table>

### ERROR.TYPE

The Error.Type function returns an integer for the given error value that denotes the type of the given error.

#### Syntax:

The syntax of the ERROR.TYPE function is

= ERROR.TYPE(value)

The given value is required.

Here is the return value of function:

<table>
<tr>
<th>
Given Value</th><th>
Return value of function</th></tr>
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
&#35;VALUE!</td><td>
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
&#35;NUM!</td><td>
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


#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
= ERROR.TYPE(#NULL!) </td><td>
1</td></tr>
<tr>
<td>
= ERROR.TYPE(even)</td><td>
#NA</td></tr>
</table>

### SUBTOTAL

The SUBTOTAL function returns a subtotal in a list. Once the subtotal list is created, you can modify it by editing the SUBTOTAL function.

#### Syntax:

The syntax of the SUBTOTAL function is

=SUBTOTAL (function_Number, ref1, (ref2),...)

A function_Number is required. This specifies which function to use in calculating subtotals within a list. Here is the list of functions supported by Syncfusion:

<table>
<tr>
<th>
FUNCTION NUMBER</th><th>
FUNCTION NAME</th></tr>
<tr>
<td>
1</td><td>
AVERAGE</td></tr>
<tr>
<td>
2</td><td>
COUNT</td></tr>
<tr>
<td>
3</td><td>
COUNTA</td></tr>
<tr>
<td>
4</td><td>
MAX</td></tr>
<tr>
<td>
5</td><td>
MIN</td></tr>
<tr>
<td>
6</td><td>
PRODUCT</td></tr>
<tr>
<td>
7</td><td>
STDEV</td></tr>
<tr>
<td>
8</td><td>
STDEVP</td></tr>
<tr>
<td>
9</td><td>
SUM</td></tr>
<tr>
<td>
10</td><td>
VAR</td></tr>
</table>


Ref1 The first named range which is used for the subtotal. This value is required.

Ref2 This value is optional.

N> If the subtotal function has any nested subtotal functions, then the nested subtotal is ignored for double counting.



### MROUND

The MROUND function rounds a given number up or down to the nearest multiple of a given number.

#### Syntax

The syntax of the MROUND function is

= MROUND (number, multiple)

Number – The value to be rounded. This value is required.

Multiple – This value is required. 

The number must be is greater than or equal to half the value of multiple.

&#35;NUM! -	Occurs if the number and multiple have different signs.

&#35;VALUE! -	Occurs if any of the given arguments are non-numeric.



#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=MROUND(10,2.6)</td><td>
8</td></tr>
<tr>
<td>
=MROUND(-10,-2.6)</td><td>
-8</td></tr>
<tr>
<td>
=MROUND(10,-2)</td><td>
&#35;NUM!</td></tr>
</table>

### RANDBETWEEN

The RANDBETWEEN function returns a random number that is between the given ranges. This function returns a new random number each time in recalculation.

#### Syntax

The syntax of the RANDBETWEEN Function is

=RANDBETWEEN (start_num, end_num)

start_num – Required. This is the smallest integer.

end_num – Required. This is the largest integer.



&#35;NUM! -	Occurs if the end_num value is larger than start_num value.

&#35;VALUE! -	Occurs if any of the given arguments are non-numeric.

#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
= RANDBETWEEN (10,20)</td><td>
12. The value is generated randomly between the given values.</td></tr>
</table>

### SQRTPI

The SQRTPI function returns the square root of a given number multiplied by π. Here π is the constant math value.

#### Syntax

The syntax of the SQRTPI function is

=SQRTPI (number)

number – Required. 



&#35;NUM! -	If the number is less than zero (0).

&#35;VALUE! -	Occurs if any of the given arguments are non-numeric.

#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
= SQRTPI (2)</td><td>
2.506628</td></tr>
<tr>
<td>
= SQRTPI (-2)</td><td>
&#35;NUM!</td></tr>
</table>

### QUOTIENT

The QUOTIENT function returns the integer portion of a division between two given numbers. The returned value can be a integer value.

#### Syntax

The syntax of the QUOTIENT function is

=QUOTIENT (numerator, denominator)

Numerator – Required.

Denominator – Required.

#### Remarks:

&#35;VALUE! -	 Occurs if any of the given arguments are non-numeric.

#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
= QUOTIENT (10,3)</td><td>
3</td></tr>
<tr>
<td>
= QUOTIENT (-20,6)</td><td>
-3</td></tr>
</table>

### FACTDOUBLE

The FACTDOUBLE function returns the double factorial of a given value. The given value must be an integer value.

#### Syntax

The syntax of the FACTDOUBLE function is

= FACTDOUBLE (number).

number – Required.



&#35;NUM! -	If the number is less than zero (0).

&#35;VALUE! -	Occurs if any of the given arguments are non-numeric

#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
= FACTDOUBLE (6)</td><td>
48</td></tr>
<tr>
<td>
= FACTDOUBLE (-2)</td><td>
&#35;NUM!</td></tr>
</table>

### GCD

The GCD function returns the greatest common divisor of two or more given values. The values must be a numeric value.

#### Syntax

The syntax of the GCD function is

= GCD (number1, number2, ...)

Number1 – Required. 

If any value is not an integer, then it is rounded down.



&#35;NUM!	 -	 If the number is less than zero (0).

&#35;VALUE! -	 Occurs if any of the given arguments are non-numeric.

#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
= GCD (5,3,2)</td><td>
1</td></tr>
<tr>
<td>
= GCD (-2)</td><td>
&#35;NUM!</td></tr>
</table>

### LCM

The LCM function returns the least common multiple of two or more given values. The values must be numeric values.

#### Syntax

The syntax of the LCM function is

= LCM (number1, number2, ...)

number1 – Required. 

If any value is not an integer, then it is rounded down.



&#35;NUM!	 -	 If the number is less than zero (0).

&#35;VALUE! -	 Occurs if any of the given arguments are non-numeric.

#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
= LCM (5,2)</td><td>
10</td></tr>
<tr>
<td>
= LCM (-2)</td><td>
&#35;NUM!</td></tr>
</table>

### ROMAN

The ROMAN function converts an Arabic number to a Roman numeral. This function returns a text string depicting the Roman numeral form of the given number.

#### Syntax

The syntax of the ROMAN function is

=ROMAN( number, (form) )

number – Required.

Form – Optional, this value specifies the style of the Roman numeral.

If number is not an integer, then it is rounded down.

<table>
<tr>
<th>
Form</th><th>
Type</th></tr>
<tr>
<td>
0 or omitted</td><td>
Classic.</td></tr>
<tr>
<td>
1</td><td>
More concise. See example below.</td></tr>
<tr>
<td>
2</td><td>
More concise. See example below.</td></tr>
<tr>
<td>
3</td><td>
More concise. See example below.</td></tr>
<tr>
<td>
4</td><td>
Simplified.</td></tr>
</table>
&#35;VALUE! -	Occurs if any of the given values is non-numeric, or for values less than 0 and greater than 3999.

#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
= ROMAN (499,0)</td><td>
CDXCIX</td></tr>
<tr>
<td>
= ROMAN (499,1)</td><td>
ID</td></tr>
<tr>
<td>
=ROMAN(-100)</td><td>
&#35;VALUE!</td></tr>
</table>

### IFERROR

The IFERROR function tests if an initial given value (or expression) returns an error, and if so, this function returns a second given argument. Otherwise, the function returns the initial tested value.

#### Syntax

The syntax of the IFERROR function is

= IFERROR (value, value_error)

value – Required. This is a value to check the error.

value_error – Required. This value is returned if the value has an error.

If the value_error is an empty cell, then the function takes the error value as empty string.

#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
= IFERROR (200/55, “ERROR in DIVISION”)</td><td>
3</td></tr>
<tr>
<td>
= IFERROR (200/0, “ERROR in DIVISION”)</td><td>
ERROR in DIVISION</td></tr>
</table>

### T

The T function tests whether the given value is text or not. If the given value is text, then it returns the given text. Otherwise, the function returns an empty text string.



#### Syntax

The syntax of the T function is

=T( value )

value – Required. This is a value to be checked.

If the value is not a number or logical value, then the function returns an empty string.

#### Example:

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=T('SYNCFUSION')</td><td>
SYNCFUSION</td></tr>
<tr>
<td>
=T(TRUE)</td><td>
</td></tr>
<tr>
<td>
=T(10)</td><td>
</td></tr>
</table>

### XOR

The XOR function returns the exclusive OR for the given arguments.

#### Syntax 

XOR (logical_value1, logical_value2,…)

Logical_value1: Required. This can be either TRUE or FALSE, and can be logical values, arrays, or references.

N> If the given arguments do not have the logical values, XOR returns the &#35;VALUE! error value.



#### Example

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
= XOR( 5>0, 7<9 )</td><td>
FALSE</td></tr>
<tr>
<td>
=XOR(3>12, 4>6)</td><td>
TRUE</td></tr>
</table>

### IFNA 

The IFNA function returns the value specified if the formula returns the #N/A error value; otherwise, it returns the result of the given formula.

#### Syntax

=IFNA (Formula_value, value_if_na)

Formula_value: Required. The argument that is checked for the #N/A error value.

value_if_na: Required. The value returned if the formula evaluates to the #N/A error value.

#### Example 

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=IFNA(“#N/A”,”Incorrect”)</td><td>
Incorrect</td></tr>
<tr>
<td>
=IFNA(1602,”incorrect”)</td><td>
1602</td></tr>
</table>

### CLEAN

The CLEAN function is used to remove the non-printable characters from the given text, represented by numbers 0 to 31 of the 7-bit ASCII code.

#### Syntax

=Clean(Text)

Text: Required. String or text from which to remove nonprintable characters.

#### Example  

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=Clean(Syncfusion)</td><td>
Syncfusion</td></tr>
<tr>
<td>
= Clean("Text*")</td><td>
Text</td></tr>
</table>

### ISREF

The ISREF function returns the logical value TRUE if the given value is a reference value; otherwise, the function returns FALSE.

#### Syntax

=ISREF(given_value)

given value:Required. The value that is to be tested. The value argument can be a blank (empty cell), error, logical value, text, number, or reference value, or a name referring to any of these.

#### Example

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=ISREF("Region1")   </td><td>
FALSE</td></tr>
<tr>
<td>
=ISREF(=ISLOGICAL(TRUE))</td><td>
TRUE</td></tr>
</table>

### AVERAGEIF

The AVERAGEIF function finds the average of values in a given array that satisfy a given criteria, and returns the average value of the corresponding values in a second given array.

#### Syntax 

=AVERAGEIF(range, criteria, average_range)

range: Array of values to be tested against the given criteria.

criteria: The condition to be tested in each of the values of the given range.

average_range: Numeric values to be evaluated against the criteria and averaged.

N> * If range is blank or a text value, AVERAGEIF returns the #DIV/0! error value. * If a cell in criteria is empty, AVERAGEIF treats it as a 0 value. * If no cells in the range meet the criteria, AVERAGEIF returns the #DIV/0! error value.



#### Example

Input Table

<table>
<tr>
<td>
</td><th>
A</th><th>
B</th></tr>
<tr>
<td>
1</td><td>
Earning</td><td>
Tax</td></tr>
<tr>
<td>
2</td><td>
100000</td><td>
3000</td></tr>
<tr>
<td>
3</td><td>
200000</td><td>
6000</td></tr>
<tr>
<td>
4</td><td>
300000</td><td>
7500</td></tr>
<tr>
<td>
5</td><td>
400000</td><td>
9000</td></tr>
</table>


<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=AVERAGEIF(B2:B5,"<7000")</td><td>
4500</td></tr>
<tr>
<td>
=AVERAGEIF(A2:A5,">250000")</td><td>
350000</td></tr>
</table>

### AVERAGEIFS

The AVERAGEIFS function finds the average of values in a given array that satisfy a set of given criteria.

#### Syntax

= AVERAGEIFS( average_range, criteria_range1, criteria1, [criteria_range2, criteria2], ... )

average_range: Specific set of values to be averaged if the criteria range meets the provided criteria.

criteria_range1: Array of values to be tested against the given criteria.

criteria1: The condition to be tested on each of the values of the given range.

N> * If average_range is blank or a text value, AVERAGEIFS returns the #DIV/0! error value. * If a cell in a criteria range is empty, AVERAGEIFS treats it as a 0 value. * If cells in average_range cannot be translated into numbers, AVERAGEIFS returns the #DIV/0! error value.



#### Example

Input Table

<table>
<tr>
<td>
</td><th>
A</th><th>
B</th><th>
C</th></tr>
<tr>
<td>
1</td><td>
Earning</td><td>
Tax</td><td>
other</td></tr>
<tr>
<td>
2</td><td>
100000</td><td>
3000</td><td>
100</td></tr>
<tr>
<td>
3</td><td>
200000</td><td>
6000</td><td>
200</td></tr>
<tr>
<td>
4</td><td>
300000</td><td>
7500</td><td>
300</td></tr>
<tr>
<td>
5</td><td>
400000</td><td>
9000</td><td>
500</td></tr>
</table>


<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
AVERAGEIFS(C2:C5, B2:B5, ">7000", B2:B5, "<10000")</td><td>
400</td></tr>
</table>

### NETWORKDAYS

The NETWORKDAYS function is used to calculate the number of whole work days between two given dates. This includes all weekdays from Monday to Friday, but excludes a supplied list of holidays.

#### Syntax

= NETWORKDAYS( start_date, end_date, [holidays] )

start_date: The start of the period to find the working days

end_date: The end of the period to find the working days.

holidays:  An optional argument, which specifies an array of dates that are not to be counted as working days.

N> If any argument is not a valid date, NETWORKDAYS returns the &#35;VALUE! error value.



Example  

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=NETWORKDAYS(DATE(2012,10,1),DATE(2013,3,1))</td><td>
110</td></tr>
</table>

### SUMIFS

The SUMIFS function sums the values in a given array that satisfy a set of given criteria.

#### Syntax:

=SUMIFS(sum_range, criteria_range1, criteria1, [criteria_range2, criteria2], …)

criteria_range1: Array of values to be tested against the given criteria.

criteria1: The condition to be tested on each of the values of given range.

sum_range: The range of values to be summed if the associated criteria range meets the specified criteria. 

N> Cells in the sum_range argument that contain TRUE evaluate to 1; cells in sum_range that contain FALSE evaluate to 0 (zero).



#### Example

Input Table

<table>
<tr>
<td>
</td><th>
A</th><th>
B</th><th>
C</th></tr>
<tr>
<td>
1</td><td>
Earning</td><td>
Tax</td><td>
other</td></tr>
<tr>
<td>
2</td><td>
100000</td><td>
3000</td><td>
100</td></tr>
<tr>
<td>
3</td><td>
200000</td><td>
6000</td><td>
200</td></tr>
<tr>
<td>
4</td><td>
300000</td><td>
7500</td><td>
300</td></tr>
<tr>
<td>
5</td><td>
400000</td><td>
9000</td><td>
500</td></tr>
</table>


<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
SUMIFS(C2:C5, B2:B5, ">7000", B2:B5, "<10000")</td><td>
800</td></tr>
</table>

### ADDRESS

The ADDRESS function returns the address of a cell in a worksheet given specified row and column numbers.

#### Syntax 

ADDRESS(row_num, column_num, [abs_num], [a1], [sheet_text])

row_num:A numeric value that specifies the row number.

column_num:A numeric value that specifies the column number

abs_num: Optional. A numeric value that specifies the type of reference to return.

A1: A logical value that specifies the A1 or R1C1 reference style.

#### Example

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=ADDRESS(2,3,2,FALSE)</td><td>
R2C[3].</td></tr>
<tr>
<td>
=ADDRESS(2,3,1,FALSE,"[Book1]Sync1")</td><td>
[Book1] Sync1!R2C3</td></tr>
</table>

### LOOKUP

The LOOKUP function returns a value either from a one-row or one-column range, or from an array. The LOOKUP function has two syntax forms: vector and array. 

Vector Form: The vector form of LOOKUP looks in a one-row or one-column range for a value, and then returns a value from the same position in a second one-row or one-column range. 

#### Syntax

=LOOKUP(lookup_value, lookup_vector, result_vector)

Array form: The array form of LOOKUP looks in the first row or column of an array for the specified value, and then returns a value from the same position in the last row or column of the array.

#### Syntax

=LOOKUP(lookup_value, array)

N> * If the LOOKUP function can't find the lookup_value, the function matches the largest value in lookup_vector that is less than or equal to lookup_value. * If lookup_value is smaller than the smallest value in lookup_vector, LOOKUP returns the #N/A error value.

#### Example

Input Table

<table>
<tr>
<th>
</th><th>
A</th><th>
B</th><th>
C</th></tr>
<tr>
<td>
1</td><td>
Earning</td><td>
Tax</td><td>
other</td></tr>
<tr>
<td>
2</td><td>
100000</td><td>
3000</td><td>
100</td></tr>
<tr>
<td>
3</td><td>
200000</td><td>
6000</td><td>
200</td></tr>
<tr>
<td>
4</td><td>
300000</td><td>
7500</td><td>
300</td></tr>
<tr>
<td>
5</td><td>
400000</td><td>
9000</td><td>
500</td></tr>
</table>


<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=LOOKUP(6000,B2:B5,C2:C5)</td><td>
200</td></tr>
<tr>
<td>
=LOOKUP("C", {"a","b","c","d";1,2,3,4})  </td><td>
3</td></tr>
</table>

### SEARCH

The SEARCH function returns the location of a substring in a string. This function is NOT case-sensitive.

#### Syntax 

SEARCH(substring, string, [start_position] )

substring: Required. The text to be found.

string:Required. The text in which to search for the value of the substring.

start_num: Optional. The starting position for searching in the string.

N> * If the value of find_text is not found, the &#35;VALUE! error value is returned. * If the start_num argument is omitted, it is assumed to be 1. * If start_num is not greater than 0, or is greater than the length of the string argument, the &#35;VALUE! error value is returned.



#### Example 

<table>
<tr>
<th>
FORMULA</th><th>
RESULT</th></tr>
<tr>
<td>
=SEARCH("base","database")  </td><td>
5</td></tr>
</table>

## Statistics

This section lists the Statistic functions included with Essential calculate in the below table.



<table>
<tr>
<th>
Function Name</th><th>
Description</th></tr>
<tr>
<td>
Avedev</td><td>
Returns average deviation.</td></tr>
<tr>
<td>
Average</td><td>
Returns the arithmetic mean.</td></tr>
<tr>
<td>
Averagea</td><td>
Returns the arithmetic mean.</td></tr>
<tr>
<td>
Binomdist</td><td>
Returns the cumulative beta probability density function.</td></tr>
<tr>
<td>
Chidist</td><td>
Returns the chi-squared distribution.</td></tr>
<tr>
<td>
Chiinv</td><td>
Returns the inverse of Chidist.</td></tr>
<tr>
<td>
Chitest</td><td>
Returns the chi-squared distribution test for independence.</td></tr>
<tr>
<td>
Confidence</td><td>
Returns the confidence interval.</td></tr>
<tr>
<td>
Correl</td><td>
Returns the correlation between two sets of data.</td></tr>
<tr>
<td>
Count</td><td>
Returns the count of the data listed in the arguments.</td></tr>
<tr>
<td>
Counta</td><td>
Returns the count of the data listed in the arguments.</td></tr>
<tr>
<td>
Countblank</td><td>
Returns the count of the empty cells listed in the arguments.</td></tr>
<tr>
<td>
Countif</td><td>
Returns the count of values that meet a specified criteria.</td></tr>
<tr>
<td>
Covar</td><td>
Returns covariance.</td></tr>
<tr>
<td>
CritBinom</td><td>
Returns the critical value for the cumulative binomial distribution.</td></tr>
<tr>
<td>
Devsq</td><td>
Returns the sum of the squares of the mean deviation.</td></tr>
<tr>
<td>
Expondist</td><td>
Returns the exponential distribution.</td></tr>
<tr>
<td>
Fdist</td><td>
Returns the F probability distribution.</td></tr>
<tr>
<td>
Finv</td><td>
Returns the inverse of Fdist.</td></tr>
<tr>
<td>
Fisher</td><td>
Returns the Fisher transformation.</td></tr>
<tr>
<td>
Fisherinv</td><td>
Returns the inverse of Fisher.</td></tr>
<tr>
<td>
Forecast</td><td>
Returns the value forecasted by the linear trend.</td></tr>
<tr>
<td>
Gammadist</td><td>
Returns the gamma distribution.</td></tr>
<tr>
<td>
Gammainv</td><td>
Returns the inverse of Gammadist.</td></tr>
<tr>
<td>
Gammaln</td><td>
Returns the natural logarithm of gamma function.</td></tr>
<tr>
<td>
Geomean</td><td>
Returns the geometric mean.</td></tr>
<tr>
<td>
Harmean</td><td>
Returns the harmonic mean.</td></tr>
<tr>
<td>
Hypgeomdist</td><td>
Returns the hypergeometric distribution.</td></tr>
<tr>
<td>
Intercept</td><td>
Returns the Y intercept of the least squares fit line.</td></tr>
<tr>
<td>
Kurt</td><td>
Returns the kurtosis of the set of arguments.</td></tr>
<tr>
<td>
Large</td><td>
Returns the kth largest value.</td></tr>
<tr>
<td>
Loginv</td><td>
Returns the inverse of the Lognormdist.</td></tr>
<tr>
<td>
Lognormdist</td><td>
Returns the cumulative lognormal distribution function.</td></tr>
<tr>
<td>
Max</td><td>
Returns the largest value among the arguments.</td></tr>
<tr>
<td>
Maxa</td><td>
Returns the largest value among the arguments.</td></tr>
<tr>
<td>
Median</td><td>
Returns the median value among the arguments.</td></tr>
<tr>
<td>
Min</td><td>
Returns the smallest value among the arguments.</td></tr>
<tr>
<td>
Mina</td><td>
Returns the smallest value among the arguments.</td></tr>
<tr>
<td>
Mode</td><td>
Returns the most frequently occurring value.</td></tr>
<tr>
<td>
Negbinomdist</td><td>
Returns the negative binomial distribution.</td></tr>
<tr>
<td>
Normdist</td><td>
Returns the normal cumulative distribution.</td></tr>
<tr>
<td>
Norminv</td><td>
Returns the inverse of Normdist.</td></tr>
<tr>
<td>
Pearson</td><td>
Returns the Pearson product.</td></tr>
<tr>
<td>
Percentile</td><td>
Returns the kth percentile of the given values.</td></tr>
<tr>
<td>
Percentrank</td><td>
Returns the position of a value in the range of values.</td></tr>
<tr>
<td>
Permut</td><td>
Returns the number of permutations.</td></tr>
<tr>
<td>
Poisson</td><td>
Returns the Poisson distribution.</td></tr>
<tr>
<td>
Prob</td><td>
Returns a probability.</td></tr>
<tr>
<td>
Quartile</td><td>
Returns which quarter a value belongs to within an ordered set of data.</td></tr>
<tr>
<td>
Rank</td><td>
Returns the position of a value in an ordered list.</td></tr>
<tr>
<td>
Rsq</td><td>
Returns the square of the Pearson product moment correlation coefficients.</td></tr>
<tr>
<td>
Skew</td><td>
Returns the skewness of a distribution.</td></tr>
<tr>
<td>
Slope</td><td>
Returns the slope of the linear regression line.</td></tr>
<tr>
<td>
Small</td><td>
Returns the kth smallest value.</td></tr>
<tr>
<td>
Standardize</td><td>
Returns the normalized value.</td></tr>
<tr>
<td>
Stdev</td><td>
Returns the sample standard deviation.</td></tr>
<tr>
<td>
Stdeva</td><td>
Returns the sample standard deviation.</td></tr>
<tr>
<td>
Stdevp</td><td>
Returns the population standard deviation.</td></tr>
<tr>
<td>
Stdevpa</td><td>
Returns the population standard deviation.</td></tr>
<tr>
<td>
Steyx</td><td>
Returns the standard error.</td></tr>
<tr>
<td>
Trimmean</td><td>
Returns the mean after removing out-liers.</td></tr>
<tr>
<td>
Var</td><td>
Returns the sample variance.</td></tr>
<tr>
<td>
Vara</td><td>
Returns the sample variance.</td></tr>
<tr>
<td>
Varp</td><td>
Returns the population variance.</td></tr>
<tr>
<td>
Varpa</td><td>
Returns the population variance.</td></tr>
<tr>
<td>
Weibull</td><td>
Returns the Weibull distribution.</td></tr>
<tr>
<td>
Ztest</td><td>
Returns the P-value of a z-test.</td></tr>
</table>


