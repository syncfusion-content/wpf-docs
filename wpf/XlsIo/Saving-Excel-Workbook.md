---
layout: post
title: Saving-Excel-Workbook
description: saving excel workbook
platform: wpf
control: XlsIO	
documentation: ug
---

# Saving Excel Workbook

Essential XlsIO is a Non-UI component that can be used on Windows Forms, WPF, Web Forms, WinRT, and WindowsPhone 8 applications. Changes made in a new or existing worksheet affects only when it is saved to a disk or a stream. XlsIO supports saving files to different formats in stream and disk by using the SaveAs method of IWorkbook. The workbook can be saved to storage file, stream, disk, or response. The only code that is specific for the usage of XlsIO in a Windows Forms application and WPF application, is the saving of the spreadsheet to disk; and for Web Forms applications, it is the streaming of the spreadsheet to the client browser. For winRT and Windows Phone 8 applications, storage file or stream can be used.

## Save Workbook as File  

The following code



 example shows how to save a workbook to disk, as a file in Windows Forms, WPF, Web applications. To know more about how to open a workbook as a file, refer to Open Workbook as File section.

[C#] 



//Sets workbook version.
workbook.Version = ExcelVersion.Excel2013;

//Saves the workbook to disk.
workbook.SaveAs("Sample.xlsx");

//Streams the workbook to the client browser and opens the saved file in the browser.
workbook.SaveAs("Sample.xlsx", Response, ExcelDownloadType.Open);

//Streams the workbook to the client browser and prompts for Save dialog box.
workbook.SaveAs("Sample.xlsx", ExcelSaveType.SaveAsXLS, Response, ExcelDownloadType.PromptDialog);



[VB.NET]



'Sets workbook version.
workbook.Version = ExcelVersion.Excel2013

'Saves the workbook to disk.
workbook.SaveAs("Sample.xlsx")

'Streams the workbook to the client browser and opens the saved file in the browser
workbook.SaveAs("Sample.xlsx", Response, ExcelDownloadType.Open)

'Streams the workbook to the client browser.
workbook.SaveAs("Sample.xlsx", ExcelSaveType.SaveAsXLS, Response, ExcelDownloadType.PromptDialog)

Saving Workbook in WinRT

The following code example shows how to save a workbook as a file in WinRT application. To know about how to open a workbook in WinRT application, refer to Open Workbook as File section.

 [C#] 



//Sets workbook version.
workbook.Version = ExcelVersion.Excel2013;

//Initializes FileSavePicker.

FileSavePicker savePicker = new FileSavePicker();
savePicker.SuggestedStartLocation = PickerLocationId.Desktop;
savePicker.SuggestedFileName = "CreateSpreadsheet";
savePicker.FileTypeChoices.Add("Excel Files", new List<string>() { ".xlsx" });

//Creates a storage file from FileSavePicker.
StorageFile storageFile = await savePicker.PickSaveFileAsync();

//Saves changes to the specified storage file.
await workbook.SaveAsAsync(storageFile);



[VB.NET]



'Sets workbook version.

workbook.Version = ExcelVersion.Excel2013

'Initializes FileSavePicker.

Dim savePicker As New FileSavePicker ()

savePicker.SuggestedStartLocation = PickerLocationId.Desktop

savePicker.SuggestedFileName = "CreateSpreadsheet"

savePicker.FileTypeChoices.Add("Excel Files", New List(Of String)() From {".xlsx"})

'Creates a storage file from FileSavePicker.

Dim storageFile As StorageFile = Await savePicker.PickSaveFileAsync()

'Saves changes to the specified storage file.

Await workbook.SaveAsAsync(storageFile)

Saving Workbook in Windows Phone 8

The following code example shows how to save a workbook as a file in Windows Phone 8 application. To know more about how to open a workbook in Windows Phone 8 application, refer to Open Workbook as File section.

 [C#] 



//Sets workbook version.
workbook.Version = ExcelVersion.Excel2013;

//Gets a local folder.
StorageFolder local = Windows.Storage.ApplicationData.Current.LocalFolder;

//Creates a storage file from FileSavePicker.
StorageFile storageFile = await local.CreateFileAsync("CreateSpreadsheet.xlsx", CreationCollisionOption.ReplaceExisting);

//Saves changes to the specified storage file.
await workbook.SaveAsAsync(storageFile);



[VB.NET]



'Sets workbook version.

workbook.Version = ExcelVersion.Excel2013

'Gets a local folder.

Dim local As StorageFolder = Windows.Storage.ApplicationData.Current.LocalFolder

'Creates a storage file from FileSavePicker.

Dim storageFile As StorageFile = Await local.CreateFileAsync("CreateSpreadsheet.xlsx", CreationCollisionOption.ReplaceExisting)

'Saves changes to the specified storage file.

Await workbook.SaveAsAsync(storageFile)

For more information on overloads of the Workbook's Save method, refer to Class Reference in the top right of the online [documentation](http://help.syncfusion.com/windows%20forms/xlsio).

## Save Workbook as a Stream 

The following code example shows how to save a workbook as a stream in Windows Forms, WPF, Web applications. To know about how to open a workbook as a stream, refer to Open Workbook as Stream section.

[C#]



//Sets workbook version.
workbook.Version = ExcelVersion.Excel2013;

//Saves the workbook to stream.
workbook.SaveAs(stream, ExcelSaveType.SaveAsTemplate);



[VB.NET]



'Sets workbook version.
workbook.Version = ExcelVersion.Excel2013

'Saves the workbook to a stream.
workbook.SaveAs(stream, ExcelSaveType.SaveAsTemplate)

## Save an Encrypted Workbook

This section illustrates how to save an encrypted document in XlsIO.

Encryption

Encryption is a method for protecting a workbook with a password that converts it into the form that cannot be understood and restricts anyone anonymous from accessing the data in a document.

A password for encrypting a workbook can be set in MS Excel through File > Info > Protect Workbook option.

{ ![](Saving-Excel-Workbook_images/Saving-Excel-Workbook_img1.png) | markdownify }
{:.image }


There are two different passwords to encrypt a document.

1. Password To Open-This password encryption helps protect data from unauthorized access.



{ ![](Saving-Excel-Workbook_images/Saving-Excel-Workbook_img2.png) | markdownify }
{:.image }


2. Password to Modify-This password does not encrypt and is only meant to give specific users permission to edit workbook data and save changes to the file.

{ ![](Saving-Excel-Workbook_images/Saving-Excel-Workbook_img3.png) | markdownify }
{:.image }


> _Note: Password protection of a workbook file is different from the workbook structure and window protection that you can set in the Protect Workbook dialog box._

1. Read-Only Recommended-This option prompts read-only recommendation when you open the file to remind that the data is important and should not be changed. This can be set with or without a password to open the file.

XlsIO allows you to set encryption with all the above options through the IWorkbook interface. You can set the password for encryption through the PasswordToOpen property. The following code example illustrates how to encrypt an Excel workbook with password to open, modify, and set the read-only option.

[C#]



// Encryption:

// Encrypts the workbook with password.

workbook.PasswordToOpen = "password";



// Sets the password to modify the workbook.

workbook.SetWriteProtectionPassword("modify_password");



// Sets the workbook as read-only.

workbook.ReadOnlyRecommended = true;



[VB.NET]



' Encryption:

' Encrypts the workbook with password.

workbook.PasswordToOpen = "password"



' Sets the password to modify the workbook.

workbook.SetWriteProtectionPassword("modify_password")



' Sets the workbook as read-only.

workbook.ReadOnlyRecommended= true



Now, the encrypted workbook can be saved. Refer to Saving Excel Workbook section for more details. To know more on how to open an encrypted document, refer to Open Encrypted Workbook section.



> _Note: Essential XlsIO supports default encryption of the type "Office97-2000 compatible", and does not support weak and strong encryption types._



Encryption and Decryption for Excel 97to2003

Parse and serialization support of encrypted files are available in MS Excel 97 onwards. The type of encryption used in Excel 2010/2013 is Agile encryption and MS Excel 2007 with SP2 can open MS Excel 2010 encrypted files as well.

## Save Workbook as CSV 

The following is the code example to save a document as Comma Separated Value (CSV) to disk. To know more about how to open a CSV file, refer to Open a CSV File section.

[C#] 



//Saves the CSV file to disk.
workbook.SaveAs("Sample.csv", ",");

//Streams the CSV file to the client browser and opens the saved file in the browser.
workbook.SaveAs("Sample.csv", ",", response, ExcelDownloadType.Open, ExcelHttpContentType.CSV);

//Streams the CSV file to the client browser and prompts Save dialog box.
workbook.SaveAs("Sample.csv", ",", response, ExcelDownloadType.PromptDialog, ExcelHttpContentType.CSV);



[VB.NET]



'Saves the CSV file to disk.
workbook.SaveAs("Sample.csv", ",")

'Streams the CSV file to the client browser and opens the saved file in browser.
workbook.SaveAs("Sample.csv", ",", response, ExcelDownloadType.Open, ExcelHttpContentType.CSV)

'Streams the CSV file to the client browser and prompts Save dialog box.
workbook.SaveAs("Sample.csv", ",", response, ExcelDownloadType.PromptDialog, ExcelHttpContentType.CSV)

## Save Workbook as HTML 

The following is the code example to save the document as HTML.

[C#]



//Saves the workbook to a stream.
workbook.SaveAsHTML(stream);

//Saves the workbook to a stream with HTML options.
workbook.SaveAsHTML(stream, HtmlSaveOptions.Default);

//Saves the workbook as HTML file with options.
workbook.SaveAsHTML("Sample.html", HtmlSaveOptions.Default);



[VB.NET]



'Saves the workbook to a stream.
workbook.SaveAsHTML(stream)

'Saves the workbook to a stream with HTML options.
workbook.SaveAsHTML(stream, HtmlSaveOptions.Default)

'Saves the workbook as a HTML file with options.
workbook.SaveAsHTML("Sample.html", HtmlSaveOptions.Default)

## Save Workbook as XML

The following code example illustrates how to save the document as XML. To know more about how to open a HTML file, refer to Open an XML Workbook section.

[C#] 



//Saves the workbook to a stream with save options.
workbook.SaveAsXML(stream, ExcelXmlSaveType.MSExcel);

//Saves the workbook as XML file with save options.
workbook.SaveAsXML("Sample.xml", ExcelXmlSaveType.MSExcel);

//Saves the workbook to XML writer with save options.
workbook.SaveAsXml(xmlWriter, ExcelXmlSaveType.MSExcel);



[VB.NET]



'Saves the workbook to stream with save options.
workbook.SaveAsXML(stream, ExcelXmlSaveType.MSExcel)

'Saves the workbook as XML file with save options.
workbook.SaveAsXML("Sample.xml", ExcelXmlSaveType.MSExcel)

'Saves the workbook to XML writer with save options.
workbook.SaveAsXml(xmlWriter, ExcelXmlSaveType.MSExcel)

## Save Workbook with Reduced size

Essential XlsIO uses the default compression technique to compresses files with .NET compression. A new compression technique has been implemented that considerably reduces the size of the compressed XLSX files.

Use Case Scenarios

The reduced size of the compressed file results in reduced data transfer between applications.

How to set the Compression level:

The Compression level can be set at the IApplication interface. This sets the level for all the workbooks created by using the same instance of Excel Engine.

[C#]



ExcelEngine excelEngine = new ExcelEngine();

IApplication application = excelEngine.Excel;

application.DefaultVersion = ExcelVersion.Excel2013; 

//Compression.
application.CompressionLevel = Syncfusion.Compression.CompressionLevel.Best;



IWorkbook workbook = application.Workbooks.Open("Sample.xlsx");



//Saves the Workbook.

workbook.SaveAs(fileName);

workbook.Close();



//Disposes the Workbook.
excelEngine.Dispose();



[VB.NET]



Dim excelEngine As New ExcelEngine()

Dim application As IApplication = excelEngine.Excel



application.DefaultVersion = ExcelVersion.Excel2013


'Compression.

application.CompressionLevel = Syncfusion.Compression. CompressionLevel.Best



Dim workbook As IWorkbook = application.Workbooks.OpenR("Sample.xlsx")



'Saves the workbook.

workbook.SaveAs(fileName)

workbook.Close()



'Disposes the workbook.
excelEngine.Dispose()



_Other Compression Options_

<table>
<tr>
<th>
Enum</th><th>
Description</th></tr>
<tr>
<td>
NoCompression</td><td>
File is not compressed.</td></tr>
<tr>
<td>
BestSpeed</td><td>
Fast compression with more size than normal compression.</td></tr>
<tr>
<td>
BelowNormal</td><td>
Compression speed and size are between Normal and BestSpeed.</td></tr>
<tr>
<td>
Normal</td><td>
Both size and speed are Normal.</td></tr>
<tr>
<td>
AboveNormal</td><td>
Takes more time to compress, with reduced file size.</td></tr>
<tr>
<td>
Best</td><td>
Slow compression, file size reduced to the best level.</td></tr>
</table>


