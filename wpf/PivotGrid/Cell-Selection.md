---
layout: post
title: Cell Selection | PivotGrid | Wpf | Syncfusion
description: Cell Selection 
platform: wpf
control: PivotGrid
documentation: ug
---


# Cell Selection


PivotGrid for WPF supports excel like cell selection where you can select grid value cells as like in MS-Excel. On cell selection, an event called PivotGridSelectionChanged will be triggered and the PivotGridSelectionChangedEventArgs will return an IEnumerable collection of column, row and value of the corresponding selected cell. The EventArgs will also return the cell range and the selection reason like mousedown, mousemove, mouseup etc,.

### Use Case Scenarios

Using Cell Selection, you can select cells that can be copied to clipboard or notepad. You can perform custom operation on cell selection and also can bind any control based on the selected cell values.

### Adding Cell Selection 

The following code snippets show how to create a PivotGrid and to specify Cell Selection.

{% tabs %}
{% highlight xml %} 


<!--Adding PivotGrid and Enabling Cell Selection-->

<syncfusion:PivotGrid AllowSelection="True"> 

  <!--Adding PivotRows-->

   <syncfusion:PivotGridControl.PivotRows>

     <syncfusion:PivotItem FieldMappingName="Product" FieldHeader="Product" TotalHeader="Total"/>

     <syncfusion:PivotItem FieldMappingName="Date" FieldHeader="Date" TotalHeader="Total"/>

   </syncfusion:PivotGridControl.PivotRows>

   <!--Adding PivotColumns-->

   <syncfusion:PivotGridControl.PivotColumns>

     <syncfusion:PivotItem FieldMappingName="Country" FieldHeader="Country" TotalHeader="Total"/>

     <syncfusion:PivotItem FieldMappingName="State" FieldHeader="State" TotalHeader="Total"/>

   </syncfusion:PivotGridControl.PivotColumns>

   <!--Adding PivotCalculations-->

     <syncfusion:PivotGridControl.PivotCalculations>

       <syncfusion:PivotComputationInfo CalculationName = "Total" Description = "Summation of values" FieldName = "Amount" Format = "C" SummaryType="DoubleTotalSum"/>

       <syncfusion:PivotComputationInfo CalculationName = "Total" Description = "Summation of values" FieldName = "Quantity" Format = "#,##0"/>

     </syncfusion:PivotGridControl.PivotCalculations>

</syncfusion:PivotGrid>

{% endhighlight %} 


{% highlight C# %}  


// Instantiating PivotGridControl.

PivotGridControl pivotGridControl1 = new PivotGridControl();

// Adding PivotRows.

pivotGridControl1.PivotRows.Add(new PivotItem { FieldHeader = "Product" });

pivotGridControl1.PivotColumns.Add(new PivotItem { FieldHeader = "Date" });

// Adding PivotColumns.

pivotGridControl1.PivotColumns.Add(new PivotItem { FieldHeader = "Country" });

pivotGridControl1.PivotColumns.Add(new PivotItem { FieldHeader = "State" });

// Adding PivotCalculations.

pivotGridControl1.PivotCalculations.Add(new PivotComputationInfo { FieldName="Amount" , Format="C"});

pivotGridControl1.PivotCalculations.Add(new PivotComputationInfo { FieldName = "Quantity", Format = "#,##0" });

// Enable Cell Selection.

this.pivotGridControl1.AllowSelection = false;

{% endhighlight %} 



{% highlight vbnet %} 




' Instantiating PivotGridControl.

Dim pivotGridControl1 As PivotGridControl = New PivotGridControl()

' Adding PivotRows.

pivotGridControl1.PivotRows.Add(New PivotItem With {.FieldHeader = "Product"})

pivotGridControl1.PivotColumns.Add(New PivotItem With {.FieldHeader = "Date"})

' Adding PivotColumns.

pivotGridControl1.PivotColumns.Add(New PivotItem With {.FieldHeader = "Country"})

pivotGridControl1.PivotColumns.Add(New PivotItem With {.FieldHeader = "State"})

' Adding PivotCalculations.

pivotGridControl1.PivotCalculations.Add(New PivotComputationInfo With {.FieldName="Amount", .Format="C"})

pivotGridControl1.PivotCalculations.Add(New PivotComputationInfo With {.FieldName = "Quantity", .Format = "#,##0"})

' Enable Cell Selection.

Me.pivotGridControl1.AllowSelection = False

{% endhighlight %} 
{% endtabs %}

![](Features_images/Features_img14.png)



### Sample Link

..\..\ Syncfusion\BI\WPF\PivotAnalysis.WPF\Samples\Appearance\Cell Selection Demo

