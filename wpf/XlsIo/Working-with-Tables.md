---
layout: post
title: Working-with-Tables
description: working with tables 
platform: wpf
control: XlsIO	
documentation: ug
---

# Working with Tables 

In Excel, Tables can be inserted by selecting Table option from the Insert menu. The following sections illustrate working with tables by using XlsIO.

Create a Table

XlsIO provides support to read and write tables in a spreadsheet. The table is added as an IListObject to the worksheet. The input data to the table must be a range of data existing in the worksheet. IListObject returns the collection of tables in the worksheet.

[C#]



// Step 1: Instantiates the spreadsheet creation engine.

ExcelEngine excelEngine = new ExcelEngine();



// Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;



// A new workbook is created. [Equivalent to creating a new workbook in MS Excel).

// The new workbook will have 2 worksheets.

IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);



IWorksheet sheet = workbook.Worksheets[0];



// Creates a Table.

IListObject table = sheet.ListObjects.Create("Table1", sheet["A1:C8"]);



string fileName = "Output.xlsx";

workbook.Version = ExcelVersion.Excel2010;



workbook.SaveAs(fileName);



// Closes the workbook.

workbook.Close();

excelEngine.Dispose();         



[VB.NET]



' Step 1: Instantiates the spreadsheet creation engine.

Dim excelEngine As ExcelEngine = New ExcelEngine



' Step 2: Instantiates the excel application object.

Dim application As IApplication = excelEngine.Excel



' A new workbook is created. [Equivalent to creating a new workbook in MS Excel].

'The new workbook will have 2 worksheets.

Dim workbook As IWorkbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic)





' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)



'Creates a Table.

Dim table As IListObject = sheet.ListObjects.Create("Table1", sheet("A1:C8"))



Dim fileName As String = "Output.xlsx"

workbook.Version = ExcelVersion.Excel2010



workbook.SaveAs(fileName)



' Closes the workbook.

workbook.Close()

excelEngine.Dispose()



{{ '![](Working-with-Tables_images/Working-with-Tables_img1.png)' | markdownify }}
{:.image }


## Adding a Total Row

You can add the Total Row to any table by accessing the Table Columns. Columns in the tables are accessed by using the index. It is possible to set Totals Calculation to the Total Row cells by using the ExcelTotalsCalculation enumerator. These cells will be updated once they are calculated.

[C#]



// Step 1: Instantiates the spreadsheet creation engine.

ExcelEngine excelEngine = new ExcelEngine();



// Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;



// A new workbook is created. [Equivalent to creating a new workbook in MS Excel).

// The new workbook will have 2 worksheets.

IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);



IWorksheet sheet = workbook.Worksheets[0];



// Creates a Table.

IListObject table = sheet.ListObjects.Create("Table1", sheet["A1:C8"]);



// Total Row.

table.ShowTotals = true;

table.Columns[0].TotalsRowLabel = "Total";

table.Columns[1].TotalsCalculation = ExcelTotalsCalculation.Sum;

table.Columns[2].TotalsCalculation = ExcelTotalsCalculation.Sum;



string fileName = "Output.xlsx";

workbook.Version = ExcelVersion.Excel2010;



workbook.SaveAs(fileName);



// Closes the workbook.

workbook.Close();

excelEngine.Dispose();         



[VB.NET]



' Step 1: Instantiates the spreadsheet creation engine.

Dim excelEngine As ExcelEngine = New ExcelEngine



' Step 2: Instantiates the excel application object.

Dim application As IApplication = excelEngine.Excel



' A new workbook is created. [Equivalent to creating a new workbook in MS Excel].

'The new workbook will have 2 worksheets.

Dim workbook As IWorkbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic)





' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)



'Creates a Table.

Dim table As IListObject = sheet.ListObjects.Create("Table1", sheet("A1:C8"))



'Total Row.

table.ShowTotals = True

table.Columns(0).TotalsRowLabel = "Total"

table.Columns(1).TotalsCalculation = ExcelTotalsCalculation.Sum

table.Columns(2).TotalsCalculation = ExcelTotalsCalculation.Sum



Dim fileName As String = "Output.xlsx"

workbook.Version = ExcelVersion.Excel2010



workbook.SaveAs(fileName)



' Closes the workbook.

workbook.Close()

excelEngine.Dispose()

## Formatting a Table

You can apply built-in styles for the tables by using the TableBuiltInStyles enumerator of XlsIO.

[C#]



// Step 1: Instantiates the spreadsheet creation engine.

ExcelEngine excelEngine = new ExcelEngine();



// Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;



// A new workbook is created. [Equivalent to creating a new workbook in MS Excel).

// The new workbook will have 2 worksheets.

IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);



IWorksheet sheet = workbook.Worksheets[0];



// Creates a Table.

IListObject table = sheet.ListObjects.Create("Table1", sheet["A1:C8"]);



// Applies built-in style.

table.BuiltInTableStyle = TableBuiltInStyles.TableStyleMedium9;



string fileName = "Output.xlsx";

workbook.Version = ExcelVersion.Excel2010;



workbook.SaveAs(fileName);



// Closes the workbook.

workbook.Close();

excelEngine.Dispose();         



[VB.NET]



' Step 1: Instantiates the spreadsheet creation engine.

Dim excelEngine As ExcelEngine = New ExcelEngine



' Step 2: Instantiates the excel application object.

Dim application As IApplication = excelEngine.Excel



' A new workbook is created. [Equivalent to creating a new workbook in MS Excel].

'The new workbook will have 2 worksheets.

Dim workbook As IWorkbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic)



' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)



'Creates a Table.

Dim table As IListObject = sheet.ListObjects.Create("Table1", sheet("A1:C8"))



' Applies built-in style.

table.BuiltInTableStyle = TableBuiltInStyles.TableStyleMedium9



Dim fileName As String = "Output.xlsx"

workbook.SaveAs(fileName)



' Closes the workbook.

workbook.Close()

excelEngine.Dispose()



## Insert/Remove Columns in a Table

XlsIO provides support to insert or remove columns in a table. There are two options provided to remove a column from the table. One option is by providing the column item and the other is by providing the column index. The following code example illustrates how to insert/remove a column from a table.

[C#]



// Step 1: Instantiates the spreadsheet creation engine.

ExcelEngine excelEngine = new ExcelEngine();



// Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;



// A new workbook is created. [Equivalent to creating a new workbook in MS Excel).

// The new workbook will have 2 worksheets.

IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);



IWorksheet sheet = workbook.Worksheets[0];



// Creates a Table.

IListObject table = sheet.ListObjects.Create("Table1", sheet["A1:C8"]);



//Inserts a column in the table.

table.Columns.Insert(listObjectColum);



// Removes a column from the table - Method 1.

table.Columns.Remove(listObjectColum);

// Removes a column from the table - Method 2.

table.Columns.RemoveAt(columnIndex);



string fileName = "Output.xlsx";

workbook.Version = ExcelVersion.Excel2010;



workbook.SaveAs(fileName);



// Closes the workbook.

workbook.Close();

excelEngine.Dispose();         



[VB.NET]



' Step 1: Instantiates the spreadsheet creation engine.

Dim excelEngine As ExcelEngine = New ExcelEngine



' Step 2: Instantiates the excel application object.

Dim application As IApplication = excelEngine.Excel



' A new workbook is created. [Equivalent to creating a new workbook in MS Excel].

'The new workbook will have 2 worksheets.

Dim workbook As IWorkbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic)



' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)



'Creates a Table.

Dim table As IListObject = sheet.ListObjects.Create("Table1", sheet("A1:C8"))



// Inserts a column in the table.

table.Columns.Insert(listObjectColum)



// Removes a column from the table - Method 1.

table.Columns.Remove(listObjectColum)

// Removes a column from the table - Method 2.

table.Columns.RemoveAt(columnIndex)



Dim fileName As String = "Output.xlsx"

workbook.Version = ExcelVersion.Excel2010



workbook.SaveAs(fileName)



' Closes the workbook.

workbook.Close()

excelEngine.Dispose()

## Accessing a Table

XlsIO provides support to read an existing table from the spreadsheet. It can be accessed from the sheet by using the Table Index.

[C#]



// Step 1: Instantiates the spreadsheet creation engine.

ExcelEngine excelEngine = new ExcelEngine();



// Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;



// A new workbook is created. [Equivalent to creating a new workbook in MS Excel).

// The new workbook will have 2 worksheets.

IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);



IWorksheet sheet = workbook.Worksheets[0];



IListObject table = sheet.ListObjects[0];

table.BuiltInTableStyle = TableBuiltInStyles.TableStyleMedium1;



string fileName = "Output.xlsx";

workbook.Version = ExcelVersion.Excel2010;



workbook.SaveAs(fileName);



// Closes the workbook.

workbook.Close();

excelEngine.Dispose();         



[VB.NET]



' Step 1: Instantiates the spreadsheet creation engine.

Dim excelEngine As ExcelEngine = New ExcelEngine



' Step 2: Instantiates the excel application object.

Dim application As IApplication = excelEngine.Excel



' A new workbook is created. [Equivalent to creating a new workbook in MS Excel].

'The new workbook will have 2 worksheets.

Dim workbook As IWorkbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic)



' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)



Dim table As IListObject = sheet.ListObjects(0)

table.BuiltInTableStyle = TableBuiltInStyles.TableStyleMedium1



Dim fileName As String = "Output.xlsx"

workbook.Version = ExcelVersion.Excel2010



workbook.SaveAs(fileName)



' Closes the workbook.

workbook.Close()

excelEngine.Dispose()



## Create a Table from External Connection 

External Connection implementation establishes a connection between data base and excel file. This support is provided only for *.xlsx files. The following table shows different data sources and its connection string formats that are supported in XlsIO.

_Data sources and its Connection String Formats_

<table>
<tr>
<td rowspan = "2">
Data Base</td><td rowspan = "2">
Connection Type</td><td rowspan = "2">
Samples connection string</td></tr>
<tr>
</tr>
<tr>
<td rowspan = "2">
MS Access</td><td>
Oledb</td><td>
OLEDB;Provider=Microsoft.JET.OLEDB.4.0;Password=\"\";<br>User ID=Admin;Data Source=C:\\Company\\DB\\TestDB.mdb</td></tr>
<tr>
<td>
Odbc</td><td>
ODBC;DSN=MS Access;DBQ=C:\\Company\\DB\\Testing.mdb;<br>DefaultDir=C:\\Company\\DB;FIL=MS Access;MaxBufferSize=2048;PageTimeout=5;</td></tr>
<tr>
<td rowspan = "2">
Sql</td><td>
Oledb</td><td>
OLEDB;Provider=SQLOLEDB.1;Integrated Security=SSPI;<br>Persist Security Info=True;Initial Catalog=Temp;<br>Data Source=SYNCFUSION\\SQLEXPRESS;Workstation ID=SYNCINC;</td></tr>
<tr>
<td>
Odbc</td><td>
ODBC;DSN=Test1;UID=syncfusion;Trusted_Connection=Yes;<br>APP=Microsoft Office 2010;WSID=SYNCINC;DATABASE=Temp</td></tr>
<tr>
<td>
Excel</td><td>
Oledb</td><td>
OLEDB;Provider=Microsoft.ACE.OLEDB.12.0;Password=\"\";<br>User ID=Admin;Data Source="c:\SourceTemplate.xlsx;<br>Jet OLEDB:Engine Type=37;</td></tr>
<tr>
<td rowspan = "2">
Share Point</td><td>
Oledb</td><td>
Stars with OLEDB</td></tr>
<tr>
<td>
Odbc</td><td>
Stars with ODBC</td></tr>
</table>


The following code example explains the method of establishing a connection in workbook.

[C#]



// Step 1: Instantiates the spreadsheet creation engine.

ExcelEngine excelEngine = new ExcelEngine();



// Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;



// A new workbook is created. [Equivalent to creating a new workbook in MS Excel).

// The new workbook will have 2 worksheets.

IWorkbook workbook = application.Workbooks.Create(2);



IWorksheet sheet = workbook.Worksheets[0];



// Database path.
string dataPath = Path.GetFullPath(@"TestDB.mdb");



// Connection string for DataSource.
string ConnectionString = "OLEDB;Provider=Microsoft.JET.OLEDB.4.0;Password=\"\";User ID=Admin;Data Source=" + dataPath;


// Adds a connection to the workbook.
IConnection Connection = workbook.Connections.Add("Connection1", "Sample                                            with MsAccess", ConnectionString, "", ExcelCommandType.Sql);

// Adds a QueryTable to sheet object.
sheet.ListObjects.AddEx(ExcelListObjectSourceType.SrcQuery, Connection,                   sheet.Range["A1"]);

// Command Text for the Connection.
sheet.ListObjects[0].QueryTable.CommandText = "Select * from tblTest";

// The Query performs Asynchronous action.
sheet.ListObjects[0].QueryTable.BackgroundQuery = true;

// The Query Table is refreshed when the Workbook is opened.
sheet.ListObjects[0].QueryTable.RefreshOnFileOpen = true;

// Represents the connection description.
Connection.Description = "Sample Connection";

// Imports data to the sheet from the database.
sheet.ListObjects[0].Refresh();

// Auto-fits the columns
sheet.UsedRange.AutofitColumns();



string fileName = "Output.xlsx";

workbook.Version = ExcelVersion.Excel2010;



workbook.SaveAs(fileName);



// Closes the workbook.

workbook.Close();

excelEngine.Dispose();         



[VB.Net]



' Step 1: Instantiates the spreadsheet creation engine.

Dim excelEngine As ExcelEngine = New ExcelEngine



' Step 2: Instantiates the excel application object.

Dim application As IApplication = excelEngine.Excel



' A new workbook is created. [Equivalent to creating a new workbook in MS Excel].

'The new workbook will have 2 worksheets.

Dim workbook As IWorkbook = application.Workbooks.Create(2)



' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)

' Database path.
Dim dataPath As String = Path.GetFullPath("c:\company\DB\TestDB.mdb")

' Connection string for DataSource.
Dim ConnectionString As String ="OLEDB;Provider=Microsoft.JET.OLEDB.4.0;Password="""";User ID=Admin;Data Source=" + dataPath

' Adds a connection to the workbook. 
Dim Connection As IConnection = workbook.Connections.Add("Connection1", "Sample   connection with MsAccess", ConnectionString, "", ExcelCommandType.Sql)

' Adds a QueryTable to sheet object.
sheet.ListObjects.AddEx(ExcelListObjectSourceType.SrcQuery, Connection, sheet.Range("A1"))

' Commands Text for the Connection.
sheet.ListObjects(0).QueryTable.CommandText = "Select * from tblTest"

' The Query performs Asynchronous action.
sheet.ListObjects(0).QueryTable.BackgroundQuery = True

' The Query Table is refreshed when the Workbook is opened.
sheet.ListObjects(0).QueryTable.RefreshOnFileOpen = True

' Represents the connection description.
Connection.Description = "Sample Connection"

' Imports data to the sheet from the database.
sheet.ListObjects(0).Refresh()

' AutoFits the columns.
sheet.UsedRange.AutofitColumns()

Dim fileName As String = "Output.xlsx"

workbook.Version = ExcelVersion.Excel2010



workbook.SaveAs(fileName)



' Closes the workbook.

workbook.Close()

excelEngine.Dispose()



The following screenshot shows the connection wizard in MS Excel.

{{ '![](Working-with-Tables_images/Working-with-Tables_img2.png)' | markdownify }}
{:.image }


{{ '![](Working-with-Tables_images/Working-with-Tables_img3.png)' | markdownify }}
{:.image }


