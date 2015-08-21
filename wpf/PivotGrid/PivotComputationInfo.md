---
layout: post
title: PivotComputationInfo
description: pivotcomputationinfo
platform: wpf
control: PivotGrid
documentation: ug
---

# PivotComputationInfo

This class holds the information needed for calculations that appear in a PivotGrid. For each calculation, there is an associated 
PivotComputationInfo object that is added to the PivotCalculations collection. The properties available in PivotComputationInfo are as follows.

Properties Table

<table>
<tr>
<th>
{{ '**Property Name**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
Value it Accepts</th><th>
Reference link</th></tr>
<tr>
<td>
CalculationName</td><td>
Gets or sets what is displayed in the Pivot table if more than one calculation is included in the PivotGrid.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Description</td><td>
Gets or sets the description of the calculation.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
FieldName</td><td>
Gets or sets the name of the property to be used in this calculation.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Format</td><td>
Gets of sets the format string to be used, to format the calculation results in the PivotGrid.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
Summary</td><td>
Gets or sets the SummaryBase object that is used to define this calculation. This value is automatically set when you specify any non-custom value of SummaryType; when you specify SummaryType.Custom, then you are required to set Summary to be an instance of your custom SummaryBase-derived object.</td><td>
SummaryBase</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
SummaryType</td><td>
Gets or sets the SummaryType enumeration for this calculation. You can set some enumeration value to the summary type, otherwise by default it is set as Custom.</td><td>
SummaryType</td><td>
DoubleTotalSumDoubleAverageDoubleMaximumDoubleMinimumDoubleStandardDeviationDoubleVarianceCountDecimalTotalSumIntTotalSumCustomDisplayIfDiscreteValues</td><td>
SummaryType</td></tr>
<tr>
<td>
DisplayOption</td><td>
Gets or sets the values to be displayed in PivotEngine</td><td>
DisplayOption</td><td>
NoneCalculationsSummaryGrandTotalsAll</td><td>
DisplayOption</td></tr>
<tr>
<td>
CalculationType</td><td>
Used to define how to make the computational objects in Grid visible.</td><td>
CalculationType</td><td>
NoCalculationPercentageOfParentTotalPercentageOfGrandTotalPercentageOfColumnTotalPercentageOfRowTotalPercentageOfParentColumnTotalPercentageOfParentRowTotalIndexFormulaPercentageOfDifferenceFromPercentageOfDifferenceFromRunningTotalInPercentageOfRunningTotalInRankLargestToSmallestRankSmallestToLargest</td><td>
CalculationType</td></tr>
</table> 


## Defining PivotComputationInfo in XAML and Code-Behind

PivotComputationInfo can be defined in XAML as well as in C# or VB code.

### Through XAML

1. To define the Pivot Item, you can add the PivotGridControl using the Syncfusion:PivotGridControl class.
2. Create a new PivotItem using PivotGridControl.PivotComputationInfo class.



 {% highlight xml %} 
 

<Grid>

        <!—Adding PivotGrid Control-->

        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="PivotGridControl1" VerticalAlignment="Top" 

                                     ItemSource="{Binding Source={StaticResource data}}" >

<!--Defining Pivot Calculations -->

   <syncfusion:PivotGridControl.PivotCalculations>

     <!--Adding PivotComputationInfo to PivotCalculations-->

     <syncfusion:PivotComputationInfo CalculationName = "Total" FieldName =   

     "Quantity" SummaryType="Count"/>

   </syncfusion:PivotGridControl.PivotCalculations>

  </syncfusion:PivotGridControl

</Grid>

{% endhighlight %} 

Through Code Behind

1. To define the PivotItem, create a new PivotGridControl using the PivotGridControl class in Window_Loaded() event handler method.
2. Create new PivotItem using the PivotComputationInfo class in PivotGridControl.



{% highlight C# %}  



protected void Window_Loaded(object sender, RoutedEventArgs e)

{

    Syncfusion.Windows.Controls.PivotGrid.PivotGridControl PivotGrid1 = new Syncfusion.Windows.Controls.PivotGrid.PivotGridControl ();   

// Defining PivotComputationInfo

PivotComputationInfo m_PivotComputationInfo = new PivotComputationInfo() { CalculationName="Amount", FieldName="Amount", SummaryType= SummaryType.Count };

// Adding PivotComputationInfo to PivotCalculations

this.pivotGrid1.PivotCalculations.Add(m_PivotComputationInfo);

}

{% endhighlight %} 


{% highlight vbnet %} 


Protected Sub Window_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)

Dim PivotGrid1 As New Syncfusion.Windows.Controls.PivotGrid.PivotGridControl()

' Defining PivotComputationInfo

Dim m_PivotComputationInfo As PivotComputationInfo = New PivotComputationInfo() With {.CalculationName="Amount", .FieldName="Amount", .SummaryType= SummaryType.Count}

' Adding PivotComputationInfo to PivotCalculations

Me.pivotGrid1.PivotCalculations.Add(m_PivotComputationInfo)

End Sub
{% endhighlight %} 


## Format String in PivotComputationInfo

The PivotComputationInfo property replaces each format specification in a specified string with the textual equivalent of a corresponding value.

{% highlight xml %} 




<!—Decimal Format-->

<syncfusion:PivotComputationInfo CalculationName = "Total" FieldName =   

   "Quantity" SummaryType="Count" Format = "0.00"/>

{% endhighlight %} 



{% highlight C# %} 




// Decimal Format

PivotComputationInfo m_PivotComputationInfo = new PivotComputationInfo() { CalculationName="Total", FieldName="Quantity", SummaryType= SummaryType.Count, Format="0.00"};



 {% endhighlight %} 

{% highlight vbnet %} 




' Decimal Format

Dim m_PivotComputationInfo As PivotComputationInfo = New PivotComputationInfo() With {.CalculationName="Total", .FieldName="Quantity", .SummaryType= SummaryType.Count, .Format="0.00"}

{% endhighlight %} 

### Types of format settings

Formats Table

<table>
<tr>
<th>
{{ '**Format**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th></tr>
<tr>
<td>
0.00</td><td>
Decimal</td></tr>
<tr>
<td>
C</td><td>
Currency</td></tr>
<tr>
<td>
#,##0</td><td>
Thousand Separator</td></tr>
<tr>
<td>
# ' degrees'</td><td>
Literal String Specifier</td></tr>
<tr>
<td>
D</td><td>
Long Date</td></tr>
</table> 


