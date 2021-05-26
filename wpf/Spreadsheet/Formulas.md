---
layout: post
title: Formulas in WPF Spreadsheet control | Syncfusion
description: Learn here all about Formulas support in Syncfusion WPF Spreadsheet (SfSpreadsheet) control and more.
platform: wpf
control: SfSpreadsheet
 documentation: ug
---

# Formulas in WPF Spreadsheet (SfSpreadsheet)

SfSpreadsheet calculation engine offers automated calculation over a formula, expression, or cross sheet references. SfSpreadsheet calculation engine is preloaded with 409 formulas covering a broad range of business functions.

## Adding Formula into cell

To add formulas into a cell programmatically, use [SetCellValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html#Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetGrid_SetCellValue_Syncfusion_XlsIO_IRange_System_String_) method of [SpreadsheetGrid](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html) should be invoked and then invalidate that cell to update the view.

{% tabs %}
{% highlight c# %}
var range = spreadsheet.ActiveSheet.Range["A2"];
spreadsheet.ActiveGrid.SetCellValue(range, "=SUM(B1:B2)");
spreadsheet.ActiveGrid.InvalidateCell(2,1);
{% endhighlight %}
{% endtabs %}

## Named Ranges

Named Ranges are the defined names that represents a cell, range of cells, formula, or constant value or table. Each name have a scope of either to a specific worksheet or to the entire workbook.

### Define named ranges at runtime

SfSpreadsheet allows the user to define/add the named ranges at runtime by using [AddNamedRange](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_AddNamedRange_System_String_System_String_System_String_) method.

{% tabs %}
{% highlight c# %}
spreadsheet.AddNamedRange("SampleName", "A3:B3", "Sheet1");
{% endhighlight %}
{% endtabs %}

### Edit or remove named ranges at runtime

SfSpreadsheet allows the user to edit the named ranges at runtime by [EditNamedRange](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_EditNamedRange_System_String_System_String_Syncfusion_XlsIO_IName_) method and remove the named ranges at runtime by [DeleteNamedRange](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_DeleteNamedRange_Syncfusion_XlsIO_IName_) method

{% tabs %}
{% highlight c# %}
//To Edit the named ranges,
IName name = spreadsheet.Workbook.Names["Sample"];
spreadsheet.EditNamedRange("Test", "A3:B3", name);

//To remove the named ranges,
IName name = spreadsheet.Workbook.Names["Sample"];
spreadsheet.DeleteNamedRange(name);
{% endhighlight %}
{% endtabs %}

## Supported functions

Following is a list of functions that are supported by SfSpreadsheet

### Database Functions

<table>
<tr>
<th>
Name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
DCOUNT<br/><br/></td><td>
Returns the number of cells containing numbers in a field of a list or database that satisfy specified conditions<br/><br/></td></tr>
<tr>
<td>
DCOUNTA<br/><br/></td><td>
Returns the number of non-blank cells in a field of a list or database, that satisfy specified conditions<br/><br/></td></tr>
<tr>
<td>
DAVERAGE<br/><br/></td><td>
Calculates the average of values in a field of a list or database, that satisfy specified conditions<br/><br/></td></tr>
<tr>
<td>
DGET<br/><br/></td><td>
Returns a single value from a field of a list or database, that satisfy specified conditions<br/><br/></td></tr>
<tr>
<td>
DMAX<br/><br/></td><td>
Returns the maximum value from a field of a list or database, that satisfy specified conditions<br/><br/></td></tr>
<tr>
<td>
DMIN<br/><br/></td><td>
Returns the minimum value from a field of a list or database, that satisfy specified conditions<br/><br/></td></tr>
<tr>
<td>
DSTDEVP<br/><br/></td><td>
Calculates the standard deviation (based on an entire population) of values in a field of a list or database, that satisfy specified conditions<br/><br/></td></tr>
<tr>
<td>
DSTEV<br/><br/></td><td>
Calculates the standard deviation (based on a sample of a population) of values in a field of a list or database, that satisfy specified conditions<br/><br/></td></tr>
<tr>
<td>
DVARP<br/><br/></td><td>
Calculates the variance (based on an entire population) of values in a field of a list or database, that satisfy specified conditions<br/><br/></td></tr>
<tr>
<td>
DVAR<br/><br/></td><td>
Calculates the variance (based on a sample of a population) of values in a field of a list or database, that satisfy specified conditions<br/><br/></td></tr>
</table>

### Date and Time Functions

<table>
<tr>
<th>
Name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
DATE<br/><br/></td><td>
Returns a date, from a user-supplied year, month and day<br/><br/></td></tr>
<tr>
<td>
DATEVALUE<br/><br/></td><td>
Converts a text string showing a date, to an integer that represents the date in Excel's date-time code<br/><br/></td></tr>
<tr>
<td>
DAY<br/><br/></td><td>
Returns the day (of the month) from a user-supplied date<br/><br/></td></tr>
<tr>
<td>
DAYS360<br/><br/></td><td>
Calculates the number of days between 2 dates, based on a 360-day year (12 x 30 months)<br/><br/></td></tr>
<tr>
<td>
HOUR<br/><br/></td><td>
Returns the hour part of a user-supplied time<br/><br/></td></tr>
<tr>
<td>
MINUTE<br/><br/></td><td>
Returns the minute part of a user-supplied time<br/><br/></td></tr>
<tr>
<td>
SECOND<br/><br/></td><td>
Returns the seconds part of a user-supplied time<br/><br/></td></tr>
<tr>
<td>
MONTH<br/><br/></td><td>
Returns the month from a user-supplied date<br/><br/></td></tr>
<tr>
<td>
NOW<br/><br/></td><td>
Returns the current date & time<br/><br/></td></tr>
<tr>
<td>
TIME<br/><br/></td><td>
Returns a time, from a user-supplied hour, minute and second<br/><br/></td></tr>
<tr>
<td>
TIMEVALUE<br/><br/></td><td>
Converts a text string showing a time, to a decimal that represents the time in Excel<br/><br/></td></tr>
<tr>
<td>
TODAY<br/><br/></td><td>
Returns today's date<br/><br/></td></tr>
<tr>
<td>
WEEKDAY<br/><br/></td><td>
Returns an integer representing the day of the week for a supplied date<br/><br/></td></tr>
<tr>
<td>
YEAR<br/><br/></td><td>
Returns the year from a user-supplied date<br/><br/></td></tr>
<tr>
<td>
DAYS<br/><br/></td><td>
Calculates the number of days between 2 dates<br/><br/></td></tr>
<tr>
<td>
EDATE<br/><br/></td><td>
Returns a date that is the specified number of months before or after an initial supplied start date<br/><br/></td></tr>
<tr>
<td>
EOMONTH<br/><br/></td><td>
Returns a date that is the last day of the month which is a specified number of months before or after an initial supplied start date<br/><br/></td></tr>
<tr>
<td>
ISOWEEKNUM<br/><br/></td><td>
Returns the ISO week number of the year for a given date<br/><br/></td></tr>
<tr>
<td>
NETWORKDAYS.INTL<br/><br/></td><td>
Returns the number of whole network days (excluding weekends & holidays), between two supplied dates, using parameters to specify weekend days <br/><br/></td></tr>
<tr>
<td>
WEEKNUM<br/><br/></td><td>
Returns an integer representing the week number (from 1 to 53) of the year from a user-supplied date<br/><br/></td></tr>
<tr>
<td>
WORKDAY<br/><br/></td><td>
Returns a date that is a supplied number of working days (excluding weekends & holidays) ahead of a given start date<br/><br/></td></tr>
<tr>
<td>
WORKDAY.INTL<br/><br/></td><td>
Returns a date that is a supplied number of working days (excluding weekends & holidays) ahead of a given start date, using supplied parameters to specify weekend days<br/><br/></td></tr>
<tr>
<td>
YEARFRAC<br/><br/></td><td>
Calculates the fraction of the year represented by the number of whole days between two dates<br/><br/></td></tr>
</table>

### Engineering Functions

<table>
<tr>
<th>
Name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
DEC2BIN<br/><br/></td><td>
Converts a decimal number to binary<br/><br/></td></tr>
<tr>
<td>
DCE2OCT<br/><br/></td><td>
Converts a binary number to octal<br/><br/></td></tr>
<tr>
<td>
DEC2HEX<br/><br/></td><td>
Converts a decimal number to hexadecimal<br/><br/></td></tr>
<tr>
<td>
BIN2DEC<br/><br/></td><td>
Converts a binary number to hexadecimal<br/><br/></td></tr>
<tr>
<td>
BIN2OCT<br/><br/></td><td>
Converts a binary number to octal<br/><br/></td></tr>
<tr>
<td>
BIN2HEX<br/><br/></td><td>
Converts a binary number to hexadecimal<br/><br/></td></tr>
<tr>
<td>
HEX2BIN<br/><br/></td><td>
Converts a hexadecimal number to binary<br/><br/></td></tr>
<tr>
<td>
HEX2DEC<br/><br/></td><td>
Converts a hexadecimal number to a decimal<br/><br/></td></tr>
<tr>
<td>
HEX2OCT<br/><br/></td><td>
Converts a hexadecimal number to octal<br/><br/></td></tr>
<tr>
<td>
OCT2BIN<br/><br/></td><td>
Converts octal number to binary<br/><br/></td></tr>
<tr>
<td>
OCT2DEC<br/><br/></td><td>
Converts octal number to a decimal<br/><br/></td></tr>
<tr>
<td>
OCT2HEX<br/><br/></td><td>
Converts octal number to hexadecimal<br/><br/></td></tr>
<tr>
<td>
IMABS<br/><br/></td><td>
Returns the absolute value (the modulus) of a complex number<br/><br/></td></tr>
<tr>
<td>
IMAGINARY<br/><br/></td><td>
Returns the imaginary coefficient of a complex number<br/><br/></td></tr>
<tr>
<td>
IMREAL<br/><br/></td><td>
Returns the real coefficient of a complex number<br/><br/></td></tr>
<tr>
<td>
COMPLEX<br/><br/></td><td>
Converts user-supplied real and imaginary coefficients into a complex number<br/><br/></td></tr>
<tr>
<td>
IMSUM<br/><br/></td><td>
Calculates the sum of two complex numbers<br/><br/></td></tr>
<tr>
<td>
IMSUB<br/><br/></td><td>
Subtracts two complex numbers<br/><br/></td></tr>
<tr>
<td>
IMPRODUCT<br/><br/></td><td>
Returns the product of up to 255 supplied complex numbers<br/><br/></td></tr>
<tr>
<td>
IMDIV<br/><br/></td><td>
Returns the quotient of two supplied complex numbers<br/><br/></td></tr>
<tr>
<td>
IMCONJUGATE<br/><br/></td><td>
Returns the complex conjugate of a complex number<br/><br/></td></tr>
<tr>
<td>
IMSQRT<br/><br/></td><td>
Returns the square root of a complex number<br/><br/></td></tr>
<tr>
<td>
IMARGUMENT<br/><br/></td><td>
Returns the argument Θ (an angle expressed in radians) of a complex number<br/><br/></td></tr>
<tr>
<td>
IMSIN<br/><br/></td><td>
Returns the sine of a complex number<br/><br/></td></tr>
<tr>
<td>
IMCSC<br/><br/></td><td>
Returns the cosecant of a complex number<br/><br/></td></tr>
<tr>
<td>
IMCOS<br/><br/></td><td>
Returns the cosine of a complex number<br/><br/></td></tr>
<tr>
<td>
IMSEC<br/><br/></td><td>
Returns the secant of a complex number<br/><br/></td></tr>
<tr>
<td>
IMTAN<br/><br/></td><td>
Returns the tangent of a complex number<br/><br/></td></tr>
<tr>
<td>
IMCOT<br/><br/></td><td>
Returns the cotangent of a complex number<br/><br/></td></tr>
<tr>
<td>
IMSINH<br/><br/></td><td>
Returns the hyperbolic sine of a complex number<br/><br/></td></tr>
<tr>
<td>
IMCSCH<br/><br/></td><td>
Returns the hyperbolic cosecant of a complex number<br/><br/></td></tr>
<tr>
<td>
IMCOSH<br/><br/></td><td>
Returns the hyperbolic cosine of a complex number<br/><br/></td></tr>
<tr>
<td>
IMSECH<br/><br/></td><td>
Returns the hyperbolic secant of a complex number <br/><br/></td></tr>
<tr>
<td>
IMLOG10<br/><br/></td><td>
Returns the base-10 logarithm of a complex number<br/><br/></td></tr>
<tr>
<td>
IMLOG2<br/><br/></td><td>
Returns the base-2 logarithm of a complex number<br/><br/></td></tr>
<tr>
<td>
IMLN<br/><br/></td><td>
Returns the natural logarithm of a complex number<br/><br/></td></tr>
<tr>
<td>
IMEXP<br/><br/></td><td>
Returns the exponential of a complex number<br/><br/></td></tr>
<tr>
<td>
IMPOWER<br/><br/></td><td>
Calculates a complex number raised to a supplied power<br/><br/></td></tr>
<tr>
<td>
GESTEP<br/><br/></td><td>
Tests whether a number is greater than a supplied threshold value<br/><br/></td></tr>
<tr>
<td>
DELTA<br/><br/></td><td>
Tests whether two supplied numbers are equal<br/><br/></td></tr>
<tr>
<td>
BITAND<br/><br/></td><td>
Returns a Bitwise 'And' of two numbers<br/><br/></td></tr>
<tr>
<td>
BITOR<br/><br/></td><td>
Returns a Bitwise 'Or' of two numbers<br/><br/></td></tr>
<tr>
<td>
BITXOR<br/><br/></td><td>
Returns a Bitwise 'Exclusive Or' of two numbers<br/><br/></td></tr>
<tr>
<td>
BITLSHIFT<br/><br/></td><td>
Returns a number shifted left by a specified number of bits <br/><br/></td></tr>
<tr>
<td>
BITRSHIFT<br/><br/></td><td>
Returns a number shifted right by a specified number of bits<br/><br/></td></tr>
<tr>
<td>
ERF<br/><br/></td><td>
Returns the error function integrated between two supplied limits<br/><br/></td></tr>
<tr>
<td>
ERF.PRECISE<br/><br/></td><td>
Returns the error function integrated between 0 and a supplied limit<br/><br/></td></tr>
<tr>
<td>
ERFC.PRECISE<br/><br/></td><td>
Returns the complementary error function integrated between a supplied lower limit and infinity<br/><br/></td></tr>
<tr>
<td>
BESSELI<br/><br/></td><td>
Calculates the modified Bessel function In(x)<br/><br/></td></tr>
<tr>
<td>
BESSELJ<br/><br/></td><td>
Calculates the Bessel function Jn(x)<br/><br/></td></tr>
<tr>
<td>
BESSELY<br/><br/></td><td>
Calculates the modified Bessel function Yn(x)<br/><br/></td></tr>
<tr>
<td>
BESSELK<br/><br/></td><td>
Calculates the modified Bessel function Kn(x)<br/><br/></td></tr>
<tr>
<td>
CONVERT<br/><br/></td><td>
Converts a number from one measurement system to another<br/><br/></td></tr>
</table>

### Financial Functions

<table>
<tr>
<th>
Name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
DB<br/><br/></td><td>
Calculates the depreciation of an asset for a specified period, using the fixed-declining balance method<br/><br/></td></tr>
<tr>
<td>
DDB<br/><br/></td><td>
Calculates the depreciation of an asset for a specified period, using the double-declining balance method, or some other user-specified method<br/><br/></td></tr>
<tr>
<td>
FV<br/><br/></td><td>
Calculates the future value of an investment with periodic constant payments and a constant interest rate<br/><br/></td></tr>
<tr>
<td>
IPMT<br/><br/></td><td>
Calculates the interest payment for a given period of an investment, with periodic constant payments and a constant interest rate<br/><br/></td></tr>
<tr>
<td>
IRR<br/><br/></td><td>
Calculates the internal rate of return for a series of cash flows<br/><br/></td></tr>
<tr>
<td>
XIRR<br/><br/></td><td>
Calculates the internal rate of return for a schedule of cash flows<br/><br/></td></tr>
<tr>
<td>
ISPMT<br/><br/></td><td>
Returns the interest paid during a specified period of an investment<br/><br/></td></tr>
<tr>
<td>
MIRR<br/><br/></td><td>
Calculates the internal rate of return for a series of periodic cash flows, considering the cost of the investment and the interest on the reinvestment of cash<br/><br/></td></tr>
<tr>
<td>
NPER<br/><br/></td><td>
Returns the number of periods for an investment with periodic constant payments and a constant interest rate<br/><br/></td></tr>
<tr>
<td>
NPV<br/><br/></td><td>
Calculates the net present value of an investment, based on a supplied discount rate, and a series of future payments and income<br/><br/></td></tr>
<tr>
<td>
PMT<br/><br/></td><td>
Calculates the payments required to reduce a loan, from a supplied present value to a specified future value<br/><br/></td></tr>
<tr>
<td>
PPMT<br/><br/></td><td>
Calculates the payment on the principal for a given investment, with periodic constant payments and a constant interest rate<br/><br/></td></tr>
<tr>
<td>
PV<br/><br/></td><td>
Calculates the present value of an investment (i.e. the total amount that a series of future payments is worth now)<br/><br/></td></tr>
<tr>
<td>
RATE<br/><br/></td><td>
Calculates the interest rate required to pay off a specified amount of a loan, or reach a target amount on an investment over a given period<br/><br/></td></tr>
<tr>
<td>
SLN<br/><br/></td><td>
Returns the straight-line depreciation of an asset for one period<br/><br/></td></tr>
<tr>
<td>
SYD<br/><br/></td><td>
Returns the sum-of-years' digits depreciation of an asset for a specified period<br/><br/></td></tr>
<tr>
<td>
VDB<br/><br/></td><td>
Returns the depreciation of an asset for a specified period, (including partial periods), using the double-declining balance method or another user-specified method<br/><br/></td></tr>
<tr>
<td>
DOLLARDE<br/><br/></td><td>
Converts a dollar price expressed as a fraction, into a dollar price expressed as a decimal<br/><br/></td></tr>
<tr>
<td>
DOLLARFR<br/><br/></td><td>
Converts a dollar price expressed as a decimal, into a dollar price expressed as a fraction<br/><br/></td></tr>
<tr>
<td>
DURATION<br/><br/></td><td>
Calculates the Macaulay duration of a security with an assumed par value of $100<br/><br/></td></tr>
<tr>
<td>
RRI<br/><br/></td><td>
Calculates an equivalent interest rate for the growth of an investment<br/><br/></td></tr>
<tr>
<td>
FVSCHEDULE<br/><br/></td><td>
Calculates the future value of an initial principal, after applying a series of compound interest rates<br/><br/></td></tr>
<tr>
<td>
DISC<br/><br/></td><td>
Calculates the discount rate for a security<br/><br/></td></tr>
<tr>
<td>
INTRATE<br/><br/></td><td>
Calculates the interest rate for a fully invested security<br/><br/></td></tr>
<tr>
<td>
CUMIPMT<br/><br/></td><td>
Calculates the cumulative interest paid between two specified periods<br/><br/></td></tr>
<tr>
<td>
CUMPRINC<br/><br/></td><td>
Calculates the cumulative principal paid on a loan, between two specified periods<br/><br/></td></tr>
<tr>
<td>
RECEIVED<br/><br/></td><td>
Calculates the amount received at maturity for a fully invested Security<br/><br/></td></tr>
</table>

### Information Functions

<table>
<tr>
<th>
Name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
ISERROR<br/><br/></td><td>
Checks whether the value is an error and returns true or false<br/><br/></td></tr>
<tr>
<td>
ISNUMBER<br/><br/></td><td>
Checks whether the value is number and returns true or false<br/><br/></td></tr>
<tr>
<td>
ISLOGICAL<br/><br/></td><td>
Checks whether a value is logical value(TRUE/FALSE) and returns true or false<br/><br/></td></tr>
<tr>
<td>
ISNA<br/><br/></td><td>
Checks whether a value is #N/A and returns true or false<br/><br/></td></tr>
<tr>
<td>
ISERR<br/><br/></td><td>
Checks whether the value is an error except #N/A and returns true or false<br/><br/></td></tr>
<tr>
<td>
ISBLANK<br/><br/></td><td>
Checks whether the reference is to an empty cell and returns true or false<br/><br/></td></tr>
<tr>
<td>
ISTEXT<br/><br/></td><td>
Checks whether the value is text and returns true or false<br/><br/></td></tr>
<tr>
<td>
ISNONTEXT<br/><br/></td><td>
Checks whether the value is not text(blank cells are not text) and returns true or false<br/><br/></td></tr>
<tr>
<td>
ISEVEN<br/><br/></td><td>
Returns true if number is even<br/><br/></td></tr>
<tr>
<td>
CONCATENATE<br/><br/></td><td>
Joins together two or more text strings<br/><br/></td></tr>
<tr>
<td>
DOLLAR<br/><br/></td><td>
Converts a number to text using currency format<br/><br/></td></tr>
<tr>
<td>
LEN<br/><br/></td><td>
Returns the length of a supplied text string<br/><br/></td></tr>
<tr>
<td>
FIXED<br/><br/></td><td>
Rounds a supplied number to a specified number of decimal places, and then converts this into text<br/><br/></td></tr>
<tr>
<td>
ISODD<br/><br/></td><td>
Returns true if number is odd<br/><br/></td></tr>
<tr>
<td>
ERROR.TYPE<br/><br/></td><td>
Tests a supplied value and returns an integer relating to the supplied value's error type<br/><br/></td></tr>
<tr>
<td>
N<br/><br/></td><td>
Converts a non-number value to a number, a date to a serial number, the logical value TRUE to 1 and all other values to 0<br/><br/></td></tr>
<tr>
<td>
NA<br/><br/></td><td>
Returns the Excel #N/A error<br/><br/></td></tr>
<tr>
<td>
CELL<br/><br/></td><td>
Returns information about the contents, formatting or location of a given cell<br/><br/></td></tr>
<tr>
<td>
INFO<br/><br/></td><td>
Returns information about the the current operating environment<br/><br/></td></tr>
<tr>
<td>
TYPE<br/><br/></td><td>
Returns information about the data type of a supplied value<br/><br/></td></tr>
<tr>
<td>
ISFORMULA<br/><br/></td><td>
Tests if a supplied cell contains a formula and if so, returns TRUE; Otherwise, returns FALSE<br/><br/></td></tr>
</table>

### Logical Functions

<table>
<tr>
<th>
Name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
AND<br/><br/></td><td>
Tests a number of user-defined conditions and returns TRUE if ALL of the conditions evaluate to TRUE, orFALSE otherwise<br/><br/></td></tr>
<tr>
<td>
OR<br/><br/></td><td>
Tests a number of user-defined conditions and returns TRUE if ANY of the conditions evaluate to TRUE, orFALSE otherwise<br/><br/></td></tr>
<tr>
<td>
IF<br/><br/></td><td>
Tests a user-defined condition and returns one result if the condition is TRUE, and another result if the condition is FALSE<br/><br/></td></tr>
<tr>
<td>
IFERROR<br/><br/></td><td>
Tests if an initial supplied value (or expression) returns an error, and if so, returns a supplied value; Otherwise the function returns the initial value.<br/><br/></td></tr>
<tr>
<td>
FALSE<br/><br/></td><td>
Simply returns the logical value FALSE<br/><br/></td></tr>
<tr>
<td>
TRUE<br/><br/></td><td>
Simply returns the logical value TRUE<br/><br/></td></tr>
<tr>
<td>
NOT<br/><br/></td><td>
Returns a logical value that is the opposite of a user supplied logical value or expression<br/><br/></td></tr>
</table>

### Lookup & Reference Functions

<table>
<tr>
<th>
Name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
OFFSET<br/><br/></td><td>
Returns a reference to a range of cells that is a specified number of rows and columns from an initial supplied range<br/><br/></td></tr>
<tr>
<td>
HLOOKUP<br/><br/></td><td>
Looks up a supplied value in the first row of a table, and returns the corresponding value from another row<br/><br/></td></tr>
<tr>
<td>
VLOOKUP<br/><br/></td><td>
Looks up a supplied value in the first column of a table, and returns the corresponding value from another column<br/><br/></td></tr>
<tr>
<td>
MATCH<br/><br/></td><td>
Finds the relative position of a value in a supplied array<br/><br/></td></tr>
<tr>
<td>
COLUMN<br/><br/></td><td>
Returns the column number of a supplied range, or of the current cell<br/><br/></td></tr>
<tr>
<td>
ROW<br/><br/></td><td>
Returns the row number of a supplied range, or of the current cell<br/><br/></td></tr>
<tr>
<td>
INDIRECT<br/><br/></td><td>
Returns a cell or range reference that is represented by a supplied text string<br/><br/></td></tr>
<tr>
<td>
AREAS<br/><br/></td><td>
Returns the number of areas in a supplied range<br/><br/></td></tr>
<tr>
<td>
COLUMNS<br/><br/></td><td>
Returns the number of columns in a supplied range<br/><br/></td></tr>
<tr>
<td>
FORMULATEXT<br/><br/></td><td>
Returns a formula as a string<br/><br/></td></tr>
<tr>
<td>
HYPERLINK<br/><br/></td><td>
Creates a hyperlink to a document in a supplied location<br/><br/></td></tr>
<tr>
<td>
ROW<br/><br/></td><td>
Returns the row number of a supplied range, or of the current cell<br/><br/></td></tr>
<tr>
<td>
ROWS<br/><br/></td><td>
Returns the number of rows in a supplied range<br/><br/></td></tr>
<tr>
<td>
SHEET<br/><br/></td><td>
Returns the sheet number of the referenced sheet<br/><br/></td></tr>
<tr>
<td>
TRANSPOSE<br/><br/></td><td>
Performs a transpose transformation on a range of cells (i.e. transforms a horizontal range of cells into a vertical range and vice versa)<br/><br/></td></tr>
<tr>
<td>
SHEETS<br/><br/></td><td>
Returns the number of sheets in reference<br/><br/></td></tr>
</table>

### Math & Trigonometry functions

<table>
<tr>
<th>
Name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
ABS<br/><br/></td><td>
Returns the absolute value of a number<br/><br/></td></tr>
<tr>
<td>
ACOS<br/><br/></td><td>
Returns the arccosine of a number<br/><br/></td></tr>
<tr>
<td>
ACOSH<br/><br/></td><td>
Returns the inverse hyperbolic cosine of a number<br/><br/></td></tr>
<tr>
<td>
ASIN<br/><br/></td><td>
Returns the arcsine of a number<br/><br/></td></tr>
<tr>
<td>
ASINH<br/><br/></td><td>
Returns the inverse hyperbolic sine of a number<br/><br/></td></tr>
<tr>
<td>
ATAN<br/><br/></td><td>
Returns the arctangent of a number<br/><br/></td></tr>
<tr>
<td>
ATAN2<br/><br/></td><td>
Returns the arctangent from x- and y-coordinates<br/><br/></td></tr>
<tr>
<td>
ATANH<br/><br/></td><td>
Returns the inverse hyperbolic tangent of a number<br/><br/></td></tr>
<tr>
<td>
SUM<br/><br/></td><td>
Adds its arguments<br/><br/></td></tr>
<tr>
<td>
PI<br/><br/></td><td>
Returns the value of pi<br/><br/></td></tr>
<tr>
<td>
POWER<br/><br/></td><td>
Returns the result of a number raised to a power<br/><br/></td></tr>
<tr>
<td>
POW<br/><br/></td><td>
Returns the result of a number raised to a power<br/><br/></td></tr>
<tr>
<td>
SUBTOTAL<br/><br/></td><td>
Returns a subtotal in a list or database<br/><br/></td></tr>
<tr>
<td>
COS<br/><br/></td><td>
Returns the cosine of a number<br/><br/></td></tr>
<tr>
<td>
SIN<br/><br/></td><td>
Returns the sine of the given angle<br/><br/></td></tr>
<tr>
<td>
COSH<br/><br/></td><td>
Returns the hyperbolic cosine of a number<br/><br/></td></tr>
<tr>
<td>
SINH<br/><br/></td><td>
Returns the hyperbolic sine of a number<br/><br/></td></tr>
<tr>
<td>
TANH<br/><br/></td><td>
Returns the hyperbolic tangent of a number<br/><br/></td></tr>
<tr>
<td>
TAN<br/><br/></td><td>
Returns the tangent of a number<br/><br/></td></tr>
<tr>
<td>
ACOT<br/><br/></td><td>
Returns the arc cotangent of a number, in radians in the range 0 to Pi<br/><br/></td></tr>
<tr>
<td>
ACOTH<br/><br/></td><td>
Returns the inverse hyperbolic cotangent of a number<br/><br/></td></tr>
<tr>
<td>
SIGN<br/><br/></td><td>
Returns the sign of a number<br/><br/></td></tr>
<tr>
<td>
SQRT<br/><br/></td><td>
Returns a positive square root<br/><br/></td></tr>
<tr>
<td>
ROUND<br/><br/></td><td>
Rounds a number to a specified number of digits<br/><br/></td></tr>
<tr>
<td>
LOG<br/><br/></td><td>
Returns the logarithm of a number to a specified base<br/><br/></td></tr>
<tr>
<td>
LOG10<br/><br/></td><td>
Returns the base-10 logarithm of a number<br/><br/></td></tr>
<tr>
<td>
EXP<br/><br/></td><td>
Returns e raised to the power of a given number<br/><br/></td></tr>
<tr>
<td>
CEILING<br/><br/></td><td>
Rounds a number to the nearest integer or to the nearest multiple of significance<br/><br/></td></tr>
<tr>
<td>
CEILING.MATH<br/><br/></td><td>
Returns the RoundUp of the given number to the given significance<br/><br/></td></tr>
<tr>
<td>
COLUMNS<br/><br/></td><td>
Returns the number of columns of the passed in cell reference<br/><br/></td></tr>
<tr>
<td>
FLOOR<br/><br/></td><td>
Rounds a number down, toward zero<br/><br/></td></tr>
<tr>
<td>
PRODUCT<br/><br/></td><td>
Multiplies its arguments<br/><br/></td></tr>
<tr>
<td>
MOD<br/><br/></td><td>
Returns the remainder from division<br/><br/></td></tr>
<tr>
<td>
TRUNC<br/><br/></td><td>
Truncates a number to an integer<br/><br/></td></tr>
<tr>
<td>
INT<br/><br/></td><td>
Rounds a number down to nearest integer<br/><br/></td></tr>
<tr>
<td>
ISEVEN<br/><br/></td><td>
Returns true if the number is even<br/><br/></td></tr>
<tr>
<td>
SUMPRODUCT<br/><br/></td><td>
Returns the sum of the products of corresponding array components<br/><br/></td></tr>
<tr>
<td>
EXP<br/><br/></td><td>
Returns e raised to the power of a given number<br/><br/></td></tr>
<tr>
<td>
INT<br/><br/></td><td>
Rounds a number down to the nearest integer<br/><br/></td></tr>
<tr>
<td>
RAND<br/><br/></td><td>
Returns an evenly distributed random number &gt;= 0 and &lt; 1<br/><br/></td></tr>
<tr>
<td>
COMBIN<br/><br/></td><td>
Returns the number of combinations for a given number of objects<br/><br/></td></tr>
<tr>
<td>
DEGREES<br/><br/></td><td>
Converts radians to degrees<br/><br/></td></tr>
<tr>
<td>
EVEN<br/><br/></td><td>
Rounds a number up to the nearest even integer<br/><br/></td></tr>
<tr>
<td>
FACT<br/><br/></td><td>
Returns the factorial of a number<br/><br/></td></tr>
<tr>
<td>
LN<br/><br/></td><td>
Returns the natural logarithm of a number<br/><br/></td></tr>
<tr>
<td>
ODD<br/><br/></td><td>
Rounds a number up to the nearest odd integer<br/><br/></td></tr>
<tr>
<td>
RADIANS<br/><br/></td><td>
Converts degrees to radians<br/><br/></td></tr>
<tr>
<td>
ROUNDDOWN<br/><br/></td><td>
Rounds a number down, toward zero<br/><br/></td></tr>
<tr>
<td>
ROUNDUP<br/><br/></td><td>
Rounds a number up, away from zero<br/><br/></td></tr>
<tr>
<td>
MROUND<br/><br/></td><td>
Returns a number rounded to the desired multiple<br/><br/></td></tr>
<tr>
<td>
MULTINOMIAL<br/><br/></td><td>
Returns the multinomial of a set of numbers<br/><br/></td></tr>
<tr>
<td>
QUOTIENT<br/><br/></td><td>
Returns the integer portion of a division<br/><br/></td></tr>
<tr>
<td>
FACTDOUBLE<br/><br/></td><td>
Returns the double factorial of a number<br/><br/></td></tr>
<tr>
<td>
GCD<br/><br/></td><td>
Returns the greatest common divisor<br/><br/></td></tr>
<tr>
<td>
LCM<br/><br/></td><td>
Returns the least common multiple<br/><br/></td></tr>
<tr>
<td>
SQRTPI<br/><br/></td><td>
Returns the square root of (number * pi)<br/><br/></td></tr>
<tr>
<td>
ROMAN<br/><br/></td><td>
Converts an Arabic numeral to Roman, as text<br/><br/></td></tr>
<tr>
<td>
SUMSQ<br/><br/></td><td>
Returns the sum of the squares of the arguments<br/><br/></td></tr>
<tr>
<td>
SUMX2MY2<br/><br/></td><td>
Returns the sum of the difference of squares of corresponding values in two arrays<br/><br/></td></tr>
<tr>
<td>
SUMX2PY2<br/><br/></td><td>
Returns the sum of the sum of squares of corresponding values in two arrays<br/><br/></td></tr>
<tr>
<td>
SUMXMY2<br/><br/></td><td>
Returns the sum of squares of differences of corresponding values in two arrays<br/><br/></td></tr>
<tr>
<td>
SUMIFS<br/><br/></td><td>
Adds the cells specified by a given set of conditions or criteria<br/><br/></td></tr>
<tr>
<td>
SEC<br/><br/></td><td>
Returns the secant of an angle<br/><br/></td></tr>
<tr>
<td>
SECH<br/><br/></td><td>
Returns the hyperbolic secant of an angle<br/><br/></td></tr>
<tr>
<td>
COT<br/><br/></td><td>
Returns the cotangent of an angle<br/><br/></td></tr>
<tr>
<td>
COTH<br/><br/></td><td>
Returns the hyperbolic cotangent of a number<br/><br/></td></tr>
<tr>
<td>
CSC<br/><br/></td><td>
Returns the cosecant of an angle<br/><br/></td></tr>
<tr>
<td>
CSCH<br/><br/></td><td>
Returns the hyperbolic cosecant of an angle<br/><br/></td></tr>
<tr>
<td>
TRUNCATE<br/><br/></td><td>
Truncates a number to an integer<br/><br/></td></tr>
<tr>
<td>
COMBINA<br/><br/></td><td>
Returns the number of combinations for a given number of objects<br/><br/></td></tr>
<tr>
<td>
BASE<br/><br/></td><td>
Converts number into text representation <br/><br/></td></tr>
<tr>
<td>
DECIMAL<br/><br/></td><td>
Converts text representation of a number in a given base into decimal number<br/><br/></td></tr>
<tr>
<td>
ARABIC<br/><br/></td><td>
Converts a roman numeral to Arabic<br/><br/></td></tr>
<tr>
<td>
CEILING.MATH<br/><br/></td><td>
Rounds a number to the nearest integer or to the nearest multiple of significance<br/><br/></td></tr>
<tr>
<td>
MDETERM<br/><br/></td><td>
Returns the matrix determinant of an array<br/><br/></td></tr>
<tr>
<td>
MMULT<br/><br/></td><td>
Returns the matrix product of two arrays<br/><br/></td></tr>
<tr>
<td>
MINVERSE<br/><br/></td><td>
Returns the matrix inverse of an array<br/><br/></td></tr>
<tr>
<td>
MUNIT<br/><br/></td><td>
Returns the unit matrix for the specified dimension<br/><br/></td></tr>
</table>

### Statistical functions

<table>
<tr>
<th>
Name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
AVG<br/><br/></td><td>
Returns the average of its arguments<br/><br/></td></tr>
<tr>
<td>
AVERAGE<br/><br/></td><td>
Returns the average of its arguments<br/><br/></td></tr>
<tr>
<td>
MAX<br/><br/></td><td>
Returns the maximum value in a list of arguments<br/><br/></td></tr>
<tr>
<td>
MIN<br/><br/></td><td>
Returns the minimum value in a list of arguments<br/><br/></td></tr>
<tr>
<td>
MAXA<br/><br/></td><td>
Returns the maximum value in a list of arguments, including numbers, text, and logical values<br/><br/></td></tr>
<tr>
<td>
MINA<br/><br/></td><td>
Returns the smallest value in a list of arguments, including numbers, text, and logical values<br/><br/></td></tr>
<tr>
<td>
MEDIAN<br/><br/></td><td>
Returns the median of the given numbers<br/><br/></td></tr>
<tr>
<td>
CONFIDENCE.T<br/><br/></td><td>
Returns the confidence interval for a population mean<br/><br/></td></tr>
<tr>
<td>
SKEW.P<br/><br/></td><td>
Returns the skewness of a distribution<br/><br/></td></tr>
<tr>
<td>
COVARIANCE.P<br/><br/></td><td>
Returns population covariance, the average of the products deviation for each data point pair in two data sets.<br/><br/></td></tr>
<tr>
<td>
COVARIANCE.S<br/><br/></td><td>
Returns the sample covariance, the average of the products deviation for each data point pair in two data sets.<br/><br/></td></tr>
<tr>
<td>
PERCENTILE.EXC<br/><br/></td><td>
Returns the Kth percentile of the values in a range, where K is in the range 0….1 exclusive<br/><br/></td></tr>
<tr>
<td>
PERCENTILE.INC<br/><br/></td><td>
Returns the Kth percentile of the values in a range, where K is in the range 0….1 inclusive<br/><br/></td></tr>
<tr>
<td>
PERCENTRANK.EXC<br/><br/></td><td>
Returns the rank of value in dataset as a percentage of the data set as percentage (0….1, exclusive) of the dataset<br/><br/></td></tr>
<tr>
<td>
PERCENTRANC.INC<br/><br/></td><td>
Returns the rank of value in dataset as a percentage of the data set as percentage (0….1, inclusive) of the dataset<br/><br/></td></tr>
<tr>
<td>
STDEV.P<br/><br/></td><td>
Calculates standard deviation based on the entire population<br/><br/></td></tr>
<tr>
<td>
STDEV.S<br/><br/></td><td>
Estimates standard deviation based on a sample<br/><br/></td></tr>
<tr>
<td>
PERMUTATIONA<br/><br/></td><td>
Returns the number of permutations for a given number of objects<br/><br/></td></tr>
<tr>
<td>
NORM.DIST<br/><br/></td><td>
Returns the normal cumulative distribution<br/><br/></td></tr>
<tr>
<td>
NORM.INV<br/><br/></td><td>
Returns the inverse of the normal cumulative distribution<br/><br/></td></tr>
<tr>
<td>
NORM.S.DIST<br/><br/></td><td>
Returns the standard normal cumulative distribution<br/><br/></td></tr>
<tr>
<td>
NORM.S.INV<br/><br/></td><td>
Returns the inverse of the standard normal cumulative distribution<br/><br/></td></tr>
<tr>
<td>
WEIBULL.DIST<br/><br/></td><td>
Returns the Weibull distribution<br/><br/></td></tr>
<tr>
<td>
EXPON.DIST<br/><br/></td><td>
Returns the exponential distribution<br/><br/></td></tr>
<tr>
<td>
GAMMA.DIST<br/><br/></td><td>
Returns the gamma distribution<br/><br/></td></tr>
<tr>
<td>
GAMMA.INV<br/><br/></td><td>
Returns the inverse of the gamma cumulative distribution<br/><br/></td></tr>
<tr>
<td>
GAMMALN.PRECISE<br/><br/></td><td>
Returns the natural logarithm of the gamma function, Γ(x)<br/><br/></td></tr>
<tr>
<td>
T.INV<br/><br/></td><td>
Returns the left-tailed inverse of the Student’s t-distribution <br/><br/></td></tr>
<tr>
<td>
F.INV.RT<br/><br/></td><td>
Returns the inverse of the right-tailed F probability distribution for two data sets<br/><br/></td></tr>
<tr>
<td>
BINOM.INV<br/><br/></td><td>
Returns the smallest value for which the cumulative binomial distribution is greater than or equal to a criterion value<br/><br/></td></tr>
<tr>
<td>
HYPGEOM.DIST<br/><br/></td><td>
Returns the hypergeometric distribution<br/><br/></td></tr>
<tr>
<td>
LOGNORM.DIST<br/><br/></td><td>
Returns the cumulative log-normal distribution <br/><br/></td></tr>
<tr>
<td>
LOGNORM.INV<br/><br/></td><td>
Returns the inverse of the lognormal distribution<br/><br/></td></tr>
<tr>
<td>
CONFIDENCE.NORM<br/><br/></td><td>
Returns the confidence interval for a population mean, using a normal distribution<br/><br/></td></tr>
<tr>
<td>
CHISQ.DIST.RT<br/><br/></td><td>
Returns the right-tailed probability of the chi-squared distribution<br/><br/></td></tr>
<tr>
<td>
F.DIST<br/><br/></td><td>
Returns the F probability distribution<br/><br/></td></tr>
<tr>
<td>
F.DIST.RT<br/><br/></td><td>
Returns the right-tailed F probability distribution for two data sets<br/><br/></td></tr>
<tr>
<td>
CHISQ.TEST<br/><br/></td><td>
Returns the chi-squared statistical test for independence<br/><br/></td></tr>
<tr>
<td>
CHISQ.INV<br/><br/></td><td>
Returns the inverse of the left-tailed probability of the chi-squared distribution<br/><br/></td></tr>
<tr>
<td>
CHISQ.INV.RT<br/><br/></td><td>
Returns the inverse of the right-tailed probability of the chi-squared distribution<br/><br/></td></tr>
<tr>
<td>
BINOM.DIST<br/><br/></td><td>
Returns the individual term binomial distribution probability<br/><br/></td></tr>
<tr>
<td>
Z.TEST<br/><br/></td><td>
Returns the one-tailed probability value of a z-test<br/><br/></td></tr>
<tr>
<td>
RANK.AVG<br/><br/></td><td>
Returns the statistical rank of a given value, within a supplied array of values (if more than one value has same rank, the average rank is returned)<br/><br/></td></tr>
<tr>
<td>
RANK.EQ<br/><br/></td><td>
Returns the Mode (the most frequently occurring value) of a list of supplied numbers (if more than one value has same rank, the top rank of that set is returned)<br/><br/></td></tr>
<tr>
<td>
NEGBINOM.DIST<br/><br/></td><td>
Returns the negative binomial distribution<br/><br/></td></tr>
<tr>
<td>
POISSON.DIST<br/><br/></td><td>
Returns the Poisson distribution<br/><br/></td></tr>
<tr>
<td>
QUARTILE.EXC<br/><br/></td><td>
Returns the specified quartile of a set of supplied numbers, based on percentile value 0 - 1 (exclusive)<br/><br/></td></tr>
<tr>
<td>
QUARTILE.INC<br/><br/></td><td>
Returns the specified quartile of a set of supplied numbers, based on percentile value 0 - 1 (inclusive)<br/><br/></td></tr>
<tr>
<td>
AVEDEV<br/><br/></td><td>
Returns the average of the absolute deviations of data points from their mean<br/><br/></td></tr>
<tr>
<td>
AVERAGEA<br/><br/></td><td>
Returns the Average of a list of supplied numbers, counting text and the logical value FALSE as the value 0 and counting the logical value TRUE as the value 1<br/><br/></td></tr>
<tr>
<td>
GAMMALN<br/><br/></td><td>
Calculates the natural logarithm of the gamma function for a supplied value<br/><br/></td></tr>
<tr>
<td>
GAMMADIST<br/><br/></td><td>
Returns the gamma distribution<br/><br/></td></tr>
<tr>
<td>
GAMMAINV<br/><br/></td><td>
Returns the inverse gamma cumulative distribution<br/><br/></td></tr>
<tr>
<td>
GEOMEAN<br/><br/></td><td>
Returns the geometric mean of a set of supplied numbers<br/><br/></td></tr>
<tr>
<td>
HARMEAN<br/><br/></td><td>
Returns the harmonic mean of a set of supplied numbers<br/><br/></td></tr>
<tr>
<td>
HYPGEOMDIST<br/><br/></td><td>
Returns the hypergeometric distribution <br/><br/></td></tr>
<tr>
<td>
INTERCEPT<br/><br/></td><td>
Calculates the best fit regression line, through a supplied series of x- and y- values and returns the value at which this line intercepts the y-axis<br/><br/></td></tr>
<tr>
<td>
BINOMDIST<br/><br/></td><td>
Returns the individual term binomial distribution probability<br/><br/></td></tr>
<tr>
<td>
CHIDIST<br/><br/></td><td>
Returns the right-tailed probability of the chi-squared distribution<br/><br/></td></tr>
<tr>
<td>
CHIINV<br/><br/></td><td>
Returns the inverse of the right-tailed probability of the chi-squared distribution<br/><br/></td></tr>
<tr>
<td>
CHITEST<br/><br/></td><td>
Returns the chi-squared statistical test for independence<br/><br/></td></tr>
<tr>
<td>
NORMDIST<br/><br/></td><td>
Returns the normal cumulative distribution<br/><br/></td></tr>
<tr>
<td>
NORMINV<br/><br/></td><td>
Returns the inverse of the normal cumulative distribution<br/><br/></td></tr>
<tr>
<td>
NORMSINV<br/><br/></td><td>
Returns the inverse of the standard normal cumulative distribution<br/><br/></td></tr>
<tr>
<td>
NORMSDIST<br/><br/></td><td>
Returns the standard normal cumulative distribution<br/><br/></td></tr>
<tr>
<td>
CONFIDENCE<br/><br/></td><td>
Returns the confidence interval for a population mean, using a normal distribution <br/><br/></td></tr>
<tr>
<td>
CORREL<br/><br/></td><td>
Returns the correlation coefficient between two sets of values<br/><br/></td></tr>
<tr>
<td>
COUNT<br/><br/></td><td>
Returns the number of numerical values in a supplied set of cells or values<br/><br/></td></tr>
<tr>
<td>
COUNTA<br/><br/></td><td>
Returns the number of non-blanks in a supplied set of cells or values<br/><br/></td></tr>
<tr>
<td>
COUNTBLANK<br/><br/></td><td>
Returns the number of blank cells in a supplied range<br/><br/></td></tr>
<tr>
<td>
COUNTIF<br/><br/></td><td>
Returns the number of cells (of a supplied range), that satisfy a given criteria<br/><br/></td></tr>
<tr>
<td>
COVAR<br/><br/></td><td>
Returns population covariance (i.e. the average of the products of deviations for each pair within two supplied data sets)<br/><br/></td></tr>
<tr>
<td>
CRITBINOM<br/><br/></td><td>
Returns the smallest value for which the cumulative binomial distribution is greater than or equal to a criterion value<br/><br/></td></tr>
<tr>
<td>
DEVSQ<br/><br/></td><td>
Returns the sum of the squares of the deviations of a set of data points from their sample mean<br/><br/></td></tr>
<tr>
<td>
EXPONDIST<br/><br/></td><td>
Returns the exponential distribution<br/><br/></td></tr>
<tr>
<td>
FDIST<br/><br/></td><td>
Returns the F probability distribution (probability density or cumulative distribution function)<br/><br/></td></tr>
<tr>
<td>
FINV<br/><br/></td><td>
Returns the inverse of the right-tailed F probability distribution for two data sets<br/><br/></td></tr>
<tr>
<td>
FISHER<br/><br/></td><td>
Returns the Fisher transformation<br/><br/></td></tr>
<tr>
<td>
FISHERINV<br/><br/></td><td>
Returns the inverse of the Fisher transformation<br/><br/></td></tr>
<tr>
<td>
FORECAST<br/><br/></td><td>
Predicts a future point on a linear trend line fitted to a supplied set of x- and y- values<br/><br/></td></tr>
<tr>
<td>
KURT<br/><br/></td><td>
Returns the kurtosis of a data set<br/><br/></td></tr>
<tr>
<td>
LARGE<br/><br/></td><td>
Returns the Kth LARGEST value from a list of supplied numbers, for a given value K<br/><br/></td></tr>
<tr>
<td>
LOGNORMDIST<br/><br/></td><td>
Returns the cumulative log-normal distribution<br/><br/></td></tr>
<tr>
<td>
LOGINV<br/><br/></td><td>
Returns the inverse of the lognormal distribution<br/><br/></td></tr>
<tr>
<td>
MODE<br/><br/></td><td>
Returns the Mode (the most frequently occurring value) of a list of supplied numbers<br/><br/></td></tr>
<tr>
<td>
NEGBINOMDIST<br/><br/></td><td>
Returns the negative binomial distribution<br/><br/></td></tr>
<tr>
<td>
PEARSON<br/><br/></td><td>
Returns the Pearson product moment correlation coefficient<br/><br/></td></tr>
<tr>
<td>
PERCENTILE<br/><br/></td><td>
Returns the K'th percentile of values in a supplied range, where K is in the range 0 - 1 (inclusive)<br/><br/></td></tr>
<tr>
<td>
PERCENTILERANK<br/><br/></td><td>
Returns the rank of a value in a data set, as a percentage (0 - 1 inclusive)<br/><br/></td></tr>
<tr>
<td>
PERMUT<br/><br/></td><td>
Returns the number of permutations for a given number of objects<br/><br/></td></tr>
<tr>
<td>
POISSON<br/><br/></td><td>
Returns the Poisson distribution<br/><br/></td></tr>
<tr>
<td>
PROB<br/><br/></td><td>
Returns the probability that values in a supplied range are within given limits<br/><br/></td></tr>
<tr>
<td>
QUARTILE<br/><br/></td><td>
Returns the specified quartile of a set of supplied numbers, based on percentile value 0 - 1 (inclusive)<br/><br/></td></tr>
<tr>
<td>
RANQ<br/><br/></td><td>
Returns the Mode (the most frequently occurring value) of a list of supplied numbers (if more than one value has same rank, the top rank of that set is returned)<br/><br/></td></tr>
<tr>
<td>
RSQ<br/><br/></td><td>
Returns the square of the Pearson product moment correlation coefficient<br/><br/></td></tr>
<tr>
<td>
SKEW<br/><br/></td><td>
Returns the skewness of a distribution<br/><br/></td></tr>
<tr>
<td>
SLOPE<br/><br/></td><td>
Returns the slope of the linear regression line through a supplied series of x- and y- values<br/><br/></td></tr>
<tr>
<td>
SMALL<br/><br/></td><td>
Returns the Kth SMALLEST value from a list of supplied numbers, for a given value K<br/><br/></td></tr>
<tr>
<td>
STANDARDIZE<br/><br/></td><td>
Returns a normalized value<br/><br/></td></tr>
<tr>
<td>
STDEV<br/><br/></td><td>
Returns the standard deviation of a supplied set of values (which represent a sample of a population)<br/><br/></td></tr>
<tr>
<td>
STDEVA<br/><br/></td><td>
Returns the standard deviation of a supplied set of values (which represent a sample of a population), counting text and the logical value FALSE as the value 0 and counting the logical value TRUE as the value 1<br/><br/></td></tr>
<tr>
<td>
STDEVP<br/><br/></td><td>
Returns the standard deviation of a supplied set of values (which represent an entire population)<br/><br/></td></tr>
<tr>
<td>
STDEVPA<br/><br/></td><td>
Returns the standard deviation of a supplied set of values (which represent an entire population), counting text and the logical value FALSE as the value 0 and counting the logical value TRUE as the value 1<br/><br/></td></tr>
<tr>
<td>
STEYX<br/><br/></td><td>
Returns the standard error of the predicted y-value for each x in the regression line for a set of supplied x- and y- values<br/><br/></td></tr>
<tr>
<td>
TRIMMEAN<br/><br/></td><td>
Returns the mean of the interior of a supplied set of values<br/><br/></td></tr>
<tr>
<td>
VAR<br/><br/></td><td>
Returns the variance of a supplied set of values (which represent a sample of a population)<br/><br/></td></tr>
<tr>
<td>
VARA<br/><br/></td><td>
Returns the variance of a supplied set of values (which represent a sample of a population), counting text and the logical value FALSE as the value 0 and counting the logical value TRUE as the value 1<br/><br/></td></tr>
<tr>
<td>
VARP<br/><br/></td><td>
Returns the variance of a supplied set of values (which represent an entire population)<br/><br/></td></tr>
<tr>
<td>
VARPA<br/><br/></td><td>
Returns the variance of a supplied set of values (which represent an entire population), counting text and the logical value FALSE as the value 0 and counting the logical value TRUE as the value 1<br/><br/></td></tr>
<tr>
<td>
WEIBULL<br/><br/></td><td>
Returns the Weibull distribution<br/><br/></td></tr>
<tr>
<td>
ZTEST<br/><br/></td><td>
Returns the one-tailed probability value of a z-test<br/><br/></td></tr>
</table>

### Text Functions

<table>
<tr>
<th>
Name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
LEFT<br/><br/></td><td>
Returns a specified number of characters from the start of a supplied text string<br/><br/></td></tr>
<tr>
<td>
LEN<br/><br/></td><td>
Returns the length of a supplied text string<br/><br/></td></tr>
<tr>
<td>
TRUNC<br/><br/></td><td>
Truncates a number to an integer removing decimal part or fractional part <br/><br/></td></tr>
<tr>
<td>
MID<br/><br/></td><td>
Returns a specified number of characters from the middle of a supplied text string<br/><br/></td></tr>
<tr>
<td>
RIGHT<br/><br/></td><td>
Returns a specified number of characters from the end of a supplied text string<br/><br/></td></tr>
<tr>
<td>
VALUE<br/><br/></td><td>
Converts a text string into a numeric value<br/><br/></td></tr>
<tr>
<td>
DOLLAR<br/><br/></td><td>
Converts a supplied number into text, using a currency format<br/><br/></td></tr>
<tr>
<td>
FIXED<br/><br/></td><td>
Rounds a supplied number to a specified number of decimal places, and then converts this into text<br/><br/></td></tr>
<tr>
<td>
LOWER<br/><br/></td><td>
Converts all characters in a supplied text string to lower case<br/><br/></td></tr>
<tr>
<td>
UPPER<br/><br/></td><td>
Converts all characters in a supplied text string to upper case<br/><br/></td></tr>
<tr>
<td>
TEXT<br/><br/></td><td>
Converts a supplied value into text, using a user-specified format<br/><br/></td></tr>
<tr>
<td>
TRIM<br/><br/></td><td>
Removes duplicate spaces, and spaces at the start and end of a text string<br/><br/></td></tr>
<tr>
<td>
CONCATENATE<br/><br/></td><td>
Joins together two or more text strings<br/><br/></td></tr>
<tr>
<td>
SUBSTITUTE<br/><br/></td><td>
Substitutes all occurrences of a search text string, within an original text string, with the supplied replacement text<br/><br/></td></tr>
<tr>
<td>
T<br/><br/></td><td>
Tests whether a supplied value is text and if so, returns the supplied text; If not, returns an empty text string.<br/><br/></td></tr>
<tr>
<td>
CODE<br/><br/></td><td>
Returns the numeric code for the first character of a supplied string<br/><br/></td></tr>
<tr>
<td>
FINDB<br/><br/></td><td>
Returns the position of a supplied character or text string from within a supplied text string (case-sensitive)<br/><br/></td></tr>
<tr>
<td>
LEFTB<br/><br/></td><td>
Returns a specified number of characters from the start of a supplied text string<br/><br/></td></tr>
<tr>
<td>
LENB<br/><br/></td><td>
Returns the length of a supplied text string<br/><br/></td></tr>
<tr>
<td>
MINB<br/><br/></td><td>
Returns the smallest value in a set of values. does not ignore logical text and values<br/><br/></td></tr>
<tr>
<td>
RIGHTB<br/><br/></td><td>
Returns a specified number of characters from the end of a supplied text string<br/><br/></td></tr>
<tr>
<td>
NUMBERVALUE<br/><br/></td><td>
Converts text to a number, in a locale-independent way<br/><br/></td></tr>
<tr>
<td>
PROPER<br/><br/></td><td>
Converts all characters in a supplied text string to proper case (i.e. letters that do not follow another letter are upper case and all other characters are lower case)<br/><br/></td></tr>
<tr>
<td>
REPLACE<br/><br/></td><td>
Replaces all or part of a text string with another string (from a user supplied position)<br/><br/></td></tr>
<tr>
<td>
REPT<br/><br/></td><td>
Returns a string consisting of a supplied text string, repeated a specified number of times<br/><br/></td></tr>
<tr>
<td>
SEARCHB<br/><br/></td><td>
Returns the position of a supplied character or text string from within a supplied text string (non-case-sensitive)<br/><br/></td></tr>
<tr>
<td>
UNICHAR<br/><br/></td><td>
Returns the Unicode character that is referenced by the given numeric value<br/><br/></td></tr>
<tr>
<td>
UNICODE<br/><br/></td><td>
Returns the number (code point) corresponding to the first character of a supplied text string <br/><br/></td></tr>
</table>

### Web Functions

<table>
<tr>
<th>
Name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
ENCODEURL<br/><br/></td><td>
Returns a URL-encoded string <br/><br/></td></tr>
<tr>
<td>
FILTERXML<br/><br/></td><td>
Returns data from XML content, using a specified XPath<br/><br/></td></tr>
<tr>
<td>
WEBSERVICE<br/><br/></td><td>
Returns data from a web service on the Internet or Intranet<br/><br/></td></tr>
</table>
