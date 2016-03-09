---
layout: post
title: Conditional Formatting 
description: How to apply conditional formatting rules at run time in SfSpreadsheet.
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Conditional Formatting 

This section explains about how to apply conditional formatting rules at run time in SfSpreadsheet.

In SfSpreadsheet, to apply conditional format for a cell or range of cells, add [IConditionalFormat](http://help.syncfusion.com/cr/cref_files/wpf/xlsio/Syncfusion.XlsIO.Base~Syncfusion.XlsIO.IConditionalFormat.html) to that range by using [AddCondition](http://help.syncfusion.com/cr/cref_files/wpf/xlsio/Syncfusion.XlsIO.Base~Syncfusion.XlsIO.IConditionalFormats~AddCondition.html) method.

{% highlight c# %}

var WorkSheet =Sfspreadsheet.Workbook.Worksheets[0];

IConditionalFormats condition = WorkSheet.Range["A1"].ConditionalFormats;

IConditionalFormat condition1 = condition.AddCondition();

{% endhighlight %}
<br/><br/>

## Highlight Cell Rules

To format the cells based on cell value, set the conditional format type as **CellValue**, operator, background color etc., to the specified cell or range and then invalidate the cells to refresh the view.

{% highlight c# %}

var WorkSheet =Sfspreadsheet.Workbook.Worksheets[0];

IConditionalFormats condition = WorkSheet.Range["A1"].ConditionalFormats;

IConditionalFormat condition1 = condition.AddCondition();

condition1.FormatType = ExcelCFType.CellValue;

condition1.Operator = ExcelComparisonOperator.Greater;

condition1.FirstFormula = "10";

condition1.BackColor = ExcelKnownColors.Light_orange;

Sfspreadsheet.ActiveGrid.InvalidateCell(1,1);

{% endhighlight %}

Sample Output

![](Conditional-Formatting_images/Conditional-Formatting_img1.jpeg)



## Data Bars

To apply the conditional format based on data bars, set the conditional format type as a **DataBar** and then invalidate that cells to update the view.

{% highlight c# %}

var WorkSheet = Sfspreadsheet.Workbook.Worksheets[0];

var conditionalFormats =   WorkSheet.Range["D1:K100"].ConditionalFormats;

var conditionalFormat = conditionalFormats.AddCondition();

conditionalFormat.FormatType = ExcelCFType.DataBar;

Sfspreadsheet.ActiveGrid.InvalidateCells();

{% endhighlight %}

Sample Output

![](Conditional-Formatting_images/Conditional-Formatting_img2.jpeg)



## Color Scales

To apply the conditional format based on color scales, set a conditional format type as a **ColorScale** and then invalidate that cells to update the view.

{% highlight c# %}

var WorkSheet = Sfspreadsheet.Workbook.Worksheets[0];

var conditionalFormats = WorkSheet.Range["C1:F50 "].ConditionalFormats;

var conditionalFormat = conditionalFormats.AddCondition();

conditionalFormat.FormatType = ExcelCFType.ColorScale;

Sfspreadsheet.ActiveGrid.InvalidateCells();

{% endhighlight %}

Sample Output

![](Conditional-Formatting_images/Conditional-Formatting_img3.jpeg)


## Icon Sets

To apply the conditional format for Icon sets, set a conditional format type as **IconSet** and then then invalidate that cells to update the view.

{% highlight c# %}

var WorkSheet = Sfspreadsheet.ActiveSheet;

var conditionalFormats = WorkSheet.Range["D1:D100"].ConditionalFormats;

var conditionalFormat = conditionalFormats.AddCondition();

conditionalFormat.FormatType = ExcelCFType.IconSet;

var iconSet = conditionalFormat.IconSet;

iconSet.IconSet = ExcelIconSetType.ThreeSymbols;

Sfspreadsheet.ActiveGrid.InvalidateCells();

{% endhighlight %}

Sample Output

![](Conditional-Formatting_images/Conditional-Formatting_img4.jpeg)


