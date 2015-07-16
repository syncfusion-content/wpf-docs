---
layout: post
title: Custom-XML-Support
description: custom xml support
platform: wpf
control: XlsIO	
documentation: ug
---

# Custom XML Support

Add XML

[C#]



string fileName = "output.xlsx";

ExcelEngine excelEngine = new ExcelEngine ();

//Instantiates the excel application object.

IApplication application = excelEngine.Excel;



//Creates a new workbook.

IWorkbook book = application.Workbooks.Create();



//Adds CustomXmlData to Workbook.

ICustomXmlPart ICustomXmlPart = book.CustomXmlparts.Add("SD10003");



//Adds XmlData to CustomXmlPart.

byte[] xmlData = File.ReadAllBytes("../../Data/Test.xml");

customXmlPart.Data = xmlData;



book.SaveAs(fileName);

book.Close();

excelEngine.Dipose();



[VB]

Dim fileName As String = "output.xlsx"

Dim excelEngine As ExcelEngine = New ExcelEngine()

'Instantiates the excel application object.

Dim application As IApplication = excelEngine.Excel



'Creates a new workbook.

Dim book As IWorkbook = application.Workbooks.Create()



'Adds CustomXmlData to Workbook.

Dim customXmlPart As ICustomXmlPart = book.CustomXmlparts.Add("SD10003")



'Adds XmlData to CustomXmlPart.

Dim xmlData() As Byte = File.ReadAllBytes("../../Data/Test.xml")

customXmlPart.Data = xmlData



book.SaveAs(fileName)

book.Close()

excelEngine.Dipose()

Read XML

[C#]



string fileName = "output.xlsx";

ExcelEngine excelEngine = new ExcelEngine ();

//Instantiates the excel application object.



IApplication application = excelEngine.Excel;



//Opens an existing workbook.

IWorkbook book = application.Workbooks.Open(fileName);



//Accesses CustomXmlPart from Workbook.

ICustomXmlPart customXmlPart = book.CustomXmlparts.GetById("SD10003");



//Acesseses XmlData from CustomXmlPart.

byte[] xmlData = customXmlPart.Data;



System.Text.Encoding.Default.GetString(xmlData);



[VB]



Dim fileName As String = "output.xlsx"

Dim excelEngine As ExcelEngine = New ExcelEngine()



'Instantiates the excel application object.

Dim application As IApplication = excelEngine.Excel



'Opens an existing workbook.

Dim book As IWorkbook = application.Workbooks.Open(fileName)



'Accesses CustomXmlPart from Workbook.

Dim customXmlPart As ICustomXmlPart = book.CustomXmlparts.GetById("SD10003")



'Accessess XmlData from CustomXmlPart.

Dim xmlData() As Byte = customXmlPart.Data



System.Text.Encoding.Default.GetString(xmlData)



