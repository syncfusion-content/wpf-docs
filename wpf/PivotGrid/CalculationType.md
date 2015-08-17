---
layout: post
title: CalculationType
description: calculationtype
platform: wpf
control: PivotGrid
documentation: ug
---

## CalculationType

CalculationType is an enumerator defined in the PivotComputationInfo class that is used to specify the type of the calculation. The following table lists the various calculation types that are used for performing calculations:

_CalculationType table_

<table>
<tr>
<td>
{{ '**CalculationType**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td></tr>
<tr>
<td>
NoCalculation</td><td>
Removes the custom calculation and restore to original values (Default value). Displays the pivot values as default value.</td></tr>
<tr>
<td>
PercentageOfGrandTotal</td><td>
Displays a value cell as a percentage of grand total of all value cells of Pivot Engine.</td></tr>
<tr>
<td>
PercentageOfColumnTotal</td><td>
Displays all value cells in each column as a percentage of its corresponding column total.</td></tr>
<tr>
<td>
PercentageOfRowTotal</td><td>
Displays all value cells in each row as a percentage of its corresponding row total.</td></tr>
<tr>
<td>
PercentageOfParentColumnTotal</td><td>
Displays a value cell as a percentage of parent column item values</td></tr>
<tr>
<td>
PercentageOfParentRowTotal</td><td>
Displays a value cell as a percentage of parent row item values.</td></tr>
<tr>
<td>
PercentageOfParentTotal</td><td>
Displays a value cell as a percentage of Base Field (Parent Row/Column Total).</td></tr>
<tr>
<td>
Index</td><td>
Displays a value cell as an index value based on PivotEngine generation.</td></tr>
<tr>
<td>
Formula</td><td>
Displays a calculation based on a well formed algebraic expression involving other calculations.</td></tr>
<tr>
<td>
PercentageOf</td><td>
Displays values as a percentage of the value of the Base item in the Base field.</td></tr>
<tr>
<td>
DifferenceFrom</td><td>
Displays values as the difference from the value of the Base item in the Base field.</td></tr>
<tr>
<td>
PercentageOfDifferenceFrom</td><td>
Displays values as the percentage difference from the value of the Base item in the Base field.</td></tr>
<tr>
<td>
RunningTotalIn</td><td>
Displays the value for successive items in the Base field as a running total.</td></tr>
<tr>
<td>
PercentageOfRunningTotalIn</td><td>
Calculates the value for successive items in the Base field that are displayed as a running total as a percentage.</td></tr>
<tr>
<td>
RankSmallestToLargest</td><td>
Displays the rank of selected values in a specific field, listing the smallest item in the field as 1, and each larger value with higher rank value.</td></tr>
<tr>
<td>
RankLargestToSmallest</td><td>
Displays the rank of selected values in a specific field, listing the largest item in the field as 1, and each smaller value with higher rank value</td></tr>
</table>


### Adding CalculationType in Application

By default, the value of CalculationType is NoCalculation. To change the CalculationType, you can use the following code examples.

#### Through XAML

1. First you need to add PivotGridControl by using syncfusion:PivotGridControl class.
2. Then, create new PivotItem by using PivotGridControl.PivotComputationInfo class.
3. Finally define the CalculationType for PivotCalculation by using CalculationType property.



{% highlight xml %} 

[XAML]

<Grid>

        <!--Adding PivotGrid Control-->

        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="PivotGridControl1" VerticalAlignment="Top"                                      ItemSource="{Binding Source={StaticResource data}}" >



<syncfusion:PivotComputationInfo FieldHeader="Amount" FieldName="Amount" Format="C" SummaryType="DoubleTotalSum" CalculationType="PercentageOfParentColumnTotal" />



</syncfusion:PivotGridControl>

</Grid>

{% endhighlight %} 

#### Through Code Behind

1. First you need to create a new PivotGridControl by using PivotGridControl class in Window_Loaded() event handler.
2. Then, create a new PivotItem by using PivotComputationInfo class in PivotGridControl.
3. Finally set CalculationType property for PivotCalculations as follows.
4. Add PivotCalculation into PivotGridControl.



{% highlight C# %}   

[C#]

protected void Window_Loaded(object sender, RoutedEventArgs e)

{

    Syncfusion.Windows.Controls.PivotGrid.PivotGridControl PivotGrid1 = new Syncfusion.Windows.Controls.PivotGrid.PivotGridControl();   



// "PercentageOfParentColumnTotal” CalculationType

PivotComputationInfo m_PivotComputationInfo = new PivotComputationInfo() { CalculationName = "Amount", FieldName = "Amount", 

CalculationType = CalculationType.PercentageOfParentColumnTotal };

// Adding PivotComputationInfo to PivotCalculations

this.pivotGrid1.PivotCalculations.Add(m_PivotComputationInfo);

}

{% endhighlight %}

{% highlight vbnet %} 

[VB]



Protected Sub Window_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)

Dim PivotGrid1 As New Syncfusion.Windows.Controls.PivotGrid.PivotGridControl()



' "PercentageOfParentColumnTotal" CalculationType

Dim m_PivotComputationInfo As PivotComputationInfo = New PivotComputationInfo()With {.CalculationName="Amount",.FieldName="Amount", . CalculationType = CalculationType.PercentageOfParentColumnTotal }

' Adding PivotComputationInfo to PivotCalculations

Me.pivotGrid1.PivotCalculations.Add(m_PivotComputationInfo)

End Sub


{% endhighlight %} 


![](Concepts_images/Concepts_img6.png)



_PivotValues as PercentageOfParentColumnTotal calculation_
