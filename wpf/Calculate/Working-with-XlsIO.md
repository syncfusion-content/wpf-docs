---
layout: post
title: Working with Essential XlsIO | Calculate | WPF | Syncfusion
description: Explains about working with CalcWorkbook, CalcSheet
platform: wpf
control: Calculate
documentation: ug
---

# Working with Essential XlsIO

Essential XIsIO provides an Excel-like Automation-type support without having Microsoft Excel installed on the host system.This means that you can use this library 
to read and write an XLS file and hold its contents in memory. But you cannot perform actual computations on the contents of the XLS file. Hence Essential Calculate
is integrated with Essential XlsIO, to calculate formulas entered at runtime without any additional references or packages.

## Open a Workbook using XlsIO

To open a workbook using XIsIO, instantiate the [ExcelEngine](https://help.syncfusion.com/cr/cref_files/file-formats/Syncfusion.XlsIO.Base~Syncfusion.XlsIO.ExcelEngine.html) to initialize the application object for creating or manipulating Excel documents. To open an existing workbook,
use the [Open](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.XlsIO.Base~Syncfusion.XlsIO.IWorkbooks~Open.html) methods of [IWorkbook](http://help.syncfusion.com/cr/cref_files/file-formats/Syncfusion.XlsIO.Base~Syncfusion.XlsIO.IWorkbook.html) interface.

{% tabs %}
{% highlight c# %}

//Creates a new instance for ExcelEngine.

ExcelEngine excelEngine = new ExcelEngine();

//Loads or open an existing workbook through Open method of IWorkbook

IWorkbook workbook = excelEngine.Excel.Workbooks.Open(@"..\..\Data\Sample.xlsx");

{% endhighlight %}
{% endtabs %}

## Enable and Disable Calculations in XlsIO

To perform calculation in an Excel workbook, it is recommended to invoke [EnableSheetCalculations](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.XlsIO.Base~Syncfusion.XlsIO.IWorksheet~EnableSheetCalculations.html) method of [IWorksheet](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.XlsIO.Base~Syncfusion.XlsIO.IWorksheet.html). Enabling this method will initialize
[CalcEngine](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.XlsIO.Base~Syncfusion.XlsIO.IWorksheet~CalcEngine.html) objects and retrieves calculated values of formulas in a worksheet.

On completion of worksheet calculation, it is also recommended to invoke [DisableSheetCalculations](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.XlsIO.Base~Syncfusion.XlsIO.IWorksheet~DisableSheetCalculations.html) method of `IWorksheet`. 
This will dispose all the `CalcEngine` objects.

{% tabs %}
{% highlight c# %}

//Creates a new instance for ExcelEngine,

ExcelEngine excelEngine = new ExcelEngine();

//Loads or open an existing workbook through Open method of IWorkbook, 

IWorkbook workbook = excelEngine.Excel.Workbooks.Open(@"..\..\Data\Sample.xlsx");

//Accessing the worksheet,
IWorksheet sheet = workbook.Worksheets[0];

//Formula calculation is enabled for the sheet,
sheet.EnableSheetCalculations();

//Assigning values in the worksheet,

worksheet["C3"].Number = 45;
         
worksheet["C4"].Number = 20;
            
worksheet["C5"].Number = 38;

//Assigning the formula in the worksheet,           
worksheet["C24"].Formula = "=SUM(C3:C4)-C5";

//Getting the calculated value,
var value = sheet.Range["C24"].CalculatedValue;

//Formula calculation is disabled for the sheet,
sheet.DisableSheetCalculations();

{% endhighlight %}
{% endtabs %}

## Set and Compute the values at runtime in the Worksheet

At runtime, user can set the values in the particular `IWorksheet` by indexing the worksheet with the sheet name or id
and then use the appropriate row and column indexes. Invoking [UpdateCalcID](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~UpdateCalcID.html) and [PullUpdatedValue](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~PullUpdatedValue.html) method of `CalcEngine` 
guarantees the current/updated values in the workbook.

[CalculatingSuspended](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~CalculatingSuspended.html) method of `CalcEngine`  is to suspend calculations while a series of changes are made to dependent cells 
either by the user or programmatically. When the changes are complete, set this property to False.

{% tabs %}
{% highlight c# %}

//Creates a new instance for ExcelEngine,

ExcelEngine excelEngine = new ExcelEngine();

//Loads or open an existing workbook through Open method of IWorkbook,

IWorkbook workbook = excelEngine.Excel.Workbooks.Open(@"..\..\Data\Sample.xlsx");

//Accessing the worksheet,
IWorksheet sheet = workbook.Worksheets["Inputs"];

Random r = new Random();

sheet.CalcEngine.CalculatingSuspended = true;

//Set random values into the "Inputs" sheet,
sheet[1, 2].Value = (r.Next(74) + 15).ToString();
sheet[2, 2].Value = r.Next(2) == 1 ? "M" : "F";
sheet[3, 2].Value = r.Next(50);
sheet[4, 2].Value = r.Next(15).ToString();
sheet[5, 2].Value = r.Next(11).ToString();
sheet[6, 2].Value = (33 + r.Next(1972)).ToString();
sheet[7, 2].Value = r.Next(2) == 1 ? "Yes" : "No";
sheet[8, 5].Value = r.Next(20); 

//Calculations are suspended so need to pull the computed value to make sure it has been calculated with the latest changes,
sheet.CalcEngine.UpdateCalcID();
sheet.CalcEngine.PullUpdatedValue(sheet.CalcEngine.GetSheetID("Outputs"), 1, 1);

//Get the Calculated value from "Outputs" sheet,
string val = workbook.Worksheets["Outputs"][1, 1].CalculatedValue;

sheet.CalcEngine.CalculatingSuspended = false;

{% endhighlight %}
{% endtabs %}

## To compute particular cell in the worksheet

To compute particular cell in the worksheet, use [ParseAndComputeFormula](https://help.syncfusion.com/cr/cref_files/windowsforms/Syncfusion.Calculate.Base~Syncfusion.Calculate.CalcEngine~ParseAndComputeFormula.html) method of `CalcEngine`. For more details regarding 
`ParseAndComputeFormula` method, refer [here](https://help.syncfusion.com/wpf/calculate/parse-and-compute#parseandcomputeformula).

{% tabs %}
{% highlight c# %}

//Creates a new instance for ExcelEngine,

ExcelEngine excelEngine = new ExcelEngine();

//Loads or open an existing workbook through Open method of IWorkbook,

IWorkbook workbook = excelEngine.Excel.Workbooks.Open(@"..\..\Data\Sample.xlsx");

//Accessing the worksheet,
IWorksheet sheet = workbook.Worksheets["Sheet1"];

//To calculate particular cell,
sheet.CalcEngine.ParseAndComputeFormula(sheet["C5"].Formula);

{% endhighlight %}
{% endtabs %}

## Ambiguity Issue 

If the Calculate.Base and XlsIO.Base references are added in the same application, it will throw conflict errors. Since Calculate.Base is already integrated with XlsIO. Hence, if XlsIO.Base reference has been included in the application, 
there is no need to add Calculate.Base reference explicitly. The calculate references get reflected in the XlsIO.Base permanently.  

But if you want both the references in your project, you can use `extern alias` to differentiate the namespaces.
For your reference, please find the MSDN [link](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/extern-alias) regarding
`extern alias`.

## Table Formulas

A table is a collection of data about a specific topic that is stored in rows and columns. These tables are defined with a name and `CalcEngine` supports these table format.

For Example: =SUM(Table1[[#All],[Column1]:[Column2]])

A table needs to be defined with the following protocols,

* All table, column, and special item specifiers must be enclosed in matching brackets [ ]
* Expression cannot be used with these brackets. Column headers should be a text strings.
* The special characters such as comma ,, colon :, period ., left bracket [ , right bracket ], pound sign #, single quotation mark ', double quotation mark ", 
  left brace {, right brace }, dollar sign $, caret ^, ampersand &, asterisk *, plus sign +, equal sign =, minus sign -, greater than symbol >,  less than symbol <, and division sign / can be used.

These table are converted into cell ranges and then it will be evaluated. The data from one row can also be taken with this table structure.

{% tabs %}
{% highlight c# %}

//Creates a new instance for ExcelEngine,

ExcelEngine excelEngine = new ExcelEngine();

//Loads or open an existing workbook through Open method of IWorkbook,

IWorkbook workbook = excelEngine.Excel.Workbooks.Open(@"..\..\Data\Sample.xlsx");

//Accessing the worksheet,
IWorksheet sheet = workbook.Worksheets[0];

//Formula calculation is enabled for the sheet,
sheet.EnableSheetCalculations();

//Create Table,
IListObject table1 = sheet.ListObjects.Create("Table1", sheet["A1:F6"]);

// Fill table data
sheet[1, 1].Text = "Column1";
sheet[1, 2].Text = "Column2";
sheet[1, 3].Text = "Column3";

sheet[2, 1].Number = 3;
sheet[2, 2].Number = 2;
sheet[2, 3].Number = 16.80;

sheet[3, 1].Number = 5;
sheet[3, 2].Number = 3;
sheet[3, 3].Number = 15.60;

sheet[4, 1].Number = 8;
sheet[4, 2].Number = 2;
sheet[4, 3].Number = 20.10;

string result1 = sheet.CalcEngine.ParseAndComputeFormula("=SUM(Table1[Column1])");

string result2 = sheet.CalcEngine.ParseAndComputeFormula("=MIN(Table1[#All])");

{% endhighlight %}
{% endtabs %}
