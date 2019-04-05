---
layout: post
title: Custom Function | Calculate | Syncfusion Essential WPF
description: This section describes that how to add and remove the user defined function for wpf/Syncfusion essential calculate
platform: wpf
control: Calculate
documentation: ug
---

# Custom Function

Essential Calculate holds many functions from statistics, finance and mathematics, along with other general purpose functions. There are
more than 400+ entries in the library. Also, it is easy to add the own calculations with custom functions.

## LibraryFunction

A property which holds the collection of library functions in Essential Calculate is [LibraryFunctions](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~LibraryFunctions.html). The function name in the library should only contain letters, digits or underscore. The function name serves as the hash key and the function delegate serves as the hash value.

## Add Custom Function

Adding a custom function to the Formula Library in Essential Calculate is a two step process. The first step is to write a method that actually does the calculation work for your
custom function. The second step is to register this method with the [CalcEngine](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine.html). So, when the `CalcEngine` object is a member of an application, the additional
function methods can be added to the application and then these methods should be registered with the `CalcEngine` object after the object is created.

### Write a method

The method must have the signature specified by the delegate, [LibraryFunction](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine+LibraryFunction.html). The method must accept a string argument and returns a string value. 

For writing a custom formula method, any convention with respect to passing arguments can be used within the implementation code. Thus, arguments can be a single entry 
like A1 or 153 or it can be more complex like A1:C15. The computed value will be returned as a string. The arguments can be enhanced with standard items like cell references, 
numbers, other formulas, etc., using the parsing tools of `CalcEngine` to minimize the amount of code that is required to be written.

Below code example shows implementing the custom function of computing minimum value,

{% tabs %}
{% highlight c# %}

public string CustomMin(string args)
{
  double min = double.MaxValue;
  double d;
  var splitArgs = args.Split(new char[] { CalcEngine.ParseArgumentSeparator });
  foreach (string s in splitArgs)
  {
     if (double.TryParse(s, NumberStyles.Number | NumberStyles.AllowExponent, null, out d))
         min = Math.Min(min, d);
  }
}

{% endhighlight %}
{% endtabs %}

### Register the method with CalcEngine

The second step for adding the own formula is to register the custom method with the `CalcEngine` object. This is done with the help of [AddFunction](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~AddFunction.html) method of `CalcEngine` which accepts the string that is used when you refer the function, and the second argument is a delegate for method name. The only requirement here is that the function name should 
start with an alpha character and should only contain alpha-numeric characters. Additionally, the string cannot be the name of any existing library function.

{% tabs %}
{% highlight c# %}

//Class derived from ICalcData,
CalcData calcData = new CalcData();

CalcEngine engine = new CalcEngine(calcData);

//Adding custom function to the library with user defined formula name,
engine.AddFunction("CheckMin", new LibraryFunction(CustomMin));

{% endhighlight %}
{% endtabs %}

### Compute the Custom Function

To compute the custom formula, you need to pass the registered custom formula in `PareAndComputeFormula` method of `CalcEngine`.

{% tabs %}
{% highlight c# %}

//Set value 100 to variable "A1"
calcData.SetValueRowCol(100, 1, 1);

//Set value 200 to variable "B1"
calcData.SetValueRowCol(200, 1, 2);

//Set value 300 to variable "C1"
calcData.SetValueRowCol(300, 1, 2);

//compute the registered method using CalcEngine.
var r = engine.ParseAndComputeFormula("=CustomMin(A1,B1,C1)");

{% endhighlight %}
{% endtabs %}

## Remove Custom Function

To remove a single function from the Function Library, use [RemoveFunction](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~RemoveFunction.html) method of `CalcEngine`, passing a formula name as the string that references this function and to remove all functions, you can clear the hash table that holds them by using the `Clear` method of `LibraryFunction`.

{% tabs %}
{% highlight c# %}

//To remove a single function from library,
engine.RemoveFunction("CheckMin");

//To remove all functions from library,
engine.LibraryFunctions.Clear();

{% endhighlight %}
{% endtabs %}

## Replace Function

To replace a function with another implementation, remove the original name and add the same name again with a different method name.

{% tabs %}
{% highlight c# %}

// Remove formula name "CheckMin" from the library,
 engine.RemoveFunction("CheckMin");

//Adds formula name "Minimum" to the library,
engine.AddFunction("Minimum", new LibraryFunction(CustomMin));

{% endhighlight %}
{% endtabs %}


T> Removing unused functions from the Function Library, **reduces the memory usage and speeds up parsing** as well. Also, if you are only 
using a selected few Library functions, you may want to remove the unused ones. This can be done using the `Clear` method of `LibraryFunction`.
and after clearing all functions, you can add few functions that will be used often by using `AddFunction` method of `CalcEngine`.