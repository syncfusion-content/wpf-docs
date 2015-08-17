---
layout: post
title: Filter-Expression
description: filter expression
platform: wpf
control: PivotGrid
documentation: ug
---

## Filter Expression

This class encapsulates the information needed to define a filter. It contains the following properties.

_Property Table_

<table>
<tr>
<td>
{{ '**Property Name**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Value it Accepts**' | markdownify }}</td></tr>
<tr>
<td>
CaseSensitive</td><td>
Gets or sets whether the expression should be treated in a case sensitive manner.</td><td>
bool</td><td>
True or False</td></tr>
<tr>
<td>
Error</td><td>
Gets the last error that was logged during the compilation and calculation phases.</td><td>
ExpressionError</td><td>
CannotCompareDifferentTypesExceptionRaisedMismatchedParenthesesMissingRightQuoteNoneNotAValidFormulaUnknownOperator</td></tr>
<tr>
<td>
ErrorString</td><td>
Gets a descriptive string for the last error raised.</td><td>
string</td><td>
-</td></tr>
<tr>
<td>
Expression</td><td>
Gets or sets the well-formed logical expression that defines this FilterExpression.</td><td>
string</td><td>
-</td></tr>
<tr>
<td>
Name</td><td>
Gets or sets the name of this FilterExpression.</td><td>
string</td><td>
-</td></tr>
</table> 


