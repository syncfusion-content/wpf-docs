---
layout: post
title: Opening-Excel-Workbook
description: opening excel workbook
platform: wpf
control: XlsIO	
documentation: ug
---

# Opening Excel Workbook

Essential XlsIO allows you to open the existing MS Excel workbook with an interface IWorkbooks. IWorkbooks is a collection of all the workbook objects that are currently open in the Excel application. This interface is responsible for adding new workbooks, opening existing workbooks, creating new workbooks, and copying workbooks. 

## Open Workbook as File

The following is the code example to open a document from file.

[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;


//Opens a workbook.
IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic);



[VB.NET]



Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Opens the workbook as file.
Dim workbook As IWorkbook = application.Workbooks.Open("Sample.xlsx", ExcelOpenType.Automatic)

To open a binary excel document, the file name with the extension *.xls is sufficient.

[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;


//Opens the workbook.
IWorkbook workbook = application.Workbooks.Open("Sample.xls", ExcelOpenType.Automatic);



[VB.NET]



Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Opens the workbook as file.
Dim workbook As IWorkbook = application.Workbooks.Open("Sample.xls", ExcelOpenType.Automatic)

Opening a Workbook as a file in WinRT

The following is the code sample to open a document from file.

[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;


//Instantiates the File Picker.
FileOpenPicker openPicker = new FileOpenPicker();

openPicker.SuggestedStartLocation = PickerLocationId.Desktop;

openPicker.FileTypeFilter.Add(".xlsx");

openPicker.FileTypeFilter.Add(".xls");



StorageFile openFile = await openPicker.PickSingleFileAsync();

//Opens the workbook.
IWorkbook workbook = await application.Workbooks.OpenAsync(openFile);



[VB.NET]



Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Instantiates the File Save Picker.
Dim openPicker As New FileOpenPicker()
openPicker.SuggestedStartLocation = PickerLocationId.Desktop
openPicker.FileTypeFilter.Add(".xlsx")

openPicker.FileTypeFilter.Add(".xls")
Dim openFile As StorageFile = Await openPicker.PickSingleFileAsync()

'Opens the Workbook.
Dim workbook As IWorkbook = Await application.Workbooks.OpenAsync(openFile)



Opening a Workbook as a file in Windows Phone 8

The following is the code example to open a document from file.

[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

//Opens the workbook.
StorageFolder local = Windows.Storage.ApplicationData.Current.LocalFolder;

StorageFile outFile = await local.GetFileAsync("Sample.xlsx");

IWorkbook workbook = await application.Workbooks.OpenAsync(outFile);



[VB.NET]



Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Opens the Workbook.
Dim local As StorageFolder = Windows.Storage. ApplicationData.Current.LocalFolder
Dim outFile As StorageFile = Await local.GetFileAsync("Sample.xlsx")

Dim workbook As IWorkbook = Await application.Workbooks.OpenAsync(outFile)

To know about saving workbook as a file, refer to Save Workbook as File section.

## Open Workbook as a Stream 

The following is the code example to open a document from file.

[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

//Converts the file into a stream.
FileStream fileStream = new FileStream ("Sample.xlsx", FileMode.Open);

//Opens the workbook as a stream.
IWorkbook workbook = application.Workbooks.Open(fileStream, ExcelOpenType.Automatic);



[VB.NET]

Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Converts the file into a stream.
Dim fileStream As New FileStream("Sample.xlsx", FileMode.Open)

'Opens the workbook as a stream.
Dim workbook As IWorkbook = application.Workbooks.Open(fileStream, ExcelOpenType.Automatic)


Opening a Workbook as a stream in Windows Phone 8.

[C#]

ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

//Opens the file as a stream.
StorageFolder local = Windows.Storage.ApplicationData.Current.LocalFolder;
Stream outFile = await local.OpenStreamForReadAsync("sample.xlsx");

//Opens the workbook.
IWorkbook workbook = await application.Workbooks.OpenAsync(outFile);



[VB.NET]



Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Opens the file as a stream.
Dim local As StorageFolder = Windows.Storage. ApplicationData.Current.LocalFolder
Dim outFile As Stream = Await local.OpenStreamForReadAsync("Sample.xlsx")



'Opens the workbook.
Dim workbook As IWorkbook = Await application.Workbooks.OpenAsync(outFile)


To know more about saving workbook as a stream, refer to Save Workbook as Stream section. 

## Open Workbook in Read-Only mode 

XlsIO allows you to open a spreadsheet in Read-Only mode, even if the spreadsheet is already open in your machine. 



[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

//Opens the workbook as Read only.
IWorkbook workbook = application.Workbooks.OpenReadOnly("Sample.xlsx");



[VB.NET]

Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Opens the workbook as Read only.
Dim workbook As IWorkbook = application.Workbooks.OpenReadOnly("Sample.xlsx")



## Open an Encrypted Workbook

This section illustrates how to open an encrypted document in XlsIO. To open an encrypted file, the password must be provided to decrypt the file. The following code example shows the way of decrypting a file to access its data.

{{ '![](Opening-Excel-Workbook_images/Opening-Excel-Workbook_img1.png)' | markdownify }}
{:.image }


Opening an encrypted workbook

[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

//Decryption:
//Opens the encrypted workbook.

IWorkbook workbook = application.Workbooks.Open("Sample.xlsx", ExcelParseOptions.Default, true, "password");



[VB.NET]



Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Decryption:
'Opens the encrypted workbook.
Dim workbook As IWorkbook = application.Workbooks.Open("Sample.xlsx", ExcelParseOptions.Default, True,"password")

Opening Opening an encrypted workbook in WinRT

[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

//Instantiates the File Picker.
FileOpenPicker openPicker = new FileOpenPicker();

openPicker.SuggestedStartLocation = PickerLocationId.Desktop;

openPicker.FileTypeFilter.Add(".xlsx");

StorageFile openFile = await openPicker.PickSingleFileAsync();

//Decryption:
//Opens the encrypted workbook.
IWorkbook workbook = await application.Workbooks.OpenAsync(openFile, ExcelParseOptions.Default, true, "password");



[VB.NET]



Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Instantiates the File Save Picker.
Dim openPicker As New FileOpenPicker()
openPicker.SuggestedStartLocation = PickerLocationId.Desktop
openPicker.FileTypeFilter.Add(".xlsx")
Dim openFile As StorageFile = Await openPicker.PickSingleFileAsync()

'Decryption:
'Opens the encrypted workbook.
Dim workbook As IWorkbook = Await application.Workbooks.OpenAsync(openFile, ExcelParseOptions.Default, true, "password")

Opening a Workbook in Windows Phone 8

[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

//Opens the file.
StorageFolder local = Windows.Storage.ApplicationData.Current.LocalFolder;
StorageFile openFile = await local.GetFileAsync("Sample.xlsx");

//Decryption:
//Opens the encrypted workbook.

IWorkbook workbook = await application.Workbooks.OpenAsync(openFile, ExcelParseOptions.Default, true, "password");



[VB.NET]



Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Opens the file.
Dim local As StorageFolder = Windows.Storage. ApplicationData.Current.LocalFolder
Dim openFile As StorageFile = Await local.GetFileAsync("Sample.xlsx")



'Opens the Workbook.

Dim workbook As IWorkbook = Await application.Workbooks.OpenAsync(openFile, ExcelParseOptions.Default, true, "password")

To know about saving an encrypted workbook, refer to Save an Encrypted Workbook section.


## Open a CSV File

Opening a Comma Separated Value (CSV) file

XlsIO allows you to open a CSV file. The following code example shows how to achieve this.

[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

//Opens the workbook.
IWorkbook workbook = application.Workbooks.Open("Sample.csv", ",");



[VB.NET]



Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Opens the workbook as a file.
Dim workbook As IWorkbook = application.Workbooks.Open("Sample.csv", ",")

To know about saving workbook as CSV file, refer to Save Workbook as CSV section.

## Open an XML Workbook

Opening an XML Workbook

[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

//Opens the workbook.
IWorkbook workbook = application.Workbooks.Open("Sample.xml", ExcelOpenType.Automatic);



[VB.NET]



Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Opens the workbook as file.
Dim workbook As IWorkbook = application.Workbooks.Open("Sample.xml", ExcelOpenType.Automatic)

Opening an XML Workbook in WinRT

[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

//Instantiates the File Picker.
FileOpenPicker openPicker = new FileOpenPicker();

openPicker.SuggestedStartLocation = PickerLocationId.Desktop;

openPicker.FileTypeFilter.Add(".xml");

StorageFile openFile = await openPicker.PickSingleFileAsync();

//Opens the workbook.
IWorkbook workbook = await application.Workbooks.OpenAsync(openFile);



[VB.NET]



Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Instantiates the File Save Picker.
Dim openPicker As New FileOpenPicker()
openPicker.SuggestedStartLocation = PickerLocationId.Desktop
openPicker.FileTypeFilter.Add(".xml")
Dim openFile As StorageFile = Await openPicker.PickSingleFileAsync()

'Opens the Workbook.
Dim workbook As IWorkbook = Await application.Workbooks.OpenAsync(openFile)



Opening an XML Workbook in Windows Phone 8



[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

//Opens the xml file.
StorageFolder local = Windows.Storage.ApplicationData.Current.LocalFolder;

StorageFile openFile = await local.GetFileAsync("Sample.xm1");



//Opens the workbook.

IWorkbook workbook = await application.Workbooks.OpenAsync(openFile);



[VB.NET]

Dim excelEngine As ExcelEngine = New ExcelEngine()

Dim application As IApplication = excelEngine.Excel


'Opens the file.
Dim local As StorageFolder = Windows.Storage. ApplicationData.Current.LocalFolder
Dim openFile As StorageFile = Await local.GetFileAsync("Sample.xml")



'Opens the Workbook.

Dim workbook As IWorkbook = Await application.Workbooks.OpenAsync(openFile)

To know more about saving workbook as XML, refer to Save Workbook as XML section.

