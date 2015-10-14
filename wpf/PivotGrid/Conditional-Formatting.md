---
layout: post
title: Conditional Formatting | PivotGrid | Wpf | Syncfusion
description: Conditional Formatting
platform: wpf
control: PivotGrid
documentation: ug
---


# Conditional Formatting

Conditional formatting is the process of applying customized styles to any object based on specified conditions. Conditional Formatting for
PivotGrid WPF allows you to format Grid cells based on specified conditions. This can be achieved by defining PivotGridDataConditionalFormat 
for the Grid, which allows you to specify the criteria for filtering the cells and the style to be applied to the filtered cells. After the 
specifications are defined, the styles are applied only to the cells that fulfil the specified conditions. Conditional Formatting can be 
specified by using the PivotGridControl.ConditionalFormats property, which is an observable collection of type PivotGridDataConditionalFormat. 


The criteria for filtering the cells are specified by using the PivotGridDataConditionalFormat.Conditions property, which is a collection of PivotGridDataCondition objects. The Style for each ConditionalFormat can be specified by using the PivotGridDataConditionalFormat.CellStyle property, which should be of type PivotGridCellStyle.

### Use Case Scenarios

Conditional Formatting can be used in Marketing software to help users easily trace the product sales rate for different regions. 

![C:/Users/dwarageshmb/Desktop/Vol 4 Docs/Images/PivotGrid CF.png](Features_images/Features_img10.png)


## Adding Conditional Formatting

Conditional Formatting can be added to code behind and XAML, as shown in the following code snippets. 

{% tabs %}
{% highlight xml %} 


  <!--Specifying PivotRows.-->

            <syncfusion:PivotGridControl.PivotRows>

                <syncfusion:PivotItem FieldMappingName="Product" TotalHeader="Total"/>

                <syncfusion:PivotItem FieldMappingName="Date" TotalHeader="Total"/>

            </syncfusion:PivotGridControl.PivotRows>

            <!--Specifying PivotColumns.-->

            <syncfusion:PivotGridControl.PivotColumns>

                <syncfusion:PivotItem FieldMappingName="Country" TotalHeader="Total"/>

                <syncfusion:PivotItem FieldMappingName="State" TotalHeader="Total"/>

            </syncfusion:PivotGridControl.PivotColumns>

            <!--Specifying PivotCalculationValues.--> 

            <syncfusion:PivotGridControl.PivotCalculations>

                <syncfusion:PivotComputationInfo FieldName="Amount" Format="C" SummaryType="DoubleTotalSum"/>

                <syncfusion:PivotComputationInfo FieldName="Quantity" Format="#,##0"/>

            </syncfusion:PivotGridControl.PivotCalculations>



	<syncfusion:PivotGrid.ConditionalFormats> 

	<!-- Adding Conditions. -->                       

	<syncfusion:PivotGridDataConditionalFormat Name="C1">

	<!-- Specifying the Cell Style. -->

	<syncfusion:PivotGridDataConditionalFormat.CellStyle>

	<syncfusion:PivotGridCellStyle Background="Green" FontFamily="Calibri" FontSize="12"/>

	</syncfusion:PivotGridDataConditionalFormat.CellStyle>

	<!-- Specifying Conditions. --> 

	<syncfusion:PivotGridDataConditionalFormat.Conditions>

	<syncfusion:PivotGridDataCondition ConditionType="GreaterThan" Value="5000000" MeasureElement="Amount" PredicateType="And"/>

	</syncfusion:PivotGridDataConditionalFormat.Conditions>

	</syncfusion:PivotGridDataConditionalFormat>

	<syncfusion:PivotGridDataConditionalFormat Name="C2">

	<!-- Specifying the Cell Style. -->

	<syncfusion:PivotGridDataConditionalFormat.CellStyle>

	<syncfusion:PivotGridCellStyle Background="Red" FontFamily="Calibri" FontSize="12"/>

	</syncfusion:PivotGridDataConditionalFormat.CellStyle>

	<!-- Specifying Conditions. --> 

	<syncfusion:PivotGridDataConditionalFormat.Conditions>

	<syncfusion:PivotGridDataCondition ConditionType="LessThan" Value="100000

	" MeasureElement="Amount" PredicateType="And"/>

	</syncfusion:PivotGridDataConditionalFormat.Conditions>

	</syncfusion:PivotGridDataConditionalFormat>           

	</syncfusion:PivotGrid.ConditionalFormats>

{% endhighlight %} 



{% highlight C# %} 


// Specifying PivotGridDataConditionalFormat.

PivotGridDataConditionalFormat conditionalFormat1 = new PivotGridDataConditionalFormat();

// Adding Conditions to PivotGridDataConditionalFormat.

conditionalFormat1.Conditions.Add(new PivotGridDataCondition() { 

ConditionType= PivotGridDataConditionType.GreaterThan , 

MeasureElement="Amount",

Value="5000000",

PredicateType = PredicateType.And });



// Specifying the Cell Style.

conditionalFormat1.CellStyle = new PivotGridCellStyle() { Background= Brushes.Green, FontFamily = new FontFamily("Calibri"), FontSize=12 

};





// Specifying PivotGridDataConditionalFormat.

PivotGridDataConditionalFormat conditionalFormat2 = new PivotGridDataConditionalFormat();

// Adding Conditions to PivotGridDataConditionalFormat.

conditionalFormat2.Conditions.Add(new PivotGridDataCondition() { 

ConditionType= PivotGridDataConditionType.LessThan , 

MeasureElement="Amount",

Value="100000",

PredicateType = PredicateType.And });



// Specifying the Cell Style.

conditionalFormat2.CellStyle = new PivotGridCellStyle() { Background= Brushes.Red, FontFamily = new FontFamily("Calibri"), FontSize=12 

};





// Adding Conditions to PivotGrid.

this.PivotGrid1.ConditionalFormats.Add(conditionalFormat1);

this.PivotGrid1.ConditionalFormats.Add(conditionalFormat2);

 {% endhighlight %} 



{% highlight vbnet %}  


' Specifying PivotGridDataConditionalFormat.

Dim conditionalFormat1 As PivotGridDataConditionalFormat = New PivotGridDataConditionalFormat()

' Adding Conditions to PivotGridDataConditionalFormat.

conditionalFormat1.Conditions.Add(New PivotGridDataCondition() With {.ConditionType= PivotGridDataConditionType.GreaterThan, .MeasureElement="Amount", .Value="5000000", .PredicateType = PredicateType.And})



' Specifying the Cell Style.

conditionalFormat1.CellStyle = New PivotGridCellStyle()

Dim TempFontFamily As FontFamily = New FontFamily("Calibri"), FontSize=12

Brushes.Green, FontFamily = New FontFamily("Calibri"), FontSize

Background= Brushes.Green, FontFamily



' Specifying PivotGridDataConditionalFormat.

Dim conditionalFormat2 As PivotGridDataConditionalFormat = New PivotGridDataConditionalFormat()

' Adding Conditions to PivotGridDataConditionalFormat.

conditionalFormat2.Conditions.Add(New PivotGridDataCondition() With {.ConditionType= PivotGridDataConditionType.GreaterThan, .MeasureElement="Amount", .Value="100000", .PredicateType = PredicateType.And})



' Specifying the Cell Style.

conditionalFormat2.CellStyle = New PivotGridCellStyle()

Dim TempFontFamily As FontFamily = New FontFamily("Calibri"), FontSize=12

Brushes.Red, FontFamily = New FontFamily("Calibri"), FontSize

Background= Brushes.Red, FontFamily





' Adding Conditions to PivotGrid.

Me.PivotGrid1.ConditionalFormats.Add(conditionalFormat1)

Me.PivotGrid1.ConditionalFormats.Add(conditionalFormat2)

{% endhighlight %}
{% endtabs %}


![C:/Users/dwarageshmb/Desktop/Vol 4 Docs/Images/PivotGrid CF.png](Features_images/Features_img11.png)



### Sample Link

A sample application that illustrates Conditional Formatting is distributed along with the Essential PivotGrid WPF installation and can be found at:

..\Syncfusion\BI\WPF\PivotAnalysis.WPF\Samples\Appearance\ Conditional Formatting Demo.

To access a Conditional Formatting sample:

1. Open the Syncfusion Dashboard. 
2. Click Business Intelligence.
3. Click the WPF drop-down list, and then select Explore Samples. 
4. Navigate to PivotAnalysis.WPF -> Samples -> Appearance -> Conditional Formatting Demo. 

