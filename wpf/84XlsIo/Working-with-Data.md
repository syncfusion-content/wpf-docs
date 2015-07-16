---
layout: post
title: Working-with-Data
description: working with data
platform: wpf
control: XlsIO	
documentation: ug
---

# Working with Data

XlsIO has some helper methods that enable working with the ADO.NET data sources very easily. The following sections illustrate working with Data by using XlsIO.

## Importing Data to Worksheets 

It only takes one line of code to import an ADO.NET data table into a worksheet. There are similar methods for working with other data sources like Array, Business Objects, Data Column, Data Table, and Data View. A data table from another source can be imported inside a worksheet by using the ImportDataTable method.It has an option to select the record range (start row, end row, start col, and end col). It also allows preserving the data type in the data source.

### Import Data from Array

XlsIO imports array of data into a worksheet. The following code examples illustrates how to achieve this.

[C#]



// Step 1: Instantiates the spreadsheet creation engine.

ExcelEngine excelEngine = new ExcelEngine();



// Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;



// A new workbook is created. [Equivalent to creating a new workbook in MS Excel).

// The new workbook will have 2 worksheets.

IWorkbook workbook = application.Workbooks.Create(2);



IWorksheet sheet = workbook.Worksheets[0];



//Initializes the Object Array.

object[] array = new object[4];



//Imports the Object Array to Sheet.

sheet.ImportArray(array, 1, 1, false);

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

Dim workbook As IWorkbook = application.Workbooks.Create(2)



' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)



' Initializes the Array Object.

Dim array() As Object = New Object(4) {}



' Imports the Array Object to Sheet.

sheet.ImportArray(array, 1, 1, False)



Dim fileName As String = "Output.xlsx"

workbook.Version = ExcelVersion.Excel2010

workbook.SaveAs(fileName)



' Closes the workbook.

workbook.Close()

excelEngine.Dispose()



### Import Data from Business Objects

Business object usually holds a set of instance variables or properties also known as attributes. Essential XlsIO allows you to import data directly from Business Objects. 

Business Object

The class Customer is a business object that is imported into a worksheet. The following code example illustrates how Customer data is imported into a worksheet.

[C#]

// Imports the data to worksheet.
IList<Customer> customers = GetCustomerAsObjects();
sheet.ImportData(customers, 2, 1, false);



[VB.NET]

' Imports the Data to Sheet.
Dim customers As IList(of Customer) = GetCustomerAsObjects()
Worksheet.ImportData(customers, 2, 1, False)



GetCustomerAsObjects Method:

[C#]

// Initializes the DataSet.
DataSet customersDataSet = new DataSet();
DataTable northwindDt = new DataTable();

// Gets the path of the input file.
string inputXmlPath = GetFullTemplatePath("Customers.xml");
customersDataSet.ReadXml(inputXmlPath, XmlReadMode.ReadSchema);
northwindDt = customersDataSet.Tables[0];

// Initializes the CustomerList.
IList<Customer> tmpCustomers = new List<Customer>();
Customer customer = new Customer();
DataColumnCollection columns = northwindDt.Columns;
DataRowCollection rows = northwindDt.Rows;

// Iterates the rows.
foreach (DataRow row in rows)
{   
    customer = new Customer();
    customer.SalesPerson = row[0].ToString();
    customer.SalesJanJune = Convert.ToInt32(row[1]);
    customer.SalesJulyDec = Convert.ToInt32(row[2]);
    customer.Change = Convert.ToInt32(row[3]);
    tmpCustomers.Add(customer);
}
return tmpCustomers;



[VB.NET]



' Initializes the DataSet.
Dim customersDataSet As New DataSet()
Dim northwindDt As New DataTable()

' Gets the path of the input file.
Dim inputXmlPath As string = GetFullTemplatePath("Customers.xml")
customersDataSet.ReadXml(inputXmlPath, XmlReadMode.ReadSchema)
northwindDt = customersDataSet.Tables(0)
Dim tmpCustomers As IList(of Customer) = new List<Customer>()
Dim customer As New Customer()
Dim columns As DataColumnCollection = northwindDt.Columns
Dim rows As DataRowCollection = northwindDt.Rows

' Iterates the rows in DataRow.
For Each row As DataRow in rows
    customer = new Customer()
    customer.SalesPerson = row(0).ToString()
    customer.SalesJanJune = Convert.ToInt32(row(1))
    customer.SalesJulyDec = Convert.ToInt32(row(2))
    customer.Change = Convert.ToInt32(row(3))
    tmpCustomers.Add(customer)
Next
Return tmpCustomers



Customer Class:



[C#]



class Customer
   {

       // Defines the Members.
        #region Members
        private string m_salesPerson;
        private int m_salesJanJune;
        private int m_salesJulyDec;
        private int m_change;
        #endregion

        // Defines the properties.
        #region Properties
        public string SalesPerson
        {
            get
            {
                return m_salesPerson;
            }
            set
            {
                m_salesPerson = value;
            }
        }


        public int SalesJanJune
        {
            get
            {
                return m_salesJanJune;
            }
            set
            {
                m_salesJanJune = value;
            }

        }


        public int SalesJulyDec
        {
            get
            {
                return m_salesJulyDec;
            }
            set
            {
                m_salesJulyDec = value;
            }
        }

        public int Change
        {
            get
            {
                return m_change;
            }
            set
            {
                m_change = value;
            }
        }
        #endregion


        #region Initialization
        public Customer()
        {
        }
        public Customer(string name, int juneToJuly, int julyToDec, int change)
        {
            this.m_salesPerson = name;
            this.m_salesJanJune = juneToJuly;
            this.m_salesJulyDec = julyToDec;
            this.m_change = change;
        }
        #endregion
    }



[VB.NET]



Class Customer 

        ' Defines the Members.
        #Region “Members”
        Private m_salesPerson As String
        Private m_salesJanJune As Integer
        Private m_salesJulyDec As Integer
        Private m_change As Integer
        #End Region

        'Defines the Properties.
        #Region “Properties”
        Public Property SalesPerson() As String        
            Get            
                Return m_salesPerson
            End Get
            Set            
                m_salesPerson = value
            End Set  
        End Property     


        Public Property SalesJanJune() As Integer        
            Get            
                Return m_salesJanJune            
            End Get
            Set            
                m_salesJanJune = value
            End Set        
        End Property     


        Public Property SalesJulyDec() As Integer                
            Get            
                Return m_salesJulyDec

            End Get
            Set          
               m_salesJulyDec = value
            End Set        
       End Property     


       Public Property Change() As Integer                        
            Get            
                Return m_change            
            End Get
            Set  

                  m_change = value
            End Set        
       End Property     
       #End Region

        #Region “Initialization”
        Public Sub New()
        End Sub
        Public Sub New(name As String, juneToJuly As Integer, julyToDec As Integer, change As Integer)      
            Me.m_salesPerson = name
            Me.m_salesJanJune = juneToJuly
            Me.m_salesJulyDec = julyToDec
            Me.m_change = change   
         End Sub      
        #End Region
End Class    



### Import Data from Data Column

XlsIO imports DataColumn to a worksheet. The following code example illustrates how to achieve this.

[C#]



// Step 1: Instantiates the spreadsheet creation engine.

ExcelEngine excelEngine = new ExcelEngine();



// Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;



// A new workbook is created. [Equivalent to creating a new workbook in MS Excel).

// The new workbook will have 2 worksheets.

IWorkbook workbook = application.Workbooks.Create(2);



IWorksheet sheet = workbook.Worksheets[0];



DataTable table = SampleDataTable();



// Imports DataColumn to the worksheet.

DataColumn column = table.Columns[0];

sheet.ImportDataColumn(column, true, 1, 1);



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

Dim workbook As IWorkbook = application.Workbooks.Create(2)



' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)



Dim table As DataTable = sampleDataTable()



' Imports DataColumn to the worksheet.

Dim column As DataColumn = table.Columns(0)

sheet.ImportDataColumn(column, True, 1, 1)



Dim fileName As String = "Output.xlsx"

workbook.Version = ExcelVersion.Excel2010

workbook.SaveAs(fileName)



' Closes the workbook.

workbook.Close()

excelEngine.Dispose()



### Import Data from Data Table

XlsIO imports DataTable in to a worksheet. The following code examples illustrates on how to achieve this.

[C#]



// Step 1: Instantiates the spreadsheet creation engine.

ExcelEngine excelEngine = new ExcelEngine();



// Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;



// A new workbook is created. [Equivalent to creating a new workbook in MS Excel).

// The new workbook will have 2 worksheets.

IWorkbook workbook = application.Workbooks.Create(2);



IWorksheet sheet = workbook.Worksheets[0];



// Initializes the table.

DataTable table = SampleDataTable();



// Imports DataTable to the worksheet.

sheet.ImportDataTable(table, true, 1, 1);



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

' The new workbook will have 2 worksheets.

Dim workbook As IWorkbook = application.Workbooks.Create(2)



' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)



'Initializes the DataTable.

Dim table As DataTable = sampleDataTable()



' Imports DataTable to the worksheet.

sheet.ImportDataTable(table, True, 1, 1)



Dim fileName As String = "Output.xlsx"

workbook.Version = ExcelVersion.Excel2010

workbook.SaveAs(fileName)



' Closes the workbook.

workbook.Close()

excelEngine.Dispose()



### Import Data from Data View

XlsIO imports DataView in to a worksheet. The following code examples illustrates how to achieve this.

[C#]



// Step 1: Instantiates the spreadsheet creation engine.

ExcelEngine excelEngine = new ExcelEngine();



// Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;



// A new workbook is created. [Equivalent to creating a new workbook in MS Excel).

// The new workbook will have 2 worksheets.

IWorkbook workbook = application.Workbooks.Create(2);



IWorksheet sheet = workbook.Worksheets[0];



// Initializes the table.

DataTable table = SampleDataTable();



// Imports Dataview to the worksheet.

DataView view = table.DefaultView;

sheet.ImportDataView(view, true, 1, 1);



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

Dim workbook As IWorkbook = application.Workbooks.Create(2)



' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)



'Initializes the DataTable.

Dim table As DataTable = sampleDataTable()



'Imports Dataview to the worksheet.

Dim view As DataView = table.DefaultView

sheet.ImportDataView(view, True, 1, 1)



Dim fileName As String = "Output.xlsx"

workbook.Version = ExcelVersion.Excel2010

workbook.SaveAs(fileName)



'Closes the workbook.

workbook.Close()

excelEngine.Dispose()



## Exporting from Worksheet to Data Table 

It is easy to export the sheet data to a data table by using the ExportDataTable method of IWorksheet. This method allows selection of various data table options such as include column names, export formula calculated values, styles, and types through the ExcelExportDataTableOptions enumeration. It has the following values.



_ExcelExportDataTableOptions enumeration values_

<table>
<tr>
<td>
Members </td><td>
Description</td></tr>
<tr>
<td>
None</td><td>
Indicates default export to datatable.</td></tr>
<tr>
<td>
ColumnNames</td><td>
Indicates to export ColumnNames to datatable.</td></tr>
<tr>
<td>
ComputedFormulaValues</td><td>
Indicates to export ComputedFormulaValues to datatable.</td></tr>
<tr>
<td>
DetectColumnTypes</td><td>
Indicates that XlsIO should try to detect column types.</td></tr>
<tr>
<td>
DefaultStyleColumnTypes</td><td>
When DetectColumnTypes is set and this flag is set too, it means that  the default column style must be used to detect style. If this flag is not set, but DetectColumnTypes is set, then the first cell in the column is used to detect column type.</td></tr>
</table>


The following code example illustrates how to import data to grid from worksheet by using DataTable.

[C#]



// Step 1: Instantiates the spreadsheet creation engine.

ExcelEngine excelEngine = new ExcelEngine();



// Step 2: Instantiates the excel application object.

IApplication application = excelEngine.Excel;



// A new workbook is created. [Equivalent to creating a new workbook in MS Excel).

// The new workbook will have 2 worksheets.

IWorkbook workbook = application.Workbooks.Create(2);



IWorksheet sheet = workbook.Worksheets[0];



// Reads data from the spreadsheet and Export the DataTable.

DataTable customersTable = sheet.ExportDataTable(sheet.UsedRange, ExcelExportDataTableOptions.ColumnNames);

this.dataGrid1.DataSource = customersTable;



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

Dim workbook As IWorkbook = application.Workbooks.Create(2)



' Accesses via index.

Dim sheet As IWorkbook = workbook.Worksheets(0)



'Reads data from the spreadsheet and Export the DataTable.

Dim customersTable As DataTable = sheet.ExportDataTable(sheet.UsedRange, ExcelExportDataTableOptions.ColumnNames)

Me.dataGrid1.DataSource = customersTable



Dim fileName As String = "Output.xlsx"

workbook.Version = ExcelVersion.Excel2010

workbook.SaveAs(fileName)



' Closes the workbook.

workbook.Close()

excelEngine.Dispose()

The following images illustrates the import from excel to grid and export from grid to excel by using DataTable.

{ ![](Working-with-Data_images/Working-with-Data_img1.png) | markdownify }
{:.image }


__

{ ![](Working-with-Data_images/Working-with-Data_img2.png) | markdownify }
{:.image }


## Improving performance and memory while importing data

Import DataTable has few overloads that is used for some of the customized options. Here, an overload with ImportonSave__argument allows you to import data with less memory consumption along with improved performance by serializing the data directly on save method. This options is preferred for larger data that need to be import in short time.



[C#]


DataTable table = Worksheet.ExportDataTable(1, 1, Worksheet.UsedRange.LastRow, Worksheet.UsedRange.LastColumn, ExcelExportDataTableOptions.DetectColumnTypes);



//Enabling the import on save options.

workbook.Worksheets[0].ImportDataTable(table, 1, 1, true);



workbook.Version = ExcelVersion.Excel2013;



workbook.SaveAs("Output.xlsx");





[VB.NET]



Dim table As DataTable = Worksheet.ExportDataTable(1, 1, Worksheet.UsedRange.LastRow, Worksheet.UsedRange.LastColumn, ExcelExportDataTableOptions.DetectColumnTypes)



'Enabling the import on save options.

workbook.Worksheets(0).ImportDataTable(table, 1, 1, True)



workbook.Version = ExcelVersion.Excel2013



workbook.SaveAs("Output.xlsx")




Advantages

* Improved performance
* Less memory consumption



Limitations

* Cannot modify data dynamically
* Styles cannot be applied
* Table style cannot be applied
* Existing sheet data will be lost





