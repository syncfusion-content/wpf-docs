---
layout: post
title: SummaryType
description: summarytype
platform: wpf
control: PivotGrid
documentation: ug
---

## SummaryType

SummaryType is an enumerator defined in the PivotComputationInfo class that is used to specify the type of the summary. The following table lists the various summary types that are used for performing calculations:

_Summar types table_

<table>
<tr>
<td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td></tr>
<tr>
<td>
DoubleTotalSum</td><td>
Computes the sum of double or integer values.</td></tr>
<tr>
<td>
DoubleAverage</td><td>
Computes the average of double or integer values.</td></tr>
<tr>
<td>
DoubleMaximum</td><td>
Computes the maximum of double or integer values.</td></tr>
<tr>
<td>
DoubleMinimum</td><td>
Computes the minimum of double or integer values.</td></tr>
<tr>
<td>
DoubleStandardDeviation</td><td>
Computes the standard deviation of double or integer values.</td></tr>
<tr>
<td>
DoubleVariance</td><td>
Computes the variance of double or integer values.</td></tr>
<tr>
<td>
Count</td><td>
Computes the count of double or integer values.</td></tr>
<tr>
<td>
DecimalTotalSum</td><td>
Computes the sum of decimal values.</td></tr>
<tr>
<td>
IntTotalSum</td><td>
Computes the sum of integer values.</td></tr>
<tr>
<td>
Custom</td><td>
Specifies that you are using a custom SummaryBase object to define the calculation.</td></tr>
<tr>
<td>
DisplayIfDiscreteValues</td><td>
Displays the aggregated value in the Pivot Computation column if all the values are aggregated to be same, else the PadString property value is displayed (By default, PadString property is set to “*”).</td></tr>
</table>  


### DisplayIfDiscreteValues Summary Type

DisplayIfDiscreteLevelsEqual is a new summary type that has been added to the PivotComputationInfo class of the Pivot Grid control. This summary type displays the  aggregated value in the Pivot Computation column if all the values are common, else the default value displayed is “*”.

You can also change the default  value to any custom string of your choice by using the PadString property.

#### Property

_Property Table_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td></tr>
<tr>
<td>
PadString</td><td>
You can use this property to specify a custom string in the Pivot Computation column instead of the cell’s original value. The default value is “*”.> {{ '_Note: The SummaryType enumerator must be set to DisplayIfDiscreteValuesEqual to use this property._' | markdownify }}</td></tr>
</table>


#### Code Sample

{% highlight xml %} 





<syncfusion:PivotComputationInfo FieldHeader="Amount" FieldName="Amount" Format="C" SummaryType="DisplayIfDiscreteValuesEqual" PadString="***"/>

{% endhighlight %} 

{% highlight C# %}  





// "DisplayIfDiscreteValuesEqual" Summary Type

PivotComputationInfo m_PivotComputationInfo = new PivotComputationInfo() { CalculationName = "Amount", FieldName = "Amount", 

SummaryType = SummaryType.DisplayIfDiscreteValuesEqual, PadString = "***" };

{% endhighlight %} 

{% highlight vbnet %}





’ "DisplayIfDiscreteValuesEqual" Summary Type

Dim m_PivotComputationInfo As PivotComputationInfo = New PivotComputationInfo() With {.CalculationName="Amount", .FieldName="Amount", .SummaryType= SummaryType. DisplayIfDiscreteValuesEqual, .PadString = "***" }


 {% endhighlight %} 
 
#### Screenshot

![](Concepts_images/Concepts_img7.png)



_DisplayIfDiscreteValues Summary Type Illustrated_

#### Sample Location

{InstallationDrive}:\Users\{UserName}\AppData\Local\Syncfusion\EssentialStudio\11.1.0.9\Wpf \PivotAnalysis.Wpf\ Summaries\CustomSummaries Demo

### DisplayIfDiscreteValues Summary Type in Numeric Format

This feature lets users provide an optional value like 999, 99, or 1000 to represent a discrete value. This will behave like the DisplayIfDiscreteValuesEqual summary type but it will carry a number format instead of characters to represent the aggregate values. The user can assign certain fields to be in a number format instead of the PadString displaying a special character, e.g., 999 instead of ***.

#### Use Case Scenario

Users can perform calculations using the numeric format assigned to a field when it is exported to Excel. Previously the summary type of “DisplayIfDiscreteValue” was always treated as a string which on exported to excel, user cannot perform any calculations since it had string format assigned for the field.

#### Property

_Property Table_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Data Type**' | markdownify }}</td></tr>
<tr>
<td>
PadString</td><td>
Gets or sets the PadString for the discrete value in numeric format to display.</td><td>
Normal</td><td>
string</td></tr>
</table> 


#### Adding DisplayIfDiscreteValues Summary Type in Numeric Format in an Application 

To enable the DisplayIfDiscreteValues summary type in numeric format in an application, we need to set a numerical value to the property PadString. For example, PadString=”999”

The following code sample explains how to set PadString to display the discrete value in a numerical format. It can be set by XAML or C# code.

{% highlight xml %} 





<syncfusion:PivotComputationInfo FieldHeader="Amount" FieldName="Amount" Format="C" SummaryType="DisplayIfDiscreteValuesEqual" PadString="999"/>

 {% endhighlight %}

{% highlight C# %}  





// DisplayIfDiscreteValuesEqual Summary Type

PivotComputationInfo m_PivotComputationInfo = new PivotComputationInfo() { CalculationName = "Amount", FieldName = "Amount", 

SummaryType = SummaryType.DisplayIfDiscreteValuesEqual, PadString = "999" };

{% endhighlight %} 


{% highlight vbnet %} 





’ DisplayIfDiscreteValuesEqual Summary Type

Dim m_PivotComputationInfo As PivotComputationInfo = New PivotComputationInfo() With {.CalculationName="Amount", .FieldName="Amount", .SummaryType= SummaryType. DisplayIfDiscreteValuesEqual, .PadString = "999" }

{% endhighlight %} 


![](Concepts_images/Concepts_img8.png)



_DisplayIfDiscreteValues Summary Type in Numeric Format_

#### Sample Location

{Installation Drive}:\Users\{UserName}\AppData\Local\Syncfusion\EssentialStudio\11.4.0.20\Wpf \PivotAnalysis.Wpf\Summaries\CustomSummaries Demo



