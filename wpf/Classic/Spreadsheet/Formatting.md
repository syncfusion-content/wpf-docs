---
layout: post
title: Formatting in WPF Wizard Control control | Syncfusion
description: Learn here all about Formatting support in Syncfusion WPF SpreadsheetControl (Classic) control and more.
platform: wpf
control: Spreadsheet
documentation: ug
---

# Formatting in WPF SpreadsheetControl (Classic)

## Conditional Formatting 

Conditional formatting is a feature by which cell styles will be dynamically formatted based on its value and specified condition. It enables you to apply formatting to the cell through a dialog window. 

### Use Case Scenarios 

This feature enables you to categorize the cell for analysis.  For example, you can format a time sheet, to point out the overtime obtained by an employee. You can also use it to track the best sales employees in the company, by setting a quota that makes a cell range particular.

### Defining Condition for Spreadsheet Cells

You can define the condition for formatting the Spreadsheet cells using a conditional formatting dialog box. Specify the conditional value and style format in the dialog box. You can open the conditional formatting dialog using the ConditionalFormatCommand. Based on the Command parameter one of the following dialogs will open:

* Greater than

![Formatting_img1](Formatting_images/Formatting_img1.png)

* Less Than

![Formatting_img2](Formatting_images/Formatting_img2.png)

* Between

![Formatting_img3](Formatting_images/Formatting_img3.png)

* Equal to 

![Formatting_img4](Formatting_images/Formatting_img4.png)

The following code illustrates how to bind the ConditionalFormatCommand to a button: 

{% highlight xaml %}

<Button Command="{Binding Path=ConditionalFormatCommand}">

	<Button.CommandParameter>

		<XlsIO:ExcelComparisonOperator>Greater</XlsIO:ExcelComparisonOperator>

	</Button.CommandParameter>

</Button>

{% endhighlight %}

![Formatting_img5](Formatting_images/Formatting_img5.png)

## Number formatting

Number formatting helps you to control the format of the number in Spreadsheet cells. Number in the cell will be displayed based on the number format applied. 

### Defining number formatting for Spreadsheet Cells

You can define the number formatting using the NumberFormattingCommand. Number formatting will be applied to the Spreadsheet cells based on the command parameter. The following code illustrates this:

{% highlight xaml %}

<Button Command="{Binding Path=NumberFormatCommand}" Grid.Row="2">

	<Button.CommandParameter>

		<System:String>0.00%</System:String>

	</Button.CommandParameter>

</Button>

{% endhighlight %}

![Formatting_img6](Formatting_images/Formatting_img6.png)

## Center Across Selection

### Overview

This feature center aligns the cell value in Spreadsheet, across the range of selected cells. 

![Formatting_img7](Formatting_images/Formatting_img7.png)


### Properties, Methods and Events

### Methods

<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Type</th><th>
Return Type</th></tr>
<tr>
<td>
SetCenterAcrossSelection()</td><td>
This method sets the Center Across Selection on the selected cells. It should be explicitly called to set Center Across Selection.</td><td>
setCenterAcrossSelection() </td><td>
null</td><td>
void </td></tr>
</table>


### Center aligning cell values in Spreadsheet

The following code snippets manually set the center across selection by calling the method: 

{% tabs %}

{% highlight c# %}

SpreadsheetControl.GridProperties.CurrentExcelGridModel.setCenterAcrossSelection();

{% endhighlight %}

{% highlight vbnet %}
 
 SpreadsheetControl.GridProperties.CurrentExcelGridModel.setCenterAcrossSelection()

{% endhighlight %}

{% endtabs %}

The following code snippet manually sets the center across selection by calling the command: 

{% highlight xaml %}

<Button Content="CentreAcrossSelection" Margin="5" Width="200" Command="{Binding ElementName=spreadSheetControl, Path=CenterAcrossSelectionCommand}"/>

{% endhighlight %}

The output displayed is shown in the following screenshot:

![Formatting_img8](Formatting_images/Formatting_img8.png)
