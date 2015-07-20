---
layout: post
title: Formatting
description: formatting
platform: wpf
control: Spreadsheet
documentation: ug
---

# Formatting

## Conditional Formatting 

Conditional formatting is a feature by which cell styles will be dynamically formatted based on its value and specified condition. It enables you to apply formatting to the cell through a dialog window. 



Use Case Scenarios 

This feature enables you to categorize the cell for analysis.  For example, you can format a time sheet, to point out the overtime obtained by an employee. You can also use it to track the best sales employees in the company, by setting a quota that makes a cell range particular.



### Defining Condition for Spreadsheet Cells

You can define the condition for formatting the Spreadsheet cells using a conditional formatting dialog box. Specify the conditional value and style format in the dialog box. You can open the conditional formatting dialog using the ConditionalFormatCommand_._ Based on the Command parameter one of the following dialogs will open:



* Greater than



{ ![](Formatting_images/Formatting_img1.png) | markdownify }
{:.image }




* Less Than



{ ![](Formatting_images/Formatting_img2.png) | markdownify }
{:.image }




* Between



{ ![](Formatting_images/Formatting_img3.png) | markdownify }
{:.image }




* Equal to 



{ ![](Formatting_images/Formatting_img4.png) | markdownify }
{:.image }




The following code illustrates how to bind the ConditionalFormatCommand to a button: 



[XAML]



&lt;Button Command="{Binding Path=ConditionalFormatCommand}"&gt;

            &lt;Button.CommandParameter&gt;

                <XlsIO:ExcelComparisonOperator>Greater</XlsIO:ExcelComparisonOperator>

            &lt;/Button.CommandParameter&gt;

        &lt;/Button&gt;



{ ![](Formatting_images/Formatting_img5.png) | markdownify }
{:.image }




## Number formatting

Number formatting helps you to control the format of the number in Spreadsheet cells. Number in the cell will be displayed based on the number format applied. 

### Defining number formatting for Spreadsheet Cells

You can define the number formatting using the NumberFormattingCommand. Number formatting will be applied to the Spreadsheet cells based on the command parameter. The following code illustrates this:



[XAML]



&lt;Button Command="{Binding Path=NumberFormatCommand}" Grid.Row="2"&gt;

&lt;Button.CommandParameter&gt;

<System:String>0.00%&lt;/System:String&gt;

&lt;/Button.CommandParameter&gt;

&lt;/Button&gt;



{ ![](Formatting_images/Formatting_img6.png) | markdownify }
{:.image }




## Center Across Selection

### Overview

This feature center aligns the cell value in Spreadsheet, across the range of selected cells. 



{ ![](Formatting_images/Formatting_img7.png) | markdownify }
{:.image }




### Properties, Methods and Events

Methods

<table>
<tr>
<th>
Method </th><th>
Description </th><th>
Parameters </th><th>
Type </th><th>
Return Type </th></tr>
<tr>
<th>
SetCenterAcrossSelection()</th><th>
This method sets the Center Across Selection on the selected cells. It should be explicitly called to set Centre Across Selection.</th><th>
setCenterAcrossSelection() </th><th>
null</th><th>
void </th></tr>
</table>


### Center aligning cell values in Spreadsheet

The following code snippets manually set the center across selection by calling the method: 



<table>
<tr>
<td>
[C#]SpreadsheetControl.GridProperties.CurrentExcelGridModel.setCenterAcrossSelection();</td></tr>
<tr>
<td>
 [VB]SpreadsheetControl.GridProperties.CurrentExcelGridModel.setCenterAcrossSelection()</td></tr>
</table>


The following code snippet manually sets the center across selection by calling the command: 



[XAML]

&lt;Button Content="CentreAcrossSelection" Margin="5" Width="200" Command="{Binding ElementName=spreadSheetControl, Path=CenterAcrossSelectionCommand}"/&gt;





The output displayed is shown in the following screenshot:



{ ![](Formatting_images/Formatting_img8.png) | markdownify }
{:.image }


