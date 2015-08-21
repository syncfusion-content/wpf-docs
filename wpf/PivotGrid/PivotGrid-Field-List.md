---
layout: post
title: PivotGrid Field List
description: PivotGrid Field List
platform: wpf
control: PivotGrid
documentation: ug
---


# PivotGrid Field List

With the current implementation of ‘Grouping bar, users cannot add or delete items in it. The Delete operation can be easily performed using the context menu, but in case of adding an item there should be a separate window, which should hold the fields present in the Item Source. In order to achieve this, a window called PivotGrid Field List is available in PivotGrid control, which is bound to a collection of PivotItems defined in the PivotFields property of PivotGridControl. 

### Use Case Scenarios

This feature will be useful for applications that need to configure PivotGrid at run-time, that is to add/remove items to/from PivotGrid at run-time

### Adding PivotGrid Field List

PivotGrid Field List (or Dynamic Field List ) can be launched by setting the ShowFieldList property to true or by clicking on the ShowFieldList menu item of Grouping bar context menu. PivotGrid Field List is bound to PivotFilelds property of PivotGridControl, which is a collection of  PivotItems. PivotFields can be added via code-behind and XAML, as shown in the following code snippets. 

{% highlight xml %} 

        <syncfusion:PivotGridControl ShowFieldList="True"

           <!--Specifying PivotRows-->

            <syncfusion:PivotGridControl.PivotRows>

                <syncfusion:PivotItem FieldMappingName="Product" TotalHeader="Total"/>

                <syncfusion:PivotItem FieldMappingName="Date" TotalHeader="Total"/>

             </syncfusion:PivotGridControl.PivotRows>

            <!--Specifying PivotColumns-->

            <syncfusion:PivotGridControl.PivotColumns>

                <syncfusion:PivotItem FieldMappingName="Country" TotalHeader="Total"/>

            </syncfusion:PivotGridControl.PivotColumns>

            <!--Specifying PivotCalculationValues--> 

            <syncfusion:PivotGridControl.PivotCalculations>

                <syncfusion:PivotComputationInfo FieldName="Amount" Format="C" SummaryType="DoubleTotalSum"/>

                <syncfusion:PivotComputationInfo FieldName="Quantity" Format="#,##0"/>

            </syncfusion:PivotGridControl.PivotCalculations>

            <!--Specifying Pivot Fields--> 

               <syncfusion:PivotGridControl.PivotFields>

                <syncfusion:PivotItem FieldMappingName="State" FieldHeader="State" TotalHeader="Total"/>

            </syncfusion:PivotGridControl.PivotFields>

                   </syncfusion:PivotGridControl>


{% endhighlight %} 


{% highlight C# %}  


  /// Adding Pivot Columns

            this.pivotGrid1.PivotColumns.Add(new PivotItem() { FieldHeader="Country", FieldMappingName="Country",TotalHeader="Total" });

            /// Adding Pivot Rows

            this.pivotGrid1.PivotRows.Add(new PivotItem() { FieldHeader = "Product", FieldMappingName = "Product", TotalHeader = "Total" });

            this.pivotGrid1.PivotRows.Add(new PivotItem() { FieldHeader = "Date", FieldMappingName = "Date", TotalHeader = "Total" });

            /// Adding Pivot Calculations

            this.pivotGrid1.PivotCalculations.Add(new PivotComputationInfo() { FieldName="Amount", SummaryType= SummaryType.DoubleTotalSum, Format="C" });

            this.pivotGrid1.PivotCalculations.Add(new PivotComputationInfo() { FieldName="Quantity", Format="#,###" });

            /// Adding Pivot Fields

            this.pivotGrid1.PivotFields.Add(new PivotItem() { FieldHeader="State", FieldMappingName="State" }); 

            /// Displaying Field List

            this.pivotGrid1.ShowFieldList = true;


{% endhighlight %} 


{% highlight vbnet %} 


            ' Adding Pivot Columns

            Me.pivotGrid1.PivotColumns.Add(New PivotItem() With {.FieldHeader = "Country", .FieldMappingName = "Country", .TotalHeader = "Total"})

            ' Adding Pivot Rows

            Me.pivotGrid1.PivotRows.Add(New PivotItem() With {.FieldHeader = "Product", .FieldMappingName = "Product", .TotalHeader = "Total"})

            Me.pivotGrid1.PivotRows.Add(New PivotItem() With {.FieldHeader = "Date", .FieldMappingName = "Date", .TotalHeader = "Total"})

            ' Adding Pivot Calculations

            Me.pivotGrid1.PivotCalculations.Add(New PivotComputationInfo() With {.FieldName = "Amount", .SummaryType = SummaryType.DoubleTotalSum, .Format = "C"})

            Me.pivotGrid1.PivotCalculations.Add(New PivotComputationInfo() With {.FieldName = "Quantity", .Format = "#,###"})

            ' Adding Pivot Fields

            Me.pivotGrid1.PivotFields.Add(New PivotItem() With {.FieldHeader = "State", .FieldMappingName = "State"})

            ' Displaying Field List

            Me.pivotGrid1.ShowFieldList = True

{% endhighlight %} 



![Description: C:/Users/dwarageshmb/Desktop/2011 Vol 1 Docs/PivotGrid Field List.png](Features_images/Features_img19.png)



#### Properties

PivotGridControl Table

<table>
    <tr>
        <th>{{ '**Property**' | markdownify }}</th>
		<th>{{ '**Description**' | markdownify }}</th>
		<th>{{ '**Type**' | markdownify }}</th>
		<th>{{ '**Data Type**' | markdownify }}</th>
		<th>{{ '**Reference links**' | markdownify }}</th>
	</tr>
	
    <tr>
        <td>PivotFields</td>
		<td>Gets the collection of PivotItems to be displayed in FieldList</td>
		<td>Normal</td>
		<td>ObservableCollection</td>
		<td>NA</td>
    </tr>
	
    <tr>
        <td>ShowFieldList</td>
		<td>Gets or sets a value indicating whether to display FieldList</td>
		<td>Dependency</td>
		<td>bool</td>
		<td>NA</td>
    </tr>
</table>

GroupingBar Table

<table>
	<tr>
		<th>{{ '**Property**' | markdownify }}</th>
		<th>{{ '**Description**' | markdownify }}</th>
		<th>{{ '**Type**' | markdownify }}</th>
		<th>{{ '**Data Type**' | markdownify }}</th>
		<th>{{ '**Reference links**' | markdownify }}</th>
	</tr>
	<tr>
		<td>FieldList</td>
		<td>Gets the field list, which is used to add items into the Grouping Bar</td>
		<td>Normal</td>
		<td>Window</td>
		<td>NA</td>
	</tr>
	<tr>
		<td>FieldListBorderBrush</td>
		<td>Gets or sets the Border brush for Field List</td>
		<td>Dependency</td>
		<td>Brush</td>
		<td>NA</td>
	</tr>
</table>

### Sample Link

To access a Conditional Formatting sample

1. Open the Syncfusion Dashboard. 
2. Click Business Intelligence.
3. Click the WPF drop-down list, and select Explore Samples. 
4. Navigate to PivotAnalysis.WPF -> Samples -> Field List -> Field List Demo.

