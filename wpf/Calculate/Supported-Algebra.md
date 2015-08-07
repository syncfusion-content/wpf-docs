---
layout: post
title: Supported-Algebra
description: supported algebra
platform: wpf
control: Calculate
documentation: ug
---

# Supported Algebra

The explicit look of a valid formula in Essential Calculate may vary depending upon the context of the formula. For example, if you are using a formula in a CalcSheet class based on an Excel spreadsheet, then something like = A1 + A3 is valid since CalcSheet recognizes the "A1" and "A3" as valid cell references. But, when you are using a CalcQuickBase object to manage formulas for controls on a WPF, then the same = A1 + A3 is not valid since CalcQuickBase only recognizes registered names inside square brackets as valid arguments. Hence, all Essential Calculation formulas support the same algebra with the exception of what comprises the definition of valid arguments.

This section comprises the following topics:

## Operators

The following is a list of the operators which are supported by Essential Calculate.

### Unary Arithmetic Operator

-         Unary Minus Sign

### Binary Arithmetic Operators

+        Addition

-         Subtraction

*         Multiplication

/         Division

^        Exponentiation

### Binary Literal Operator

&        Concatenation

### Binary Logical Operators

<        Less Than 

>        Greater Than

=         Equal To

<=       Less Than Or Equal

>=       Greater Than Or Equal

<>       Not Equal

All operations are subject to the following hierarchy of operations. The level 1 operations are done first, followed by level 2, and so on. Within the same level, the operations are performed from left to right in the order in which they are encountered during the parsing of the formula.

1. - (Unary Minus)
2. *    /
3. +    -
4. <   >    =    <=    >=    <>
5. & (Concatenation)

If you want to change the default operator’s precedence, then use parentheses to explicitly indicate the operation order.

### Examples

1. Formulas                Computed Value
2. = 6 / 2 + 1                     4
3. = 6 / (2 + 1)                   2
4. = 2 + 4 / 2                     4
5. = (2 + 4) / 2                   3



Logical operations return specific values: True or False. If you need specific numerical values associated with any logical expression, then use the logical expression as the first argument in the Formula Library IF-function, with the second argument being the numerical value of True and the third argument being the numerical value of False. If you use a well-formed logical expression in a larger calculation, True evaluates to numerical 1 and False evaluates to numerical 0 for use in the calculations.

## Square Brackets in CalcQuickBase Formulas

If you are using a CalcQuickBase object to add calculation support to your business object, then you must use strings as indexers on the CalcQuickBase instance to get and set values. These strings are referred to as the value's Name. If you need to use a Name in a formula, then you should enclose the string within brackets, [ ]. In step three of the code below, four names A, B, C, and D are registered. Notice that the formula entered in step two uses the values from A and B by enclosing these names in brackets.
{% highlight c# %}
[C#]



// 1) Instantiates a CalcQuickBase object.

calculator = New CalcQuickBase();



// 2) Populate your controls.

this.textBoxA.Text = "12";

this.textBoxB.Text = "3";

this.textBoxC.Text = "= [A] + 2 * [B]";



// Must enter formula names before turning on calculations.

// 3) Assigns formula object names.

calculator("A") = this.textBoxA.Text;

calculator("B") = this.textBoxB.Text;

calculator("C") = this.textBoxC.Text;

calculator("D") = this.textBoxD.Text;

{% endhighlight  %}
{% highlight vbnet %}

[VB]



' 1) Instantiates a CalcQuickBase object.

calculator = New CalcQuickBase()



' 2) Populate your controls.

Me.textBoxA.Text = "12"

Me.textBoxB.Text = "3"

Me.textBoxC.Text = "= [A] + 2 * [B]"    



' Must enter formula names before turning on calculations.

' 3) Assigns formula object names.

calculator("A") = Me.textBoxA.Text

calculator("B") = Me.textBoxB.Text

calculator("C") = Me.textBoxC.Text

calculator("D") = Me.textBoxD.Text
{% endhighlight %}

## Equal Sign, the Formula Character

To indicate that a particular string should be treated as a formula, you must start the string with a special character, CalcEngine.FormulaCharacter. This property is static (Shared in VB), so you can change the formula character within your code. It's default value is the equal sign, (=).

In general, in order for Essential Calculate to recognize a string as containing a formula; the string is required to start with the CalcEngine.FormulaCharacter. There is one exception though, if you explicitly call a CalcEngine Parse method like CalcEngine.ParseFormula or CalcEngine.ParseAndComputeFormula, including the formula character as the first character in the passed string, it is optional.

## Using Function Library Formulas

Function Library formulas may be used as a stand-alone formula, and they can be incorporated into more complex formulas.

_Function Library_

<table>
<tr>
<th>
Formula</th><th>
Comment</th></tr>
<tr>
<td>
= Sin(3.14159)</td><td>
Returns the sine of 3.14159 radians</td></tr>
<tr>
<td>
= 2 * Sin(3.14159) + Sqrt(2)      </td><td>
Returns 2 * sine of 3.14159 radians plus the square root of 2.</td></tr>
<tr>
<td>
  = 2 * Pi()       </td><td>
 Returns 2 * pi.</td></tr>
</table>
Some library functions may not have arguments but, you must still include the parentheses to indicate that you are using a library function. For example, = 2 * Pi(), shows the proper use of the library function Pi.

